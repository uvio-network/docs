# Trigger Resolve

During the early days of the first testnet deployment we found a bug that effectively created a `resolve` by overwriting an existing comment. There have been two takeaways for debugging and fixing this situation.

First, the question was how one post object can overwrite another, especially if those two post objects where of different kinds. In this particular case a post object of kind `claim` overwrote a post object of kind `comment`. The bit that gave away the root cause was basically the `created` field of the broken post object. If the post object was a comment in the first place, then it must have already existed before the resolve got triggered, which was the case in the incident that we are describing here. That means a comment existed, then a resolve got triggered, and somehow that resolve overwrote the already existing comment. Understanding this relationship and turn of events allowed to debug the worker code that is responsible for automatically creating resolves. And as it turned out, searching for resolves to see whether they exist already returned the wrong post object, which was then a bug that could be fixed and verified with unit tests.

Second, once the problem was identified and the bug was fixed, we had to trigger the creation of the correct resolve again. How to do that works as follows. The expiry queue for all proposes contains the propose IDs and their expiries. A worker task is continuously looking for proposes that expired, because once they expired somebody has to create a resolve for them. What we wanted to do in this particular scenario was to pretend that the propose had not yet expired. So all we had to do was to add the propose ID as `member` to the sorted set below, and add the propose expiry converted to nanoseconds as `score`.

```
post/lifecycle/propose/expiry
```

When the worker task for expiring proposes got executed again, it saw our `propose` and that it expired already. So it took the `propose` and created a proper `resolve` for it using the fixed code.
