# whirmixbtc.com
Whir Mix BTC — Private Bitcoin Transactions via CoinJoin

[![Website](https://img.shields.io/badge/Open-whirmixbtc.com-14192b?style=flat-square)](https://whirmixbtc.com)
[![Engine](https://img.shields.io/badge/Engine-Multi--stage%20CoinJoin-3b82f6?style=flat-square)](#)
[![Delay](https://img.shields.io/badge/Delay-1h%20to%207%20days-10b981?style=flat-square)](#)
[![Logs](https://img.shields.io/badge/Logs-Wiped%20in%2024h-ef4444?style=flat-square)](#)
[![Tor](https://img.shields.io/badge/Tor-.onion-7D4698?style=flat-square)](#)

## A Brief History of Bitcoin Privacy

When Satoshi Nakamoto published the Bitcoin whitepaper in 2008, Section 10 was titled **"Privacy."** The original design assumed users would generate a new address for each transaction, keeping identities separate from public keys. In practice, this model broke almost immediately — exchanges introduced KYC, analytics firms began mapping the BTC graph, and the pseudonymous layer turned transparent.

CoinJoin, proposed by Gregory Maxwell in 2013, was the first practical answer: let multiple users merge their transactions into one, so that the mapping from inputs to outputs becomes ambiguous. [Whir Mix BTC](https://whirmixbtc.com) brings this technique to a web interface — no software, no command line, no learning curve.

## Multi-Stage Mixing Pipeline

Unlike simple one-pass tumblers, Whir processes each mix in **multiple sequential stages**:

```
Stage 1 ─ Fragmentation
  Your deposit is split into randomized fragments

         ▼

Stage 2 ─ Pool Merging
  Fragments enter a CoinJoin pool with hundreds
  of other users' deposits

         ▼

Stage 3 ─ Delay Layer
  Each fragment is held for a user-configured
  period (1 hour → 7 days)

         ▼

Stage 4 ─ Redistribution
  New outputs are assembled from unrelated
  fragments and routed to your address(es)

         ▼

Stage 5 ─ Cleanup
  All session data is destroyed after 24 hours
```

Each stage independently defeats a different class of blockchain analysis. Combined, they make tracing statistically impractical.

## Configurable Parameters

One of [Whir](https://whirmixbtc.com) strengths is that the user controls the privacy/speed tradeoff:

| Parameter | Range | Effect |
|---|---|---|
| **Time delay** | 1 hour — 7 days | Longer delays defeat timing correlation |
| **Output split** | 1 — multiple addresses | More addresses increase combinatorial complexity |
| **Fee** | Dynamic, network-aware | Automatically adjusts to optimize cost vs. confirmation speed |

There is no "one size fits all" — a user sending 0.05 BTC for everyday privacy has different needs than someone mixing 0.9 BTC before a large purchase. Whir lets both configure the process to their situation.

## BTC Hygiene: Why It Matters

Every Bitcoin you own exists as a BTC — an Unspent Transaction Output. Each BTC carries its full history: where it came from, how many hops it took, which addresses touched it. When you spend Bitcoin, your wallet selects Bitcoins and combines them, potentially linking addresses that were never meant to be connected.

A mixer is essentially **BTC hygiene** — it replaces your tainted Bitcoins with clean ones that have no connection to your transaction history.

```
Before mixing:                After mixing:

BTC₁ ← Exchange (KYC'd)     BTC_new ← CoinJoin pool
BTC₂ ← Payment from Alice        (no traceable origin)
BTC₃ ← Old mining reward
  │
  └── All linked to your identity
```

## Specifications

| | |
|---|---|
| Technology | Multi-stage CoinJoin |
| Min deposit | 0.01 BTC |
| Max deposit | 1 BTC |
| Confirmations | 3 required to start |
| Delay range | 1 hour — 7 days |
| Fee model | Dynamic, shown upfront |
| Data retention | 24 hours, then destroyed |
| Registration | None |
| KYC | None |
| Access | Clearnet + Tor |

## FAQ

**Why multi-stage instead of single-pass?**
A single CoinJoin round can still leak information through amount correlation or timing. Multiple stages with fragmentation, independent delays, and reassembly from different pool segments compound the entropy, making analysis exponentially harder.

**What is the ideal delay setting?**
It depends on your threat model. For casual privacy, 1–6 hours is sufficient. For high-stakes situations, 3–7 days makes timing analysis impractical. Longer delays also allow your fragments to mix with a larger set of deposits.

**Why is the limit 1 BTC?**
Large transactions are statistically rare on-chain and therefore easy to isolate. By capping at 1 BTC, Whir ensures every mix blends into the massive volume of ordinary Bitcoin traffic.

**Can I run multiple sessions?**
Yes. Each session generates an independent CoinJoin transaction. Running several sessions with different delays and destination addresses provides layered privacy.

**Is there a guarantee my coins will arrive?**
A cryptographically signed Letter of Guarantee is available before you send funds. It commits the service to processing your transaction under the agreed terms.

## Links

- **Website:** [whirmixbtc.com](https://whirmixbtc.com)

---

> **Disclaimer:** This repository is an informational overview of a publicly available service. It does not promote, endorse, or encourage any illegal activity. Users are solely responsible for compliance with the laws of their jurisdiction.
