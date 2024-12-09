---
title: Personal token white paper v0.1
started: December 2024
src: https://github.com/karthikuppu/writing/commits/main/personal-token.md
heroImageSrc: /images/individual/individual.png
---

_This essay is an early exploration of a financial instrument (personal token) that lets people raise money in exchange for equity in their future outcomes. This is a continuation of my previous [essay](/vc-learning) ("VC will be the best way to finance learning") in which I explore why we will need personal tokens to democratize access to opportunity as AI becomes more powerful._

### A personal token

A personal token is a fictional entity that represents an individual's equity in two kinds of assets:

1. Equity in other personal tokens.
2. Equity in companies.

![personal token](/images/personal-token/personal-token.png)

A user (Alice) can raise money from others in the network by selling equity in her personal token. This represents Alice giving up equity in her future outcomes in exchange for valuable capital today that would help Alice generate outcomes.

Over time, Alice will create value for herself and her investors by earning equity in companies by creating, working at, or investing in them, and also by earning equity in personal tokens by investing in them.

When Alice sells her equity in a personal token, or sells her equity in a company, a portion of the capital she gains goes to those who hold equity in Alice's personal token - proportional to how much equity they hold.

With such a personal token system, ambitious individuals can raise money by selling equity in their future outcomes. They can raise money much earlier in their learning journey, perhaps even years before they actually start their own company or work at one.

Examples:

Bob is a high schooler with a podcast in which he interviews people he finds interesting. He demonstrates a knack for asking the right questions & choosing interesting people to interview. Ryan, A famous podcaster recognizes that Bob may have a special talent and decides to invest $50k in Bob in exchange for a 3% equity in Bob's personal token.

Ryan is now incentivized to mentor Bob and help him succeed. Ryan creates wealth when Bob does. Bob can now afford to dedicate all of his time towards his podcast and will likely improve much faster than if he had to also get a part time to job to help him survive and invest in his podcast.

Amy is an undergrad researching nuclear power. She just published a paper that was met with a lukewarm reception at a popular conference, but caught the eye of Maya, a startup CEO building a nuclear power plant. Maya finds Amy's research promising and invests in Amy's personal token to enable Amy to follow her natural curiosity in her research without worrying about grants which she's struggling to get because the community doesn't quite value her research.

Maya doesn't consider her investment in Amy to be that risky because Maya is convinced that nuclear power will create incredible economic value within a couple of decades, and that the skills Amy will build through her research - regardless of how successful her current research direction is - will make Amy very wealthy, and therefore will make Maya wealthy.

### Why

We will need personal tokens to be able to democratize access to opportunity.

As AI becomes better, the power law distribution of outcomes will become more extreme (fewer will create most economic value) as AI rapidly makes our work more creative. It won't make sense for people to pay for education because most won't earn back their investment on a reasonable timeline, if ever. Raising venture capital by selling equity in personal tokens will be the best (and eventually, only) way to finance learning.

Personal tokens enables those with potential to gain access to valuable capital that they likely wouldn't have access to otherwise - regardless of background.

_(Further reading: my [previous essay](/vc-learning) that dives into this in greater depth)._

### A new primitive

How is a personal token different than just a company that you create to represent your investments in other companies - sort of like a VC firm? Why is a new sort financial instrument necessary?

To be clear, the starting point for a personal token from a legal perspective may very well look like a "company" with a few modifications [1]. But, there are crucial differences between a personal token and a company that it makes sense to treat them differently.

A personal token is inseparable from the individual. Unlike a company who's owners can change entirely, an individual can't give away their personal token such that they no longer have it. In another sense, a personal token is like an abstraction "above" all the companies that a person will have equity in.

A personal token also represents a different sort of behavior: investing in people _before_ they may have something specific that they are going to create. Companies are generally formed when there is a specific product or service that the founders want to create.

Even if the underlying implementation is a "company", from a use-case, behavioral, social context, a personal token is a new financial primitive.

### Priorities

Before we think about how to implement this personal token system, we need to know what our priorities are so that we can make the right trade-offs.

**Trust** is the foundation of this system. Without trust, capital won't flow into the network of personal tokens because people won't be sure of the returns even if they invested in the right tokens. People don't play when they think the game might be rigged.

Investors should have confidence that they will receive payouts. They should have confidence in the system's ability to prevent fraud. They should have some recourse in the case of fraud (i.e. an individual raises money and runs with it, or doesn't accurately disclose their earnings from equity sales).

In addition to trust, creating a personal token should be fast, simple, and affordable. Eventually, everyone will just have one by default similar to IDs, etc. Also, capital distribution - when an individual sells equity in a company or a personal token, what they gain is distributed amongst holders of their personal token proportional to how much equity they have - should become instantaneous. But, nothing matters without sufficient trust.

### How

#### A network

Personal tokens exist in a network of people. Each person in this network would have a personal token associated with them. Each person can only have one personal token.

This network and its transactions will be implemented with a blockchain.

Using a blockchain as the source of truth for the network helps create confidence in the network as it can be verified by anyone. Even though we'll need some centralized authority to help minimize fraud (as I'll discuss below), implementing the network with a blockchain makes the actions of the centralized authority more transparent - open to critique and pressure from the users in the network. A blockchain also allows for a more efficient implementation of rules through [smart contracts](https://en.wikipedia.org/wiki/Smart_contract).

#### Distribution when personal token equity is sold (on chain).

Implementing capital distribution within the network (when equity in another personal token is sold) is straightforward: through a smart contract. When Alice successfully sells her equity in a personal token, some of it is automatically siphoned off by the smart contract to the wallets of those who hold equity in Alice's personal token - proportional to how much equity they hold.

#### Distribution when company equity is sold (off chain).

Implementing capital distribution when Alice sells equity in a company is more challenging. When equity in a company is cashed out, Alice technically "owes" those who hold equity in her personal token their share of the capital Alice gained from selling equity in a company.

Alice will need to report this somehow, and be able to transfer value within the network to those who hold equity in Alice's personal token.

Equity in the real world must be reflected on chain, and must be kept in sync.

<TODO>Propose good ways to record and sync on chain record of equity in companies with reality.</TODO>

#### Preventing fraud.

Let's say Dan is a bad actor: he wants to raise money on this network without any intention to actually create value in the world (or hide it) and just run away with the money he raises from investors. Dan would then be incentivized to hide his successes in the real world from the network so that he doesn't have to pay investors their share of the value he's created in the world.

The success of this personal token network depends on how well it can dis-incentivize bad actors like Dan.

Some ideas on how this can be done:

1. Once it's clear someone is a fraud, block them from participating in the network in the future: meaning they cannot invest in others' personal tokens. Over time this will be the most powerful lever to minimize fraud because the economic potential of investing in people will be enormous.
2. Track their successes in the real world and identify discrepancies (e.g. they may say they joined a startup on LinkedIn, but haven't reported that they've gained equity in a company to their investors).
3. Ensure all investments comply with regulations around securities so that in the case of fraud users have access to the courts to sue fraudsters. As the network becomes more powerful, it will rely less on the public courts, and more on incentives that will keep people in line (i.e. people will not be want to lose out on the opportunity to profit from personal tokens).

#### Identity.

In order to implement these ideas, each user must be associated with their real-world identity (e.g. government issued ID / something like [WorldID](https://world.org/world-id)). Users can't just create new personal tokens and disassociate with their past.

#### Privacy.

Privacy can be supported via [zero knowledge proofs](https://vitalik.eth.limo/general/2021/01/26/snarks.html) so that a person can keep information about their investments private.

#### Sufficiently decentralized governance.

I currently can't see a way in which the network can be completely decentralized because if it were, how would fraud be identified, and how would bad actors be kicked out of the network? Actions like these can't just be put to a vote. There needs to be some central authority with the power to make these calls in order to protect the integrity of the network.

Complete decentralization creates great opportunity for fraud. ([NFT rug pulls](https://www.perplexity.ai/search/what-is-an-nft-rug-pull-and-wh-l2MUzbggRFGpyJ83Mf1A7w)).

Governance of the centralized authority will need to be well designed. Over time, the central authority should lose power (proportional to how good AI becomes). Its decision making should be transparent. And there should probably be a way for the network to vote on certain decisions.

#### Legal.

From a legal standpoint, a personal token is undeniably a [security](https://law.duke.edu/lib/research-guides/securities). Trying to present it as something else in order to skirt laws is a shortsighted, unambitious approach. We'll need to constantly strive to be compliant with regulations (and help define them in the many emerging legal gray areas), to be able to build a system that will last.

We'll need to be creative because existing legal structures ("C corp", "LLC", etc.) weren't designed for personal tokens. We'll also need to design the system such that there isn't unnecessary friction to creating your personal token and raising money.

I don't have a legal background, so I have a lot of work to get up to speed. Most of my understanding so far has come from conversations with LLMs. I've yet to ground my intuitions in reality by studying the source of truth: the laws and precedents themselves. The following idea proposed by Claude (3.5 Sonnet) seems like an interesting angle to study in greater depth:

```
Let me help explain how we could structure this platform while navigating the regulatory requirements. I'll break this down into steps and explain both what needs to happen and why.

First, let's understand what's happening from a regulatory perspective: When someone creates a personal equity token and sells portions of it to investors in exchange for money and with the expectation of future returns, they're creating a security. This is true regardless of whether it's on a blockchain or not - the underlying economic reality is what matters.

Now, let's look at how we could structure this:

Instead of individual LLCs, we could have your platform company create a master LLC with what's called a "series LLC" structure. Think of this like an apartment building where each apartment is legally separate from the others. Each personal token would be a separate series under this master LLC.

Here's how it would work step by step:

When a user creates their personal token:

1. They provide identity verification (crucial for regulatory compliance)
2. They sign a standardized contract that:
    - Assigns their rights to future earnings to their specific series under the master LLC
    - Defines what earnings are included (equity sales, etc.)
    - Sets up their obligations to report earnings
    - Establishes how proceeds will be distributed

When they want to fundraise:

1. Your platform (the master LLC) files a Form D for their specific series
2. The fundraising link is technically an invitation to invest in that series
3. When investors "apply," they go through accreditation verification
4. The smart contract that records ownership percentages is connected to the legal rights established in the series LLC

The advantage of this structure is that:

1. Individual users don't need their own LLCs
2. One master Form D filing can cover multiple series
3. The blockchain records serve as a transparent ledger of ownership
4. The legal structure provides enforceability

However, this approach means your platform company takes on significant responsibilities:

1. You'll need to register as an investment adviser or broker-dealer
2. You'll need robust systems for tracking and distributing proceeds
3. You'll need strong compliance procedures
4. You'll need to manage tax reporting for all the series

The key to making this work is ensuring that the legal agreements and blockchain implementation work together seamlessly. For example, when the smart contract records that someone owns 10% of a personal token, that needs to correspond to actual legal rights to 10% of the designated earnings under the series LLC structure.

This is similar to how some real estate investment platforms operate - they use a series LLC structure to separate different properties while maintaining a unified platform for investors.
```

### Next steps

1. Come up with a spec of this system. The magic is in the details, and this essay only serves as a primer to give a high level understanding of this system. A spec will represent ideal state of this system that we aspire to achieve, without regarding the legal / technical realities of the world. This spec will act as a North Star to help us prioritize and focus.
2. Thorough analysis of the messy realities of the world to understand diff(north_star, reality) and have a plan to bridge the gap.
3. Find motivated, determined, highly competent people to work with and bring this to life - across domains: legal, technical, design, etc.

To be clear, parts (or even all) of my thinking above will likely change as I continue to learn.

I'm looking to bring together a small group of ambitious, talented, hard working individuals to bring this to life. If you're interested in exploring this with me, [reach out](https://x.com/saltykarthik). LFG.

### Notes

<Footnotes>
[1] For example, since a personal token isn't the same as a company, certain features of companies won't translate to personal tokens.
- It probably doesn't make sense to give investors "voting rights" or to have some kind of "board of directors" that oversees the activities that the individual does. This curbs freedom that is bad for both the individual and the investors.
- Might make sense to "cap" returns. E.g. when an investor makes 1000x their investment from a personal token, their equity in it is transferred back to its owner. 
- Might need to limit how much of a personal token an individual can sell. e.g. if 99% of my future outcomes go to my investors, my life feels screwed.
</Footnotes>
