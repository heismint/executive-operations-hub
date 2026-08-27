# 🏢 Executive Operations OS & Standard Operating Procedures (SOPs)

A centralized operational repository containing standard operating procedures, automated workflows, and management runbooks designed for high-growth tech executives and distributed engineering teams.

---

## 📑 Table of Contents
1. [Module 1: Email Triage & AI Voice Pipeline (Gmail + Claude)](#-module-1-email-triage--ai-voice-pipeline)
2. [Module 2: GitHub Project Consolidation & Issue Lifecycle](#-module-2-github-project-consolidation--issue-lifecycle)
3. [Module 3: Bookkeeping, Invoicing & Financial Operations](#-module-3-bookkeeping-invoicing--financial-operations)
4. [Module 4: Crypto Access Recovery & Asset Ledger Runbook](#-module-4-crypto-access-recovery--asset-ledger-runbook)

---

## 📧 Module 1: Email Triage & AI Voice Pipeline

### 1. Label Architecture
Every incoming message is processed through a strict 3-tier triage system:
* `📥 01_NEEDS_ACTION` — Critical emails requiring decisions or external executive signatures.
* `✍️ 02_EA_DRAFTED` — Messages where a complete response has been drafted by the EA and queued for 1-click review.
* `⏳ 03_WAITING_ON` — Outgoing threads awaiting responses from external clients/vendors.
* `📁 04_ARCHIVE/RECEIPTS` — Filtered automatically; skips inbox.

### 2. Custom Gmail Filter Operators
```text
# Catch calendar notices and system alerts
Matches: filename:ics OR from:(*@calendar-notification.google.com)
Action: Apply label "📁 System/Calendar", Skip Inbox

# Isolate vendor invoices and statements
Matches: (subject:invoice OR subject:receipt OR subject:statement) filename:pdf
Action: Apply label "💰 Finance/Invoices", Star message
