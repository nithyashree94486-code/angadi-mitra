# Hackathon Submission Descriptions — Angadi Mitra
## Tech4Bharat 2026 | PS 5.1 – Kirana Stock

> **Status:** Submission-ready draft content.
> **Last updated:** November 2026

---

## 1. Brief Description (Portal Short Description)

**Angadi Mitra** ("Shop Friend") is a multilingual, image-first, voice-assisted **Agentic AI** inventory management assistant for small and village-level kirana stores across India. It is designed for shopkeepers who manage stock through memory and manual shelf checks — with no existing billing system, limited digital literacy, and intermittent internet connectivity.

Using Agentic AI (Google Gemini with function calling), Angadi Mitra understands natural-language voice commands in Indian languages, analyses current inventory, identifies low-stock and expiring products, spots slow-moving dead stock, and generates budget-aware restocking recommendations — all within the shopkeeper's chosen cash budget. Every purchase recommendation requires explicit shopkeeper approval before any action is taken.

The app is designed to deliver useful insights within the first 7 days, even with no prior records. It runs as a Progressive Web App on Android, supports 8+ Indian languages for both speech and interface, and works offline for core features.

**Problem Addressed:** PS 5.1 — Kirana Stock | Tech4Bharat 2026 | Theme 5 — Rural FMCG and Logistics

---

## 2. Detailed Description

### Problem Statement

India's 12+ million small kirana and provision stores are the backbone of local retail — especially in villages and semi-urban areas. Yet most of them manage stock the same way they always have: through memory, visual shelf checks, and experience.

This informal approach creates a cycle of costly problems:
- **Fast-moving products go out of stock**, causing lost sales and disappointed customers
- **Dead stock ties up 15–20% of working capital** in products that aren't selling (PS 5.1 estimate)
- **Expiry losses cost approximately ₹5,000–₹10,000 per month** per store (PS 5.1 estimate)
- **Festival and seasonal demand is guessed**, not anticipated
- **Distributor visits drive purchasing** without any demand data
- **Local product names and inconsistent records** make data-driven tools unusable

> *Figures attributed to Tech4Bharat 2026 PS 5.1 — verify against the official problem statement document.*

Existing software tools — Vyapar, myBillBook, GoFrugal, Marg ERP — are designed for urban businesses with billing needs and digital infrastructure. They are not built for a first-time digital user in a village who prefers to speak in Kannada or Tamil and doesn't know what a "stock ledger" is.

---

### Proposed Solution

**Angadi Mitra** (ಅಂಗಡಿ ಮಿತ್ರ / अंगड़ी मित्र) is a shop-first digital assistant, not a business ERP.

**Core design philosophy:**
- **Talk to it, don't type into it** — voice is the primary input
- **See your products, not data tables** — image-first visual interface
- **In your language** — not just Hindi and English, but Kannada, Tamil, Telugu, Malayalam, Bengali, Marathi, and more
- **On your phone** — a Progressive Web App on the Android you already have
- **Within your budget** — AI recommendations always respect your chosen cash limit
- **You decide** — the AI suggests, you approve, nothing happens without your permission

---

### Main Features

1. **Multilingual Onboarding** — Language selection on first visit; interface adapts entirely to the chosen language
2. **Simple Authentication** — Phone-based OTP login; no email, no complicated forms
3. **Image-First Dashboard** — Large product photos, local-language names, clear stock indicators
4. **Voice Stock Updates** — "10 biscuit packets arrived" → system confirms → stock updated
5. **Distributor Receiving** — Record deliveries via voice or visual selection
6. **Product Identification** — Barcode, image, manual, regional names — all supported
7. **Low-Stock Alerts** — Configurable thresholds and instant notifications
8. **Expiry Monitoring** — Tracks expiry dates and alerts before stock expires
9. **Dead-Stock Analysis** — Identifies slow-moving products with explanations
10. **Fast-Moving Tracking** — Spots high-velocity products before they run out
11. **AI Restocking Recommendations** — Budget-aware, reason-explained, approval-gated
12. **Festival Demand Estimates** — Seasonal demand signals, clearly labelled as estimates
13. **7-Day Onboarding Journey** — Useful insights from day 1, even without prior records
14. **Offline Mode** — Core features work without internet; syncs when back online

---

### Agentic AI Workflow

Angadi Mitra implements a **genuine agentic AI architecture** using Google Gemini with function calling — not a simple chatbot.

The agent:
1. Understands natural-language voice input in Indian languages
2. Identifies the shopkeeper's intent (update stock, get recommendation, check alerts, etc.)
3. Plans a sequence of tool calls to gather relevant information
4. Calls tools: `get_inventory_status()`, `analyse_stock_velocity()`, `check_budget_headroom()`, `generate_restock_plan()`, etc.
5. When uncertain, asks a clarifying question before proceeding
6. For consequential actions (stock updates, restocking plans), presents findings and **requests shopkeeper approval**
7. Only after approval: executes the action and writes to the database
8. Logs every action in an audit trail

**Three-layer separation:**
- **LLM (Gemini):** Understanding, planning, reasoning, explaining
- **Deterministic code:** Inventory arithmetic, budget calculations, threshold checks — not AI-estimated
- **Human:** Approves every purchase — the AI never spends money autonomously

---

### Technology Approach

| Layer | Technology |
|---|---|
| Frontend | React + TypeScript + Vite (PWA) |
| UI | Tailwind CSS + shadcn/ui |
| Backend & Database | Supabase (PostgreSQL + Auth + Storage) |
| Authentication | Supabase OTP (phone-based) |
| AI Agent | Google Gemini (evaluating gemini-3.8-flash) (Function Calling) |
| Voice STT | Web Speech API + Google Cloud STT |
| Voice TTS | Web Speech API + Google Cloud TTS |
| Offline | Dexie.js (IndexedDB) + Service Worker |
| Hosting | Vercel (PWA deployment) |

**Indian Languages with verified voice support (Google Cloud):**
Hindi, Kannada, Tamil, Telugu, Bengali, Malayalam, Marathi, Gujarati *(verify current support at https://cloud.google.com/speech-to-text/docs/speech-to-text-supported-languages)*

---

### Accessibility and Connectivity

- **Low digital literacy:** Image-first, voice-first, minimal text entry, guided onboarding
- **Entry-level Android:** PWA on Chrome, optimised assets, no native install required
- **Low bandwidth:** Offline core features, compressed images, background sync
- **First-time users:** 7-day guided onboarding; JanAI Café physical support pathway (proposed)

---

### Expected Impact

If adopted by even a fraction of India's small kirana stores:
- Reduction in monthly expiry losses through timely alerts
- Reduction in dead-stock through identification and re-prioritisation
- Reduction in stockout frequency through early low-stock detection
- Improved purchase decisions through data-backed, budget-aware recommendations
- Accessible inventory intelligence for first-time digital users

> *All impact estimates are projections. No pilot has been conducted yet. Outcomes to be measured through field validation.*

---

### Limitations and Dependencies

| Limitation | Current Status |
|---|---|
| AI recommendation quality improves with data | Day-1 recommendations are limited — communicated honestly |
| Festival forecasting requires historical data | Calendar-based estimates for Year 1; clearly labelled |
| AI features require internet | AI queued for reconnect; core features offline |
| Field research not yet conducted | Shopkeeper interviews are proposed, not completed |
| Voice accuracy on low-end devices | To be tested on target devices |
| Implementation in progress | Foundation phase complete; prototype in development |

---

### Future Scope

- Optional digital billing and bill history
- Online wholesale ordering (with verified supplier integrations)
- Group purchasing for neighbouring kirana stores
- Neighbourhood stock comparison
- Deeper FMCG brand analytics (opt-in, with revenue sharing for shopkeepers)
- Supplier and distributor app integration (when API partnerships are established)

---

## 3. Quality Checklist

Before final submission, verify:

- [ ] All PS 5.1 requirements are mapped to features (see requirements_traceability.md)
- [ ] All figures from PS 5.1 verified against the official PDF
- [ ] No claim that implementation is complete — foundation only
- [ ] No claim that integrations are live when proposed
- [ ] No fabricated interview results or pilot data
- [ ] All forecasts labelled as estimates
- [ ] Budget enforcement is deterministic, not AI-estimated
- [ ] Shopkeeper approval gate is in every consequential workflow
- [ ] Language support claims match official Google Cloud documentation
- [ ] Competitor analysis is sourced and verified
- [ ] Privacy and consent addressed in architecture

---

*Submission content prepared for Tech4Bharat 2026. All proposed features are planned, not yet implemented.*
