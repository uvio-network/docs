# Claims

<details>

<summary>What is a Claim?</summary>

<mark style="color:green;">**`oneliner`**</mark>

A claim is a statement that can either be true or false.

<mark style="color:blue;">**`extended`**</mark>

The main posts that users create on Uvio are called claims. Posting claims is called proposing on Uvio. When a user proposes a claim, then they stake a chosen amount of their own reputation with that claim. That staked amount of reputation is punishable in a way that it can be taken away from the user upon misbehaving. In the context of blockchain networks we refer to this particular form of punishment as slashing. If the proposed claim is eventually resolved to be false, then the user loses their staked amount of reputation. If the proposed claim is eventually resolved to be true, then the user gains reputation proportional to the total of the staked amount in agreement, plus some amount of reward.

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

There are several implications of the three rules above. One notable implication is that the staked reputation can either be gained or lost upon resolution. Choosing the initial amount of staked reputation when proposing a claim may also express a level of conviction that the user is willing to exercise. That level of conviction may become relevant if the proposed claim were to be disputed or nullified. Another important implication here is that claims may be deemed invalid by the community. Anyone may challenge whether a proposed claim is even verifiable or whether its resolved outcome was actually true. On one hand a users staked amount of reputation creates a minimum threshold on a multiple basis that will be required in order to challenge any claims legitimacy. On the other hand a users staked amount of reputation is the maximum amount of reputation that may be slashed upon proven misbehaviour.&#x20;

</details>

<details>

<summary>How to resolve a Claim?</summary>

<mark style="color:green;">**`oneliner`**</mark>

A proposed claim may be resolved by staking reputation and sampling truth.

<mark style="color:blue;">**`extended`**</mark>

Every proposed claim is going through two lifecycle stages when it is being resolved.&#x20;

1. **User opinions** are expressed by staking reputation in agreement or disagreement with the statement of the proposed claim. Anyone having any amount of reputation on the Uvio platform can stake that amount of reputation on any proposed claim in order to **express opinions** about the statements associated with those proposed claims.
2. **True outcomes** are eventually being verified by the community in order to transfer the staked amounts of reputation towards the users that have staked their reputation on the actually true outcome. **Verifying events** independently as they happened in the real world is done by random truth sampling on a "one user one vote" basis.

Once all opinions have been expressed and the proposed claim expired, the proposed claim is being resolved by what we call random truth sampling. A resolving claim is automatically proposed in order to verify the true outcome as it can be verified in the real world.&#x20;

The system selects a random set of users who have expressed their opinions in the proposed claim. Only users who have expressed their opinions by staking reputation are allowed to verify the truth for the initially proposed claim. The random selection aims to find an even amount of users, of which 50% are selected from the agreeing users and 50% are selected from the disagreeing users. The randomly selected users are each given **one vote** to decide whether the majority of staked reputation has been right or wrong. A single honest vote may ensure a truthful outcome amidst a pool of exclusively selfish users.

If no vote can be captured during the random truth sampling, or if the outcome of verifying the truth ends up being tied, then a disputing claim is automatically created in order to challenge the lazy or dishonest actors. Disputing claims do then allow any user on the Uvio platform to stake reputation on the dispute, and a random set of users is subsequently selected from this new group of users, in order to resolve the dispute itself. That very act of challenging user behaviour aims to incentivize users to A) participate and B) participate honestly. If challenged users were eventually found to be lazy or dishonest, then significant amounts of their reputation should be slashed.

If a claim can be resolved by the random truth sampling process, then all honest voters get partially rewarded upon resolution. That particular incentive aims to convince users to verify real world events truthfully, even against their own wrong opinion.

</details>

<details>

<summary>How to dispute a Claim?</summary>

<mark style="color:green;">**`oneliner`**</mark>

A resolved claim may be disputed by proving its actually true outcome.

<mark style="color:blue;">**`extended`**</mark>

A claim may be falsely resolved so that its resolved outcome does not match the true outcome of the real world. In that case a resolved claim may be disputed by providing the actually true outcome as it was generated by the real world. A claim proposed to dispute another claim may be resolved in agreement or disagreement based on its own merits.&#x20;

If the disputing claim is accepted, then all of the reputation of the disputed claim is transferred proportionally to the disputing users. The incentive here for all users is to only act honestly across Uvio, since participating in disputable claims may be punished by losing reputation even after claims have been resolved in agreement.&#x20;

If the disputing claim is rejected, then the claim created to dispute another is simply rendered null and void without having any effect on the disputed claim. In either case the Uvio platform may have received a challenge fee.

</details>

<details>

<summary>How to nullify a Claim?</summary>

<mark style="color:green;">**`oneliner`**</mark>

Any claim may be nullified by proving how it was never verifiable in the first place.

<mark style="color:blue;">**`extended`**</mark>

A claim may be falsely proposed so that its outcome may never be be able to be resolved. In that case a proposed claim may be nullified by providing arguments for how the nullified claim was never verifiable in the first place. A claim proposed to nullify another claim may be resolved in agreement or disagreement based on its own merits.

If the nullifying claim is accepted, then all of the reputation of the nullified claim is transferred proportionally to the nullifying users. The incentive here for all users is to only act honestly across Uvio, since participating in nullifiable claims may be punished by losing reputation even after claims have been resolved in agreement.

If the nullifying claim is rejected, then the claim created to nullify another is simply rendered null and void without having any effect on the nullified claim. In either case the Uvio platform may have received a challenge fee.

</details>

<details>

<summary>What is the difference between Disputing and Nullifying a Claim?</summary>

<mark style="color:green;">**`oneliner`**</mark>

Disputing and Nullifying applies to different lifecycle stages a claim may go through.

<mark style="color:blue;">**`extended`**</mark>

Uvio needs to make sure that claims are valid to begin with. Only valid claims that can be truthfully verified eventually are actually useful to work with. A claim may be disputed after it was resolved. A claim may be nullified at any point across all possible lifecycle stages. Where disputing a claim aims to improve the resolved outcome of said claim, nullifying a claim aims to remove said claim entirely from the system for validity reasons.

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
