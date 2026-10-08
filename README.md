# AgentPay
![AgentPay logo](assets/logo.png)

Instant stablecoin payments between AI agents for data, compute, and APIs on Solana.

## Overview

AgentPay is a payment protocol and SDK that lets autonomous AI agents pay each other in real time using USDC on Solana. It wraps Solana Pay in a simple 402-style HTTP handshake so any agent can monetize its endpoint in minutes. A live dashboard visualizes agent-to-agent transaction flows for demo purposes.

## Problem

AI agents need a fast, machine-native way to pay for services without a human in the loop approving credit cards or invoices. As agent frameworks grow, this manual billing bottleneck prevents agents from transacting autonomously at machine speed.

## Solution

AgentPay is a lightweight Solana-based payment middleware that lets any HTTP endpoint require an instant USDC micropayment before returning a response. Agent wallets auto-fund and sign transactions, within configurable spending limits, so payments happen without human intervention.

## Features (MVP)

- SDK that adds a pay-to-call header check to any API endpoint
- Agent wallet that auto-funds and signs USDC micro-transactions via Solana Pay
- Live dashboard visualizing the agent-to-agent payment graph
- Example marketplace with 2-3 demo agents selling data/compute to each other
- Spending limits and policy rules per agent wallet

## Tech stack

- Solana Pay, USDC
- Rust / Anchor
- Node.js SDK
- WebSockets
- React dashboard

## How it works

```
Agent A (caller)        Paid Endpoint (Agent B)
      |                          |
      |----- HTTP request ------>|
      |<---- 402 Payment Req ----|
      |-- sign USDC payment ---->| (Solana Pay, on-chain)
      |<--- verified response ---|
      |                          |
   [Dashboard streams the payment over WebSockets]
```

1. An agent calls a paid endpoint.
2. The endpoint responds with a 402-style payment requirement.
3. The caller's wallet signs a USDC transaction via Solana Pay, respecting its spending limits and policy rules.
4. The server verifies the payment on-chain, then returns the requested data, API result, or compute output.
5. The dashboard shows the transaction live on the agent-to-agent payment graph.

## Roadmap

- Add support for subscription-style recurring agent payments
- Partner with agent frameworks (LangChain, CrewAI) for native integration
- Launch an open registry of payable agent endpoints

## Pitch

See our one-pager at [docs/pitch.pdf](docs/pitch.pdf) and our spoken pitch script at [docs/pitch-script.md](docs/pitch-script.md).

## Team

- Name - Role - [GitHub](#) / [Twitter](#)
- Name - Role - [GitHub](#) / [Twitter](#)
- Name - Role - [GitHub](#) / [Twitter](#)

Built for the Colosseum hackathon.

---

🎬 Pitch video: [docs/pitch-video.mp4](docs/pitch-video.mp4)


## Prototype

Live prototype: https://ariko-08.github.io/agentpay/

The source is [docs/index.html](docs/index.html) (served with GitHub Pages from the /docs folder). All data is simulated.
