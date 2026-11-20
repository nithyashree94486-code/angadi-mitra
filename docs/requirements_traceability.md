# Requirements Traceability Matrix — Angadi Mitra
## PS 5.1 — Kirana Stock | Tech4Bharat 2026

> **Status:** Requirements mapped — features proposed, not yet implemented.
> **Last updated:** November 2026

---

## How to Read This Matrix

Each row maps one official requirement or challenge from PS 5.1 to:
- **Angadi Mitra Response:** How we propose to address it
- **Proposed Feature/Workflow:** The specific feature or component that addresses it
- **Status:** Whether the feature is designed, planned, or not yet addressed
- **Dependency/Limitation:** What must be true for this to work

---

## Traceability Matrix

| # | Official Problem/Requirement (PS 5.1) | Angadi Mitra Response | Proposed Feature/Workflow | Status | Dependency or Limitation |
|---|---|---|---|---|---|
| R1 | Shopkeepers track stock through memory and shelf checks | Provide a simple visual inventory tool that is easier than memory | Image-first dashboard with real-time stock quantities | 📋 Designed | Shopkeeper must enter initial stock; no magic import |
| R2 | No existing billing system or inventory records | Design to work from zero — no prior data needed | Day 1 onboarding: add essential products + quantities | 📋 Designed | Quality of recommendations improves with more data |
| R3 | Fast-moving products go out of stock | Identify high-velocity products and alert before stockout | Fast-moving product analysis + low-stock alerts | 📋 Designed | Requires at least 7 days of movement data |
| R4 | Dead stock ties up ~15–20% of working capital | Identify slow-moving and unsold products with explanation | Slow-mover / dead-stock analysis | 📋 Designed | Requires movement data; threshold configurable |
| R5 | Product expiry and stock wastage | Track expiry dates and alert before expiry | Expiry date recording + expiry alerts | 📋 Designed | Shopkeeper must enter expiry dates; not all products have them |
| R6 | Festival and seasonal demand is guessed | Provide demand estimates for predictable seasonal events | Festival demand estimation (calendar + history) | 📋 Designed | Estimates clearly labelled; reliable only with historical data |
| R7 | Distributor visits drive purchasing decisions | Provide data-driven restocking recommendations | Agentic AI restocking recommendations with reasons | 📋 Designed | Requires Gemini API; quality improves with data |
| R8 | Local product names and aliases | Allow shopkeeper to name products in their own language | Product alias system; shopkeeper-defined names | 📋 Designed | Building a regional alias database requires field research |
| R9 | Incomplete product data (no barcodes/images) | Support multiple product identification methods | Barcode + image selection + manual entry — all optional | 📋 Designed | No single method is mandatory |
| R10 | Cannot generate useful insights from records | AI analysis of available data, with honest uncertainty | AI analysis tools: velocity, expiry, dead-stock, budget | 📋 Designed | Insight quality scales with data quantity |
| R11 | Useful recommendations within first 7 days | Progressive onboarding delivers value from day 1 | 7-day onboarding journey | 📋 Designed | Early recommendations will be limited — this is communicated |
| R12 | Purchases must stay within shopkeeper's cash budget | Budget enforcement is deterministic — not AI-estimated | Budget-aware recommendation + hard budget cap | 📋 Designed | Shopkeeper must set budget; no default assumed |
| R13 | Every purchase must be approved by shopkeeper | Mandatory approval gate before any purchase action | Human approval gate in agent workflow | 📋 Designed | AI never autonomously places an order |
| R14 | Voice-first and vernacular accessibility | Voice commands in Indian languages | Web Speech API + Google Cloud STT/TTS | 📋 Designed | Language support varies by device; fallback to text |
| R15 | Low digital literacy users | Minimal text, large icons, image-first, voice-first | UX design principles + simple onboarding | 📋 Designed | Usability must be tested with actual target users |
| R16 | Entry-level Android device compatibility | PWA on Chrome; minimal resource requirements | React PWA, optimised assets, low-bandwidth design | 📋 Designed | Must be tested on actual low-end devices |
| R17 | Intermittent internet connectivity | Offline mode for core features | IndexedDB local cache + background sync | 📋 Designed | AI features require internet; queued for reconnect |
| R18 | User consent and minimum data collection | Collect only what is needed for inventory management | Privacy-first design; no customer personal data | 📋 Designed | Privacy policy required before launch |
| R19 | Clear labelling of simulated integrations | Label all proposed/simulated features clearly | All documentation and UI clearly marks unbuilt features | ✅ Done | Ongoing — must maintain as features are built |
| R20 | JanAI Café as supported onboarding pathway | Design onboarding to be assistable by a third party | Simple, guided onboarding flow; JanAI Café as optional support | 📋 Designed | Not a confirmed integration; proposed pathway only |

---

## Status Key

| Icon | Meaning |
|---|---|
| ✅ Done | Feature or requirement is addressed in current form |
| 📋 Designed | Architecture/workflow designed, implementation pending |
| 🔄 Partial | Partially addressed, more work needed |
| ⚠️ At Risk | Addressed in design but significant dependency or risk |
| ❌ Not Addressed | Not yet mapped to any feature |

---

## Challenge-Wide Requirements Mapping

| # | Challenge-Wide Requirement | How Angadi Mitra Addresses It |
|---|---|---|
| CW1 | Voice-first and vernacular | Multilingual STT/TTS; interface in shopkeeper's language |
| CW2 | Low digital literacy | Image-first UI, large buttons, voice primary, text secondary |
| CW3 | Entry-level Android | PWA, optimised, no native install required |
| CW4 | Intermittent connectivity | Offline core features, sync queue, network indicator |
| CW5 | Minimum data collection | Inventory data only; no customer personal info |
| CW6 | Label simulated integrations | All proposed features clearly marked throughout docs and UI |
| CW7 | JanAI Café pathway | Onboarding designed to be supportable by a helper at a kiosk |

---

## Gaps and Unresolved Items

| Gap | Priority | Plan |
|---|---|---|
| No field-validated list of regional product aliases | High | Conduct shopkeeper interviews |
| AI recommendation quality on Day 1 (no data) | High | Communicate limitation honestly; template-based starter suggestions |
| Festival forecasting requires historical data | Medium | Use Indian festival calendar + conservative estimates for first year |
| Voice accuracy on low-end devices in noisy shop environments | High | Test on target devices; show visual confirmation always |
| Offline AI recommendations | Medium | Cache last recommendation; re-generate when back online |
| Conflict handling when offline sync returns | Medium | Surface conflicts to shopkeeper for resolution |

---

*All features listed as "Designed" are proposed implementations. No feature has been implemented or tested as of November 2026.*
