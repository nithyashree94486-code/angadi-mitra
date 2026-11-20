# Implementation Roadmap — Angadi Mitra

> **Status:** Planned roadmap — implementation has not yet started.
> **Last updated:** November 2026

---

## Overview

This roadmap outlines a realistic development plan for a student team building a hackathon prototype and moving toward a pilot.

---

## Phase 0: Foundation (Complete)

✅ Project research and documentation  
✅ Problem statement analysis  
✅ Architecture design  
✅ Technology stack selection  
✅ GitHub repository setup  
✅ Competitor analysis  
✅ Submission content preparation  

---

## Phase 1: Core Prototype — Week 1–2

**Goal:** Working skeleton with authentication, inventory CRUD, and basic dashboard.

### Week 1 Tasks
- [ ] Set up React + TypeScript + Vite project
- [ ] Configure Tailwind CSS and shadcn/ui
- [ ] Set up Supabase project (database, auth, storage)
- [ ] Create database schema (shopkeepers, products, inventory_items, stock_movements)
- [ ] Implement OTP-based phone authentication
- [ ] Language selection onboarding screen
- [ ] Basic product add/view screen

### Week 2 Tasks
- [ ] Image-first dashboard with product cards
- [ ] Stock quantity update (manual)
- [ ] Low-stock indicator on dashboard
- [ ] Simple add-product form with image upload
- [ ] Basic i18n setup (English + Hindi + Kannada strings)

**Milestone:** Shopkeeper can log in, add products, and view dashboard. No AI yet.

---

## Phase 2: Voice and Alerts — Week 3

**Goal:** Voice stock updates working. Alert system functional.

- [ ] Integrate Web Speech API for STT
- [ ] Basic voice command parsing (without full LLM yet)
- [ ] Voice-to-stock-update flow with confirmation screen
- [ ] Low-stock alert view
- [ ] Expiry date input and expiry alert view
- [ ] Text-to-speech response (Web Speech API)

**Milestone:** Shopkeeper can say "10 biscuit packets arrived" and confirm the update.

---

## Phase 3: Agentic AI Core — Week 4

**Goal:** Gemini function-calling agent working for inventory queries and restocking.

- [ ] Set up Gemini API integration with function calling
- [ ] Define and register tool functions (get_inventory_status, update_stock_quantity, etc.)
- [ ] Agent orchestration loop
- [ ] Confidence and clarification handling
- [ ] Human approval gate for purchases
- [ ] Restocking recommendation generation
- [ ] Budget-aware filtering of recommendations
- [ ] Audit log writing

**Milestone:** Agent can receive voice input, analyse inventory, and produce a restocking recommendation requiring shopkeeper approval.

---

## Phase 4: Offline Support — Week 5

**Goal:** App works without internet and syncs when back online.

- [ ] Set up Dexie.js for IndexedDB
- [ ] Service worker with Workbox (via vite-plugin-pwa)
- [ ] Offline write queue for stock updates
- [ ] Sync on reconnect with conflict detection
- [ ] Network status indicator in UI
- [ ] Offline-mode indicator and appropriate messaging

**Milestone:** Shopkeeper can update stock without internet, and it syncs automatically on reconnect.

---

## Phase 5: Polish and Demo Prep — Week 6

**Goal:** Demo-ready prototype suitable for hackathon judges.

- [ ] Complete Kannada and Hindi UI translations
- [ ] Product image display optimisation for low bandwidth
- [ ] Barcode scanner integration (@zxing/browser)
- [ ] Distributor delivery recording flow
- [ ] Festival demand estimate (simple calendar-based heuristic — clearly labelled as estimate)
- [ ] 7-day onboarding guide within app
- [ ] Error handling and loading states
- [ ] Mobile responsiveness testing on Android Chrome
- [ ] Demo data seeding for judges

**Milestone:** Fully demonstrable prototype on Android Chrome.

---

## Phase 6: Field Validation — After Hackathon

**Goal:** Test with actual kirana shopkeepers.

- [ ] Conduct shopkeeper interviews (using field_validation_plan.md)
- [ ] Recruit 3–5 pilot shops
- [ ] Deploy pilot version
- [ ] Collect usage data and feedback
- [ ] Iterate on most-used features
- [ ] Update documentation with real findings

---

## Phase 7: Pilot Launch — TBD

**Goal:** 10–50 real shops using the product.

- [ ] Production infrastructure setup
- [ ] Privacy policy and terms of service
- [ ] Support workflow
- [ ] Pricing and payment integration (UPI)
- [ ] Analytics (privacy-respecting)
- [ ] Proper Indian language voice pack testing on target devices

---

## 7-Day Onboarding Journey (In-App)

| Day | Milestone | Action |
|---|---|---|
| Day 1 | Language + 5 products added | Select language, add essential product list |
| Day 2 | First stock received | Record a distributor delivery |
| Day 3 | Voice update tried | Use voice to update at least one product |
| Day 4 | Low-stock alert viewed | App identifies a low-stock item |
| Day 5 | Stock movement tracked | 5+ movements recorded |
| Day 6 | Expiry check done | Review any expiring items |
| Day 7 | First AI recommendation | Receive and approve/modify first restock plan |

> **Note:** This timeline is aspirational. Useful insights require real data. If a shopkeeper has only one day of data, the first recommendation will be limited — this is communicated honestly.

---

## Risk Register

| Risk | Probability | Impact | Mitigation |
|---|---|---|---|
| Voice recognition fails on accented speech | Medium | High | Test on real devices, offer text fallback |
| Gemini API rate limits hit during demo | Low | High | Pre-load demo responses, implement queuing |
| Supabase free tier exceeded | Low | Medium | Monitor usage, upgrade before exceeding |
| Shopkeeper refuses to adopt new tool | Medium | High | Invest in onboarding UX, offer JanAI Café support |
| Product name matching fails for regional names | Medium | Medium | Build alias database from field research |
| Team capacity too low for all features | High | Medium | Prioritise core features, defer optional ones |

---

## MVP Feature Priority

**Must have for Demo:**
- Language selection
- Authentication
- Image-first dashboard
- Product add + inventory view
- Voice stock update
- Low-stock alerts
- Restocking recommendation (AI)
- Budget enforcement
- Shopkeeper approval gate

**Should have for Demo:**
- Expiry alerts
- Kannada + Hindi UI

**Nice to have (if time permits):**
- Barcode scanner
- Offline mode
- Distributor receiving flow
- Dead-stock analysis

**Future (post-hackathon):**
- Festival forecasting (data-driven)
- Online wholesale ordering
- Bill generation
- Group purchasing

---

*All timelines are estimates for a student team working part-time. Actual implementation velocity will determine what is achievable before the hackathon submission deadline.*
