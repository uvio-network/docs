# Claims

<details>

<summary>What is a Claim?</summary>

<mark style="color:green;">**`oneliner`**</mark>

A claim is a statement that can either be true or false.

<mark style="color:blue;">**`extended`**</mark>

The main posts that users create on Uvio are called _claims_. Posting or creating claims is called _proposing_ on Uvio. When a user proposes a claim, then that user stakes a chosen amount of their own reputation with that claim. Reputation here is simply some ERC20 like token. The user's staked reputation is punishable in a way that it can be taken away from the user upon being _wrong_ or upon being _dishonest_. In the context of blockchain networks we refer to this particular form of punishment as slashing. If the proposed claim is eventually resolved to be false, then the user loses their staked reputation. If the proposed claim is eventually resolved to be true, then the users who have been right about the claim gain reputation proportional to the total amount of reputation lost on the other side of the market.

</details>

<details>

<summary>How to propose a Claim?</summary>

<mark style="color:green;">**`oneliner`**</mark>

A claim may be proposed by staking reputation on a truth statement.

<mark style="color:blue;">**`extended`**</mark>

Just like you create a Cast on [Farcaster](https://www.farcaster.xyz), you create a Claim on Uvio. Creating a claim on Uvio is referred to as proposing a claim. Every claim must fulfil three conditions in order to be valid.

1. Every claim must be a **truth statement** that can be verified eventually. That means it must be possible for Uvio users to reasonably answer any given statement with either **yes** or **no** at some point in the future. So the true outcome of any given statement must be verifiable by independent sources that allow the community to eventually reach a simple majority of decentralized consensus.
2. Every claim must have an **expiration time** when proposing a claim. This deadline provides the point in time at which the community can start resolving that claim. Making time sensitive statements guarantees Uvio to be useful at all. If claims were allowed to not expire at a predefined point in time, then claims could eventually become true by themselves, and would therefore not provide any useful amount of predictability.
3. Every claim must have some amount of **staked reputation** bound to it. The staked reputation must solely come from the user proposing the claim. It should further never be possible to act on behalf of other users or their reputation. For instance, delegating reputation and thus delegating responsibility to other users should never be allowed in order to prevent certain [principal-agent problems](https://en.wikipedia.org/wiki/Principal%E2%80%93agent\_problem).

There are several implications of the three rules above. One notable implication is that the staked reputation can either be gained or lost upon resolution. Choosing the initial amount of staked reputation when proposing a claim may also express a level of conviction that the user is willing to exercise over time. That level of conviction may become relevant if the proposed claim were to be disputed. On one hand a user's staked reputation creates a minimum threshold that will be required in order to challenge any claim's legitimacy. On the other hand a user's staked reputation is the maximum amount of reputation that may be slashed upon being wrong or being dishonest.&#x20;

</details>

<details>

<summary>How to resolve a Claim?</summary>

<mark style="color:green;">**`oneliner`**</mark>

A proposed claim may be resolved by sampling the truth from the real world.

<mark style="color:blue;">**`extended`**</mark>

Every proposed claim is going through two lifecycle stages when it is being resolved.&#x20;

1. **User opinions** are expressed by staking reputation in agreement or disagreement with the statement of the proposed claim. Anyone having any amount of reputation on the Uvio platform can stake that amount of reputation on any proposed claim in order to **express opinions** about the statements associated with those proposed claims.
2. **True outcomes** are eventually being verified by the community in order to transfer the staked amounts of reputation towards the users that have staked their reputation on the actually true outcome. **Verifying events** independently as they happened in the real world is done by [random truth sampling](claims.md#how-to-resolve-a-claim) on a "one user one vote" basis.

Once all opinions have been expressed and the proposed claim expired, the proposed claim is being resolved by what we call _random truth sampling_. A resolving claim is automatically created in order to verify the true outcome as it actually happened in the real world.&#x20;

The system selects a random set of users who have expressed their opinions in the proposed claim. Only users who have expressed their opinions by staking reputation on the initially proposed claim can be selected to vote. The random selection aims to find an even amount of users, of which 50% are selected from the agreeing side and 50% are selected from the disagreeing side of the market. The randomly selected users are each given **one vote** to decide whether the majority of staked reputation has been right or wrong. That way a single honest vote may ensure a truthful outcome amidst a pool of exclusively selfish users.

If no vote can be captured during market resolution, or if the outcome of cast votes ends up being tied, then all stakes of the selected voters will be slashed in order to punish dishonesty or inactivity. Such punishable resolutions are definitive and binding. Further, all invalid resolutions incurred by punishment cause all other stakers to receive all of their staked tokens back, minus the applicable fees. That very act of guaranteed punishment under certain conditions aims to incentivize users to A) participate and B) participate honestly.

The current implementation of the _random truth sampling_ process can be found in the [apiserver](https://github.com/uvio-network/apiserver/blob/main/pkg/sample/interface.go) Github repository.

</details>

<details>

<summary>How to dispute a Claim?</summary>

<mark style="color:green;">**`oneliner`**</mark>

A resolved claim may be disputed by proving its actually true outcome.

<mark style="color:blue;">**`extended`**</mark>

A claim may be falsely resolved so that its resolved outcome does not match the true outcome of the real world. In that case a resolved claim may be disputed within its challenge window, by providing the actually true outcome as it was generated by the real world. A claim proposed to dispute another claim may be resolved in agreement or disagreement based on its own merits.&#x20;

A _dispute_ is effectively just other _claim_. The originally proposed claim can be disputed a maximum of two times, meaning every proposed claim has 3 chances to be resolved properly according to community consensus. If a claim is disputed, then its very resolution is forced upon all of the claims that came before it. Imagine the claims `P1`, `C2` and `C3`. Here `P1` is the originally proposed claim. `C2` and `C3` here are the first and second dispute respectively. Suppose all three claims resolve in order `false`, `false` and `true`. Here `C3` resolved with `true`, and since `C3` was the final dispute within this very claim tree, its resolution is forced upon every claim in that tree. Effectively all user balances will then be updated according to the implied resolutions `true`, `true` and `true` respectively.

The code of the latest enforced onchain version for updating user balances can be found on Github in the [contracts](https://github.com/uvio-network/contracts/blob/v0.4.0/contracts/Claims.sol#L1027) repository.

</details>

<details>

<summary>How can Claims be used?</summary>

<mark style="color:green;">**`oneliner`**</mark>

Claims can be used to find truth and to make decisions.

<mark style="color:blue;">**`extended`**</mark>

Since Uvio is fundamentally designed to surface competence, the underlying reputation system can be used for various tasks of decision making. Apart from gambling, we can group the relevant use cases here under two main categories.

1. **Truth finding** can be used by the community to figure out what is true now and what might be true in the future. The truth finding aspect of Uvio may help you to understand who you can trust across various problem domains. Contemporary social media dynamics today are as such that anyone can say anything and be rewarded with attention if only they trigger enough people with the most outrageous statements, while there are no means of recourse whatsoever.&#x20;
2. **Decision making** can be used by the community to figure out how to move forward together. The decision making aspect of Uvio may help communities that want to leverage competence in an onchain environment without being constraint by the complicated intricacies of blockchain networks. Voting is an essential part of democracy, and maybe we can make better decisions collectively if we become able to leverage reputation weighted voting for anything that matters to people.

</details>
