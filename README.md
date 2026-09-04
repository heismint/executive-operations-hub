# 🏢 Executive Operations OS & Standard Operating Procedures (SOPs)

> 🚀 **[Click Here to View the Live Executive Sprint Board](https://github.com/users/heismint/projects/1)**

A centralized operational repository containing standard operating procedures, automated workflows, and management runbooks designed for high-growth tech executives and distributed engineering teams.

---

## 📑 Table of Contents
1. [Module 1: Email Triage and AI Voice Pipeline](#module-1)
2. [Module 2: GitHub Project Consolidation and Issue Lifecycle](#module-2)
3. [Module 3: Bookkeeping, Invoicing and Financial Operations](#module-3)
4. [Module 4: Crypto Access Recovery and Asset Ledger Runbook](#module-4)
5. [Module 5: Executive Meeting Synthesis & Decision Records (EDR)](#module-5)
6. [Module 6: Cross-Functional Cadence & Commitment Tracking](#module-6)

---

<a id="module-1"></a>
## 📧 Module 1: Email Triage and AI Voice Pipeline

### 1. Label Architecture
Every incoming message is processed through a strict 3-tier triage system:
* `📥 01_NEEDS_ACTION` — Critical emails requiring decisions or external executive signatures.
* `✍️ 02_EA_DRAFTED` — Messages where a complete response has been drafted by the EA and queued for 1-click review.
* `⏳ 03_WAITING_ON` — Outgoing threads awaiting responses from external clients/vendors.
* `📁 04_ARCHIVE/RECEIPTS` — Filtered automatically; skips inbox.

### 2. Custom Gmail Filter Operators
* **Catch calendar notices and system alerts:**  
  `filename:ics OR from:(*@calendar-notification.google.com)` ➔ Apply label *📁 System/Calendar*, Skip Inbox.
* **Isolate vendor invoices and statements:**  
  `(subject:invoice OR subject:receipt OR subject:statement) filename:pdf` ➔ Apply label *💰 Finance/Invoices*, Star message.

### 3. Production Claude System Prompt (Draft Generation)
> **System Prompt:**  
> You are the Technical Executive Assistant to a tech founder. Your job is to draft a concise, professional, and clear email response based on the incoming context.  
>  
> **Rules:**  
> 1. Tone: Direct, warm, professional, zero corporate fluff.  
> 2. Structure: 1-2 sentence acknowledgment + clear next steps/action item + sign-off.  
> 3. If information is missing, use bracketed placeholders like `[Confirm Date]` for the executive.  
>  
> **Incoming Context:** `{{INSERT_EMAIL_BODY}}`  
> **Executive's Decision:** `{{INSERT_QUICK_BULLET_POINTS}}`

---

<a id="module-2"></a>
## 🐙 Module 2: GitHub Project Consolidation and Issue Lifecycle

### 1. Issue Categorization Matrix
| Tag | Description | SLA / Priority |
| :--- | :--- | :--- |
| `p0-blocker` | Production or executive bottleneck requiring immediate resolution | < 2 Hours |
| `ops-finance` | Bookkeeping, invoicing, and contract management tasks | 24 Hours |
| `access-security`| Access recovery, 2FA management, and repository permissions | 12 Hours |
| `dev-tracking` | Sprint backlog items and pull request status reviews | Weekly Sync |

### 2. Issue Lifecycle Workflow
1. **Intake:** Unstructured requests from Slack/email are turned into structured GitHub Issues.
2. **Scoping:** Clear acceptance criteria and checklists are added.
3. **Execution:** Work proceeds in `In Progress` with linked commits/branches where applicable.
4. **Approval:** Moved to `Needs Review` for executive sign-off before marking `Done`.

---

<a id="module-3"></a>
## 💰 Module 3: Bookkeeping, Invoicing and Financial Operations

### 1. Daily/Weekly Financial Operations Routine
1. **Receipt Intake:** Download PDF invoices from `💰 Finance/Invoices` label in Gmail.
2. **Spreadsheet Reconciliation:** Log Vendor, Transaction ID, Date, Amount, Expense Category, and Payment Method into Google Sheets.
3. **Invoice Generation:** Draft outgoing client invoices with standard NET 15/30 payment terms.
4. **A/R Tracking:** Send structured reminders for any balances aged past 14 days.

### 2. Transition Plan: Google Sheets ➔ QuickBooks/Xero
* **Phase 1:** Chart of Accounts Setup (Standardize Operating Expenses, SaaS, Contractor Payouts).
* **Phase 2:** Data Cleansing & CSV Export of previous 90-day transactions.
* **Phase 3:** Bank Feed & Payment Gateway Integration (Stripe, Mercury, Brex).
* **Phase 4:** Rule Automation for recurring vendor categorization.

---

<a id="module-4"></a>
## 🔐 Module 4: Crypto Access Recovery and Asset Ledger Runbook

### 1. Exchange Access Recovery Protocol (Coinbase / Custodial Wallets)
* **Step 1: Evidence Gathering Dossier**
  * Current Government ID (High-res front/back scan).
  * Proof of Address dated within last 90 days.
  * Historical transaction hashes (TxIDs) associated with funding wallets.
  * Approximate account creation date and registered primary email.
* **Step 2: Ticket Management & Escalation**
  * Open case via official support portal; record Case Number immediately.
  * Log all correspondence in internal secure tracker.
  * Set recurring calendar follow-ups every 48 hours until identity review completes.

### 2. Staked Crypto Tracking Ledger Format
| Asset | Platform | Staked Amount | Validator / Lockup | Reward Cadence | Unbonding Period |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **ETH** | Coinbase Prime | 32.0 ETH | Coinbase Pool | Daily | 9 Days |
| **SOL** | Phantom / Native | 500 SOL | Ledger Validator | Epoch (~3 days) | 1 Epoch |

---

<a id="module-5"></a>
## 🏛️ Module 5: Executive Meeting Synthesis & Decision Records (EDR)

### 1. The Synthesis Protocol
High-growth leadership teams cannot afford ambiguous meeting notes or lost action items. Every internal sync, board meeting, and strategic session follows a strict post-meeting SLA:
* **Turnaround Time:** Full synthesis distributed within **90 minutes** of meeting adjournment.
* **Intake Standard:** Real-time raw capture filtered for signal, discarding conversational filler.
* **Output Standard:** Clear separation of context, architectural/business decisions, and assigned accountability.

### 2. Standard Executive Decision Record (EDR) Template

````markdown
# [EDR] Strategy Sync: [Topic / Working Title]
**Date:** YYYY-MM-DD | **Time:** HH:MM [Timezone]  
**Participants:** [CEO], [Department Lead], [EA / Ops Lead]  
**Status:** Approved / Actionable

---

### 1. Executive Summary & Context
A 2–3 sentence distillation of why this meeting occurred, the core challenge discussed, and the net strategic outcome. Zero conversational filler.

---

### 2. Key Decisions Made
* **DECISION 1:** [Clear statement of the final call made]
  * *Rationale:* Why this approach was selected over alternatives.
  * *Impact:* Impacted teams, timelines, or capital reallocation.
* **DECISION 2:** [Clear statement of the final call made]
  * *Rationale:* Supporting technical/operational justification.

---

### 3. Action Items & Commitment Matrix
| Action Item | Directly Responsible Individual (DRI) | Priority | Hard Deadline | Issue Tracker Link |
| :--- | :--- | :--- | :--- | :--- |
| Finalize vendor evaluation matrix | @HeadOfProduct | P0 | YYYY-MM-DD (COB) | #OPS-104 |
| Draft board slide deck narrative | @CEO / @Ops | P1 | YYYY-MM-DD (12:00 EST) | #EXEC-42 |
| Update customer SLA terms in contracts | @LegalLead | P2 | YYYY-MM-DD | #LEG-18 |

---

### 4. Identified Risks, Blockers & Escalations
* **Blocker:** [Describe dependency or third-party delay]
  * *Mitigation / Next Step:* Who is unblocking it, and by when.
* **Unresolved Ambiguity:** [Points deferred to the next sync or requiring async data gathering].
