---
title: "What is Algorand Observer?"
date: 2022-06-25T02:18:38+03:00
---
## TL;DR: Real-time blockchain event streaming.

We are building a set of services around parsing and reacting to specific blockchain events on the Algorand MainNet network.

The public frontend to this will be Algorand.Observer, where users will be able to see this data, as well as aggregates & statistics, in real-time.

## What kind of on-chain events?

We are focusing on the following three types of transactions to begin with:

- DEX swaps
- Liquidations
- ASA/NFT mints

## What kind of DEX swaps will you support?

In short: most of them.

Our backend is much further ahead than our frontend. We have "processors" that parse Tinyman, AlgoFi and PactFi swaps very reliably.

We are currently focusing on the top 30-50 most popular pools on each DEX, so not all pools will be shown in the first incarnation of our frontend.

We will be working on HumbleSwap and AlgoDex processors shortly after our Alpha version is released. HDX support is also on our roadmap.

## What kind of Liquidation events will you support? 

Currently we have a processor for AlgoFi that we used to write up [this report](https://d13.co/algofi-liquidations-stats-data/).

We will be supporting Folks Finance liquidations after the Alpha release, and xBacked liquidations shortly after that.

## What kind of ASA/NFT mints will you support?

In short: all of them.

We have a processor that works reliably with both simple ASA creation transactions and inner-transactions that happen when an ASA or NFT is minted using a smart contract. 

An exmaple of smart-contract minted NFTs are NFDomains - we will likely provide a dedicated view of NFDomain mints.

We are doing this for two reasons: 

- We think it may be a useful way to discover new NFT content and that it has entertainment value. There is something fascinating about watching NFTs seconds after they have been minted.
- We want to provide a fraud notification services for NFT creators that are large enough to worry about such concerns.

As the Algorand NFT space grows, fraudulent NFT mints that infringe on creator copyright and defraud users by selling them infringing NFTs will likely become more prevalent. If there is demand for this, we intend to build a discord integration that provides a bot on customer servers and notifies when an infringing NFT has been minted, so that their community can take action as soon as the infringing NFT has hit the chain.

## What timeframes will you support?

We aim to provide data from block 17,700,000 (Sun, 28 Nov 2021 10:23:12 GMT) until "now".

If there is need for earlier data, we will be able to accomodate.

## How is this going to be profitable?

We hope to prove our competence in building an extremely reliable blockchain event responding service, and subsequently offer our data and services to creators and developers.

Further to the above example of fraudulent NFT detection, we believe we can reliably offer the following:

- DEX token pair price points
  - real-time
  - historical
  - time aggregates (daily/weekly/monthly)
  - platform-specific or chain-wide
- DEX liquidity events
- Arbitrage opportunities
- Liquidation Events
- Liquidation Opportunities

We want to build delivery channels that work for our customers, so any of the following are possible:

- HTTP APIs
- [Server-Sent Events](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events) (our favorite streaming option)
- Websocket APIs
- Webhooks
- Push notification services like [Pushbullet](https://pushbullet.com/)
- Email
- Twitter bots
- Discord bots

Building this system with _very_ high availability is our number one priority. We will be using Algorand Observer data to build both internal tools and consumer products.

## Is this an official Algorand inc or Algorand Foundation project?

No.

## Who is funding this?

The same people who are developing it - the [D13.co//ective](https://d13.co//ective).

We are not currently looking for funding.

We will not be asking for money until we have something of value to offer in return.

## Where can I be updated about your progress?

You can follow us on twitter: [@Algo_Observer](https://twitter.com/algo_observer/) and [@D13_co](https://twitter.com/d13_co/).
