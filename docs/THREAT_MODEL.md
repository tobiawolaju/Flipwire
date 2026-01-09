# Flipwire Threat Model

Flipwire is designed to protect user funds, wallet privacy, and workflow integrity. Key threats and mitigations are:

| Threat | Mitigation |
|--------|------------|
| Custodial risk / stolen keys | All operations are non-custodial; wallets remain client-side (Privy / Web3Auth) |
| Marketplace spoofing | Backend only uses verified marketplace APIs and live WebSockets |
| Stale listings / price slips | Backend caches data, validates timestamps, and executes relists atomically via smart contracts |
| Workflow abuse | Smart contracts enforce signed instructions; backend cannot override constraints |
| DDoS / spam attacks | Rate-limiting, request queuing, and caching in Redis |
| Data leaks | No sensitive keys stored server-side; only signed messages handled |

---

## Assumptions
- Users manage private keys securely
- Marketplaces provide accurate, real-time data
- Smart contracts are verified and audited
