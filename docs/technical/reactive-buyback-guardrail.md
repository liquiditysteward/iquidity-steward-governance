# 🛡️ Reactive Buyback Guardrail (RB Guardrail)

## Summary

The Reactive Buyback Guardrail is a proposed mechanism within the Liquidity Steward ecosystem designed to **deter aggressive, market-disruptive token dumping** by whales. It acts as an **automated defense system** that identifies predatory sell behavior and responds with algorithmic buy pressure, based on **confidential parameters** voted on by the DAO.

The mechanism promotes healthy, orderly token markets and helps preserve buyer confidence during volatility events.

---

## 🎯 Objectives

| Goal                       | Description                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| 🚫 Discourage dumping      | Create consequences for harmful, large-volume sells                        |
| 🪙 Stabilize price action  | Soften steep downward moves with responsive buy pressure                   |
| 🧠 Prevent exploitation    | Use hidden thresholds and randomized response patterns                     |
| 🧾 Remain verifiable       | Publish all buybacks and strategy parameters post-execution                |

---

## 🔧 System Architecture

### 1. **Detection Layer**
- Monitors live market data for signs of unhealthy price action.
- Trigger conditions include:
  - Sudden price drop (e.g. > X% within Y minutes)
  - Large sell volume from one or few wallets
  - Rapid spread widening on DEXs
  - RSI or VWAP deviations

### 2. **Confidential Trigger Parameters**
- Defined via blind voting and encrypted proposal mechanism (see Confidential Governance Protocol).
- Parameters are unknown to the public until after a trigger fires and the key is released.

### 3. **Execution Agent**
- Executes controlled buybacks using DAO-approved reserve funds.
- Trades are split into randomized intervals and amounts.
- Buys back from the same market to reduce manipulation incentives.

### 4. **Post-Execution Verification**
- Trigger conditions and buyback actions are published.
- DAO or community members can verify:
  - Strategy logic (decrypted)
  - That hash of revealed strategy matches original commit
  - Trade logs match approved behavior

---

## ⚙️ Sample DAO-Governed Parameters (Encrypted)

| Parameter                    | Description                                          |
|-----------------------------|------------------------------------------------------|
| `min_drop_pct`              | e.g. 8% drop in under 15 minutes                    |
| `trigger_window_minutes`    | Detection window (e.g. 10–30 minutes)               |
| `max_daily_buyback_usd`     | Budget cap for reactive buys                        |
| `buyback_dca_interval`      | Randomized interval between trades                  |
| `cooldown_minutes`          | Minimum delay before allowing another trigger       |
| `multi_condition_required`  | Require multiple indicators to fire (e.g. RSI + drop) |

---

## 🧠 Anti-Gaming Design Features

| Exploit Attempt                                | Defense Mechanism                                             |
|------------------------------------------------|----------------------------------------------------------------|
| Dump to trigger buys, then sell into recovery  | Randomized response timing + capped buyback volume            |
| Game known thresholds                          | Parameters are encrypted; strategy unknown until after        |
| Coordinate fake dips with partners             | Multi-indicator triggering + wallet-based cooldown tracking   |
| Mirror DAO buybacks for profit                 | Execution logs delayed; buys randomized and stealthy          |

---

## 🔍 Transparency and Trust

While behavior is concealed **before** execution, all activity becomes transparent **after**:

- Strategy and parameters are published and hashed
- Trade logs are visible on-chain or via indexers
- DAO members and auditors can validate system behavior retroactively

> **"You don't get punished for selling. You get punished for dumping."**

This mechanism is intended to enhance confidence in token markets supported by Liquidity Steward by preserving fairness and deterring abusive behavior. It will evolve as part of a broader defense suite through DAO proposal and community input.

---

## 🔗 Related Documents

- [Buy and Burn Agent](./buy-and-burn-agent.md) - Inflation management mechanism
- [Agent Architecture](./agent-architecture.md) - Technical architecture overview
- [Confidential Governance](../governance/confidential-governance.md) - Privacy-preserving governance
- [Governance Framework](../governance/framework.md) - Core governance structure

---

**Last updated:** June 28, 2025 