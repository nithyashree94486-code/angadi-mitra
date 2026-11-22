# Solution Overview — Angadi Mitra

## Tech4Bharat 2026 | PS 5.1 – Kirana Stock | Theme 5 – Rural FMCG & Logistics

> **Status:** Proposed Solution Architecture & Conceptual Design  
> **Target Audience:** Small and village-level kirana / provision store owners across India

---

## 1. Executive Summary

**Angadi Mitra** ("Shop Friend") is a multilingual, image-first, and voice-assisted **Agentic AI** inventory management assistant specifically conceived for India's 12+ million small, unorganized kirana stores.

Traditional inventory management solutions assume structured billing databases, desktop computers, barcode infrastructure, English literacy, and constant broadband connectivity. Small rural and semi-urban shopkeepers possess none of these prerequisites. Consequently, shopkeepers manage inventory through memory and physical shelf checks, leading to severe operational friction:

- Fast-moving goods routinely stock out, causing direct revenue loss.
- Unsold items stagnate as dead stock, locking up 15–20% of scarce working capital.
- Perishables expire unnoticed on shelves, resulting in ₹5,000–₹10,000 of monthly losses.
- Restocking purchases are dictated by distributor persuasion rather than data-driven demand.

Angadi Mitra bridges this digital divide by replacing complex enterprise software with a simple, conversational assistant that speaks the shopkeeper's language, understands voice commands, displays visual product images, respects cash budgets, and requires human approval for every decision.

---

## 2. Who Angadi Mitra Serves

### Primary User Persona: The Village Kirana Shopkeeper

- **Operational Reality:** Operates an independent 100–300 sq. ft. store serving 50–250 local households. Runs the business single-handedly or with family assistance.
- **Record-Keeping:** No formal point-of-sale (POS) or billing system. Sales are cash or UPI. Customer credit (udhaar) is tracked in paper khata notebooks. Stock is kept in memory.
- **Hardware & Connectivity:** Relies on an entry-level Android smartphone (2GB–4GB RAM) with intermittent 3G/4G or spotty rural cellular coverage.
- **Language & Literacy:** Comfortable with local vernacular languages (e.g., Kannada, Hindi, Tamil, Telugu) and spoken communication; intimidated by dense English text and complex multi-column software tables.
- **Financial Constraints:** Operates on tight, weekly cash-flow cycles with restricted purchasing capital. Cannot afford speculative or dead stock.

---

## 3. Why Existing Solutions Fail Kirana Stores

Existing retail software caters almost exclusively to formal, urban retailers:

1. **Billing-First Requirement:** Systems like Vyapar and myBillBook require billing every customer transaction to maintain inventory counts. Kirana shopkeepers during rush hours cannot pause to create digital invoices for a ₹5 packet of salt or ₹10 biscuit.
2. **ERP & Desktop Orientation:** Systems like Marg ERP and GoFrugal are built for desktop computers, distributors, and large supermarkets with dedicated accounting staff.
3. **Credit-Only Focus:** Apps like Khatabook excel at customer debt ledgers (udhaar) but do not solve inventory velocity, stockouts, expiry, or restocking intelligence.
4. **Language & Modality Barriers:** Nearly all platforms rely on text-heavy forms, dropdown menus, and standard FMCG catalog naming that ignores local colloquial product names.

---

## 4. How the Proposed System Works

Angadi Mitra operates around three primary pillars: **Voice-First Input**, **Image-First Interface**, and **Agentic AI Intelligence**.

```
┌────────────────────────────────────────────────────────────────────────┐
│                        HOW ANGADI MITRA OPERATES                        │
│                                                                        │
│   Shopkeeper Speaks           Agentic AI Analyzes       Shopkeeper Decides
│  ┌──────────────────┐        ┌──────────────────┐      ┌──────────────────┐
│  │ "Add 10 packets  │        │ • Identifies item│      │ • Reviews summary│
│  │  of Parle-G"     │───────>│ • Checks budget  │─────>│ • Approves with  │
│  │ (Kannada / Hindi)│        │ • Predicts runout│      │   single tap     │
│  └──────────────────┘        └──────────────────┘      └──────────────────┘
│                                        │                         │
│                                        ▼                         ▼
│                                Deterministic Logic        Updated Stock &
│                                (Exact Arithmetic)           Audit History
└────────────────────────────────────────────────────────────────────────┘
```

### 4.1 Onboarding Without Prior Records (Zero-Data Start)
Angadi Mitra requires no legacy billing import:
- **Day 1:** The shopkeeper selects their preferred language (e.g., Kannada, Hindi, English).
- **Day 1–2:** They add their top 15–20 high-velocity staple items by tapping clear product cards or speaking their names.
- **Day 3–5:** Incoming distributor deliveries are recorded simply by voice or visual counter updates.
- **Day 7:** The system provides its first data-backed restocking recommendation based on observed stock movement.

### 4.2 Handling Intermittent Connectivity (Offline-First)
- All critical daily operations—checking stock, logging sales, recording incoming goods, and viewing low-stock alerts—operate offline via browser IndexedDB caching.
- Changes are queued locally and synchronized automatically with conflict resolution once connectivity is restored.
- Heavy Agentic AI recommendations run whenever connectivity is available and cache results for offline review.

### 4.3 Multi-Language & Vernacular Speech Support
- Voice input is converted to text using Web Speech API locally or cloud speech models.
- Product aliases map regional vocabulary (e.g., "ಬಿಸ್ಕತ್", "बिस्कुट", "Parle-G") to canonical product entries.
- Spoken responses and recommendations are synthesized back to the shopkeeper in their native language.

---

## 5. Core Architectural Philosophy: AI Recommends, Human Decides

A foundational principle of Angadi Mitra is that **artificial intelligence must never make autonomous financial commitments**:

1. **No Autonomous Purchasing:** The AI agent analyzes stock levels, calculates restocking needs, and prioritizes items based on the shopkeeper's stated cash budget, but it **never** places an order or transfers funds automatically.
2. **Deterministic Financial Integrity:** Arithmetic calculations (e.g., quantity multiplication, total cost, remaining budget headroom) are handled by deterministic TypeScript logic, not estimated by language models.
3. **Transparent Reasoning:** Every AI recommendation includes an understandable explanation: *"Recommended 12 packets of tea powder because current stock is 2, average weekly sale is 10, and it fits within your ₹2,000 budget."*
4. **Mandatory Approval Gate:** Every stock adjustment and restocking plan requires an unambiguous confirmation tap from the shopkeeper.
