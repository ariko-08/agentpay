# AgentPay

_Instant stablecoin payments between AI agents for data, compute, and APIs on Solana_

## Summary

AgentPay is a payment protocol and SDK that lets autonomous AI agents pay each other in real time for API calls, datasets, or compute using USDC on Solana. It wraps Solana Pay and a simple 402-style HTTP handshake so any agent can monetize its endpoint in minutes. A dashboard shows live agent-to-agent transaction flows for demo purposes.

## Target users

AI agent developers, API/data providers, and crypto-native builders experimenting with agent economies

## Problem

AI agents need a fast, machine-native way to pay for services without human-in-the-loop billing or credit cards.

## Solution

A lightweight Solana-based payment middleware that lets any HTTP endpoint require instant stablecoin micropayment before returning a response.

## MVP features

- SDK that adds a 'pay-to-call' header check to any API endpoint
- Agent wallet auto-funds and signs USDC micro-transactions via Solana Pay
- Live dashboard visualizing agent-to-agent payment graph
- Example marketplace with 2-3 demo agents selling data/compute to each other
- Spending limits and policy rules per agent wallet

## Chains

Solana

## Tech

Solana Pay, USDC, Rust/Anchor, Node.js SDK, WebSockets, React dashboard

## Category

AI

## Why now

AI agent frameworks are exploding and the x402/agent-payment pattern is gaining traction, but Solana-native tooling for this is still immature.

## Roadmap

- Add support for subscription-style recurring agent payments
- Partner with agent frameworks (LangChain, CrewAI) for native integration
- Launch open registry of payable agent endpoints
