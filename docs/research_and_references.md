# Research & References — Angadi Mitra

## Tech4Bharat 2026 | PS 5.1 – Kirana Stock | Theme 5 – Rural FMCG & Logistics

> **Status:** Research foundation compiled from official documentation, cloud platform specifications, competitor disclosures, and public technical literature.

---

## 1. Official Hackathon Documentation

| Reference | URL | Supported Information | Source Type |
|---|---|---|---|
| **Tech4Bharat 2026 Problem Statements PDF** | [https://thegavshackathon.com/docs/Tech4Bharat-2026-Problem-Statements.pdf](https://thegavshackathon.com/docs/Tech4Bharat-2026-Problem-Statements.pdf) | Page 3: Challenge-wide accessibility, vernacular, low-bandwidth, and JanAI Café guidelines. Page 13: PS 5.1 Kirana Stock specific requirements, metrics (15–20% dead stock, ₹5,000–₹10,000 expiry losses), and 7-day value constraint. | Primary Official Document |
| **Tech4Bharat Official Portal** | [https://thegavshackathon.com](https://thegavshackathon.com) | Challenge timelines, theme definitions (Theme 5: Rural FMCG & Logistics), and submission guidelines. | Primary Portal |

---

## 2. Indian Language Speech & Voice Technologies

| Technology / Service | Documentation URL | Supported Capabilities & Verification Notes | Source Type |
|---|---|---|---|
| **Google Cloud Text-to-Speech (TTS)** | [https://docs.cloud.google.com/text-to-speech/docs/list-voices-and-types](https://docs.cloud.google.com/text-to-speech/docs/list-voices-and-types) | Verified Indian language voices: Hindi (`hi-IN`), Kannada (`kn-IN`), Tamil (`ta-IN`), Telugu (`te-IN`), Bengali (`bn-IN`), Malayalam (`ml-IN`), Marathi (`mr-IN`), Gujarati (`gu-IN`), Punjabi (`pa-Guru-IN`), Urdu (`ur-IN`). Offers Neural2 and Standard voice models. | Official Cloud Docs |
| **Google Cloud Speech-to-Text (STT)** | [https://cloud.google.com/speech-to-text/docs/speech-to-text-supported-languages](https://cloud.google.com/speech-to-text/docs/speech-to-text-supported-languages) | Verified speech recognition support for major Indian languages with regional punctuation and transcription. | Official Cloud Docs |
| **Microsoft Azure AI Speech** | [https://learn.microsoft.com/en-us/azure/ai-services/speech-service/language-support](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/language-support) | Multilingual neural voice models for Indian locales including Hindi, Kannada, Tamil, Telugu, and others. Evaluated as an alternative enterprise candidate. | Official Cloud Docs |
| **Karya Language Solutions** | [https://languageserver.karya.in/documentation/text_to_speech/](https://languageserver.karya.in/documentation/text_to_speech/) | Indian language-focused crowdsourced dataset and speech engine documentation. Evaluated as an India-centric vernacular speech reference. | Technical Documentation |
| **W3C Web Speech API Specification** | [https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API) | Browser-native `SpeechRecognition` and `SpeechSynthesis` interfaces utilized for zero-cost, client-side offline audio input/output in Chromium-based Android browsers. | Standard Specification |

> **Verification Note:** Not all Indian languages possess identical synthesis naturalness or transcription accuracy. In Angadi Mitra, language availability is dynamically checked, falling back gracefully to high-contrast visual confirmation screens.

---

## 3. Agentic AI & Orchestration Frameworks

| Concept / Technology | Documentation Reference | Relevance to Angadi Mitra | Source Type |
|---|---|---|---|
| **Google Gemini Function Calling** | [https://ai.google.dev/gemini-api/docs/function-calling](https://ai.google.dev/gemini-api/docs/function-calling) | Enables Gemini (evaluating gemini-3.8-flash) to autonomously select registered tool APIs (`get_inventory_status`, `check_budget_headroom`) while emitting structured JSON arguments. | Official AI Documentation |
| **Deterministic Safeguard Separation** | Academic & Industry Best Practices in Safe Agentic Systems | Ensures LLM hallucinations cannot alter financial totals or corrupt stock math; all state updates pass through deterministic TypeScript logic. | Architectural Methodology |
| **Human-in-the-Loop (HITL) Gateways** | Responsible AI Principles | Establishes mandatory shopkeeper approval before consequential actions (purchases, bulk updates), prohibiting autonomous money spending. | Safety Architecture |

---

## 4. Competitor & Market Research References

| Competitor | Primary Website / Documentation | Features Reviewed & Verified |
|---|---|---|
| **Vyapar** | [https://vyaparapp.in/](https://vyaparapp.in/) | Desktop/mobile GST invoicing, barcode billing, inventory tracking. No native voice-first or agentic restocking. |
| **myBillBook** | [https://mybillbook.in/](https://mybillbook.in/) | Cloud-based billing and inventory for small retailers. Desktop/mobile focus, billing-dependent stock deduction. |
| **Khatabook** | [https://khatabook.com/](https://khatabook.com/) | Digital udhaar (customer debt ledger) and payment reminders. Multi-language ledger, but lacks AI stock restocking or expiry workflows. |
| **GoFrugal** | [https://www.gofrugal.com/](https://www.gofrugal.com/) | Advanced multi-store retail ERP, batch/expiry tracking. Enterprise-grade, complex for village stores. |
| **Marg ERP** | [https://margcompusoft.com/](https://margcompusoft.com/) | Comprehensive FMCG/Pharma distributor accounting and stock software. Windows-centric, distributor-oriented. |
| **BharatPe** | [https://bharatpe.com/](https://bharatpe.com/) | Merchant QR payments and working capital lending. Payment-centric ecosystem, not an inventory intelligence system. |

---

## 5. Mobile Web & Offline Engineering Standards

| Technology | Documentation Reference | Relevance |
|---|---|---|
| **Progressive Web Apps (PWA)** | [https://web.dev/progressive-web-apps/](https://web.dev/progressive-web-apps/) | Architecture allowing installable Android experiences without Google Play Store packaging, enabling instant updates and offline service workers. |
| **Dexie.js (IndexedDB)** | [https://dexie.org/](https://dexie.org/) | Reactive local-first browser storage wrapper for caching inventory items and queuing offline mutations during network dropouts. |
| **Supabase PostgreSQL & RLS** | [https://supabase.com/docs](https://supabase.com/docs) | Managed relational database providing Row Level Security (RLS) to enforce shopkeeper data isolation. |
