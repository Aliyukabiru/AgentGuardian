# AgentGuardian
AgentGuardian — An autonomous security and risk assessment AI agent for BNB Chain, built with Binance Agent OS.
# 🛡️ AgentGuardian

## Autonomous Security & Risk Assessment AI for BNB Chain

AgentGuardian is an AI-powered security agent designed to continuously analyze BNB Chain contract and transaction data, calculate transparent risk scores, and trigger security workflows when suspicious activity is detected.

Built for the Binance Agent OS Mini Hackathon.

---

## 🎯 The Problem

BNB Chain and DeFi move quickly.

Users interact with smart contracts, tokens, wallets and protocols every day, but identifying dangerous contract behavior and suspicious transactions can require significant technical knowledge.

AgentGuardian turns complex on-chain signals into a simple security decision.

---

## 💡 The Solution

AgentGuardian follows this workflow:

BNB Chain Data
↓
Contract & Transaction Analysis
↓
Security Signal Extraction
↓
Risk Scoring
↓
Workflow Trigger
↓
Security Alert

The agent can classify activity as:

🟢 LOW RISK

🟡 REVIEW

🔴 HIGH RISK

---

## ⚙️ Core Capabilities

### 1. Contract Security Analysis

AgentGuardian analyzes available contract and transaction data for security-relevant signals.

Examples include:

- Contract metadata
- Bytecode-derived signals
- Ownership/permission signals
- Suspicious function activity
- Transaction behavior
- High-risk interactions

### 2. On-Chain Risk Scoring

Signals are converted into a transparent risk score from 0–100.

Example:

Contract risk: 82
Transaction risk: 71
Permission risk: 90
Activity risk: 68

Final Risk Score: 81/100

Classification:

81–100 = HIGH RISK
50–80 = REVIEW
0–49 = LOW RISK

### 3. Automated Security Workflows

When the risk score crosses a configured threshold, AgentGuardian triggers a workflow.

Example:

HIGH RISK
↓
Create security alert
↓
Notify user
↓
Recommend avoiding interaction

### 4. Security Alerts

AgentGuardian can send structured alerts containing:

- Contract address
- Chain
- Risk score
- Detected signals
- Recommended action
- Timestamp

---

## 🏗️ Architecture

```text
                  BNB CHAIN
                      │
                      ▼
             ┌─────────────────┐
             │  AgentGuardian  │
             │   Data Layer    │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │ Security Engine │
             └────────┬────────┘
                      │
              ┌───────┴────────┐
              ▼                ▼
       Contract Analysis   Tx Analysis
              │                │
              └───────┬────────┘
                      ▼
             ┌─────────────────┐
             │   Risk Engine   │
             └────────┬────────┘
                      ▼
              RISK SCORE 0-100
                      │
          ┌───────────┼───────────┐
          ▼           ▼           ▼
        SAFE        REVIEW       HIGH
          │           │           │
          └───────────┴───────────┘
                      │
                      ▼
             Workflow Trigger
                      │
              ┌───────┴───────┐
              ▼               ▼
          Telegram             X
            Alert            Alert
