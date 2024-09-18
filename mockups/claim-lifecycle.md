# Claim Lifecycle

{% hint style="info" %}
The following pages contain structural key elements of Uvio's intended design and workflow. Mockups provided explain various ideas about the intended reputation system in varying detail. While incomplete, the following graphics are hopefully sufficient to provide a basis for more conversations and design iterations towards a functional prototype of the platform.
{% endhint %}

#### Proposing a Claim

The first and one of the most fundamental actions on Uvio is to propose a claim. Every proposed claim effectively creates a prediction market for the statement being made. And since proposing a claim is permissionless, creating prediction markets on Uvio is permissionless too.

<figure><img src="../.gitbook/assets/Screenshot 2024-07-15 at 14.09.38.png" alt=""><figcaption></figcaption></figure>

#### Resolving a Claim

Every proposed claim needs to be resolved eventually. The act of expressing opinions about truth statements and the act of resolving truth statements according to events unfolding in the real world, both are reconciled by the users of the platform and their respective reputation.

<figure><img src="../.gitbook/assets/Screenshot 2024-07-15 at 14.14.51.png" alt=""><figcaption></figcaption></figure>

#### Staked Reputation

Staking reputation on a claim may be accompanied with a comment. Given any claim, the respective agreeing and disagreeing stakes may be viewed by category in order to understand how either side of the market reasons about the statement being made.

<figure><img src="../.gitbook/assets/Screenshot 2024-07-14 at 21.48.29.png" alt=""><figcaption></figcaption></figure>

#### Claim Lifecycle

Maybe most important to understand is the circular nature of escalation. Everything is just a claim with two options. Where expressing opinions can be done proportional to a user's balance, verifying the truth can only be done once per user as in "one user one vote". Claims can be disputed with ever higher stakes. The action space shown below is linear where claims can be proposed, resolved, proposed, resolved etc. Just note that proposing a claim on a resolving claim is called a dispute.

<figure><img src="../.gitbook/assets/Screenshot 2024-07-20 at 19.10.27.png" alt=""><figcaption></figcaption></figure>
