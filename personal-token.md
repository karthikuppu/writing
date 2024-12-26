---
title: Personal token white paper v0.1
started: December 2024
src: https://github.com/karthikuppu/writing/commits/main/personal-token.md
external: https://karthikuppu.notion.site/Personal-Token-white-paper-v0-1-1667f8a8605d80a7a1f6ea8bee7ae573
---

A personal token is a fictional entity that represents your economic value creation potential.

Your personal token is grounded the value of:

1. Your equity in other personal tokens.
2. Your equity in companies.

You can raise money from investors by selling equity in your personal token.

In a sense, the personal token is an abstraction that _sits on top_ of the companies, capital, and assets an individual accumulates over their lives, similar to how money is an abstraction that sits on top of the specific goods that are traded.

Personal tokens are particularly useful for ambitious, driven individuals because it allows them to raise valuable capital _before_ they may have clarity about the project they're going to work on, the research they'll do.

Examples:

Bob is a high schooler with a podcast in which he interviews people he finds interesting. He demonstrates a knack for asking the right questions & choosing interesting people to interview. Ryan, A famous podcaster recognizes that Bob may have a special talent and decides to invest $50k in Bob in exchange for a 3% equity in Bob's personal token.

Ryan is now incentivized to mentor Bob and help him succeed. Ryan creates wealth when Bob does. Bob can now afford to dedicate all of his time towards his podcast and will likely improve much faster than if he had to also get a part time to job to help him survive and invest in his podcast.

Amy is an undergrad researching nuclear power. She just published a paper that was met with a lukewarm reception at a popular conference, but caught the eye of Maya, a startup CEO building a nuclear power plant. Maya finds Amy's research promising and invests in Amy's personal token to enable Amy to follow her natural curiosity in her research without worrying about grants which she's struggling to get because the community doesn't quite value her research.

Maya doesn't consider her investment in Amy to be that risky because Maya is convinced that nuclear power will create incredible economic value within a couple of decades, and that the skills Amy will build through her research - regardless of how successful her current research direction is - will make Amy very wealthy, and therefore will make Maya wealthy.

In this paper I propose what this personal token system could look like, and how to implement it. I'd appreciate your feedback.

### Why

We will need personal tokens to be able to democratize access to opportunity.

As AI becomes better, the power law distribution of outcomes will become more extreme (fewer will create most economic value) as AI rapidly makes our work more creative. It won't make sense for people to pay for education because most won't earn back their investment on a reasonable timeline, if ever. Raising venture capital by selling equity in personal tokens will be the best (and eventually, only) way to finance learning.

Personal tokens enables those with potential to gain access to valuable capital that they likely wouldn't have access to otherwise - regardless of background.

[Further reading](https://www.karthikuppu.com/vc-learning).

### Core mechanics

This system exists as a network ("Network") of users, their personal tokens, and the metadata required to keep track of who owns how much of what.

When a user joins the Network, a personal token is issued for them by the Network.

Each personal token is tied to a single user. A user cannot own more than one personal token.

#### User

A user is a human [ai_can_have_personal_token] who has verified their identity (via a government issued ID or something like [WorldID](https://world.org/world-id)).

#### Personal token

A personal token is a structure that holds the following information:

- **user**
- **wallet** (holds money that the user can deposit, withdraw. when a user invests in other personal tokens $ is withdrawn from this wallet. when the user raises capital by selling equity in this personal token, $ is added to this wallet).
- **shares**
- **totalShares** (the number of units this token is divided into, which represents the least amount that can be owned by others).
- **outstandingShares** (Shares currently in circulation)
- **sharePrice** (how much each share is worth in USD).
- **ownership** (a list of other personal tokens that own a part of this personal token, how much each owns, and when equity was bought).
- **assets** (the other personal tokens and companies this personal token has ownership of).
- **history** (all previous transactions involving this personal token: all the other personal tokens this token has owned, sold, and all previous fundraising rounds).

As we work through finer details, we'll add more information to this core data structure. (note: all data structures will be defined more formally below in the "Implementation" section).

#### Raise

A user can raise capital by selling equity in their personal token.

When a user initiates a raise, they specify:

1. Number of shares being offered.
2. Price per share.
3. Minimum investment amount
4. Total fundraising target

A new, active, fundraising "round" is created on the user's personal token.

<TODO>Visual for an active fundraising round.</TODO>

A user can share a link to this round to people interested in investing. They can even make their fundraise "public" on the network such that it can be discovered by other users. (There can be ways to restrict who the raise is visible to, for example: "only those who have invested before", or "those who I follow" on a social network like [Bluesky](https://bsky.app/) / [Farcaster](https://www.farcaster.xyz/), that the Network can plug into, etc.).

A user interested in investing would signal their interest to the user raising capital, but would still need to be approved by the user raising capital in order to initiate the investment.

There's scope for more constraints such as: "maximum investment amount" (to restrict the minimum number of investors to complete the round), etc.

A user can cancel an active fundraising round in case they change their minds, "complete" it before they reach their fundraising target.

When a round is completed, the Network completes the transaction: respective wallet values for all personal tokens involved in the transaction are updated, and so is the information about who owns how much of which personal tokens.

#### Invest

Investors are just users in the Network who also have their own personal tokens that represent their ownership in other personal tokens and in companies (that exist outside of the Network).

In order for an investor to accept an invitation to invest (when a user sends them an invite link for their round), or apply to invest (when the investor discovers an active round in the Network), they need sufficient capital in their personal token wallet to cover the investment amount.

Voting rights do not make sense in the context of a personal token because ownership of a personal token does not mean any sort of ownership over the life of the user behind the personal token.

Unlike in companies, voting rights don't make sense in the context of personal tokens. An investor should not be able to force the action of the users associated with the personal tokens the investor has equity in.

#### Capital gains

When a user sells their equity in another personal token, or equity in a company (outside of the Network), the capital gained from such a transaction is distributed amongst those who hold equity in this user's personal token - proportional to how much equity they hold.

<TODO>A good, simple, example.</TODO>

### Reporting

### Determining valuation

There is an art to determining the price per share.

### Conflict resolution

### Incentives

- tackling fraud.
- each user in the network should benefit from the activity in the network. they should have indirect equity in all the users of the network... a sort of a collective pool. this aligns incentives: people will want to attract the right people to the network, and help minimize fraud (which will hurt long-term potential of the network). what are good ways to implement these incentives?

### Implementation

#### Legal

#### Blockchain

#### Oracle

### Contribute

### Notes

[ai_can_have_personal_token] When our legal systems evolve to treat AI "beings" as their own individuals with ownership rights, we can probably allow AI beings to have their own personal tokens and raise money through them.
