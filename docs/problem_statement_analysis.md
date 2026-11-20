# Problem Statement Analysis — Angadi Mitra
## PS 5.1 — Kirana Stock | Tech4Bharat 2026

> **Status:** This analysis is based on the publicly referenced problem statement.
> All specific figures and verbatim text should be verified against the official document:
> https://thegavshackathon.com/docs/Tech4Bharat-2026-Problem-Statements.pdf
> **Last updated:** November 2026

---

## 1. Source Document Reference

| Field | Value |
|---|---|
| Hackathon | Tech4Bharat 2026 — JanAI Mass Entrepreneurship Challenge |
| Problem Statement ID | PS 5.1 |
| PS Title | Kirana Stock |
| Theme | Theme 5 — Retail, FMCG & Logistics |
| Official PDF | https://thegavshackathon.com/docs/Tech4Bharat-2026-Problem-Statements.pdf |
| Relevant Pages | Page 3 (overall challenge requirements), Page 13 (PS 5.1) |

> **Important:** The researcher agent attempted to fetch the PDF during project setup. The specific figures and verbatim text should be confirmed directly from the official PDF before use in any presentation or submission.

---

## 2. Challenge-Wide Requirements (from Page 3)

Based on the Tech4Bharat 2026 challenge framework, all submissions are expected to address:

1. **Voice-first and vernacular accessibility** — solutions must be accessible to users in their native Indian language
2. **Low digital literacy support** — usable by people with no prior app experience
3. **Entry-level Android compatibility** — cannot assume a high-end device
4. **Intermittent connectivity** — must work in areas with poor or no internet
5. **User consent and minimum data collection** — privacy-first design
6. **Clear labelling of simulated integrations** — no pretending something is live when it is not
7. **JanAI Café support pathway** — physical onboarding assistance should be considered

*These requirements are incorporated into the Angadi Mitra design throughout.*

---

## 3. PS 5.1 — Kirana Stock: Problem Description

### 3.1 Core Problem

Small kirana and provision stores across India manage their inventory through:
- Memory and manual shelf checks
- No structured billing or inventory systems
- No data-driven purchasing decisions

This results in multiple costly problems that affect store profitability and sustainability.

### 3.2 Specific Challenges Identified

| # | Challenge | Description |
|---|---|---|
| 1 | **Memory-based inventory** | Stock is tracked through the shopkeeper's memory and periodic shelf checks, with no written records |
| 2 | **No billing system** | Most small kirana stores have no billing software, meaning no transaction history exists |
| 3 | **Fast-moving stockouts** | Popular products go out of stock because there is no system to flag low stock in advance |
| 4 | **Dead stock / working capital freeze** | Approximately 15–20% of working capital is estimated to be tied up in slow-moving or unsold products |
| 5 | **Expiry losses** | Stock expiry losses estimated at approximately ₹5,000–₹10,000 per month per store |
| 6 | **Festival demand guessing** | Seasonal and festival demand is guessed rather than anticipated, leading to either overstock or stockout |
| 7 | **Distributor-driven purchasing** | Purchase decisions are often made based on what the distributor recommends or offers, not on actual demand data |
| 8 | **Local product names** | Products are known by regional names and aliases; standard names from databases may not match what shopkeepers or customers use |
| 9 | **Incomplete product data** | No structured product catalogue; images and barcodes are not always available |
| 10 | **Limited insights from records** | Even where records exist, there is no way to generate useful insights from them |

> **Note:** Figures marked with * (₹5,000–₹10,000 expiry, 15–20% dead stock) are from the problem statement — verify exact wording in the official PDF.

### 3.3 Key Requirements from PS 5.1

Based on the problem statement, the solution must:

1. **Deliver useful recommendations within the first seven days** of adoption, even without prior billing history
2. **Respect the shopkeeper's chosen cash budget** for all purchasing recommendations
3. **Require shopkeeper approval** before any purchase order or consequential action
4. **Support local product names** and regional product aliases
5. **Work on the devices shopkeepers already have** (entry-level Android)
6. **Be accessible in Indian languages** relevant to the target region
7. **Handle the absence of existing data** gracefully — start from zero if needed

---

## 4. Angadi Mitra Response to Each Challenge

| PS 5.1 Challenge | Angadi Mitra Response |
|---|---|
| Memory-based inventory | Image-first dashboard with real-time stock quantities; voice update removes friction of data entry |
| No billing system | Designed to work without prior billing data; builds history from first use |
| Fast-moving stockouts | Fast-moving product analysis; low-stock alerts with configurable thresholds |
| Dead stock (15–20% capital) | Slow-moving stock analysis identifies dead stock with explanation |
| Expiry losses (₹5–10k/month) | Expiry date tracking and expiry alerts |
| Festival demand guessing | Festival demand estimates (clearly labelled as estimates, not guarantees) |
| Distributor-driven purchasing | AI restocking recommendations based on data, not distributor suggestion |
| Local product names | Product alias system; shopkeeper can name products in their own way |
| Incomplete product data | Works without barcodes; image and manual selection supported |
| No useful insights | AI analysis of stock velocity, expiry risk, dead stock, and budget-aware suggestions |

---

## 5. What PS 5.1 Does NOT Require (and We Are Not Building)

| Item | Reason Not Included |
|---|---|
| Full billing system | PS 5.1 targets inventory management, not accounting |
| Tax/GST management | Out of scope for this problem statement |
| Customer credit management | Optional future feature; not in PS 5.1 scope |
| Bank/financial integrations | Not required; privacy risk without clear benefit |
| Autonomous ordering | Explicitly forbidden — shopkeeper must approve every purchase |

---

## 6. Official Problem Statement Key Numbers

The following figures are attributed to the Tech4Bharat 2026 PS 5.1 problem statement:

| Metric | Figure | Usage in Angadi Mitra |
|---|---|---|
| Dead stock as % of working capital | ~15–20% | Used to explain the dead-stock problem; labelled as PS estimate |
| Monthly expiry losses | ~₹5,000–₹10,000 | Used to explain expiry cost; labelled as PS estimate |
| First-week insights requirement | Within 7 days | Drives the 7-day onboarding journey design |
| Budget requirement | Shopkeeper-chosen | Drives budget-aware recommendation system |

> **All figures must be verified against the exact text of the official PDF before use in formal submissions or presentations. Do not cite these numbers without reading the original document.**

---

## 7. India-Wide Scope

The PS 5.1 problem statement refers to kirana stores across India, not a specific state or language region.

Angadi Mitra is designed as an **India-wide product** with:
- Multi-language support (not Kannada-only)
- Product alias handling across regions
- No assumption that all users speak the same language
- Adaptable to different regional products and naming conventions

---

## 8. Gaps and Limitations Identified

| Gap | Current Status | Plan |
|---|---|---|
| No real-world data to validate the 15–20% dead stock figure | Unvalidated assumption | Field research required |
| Festival demand forecasting requires historical data | Cannot be reliable from day 1 | Label as estimate; improve over time |
| Regional product catalogues not yet built | No pre-existing data | Collect from field; use shopkeeper input |
| AI recommendation quality depends on data quantity | Day 1 quality will be low | Communicate honestly to shopkeeper |
| Internet required for AI features | Not always available in villages | Offline mode for core features; AI queued |

---

*This analysis is based on the publicly described PS 5.1 requirements. Exact verbatim text must be confirmed from the official PDF before use in formal submission.*
