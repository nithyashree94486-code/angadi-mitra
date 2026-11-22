# Presentation Content — Angadi Mitra
## Tech4Bharat 2026 | 9-Slide Pitch Outline

> **Status:** Content outline prepared. Final slide deck to be created separately.
> **Last updated:** November 2026

---

## Slide 1: Title and Team Introduction

**Slide Title:** Angadi Mitra — ಅಂಗಡಿ ಮಿತ್ರ

**Slide Content:**
> *Making everyday kirana management simpler through technology.*

- **Hackathon:** Tech4Bharat 2026 — JanAI Mass Entrepreneurship Challenge
- **Problem Statement:** PS 5.1 — Kirana Stock
- **Theme:** Theme 5 — Rural FMCG and Logistics
- **AI Approach:** Agentic AI

**Contributors:**
- Nithyashree H L — [https://github.com/nithyashree94486-code](https://github.com/nithyashree94486-code)
- Pooja Achar — [https://github.com/pooja132a79450](https://github.com/pooja132a79450)

**Suggested Visual:**
A warm, clean illustration of a kirana store shopkeeper holding a smartphone. The app interface is visible showing colourful product cards. Text in Kannada and Hindi visible in the background.

---

**Speaker Notes:**
"Angadi Mitra — which means 'Shop Friend' in Kannada — is our proposed solution to PS 5.1: Kirana Stock. We're building an agentic AI inventory assistant designed specifically for India's 12 million small kirana stores, in their own language, on the phones they already own."

---

## Slide 2: Problem Statement — The Real Challenges

**Slide Title:** The Kirana Stock Problem — Invisible but Costly

**Slide Content (Problem figures from PS 5.1 — verify against official PDF):**

🔴 **Stock tracked through memory and shelf checks**
- No billing system → no data → no insights

🔴 **Fast-moving items go out of stock**
- Lost sales, disappointed customers

🔴 **Dead stock freezes 15–20% of working capital**
- Money tied up in products nobody buys

🔴 **Expiry losses estimated at ₹5,000–₹10,000 per month**
- Perishables spoil before being sold

🔴 **Festival demand is guessed, not planned**
- Miss the biggest sales opportunities of the year

🔴 **Distributor visits drive purchasing — not data**
- Shopkeeper has no leverage or insight

> *Figures from Tech4Bharat 2026 PS 5.1 — verify against official document.*

**Suggested Visual:**
Split panel: Left — a shelf with dusty products and a "Sold Out" sign. Right — a notebook with illegible handwritten inventory. Statistics overlaid as bold callouts.

---

**Speaker Notes:**
"These are not hypothetical problems. The PS 5.1 problem statement describes them as everyday realities for India's small shopkeepers. They are managing stock through memory — with no data to tell them what's selling, what's expiring, or what they should buy next. And the losses are real: money tied up, money lost to expiry, money lost to stockouts."

---

## Slide 3: Target Users and Existing Practices

**Slide Title:** Who We're Building For

**Slide Content:**

**Primary User:** Small kirana / provision store owner
- Runs the shop alone or with family
- Likely uses a mid-range or low-end Android phone
- Prefers their local language
- May be first-time digital user
- Has intermittent internet connectivity

**Current Practices:**
| Task | How it's done today |
|---|---|
| Stock tracking | Memory + visual shelf check |
| Deciding what to buy | Distributor visit + gut feeling |
| Expiry monitoring | Manual check, often forgotten |
| Pricing | Mental arithmetic |
| Billing | Manual or not at all |

**What they need — not a complicated ERP:**
> "I want to know what's running low, what's not selling, and what I should buy this week — without spending an hour learning software."

**Suggested Visual:**
A realistic sketch or photograph of a typical kirana store counter. Annotation arrows pointing to: "Memory-based stock", "No barcode scanner", "Local language labels", "Low-end phone in pocket".

---

**Speaker Notes:**
"Our target user is not a tech-savvy entrepreneur. They are a shopkeeper who may have never used an inventory app before, may prefer Kannada or Hindi over English, and needs to see value within days — not weeks — of adoption."

---

## Slide 4: Proposed Solution — Angadi Mitra

**Slide Title:** Angadi Mitra — Your Shop's Digital Friend

**Slide Content:**

A **multilingual, image-first, voice-assisted Agentic AI** inventory assistant for kirana stores.

**What makes it different:**
| Feature | What it means for the shopkeeper |
|---|---|
| 🌐 Multilingual | Use it in Kannada, Hindi, or other Indian languages |
| 🎙️ Voice-first | "10 biscuit packets arrived" — just say it |
| 🖼️ Image-first | See your products, not rows of numbers |
| 🤖 Agentic AI | Analyses stock, spots risks, suggests purchases |
| 💵 Budget-aware | Never overspends your chosen cash budget |
| ✅ You approve | AI suggests — you decide — always |
| 📱 Offline-capable | Works even with bad connectivity |

**Core Promise:** Deliver useful insights within the first 7 days — even with no prior records.

**Suggested Visual:**
App mockup showing three screens: (1) Visual dashboard with product images. (2) Voice command interface with Kannada text. (3) Restocking recommendation card with ₹ budget meter.

---

**Speaker Notes:**
"Angadi Mitra is not just another billing app with a new name. It's designed around how a kirana shopkeeper actually works — through voice, through images, in their own language. And unlike an ERP, it doesn't require training or a data entry person. The shopkeeper just talks to it."

---

## Slide 5: Core Features and 7-Day User Journey

**Slide Title:** Features That Deliver Value Fast

**Slide Content:**

**7-Day Onboarding Journey:**

| Day | Activity | Value Delivered |
|---|---|---|
| 1 | Select language + add 5 products | Personalised start |
| 2 | Record distributor delivery | First stock record |
| 3 | Voice update: "5 soaps arrived" | Effortless data entry |
| 4 | See first low-stock alert | Actionable insight |
| 5 | Track 5+ stock movements | Velocity data building |
| 6 | Review expiry alert | Money saved on waste |
| 7 | First AI restocking suggestion | Budget-aware purchase plan |

**Key Feature Summary:**
- Low-stock, out-of-stock, expiry alerts
- Dead-stock and slow-mover identification
- Fast-moving product tracking
- Budget-aware restocking plan
- Regional product names and aliases
- Barcode + image + voice product identification

**Suggested Visual:**
A horizontal timeline (Day 1 → Day 7) with icons for each day's activity. Each milestone has a small illustrative icon.

---

**Speaker Notes:**
"The seven-day journey is designed to deliver real value from day one, even if the shopkeeper has never used software before. By day seven, they have enough data for the AI to generate a meaningful first restocking recommendation — within their budget."

---

## Slide 6: Agentic AI Architecture and Workflow

**Slide Title:** Genuine Agentic AI — Not Just a Chatbot

**Slide Content:**

```
Shopkeeper says: "What should I buy? I have ₹3,000."
        ↓
Agent understands: "generate_restock_plan, budget=3000"
        ↓
Agent calls tools:
  • get_low_stock_alerts()
  • get_fast_moving_stock()
  • get_expiry_alerts()
  • check_budget_headroom(3000)
        ↓
Deterministic engine: arithmetic, budget validation
        ↓
Agent explains: "I suggest these 8 products (₹2,840 total) because..."
        ↓
Shopkeeper reviews and approves
        ↓
Recommendation saved — NEVER spent without approval
```

**Three-Layer Separation:**
| Layer | Responsibility |
|---|---|
| LLM (Gemini) | Understand, plan, explain |
| Deterministic Code | Arithmetic, budget checks |
| Human | Approve every purchase |

**Suggested Visual:**
A clean flowchart (from the agentic_ai_workflow.md Mermaid diagram) showing the agent loop with the human approval gate highlighted.

---

**Speaker Notes:**
"This is a true agentic workflow — the AI doesn't just answer questions, it uses tools to fetch real inventory data, runs deterministic budget checks, plans a sequence of actions, and then stops to ask the shopkeeper before doing anything consequential. The AI never spends money autonomously. Never."

---

## Slide 7: Technology Stack and Feasibility

**Slide Title:** A Practical Stack for a Student Team

**Slide Content:**

| Layer | Technology | Why |
|---|---|---|
| Frontend | React + TypeScript + Vite | Ecosystem, speed, PWA |
| UI | Tailwind CSS + shadcn/ui | Rapid, accessible |
| Backend & DB | Supabase (PostgreSQL) | Managed, free tier, RLS |
| Auth | Supabase Auth (OTP) | Phone-based, no email |
| AI Agent | Google Gemini (evaluating gemini-3.8-flash) | Indian languages, function calling |
| Voice (STT) | Web Speech API + Cloud STT | Free + verified Indian language |
| Voice (TTS) | Web Speech API + Cloud TTS | Hindi, Kannada, Tamil verified |
| Offline | IndexedDB (Dexie.js) + PWA | Local-first, sync on reconnect |
| Hosting | Vercel | Free tier, instant deploy |

**Indian Language Voice Coverage (verified):**
Hindi ✅ | Kannada ✅ | Tamil ✅ | Telugu ✅ | Bengali ✅ | Malayalam ✅ | Marathi ✅ | Gujarati ✅

> Source: Google Cloud STT/TTS documentation — verify current support before submission.

**Suggested Visual:**
A clean architecture diagram showing layers (Frontend → Backend → Database → AI Services) with technology logos.

---

**Speaker Notes:**
"Our stack is chosen for two things: beginner-friendliness for a student team, and genuine technical credibility. Supabase gives us a managed PostgreSQL database with privacy controls. Gemini gives us function-calling agentic AI with strong Indian language support. And the whole thing runs as a PWA — installable on any Android device, even offline."

---

## Slide 8: Differentiation, Impact and Business Model

**Slide Title:** Why Angadi Mitra — Impact and Sustainability

**Slide Content:**

**Competitor Landscape:**
| Product | Inventory | Voice | Multilingual | Village-first | Agentic AI |
|---|---|---|---|---|---|
| Vyapar | ✅ | ❌ | Hindi + limited | ❌ Urban | ❌ |
| Khatabook | Khata only | ❌ | Hindi + limited | ❌ Urban | ❌ |
| myBillBook | ✅ | ❌ | Limited | ❌ Urban | ❌ |
| GoFrugal | ✅ Advanced | ❌ | English + limited | ❌ Enterprise | ❌ |
| **Angadi Mitra** | ✅ | ✅ | 8+ Indian lang | ✅ **Core focus** | ✅ |

> *Competitor table based on publicly available product information. Some features not verified — see competitor_analysis.md.*

**Proposed Impact:**
- Target: India's 12 million+ kirana stores
- Potential reduction in expiry losses (to be validated)
- Potential improvement in stockout rate (to be validated)
- Accessible to first-time digital users

**Business Model:**
- Free tier (up to 100 products)
- Angadi Pro: ₹99–₹199/month
- Future: Distributor insights, wholesale commission (proposed)

**Suggested Visual:**
A differentiation radar chart or feature comparison table. Impact metrics as large-number callouts.

---

**Speaker Notes:**
"Existing apps serve urban, literate shopkeepers who already have billing systems. Angadi Mitra is designed for the other end of the market — village-level stores with no existing software, in their own language, with voice and images as the primary interaction. That's our differentiation: not just inventory software, but accessible agentic AI for India's smallest retailers."

---

## Slide 9: Roadmap, Validation Plan and Conclusion

**Slide Title:** Next Steps — From Foundation to Pilot

**Slide Content:**

**Current Status:**
✅ Research complete | ✅ Architecture designed | ✅ Documentation ready | ✅ Repository set up

**6-Week Development Roadmap:**
- Week 1–2: Core prototype (auth, inventory, dashboard)
- Week 3: Voice integration and alerts
- Week 4: Agentic AI core (Gemini + function calling)
- Week 5: Offline mode and sync
- Week 6: Polish and demo preparation

**Field Validation Plan:**
- Conduct 8–12 shopkeeper interviews (plan prepared)
- Usability testing with prototype
- Pilot with 3–5 real shops

**What We're Not Claiming:**
- ✗ Not claiming implementation is complete
- ✗ Not claiming forecasts are accurate predictions
- ✗ Not claiming partnerships are confirmed
- ✗ Not claiming validation has been conducted

**What We Are Claiming:**
- ✅ The problem is real and significant
- ✅ The architecture is technically sound
- ✅ The approach is genuinely agentic
- ✅ The stack is practical and feasible
- ✅ The design is built for Indian villages, not urban India

**Closing:**
> *"Every kirana store owner deserves a shop friend — in their own language, within their budget, on their own terms."*

**Suggested Visual:**
A roadmap timeline + a warm closing image of a shopkeeper successfully using the app. QR code linking to the GitHub repository.

---

**Speaker Notes:**
"We're not claiming we've built this yet. We're claiming we have a technically sound, well-researched foundation for something that could genuinely change how India's smallest shopkeepers manage their stock. We're asking for the opportunity to build it, validate it in the field, and get it into the hands of the people who need it most."

---

## Presentation Design Tips

- **Font sizes:** Minimum 24pt for body text — judges may view from a distance
- **Contrast:** Dark text on light background, or vice versa — no busy backgrounds
- **Language:** Use local script on title slides (ಅಂಗಡಿ ಮಿತ್ರ, अंगड़ी मित्र)
- **Numbers:** Round numbers for impact — exact figures on documentation
- **Colour palette:** Warm saffron/green tones (Indian market feel) + clean white
- **Images:** Real kirana store photos (Creative Commons or original) if available
- **Avoid:** Bullet-point-only slides, tiny fonts, unexplained acronyms, claims without sources

---

*This is a 9-slide outline. Actual slides to be created in Google Slides or Canva.*
