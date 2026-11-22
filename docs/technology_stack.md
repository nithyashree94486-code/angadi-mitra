# Technology Stack — Angadi Mitra

> **Status:** Candidate technologies evaluated for future prototyping (Research & Architectural Planning Phase).  
> **Notice:** All technologies listed below represent **evaluated candidates** for future prototype development, not finalized implementation decisions. In accordance with the current hackathon evaluation stage, **no software packages, libraries, or framework dependencies have been installed or configured in this repository.**  
> **Last updated:** November 2026

---

## 1. Evaluation Criteria

For a student team planning a credible hackathon solution for small village stores, technology choices must balance feasibility, accessibility, cost, and robustness:

| Criterion | Priority | Rationale & Evaluation Target |
|---|---|---|
| **Beginner-friendliness** | High | Fast iteration speed for a small team with clean, maintainable patterns. |
| **Zero / Low-Cost Tier** | High | Must operate on accessible developer tiers without mandatory upfront cloud expenditure. |
| **Indian Language Breadth** | High | Multi-vernacular support (Kannada, Hindi, Tamil, Telugu, etc.) is a non-negotiable PS 5.1 requirement. |
| **Low-End Mobile Suitability** | High | Must run smoothly on entry-level Android devices (2GB–4GB RAM) with constrained processors. |
| **Offline Resilience** | High | Graceful degradation during intermittent rural network connectivity. |
| **Ecosystem & Documentation** | Medium | Strong community troubleshooting resources and mature libraries. |
| **Scalability Path** | Medium | Clear migration path from initial prototype to pilot deployments. |

---

## 2. Frontend Layer (Candidate Evaluation)

### Recommended Candidate: React + TypeScript + Vite (Progressive Web App)

- **Why React with Vite?**
  - **Ecosystem & Community:** React possesses the largest developer ecosystem with extensive UI libraries suitable for fast prototyping.
  - **Tooling Speed:** Vite provides significantly faster build and reload times than legacy bundlers (e.g., Create React App). [Vite Documentation](https://vite.dev/)
  - **Type Safety:** TypeScript enforces compile-time type verification, which is critical for deterministic inventory arithmetic and financial calculation safeguards. [TypeScript Documentation](https://www.typescriptlang.org/docs/)
  - **PWA Packaging:** Progressive Web App plugins (`vite-plugin-pwa`) allow Android home-screen installation without mandatory Google Play Store distribution, enabling lightweight footprint and offline asset caching via Service Workers. [Vite PWA Guide](https://vite-pwa-org.netlify.app/)

- **UI & Accessibility Components: Tailwind CSS + shadcn/ui**
  - Utility-first styling enables rapid creation of high-contrast, large touch-target buttons (minimum 48px height) essential for shopkeepers operating on low-brightness screens in sunlight. [Tailwind CSS Documentation](https://tailwindcss.com/)
  - Accessible unstyled primitives allow customized vernacular text scaling. [shadcn/ui Documentation](https://ui.shadcn.com/)

- **Multilingual Support: react-i18next**
  - Industry-standard internationalization library supporting dynamic language switching between Indian scripts without full page reloads. [react-i18next Documentation](https://react.i18next.com/)

- **Optional Barcode Scanning: @zxing/browser**
  - Client-side JavaScript barcode and QR decoding library utilizing the device's native camera stream without requiring external paid scanning SDKs. [ZXing Browser Repository](https://github.com/zxing-js/browser)

---

## 3. Backend & Data Layer (Candidate Evaluation)

### Recommended Candidate: Supabase (Managed PostgreSQL)

- **What is Supabase?**
  - Supabase is an open-source Backend-as-a-Service providing a managed PostgreSQL relational database, built-in phone/OTP authentication, file storage for product imagery, and real-time subscription capabilities. [Supabase Documentation](https://supabase.com/docs)

- **Why Evaluated for Angadi Mitra?**
  - **Relational Integrity:** PostgreSQL enforces strict schema constraints, foreign key validation, and relational consistency required for financial inventory ledgers and stock movement logs.
  - **Row Level Security (RLS):** Supabase RLS enforces multi-tenant data isolation directly at the database engine level, ensuring shopkeepers cannot access each other's stock or pricing records.
  - **Phone-Based Authentication:** Native support for SMS/OTP authentication aligns with rural Indian users who lack active email addresses.
  - **Flexible Storage (JSONB):** Native JSONB support enables storage of dynamic AI agent tool calls, reasoning traces, and audit recommendations alongside structured tabular inventory records.

- **Pricing & Free-Tier Notice:**
  - Supabase offers a Free tier intended for hobby and development projects. However, specific resource allowances (such as database size, storage limits, egress bandwidth, and project inactivity pausing policies) are governed by Supabase's published pricing and are subject to change over time.
  - *Source & Verification:* Always check the current live tiers directly at [Supabase Pricing Documentation](https://supabase.com/pricing) and [Supabase Project Status & Pausing Guidelines](https://supabase.com/docs/guides/platform/orgs-and-projects#project-status-and-pausing).

- **Alternatives Considered:**
  - *Firebase (Firestore):* Highly accessible, but its NoSQL document paradigm lacks native relational foreign keys and complex SQL aggregations required for rigorous inventory accounting.
  - *Custom Node.js / Express + self-hosted PostgreSQL:* Offers maximum flexibility but increases infrastructure setup overhead for a student hackathon team.

---

## 4. AI & Agent Orchestration (Candidate Evaluation)

### Recommended Candidate: Google Gemini API (Function Calling)

- **Why Google Gemini?**
  - **Native Function Calling:** Enables true Agentic AI behavior where the model deterministically selects registered tool APIs (`get_inventory_status`, `check_budget_headroom`, `generate_restock_plan`) and returns structured JSON arguments rather than hallucinated text. [Gemini Function Calling Guide](https://ai.google.dev/gemini-api/docs/function-calling)
  - **Indian Language Evaluation Target:** Language suitability across Indian languages—including Kannada, Hindi, Tamil, and Telugu—cannot be assumed uniformly and must be evaluated individually through actual testing on localized retail vocabulary.
  - **Large Context Window:** Extensive context capacity (up to 1,048,576 input tokens) enables ingestion of comprehensive product catalogs, seasonal sales histories, and local product alias dictionaries in a single analytical turn. [Gemini Models Overview](https://ai.google.dev/gemini-api/docs/models/gemini)

- **Evaluated Model Candidate (Current Generation):**
  - **`gemini-3.8-flash` (Primary Recommended Candidate):** Google's high-efficiency multimodal model evaluated for low latency, high throughput, and robust Agentic AI tool use. [Google AI Studio Models Documentation](https://ai.google.dev/gemini-api/docs/models/gemini)
  - **Function-Calling & Tool Support:** Official model documentation specifies native support for structured function calling, allowing the model to deterministically output verified JSON arguments for registered inventory APIs (`get_inventory_status`, `check_budget_headroom`, `generate_restock_plan`). [Gemini Function Calling Guide](https://ai.google.dev/gemini-api/docs/function-calling)
  - **Context Window:** Supports a 1,048,576-token input context window according to official documentation, enabling ingestion of complete store inventories, historical purchase records, and regional dialect alias tables in a single conversational session. [Gemini Models Overview](https://ai.google.dev/gemini-api/docs/models/gemini)
  - **Latency & Performance Measurement:** While designed for fast execution, conversational response times are not guaranteed, and actual end-to-end latency must be empirically measured during future testing on realistic rural mobile networks and constrained devices.
  - **Indian Language Suitability:** Practical comprehension and generation across Indian languages—including Kannada, Hindi, Tamil, and Telugu—must be evaluated individually through actual testing on localized shopkeeper speech, regional vocabulary, and colloquial product aliases rather than assumed broadly.
  - **Status & Integration Notice:** In accordance with project rules, `gemini-3.8-flash` is an **evaluated proposed candidate** for future prototype development. It has **not** been integrated, API-configured, or tested in software at this stage.
  - *Source & Verification:* Verify current model availability, technical specifications, and lifecycle schedules directly at [Google AI Studio Models Documentation](https://ai.google.dev/gemini-api/docs/models/gemini).

- **Pricing & Free-Tier Quotas Notice:**
  - Google AI Studio provides a free-of-charge tier designed for evaluation and prototyping, alongside pay-as-you-go paid tiers.
  - Free-tier rate limits (Requests Per Minute - RPM, Tokens Per Minute - TPM, and Requests Per Day - RPD) are dynamically managed and vary by model and region. In the free tier, input/output data may be utilized to improve Google products, whereas paid tiers offer data privacy without training usage.
  - Quotas, token pricing, and model availability change frequently; developers must not rely on outdated static numbers.
  - *Source & Verification:* Verify current quotas, rate limits, and model pricing directly at [Google AI Studio Pricing](https://ai.google.dev/pricing) and [Gemini API Rate Limits Documentation](https://ai.google.dev/gemini-api/docs/rate-limits).

- **Alternatives Considered:**
  - *OpenAI API (GPT-4o / GPT-4o-mini):* Strong function-calling support, but evaluated as having higher operational costs at scale and less generous free experimentation tiers.
  - *LangChain / LlamaIndex Frameworks:* Useful abstraction layers for complex multi-agent workflows, but evaluated as introducing unnecessary runtime complexity for the initial hackathon scope. Direct API function calling is recommended for transparency and deterministic debugging.

---

## 5. Voice Interaction: Speech-to-Text (STT)

### Candidate Tier 1: Client-Side Web Speech API (`SpeechRecognition`)

- **What it is:** A browser-native JavaScript interface allowing web applications to capture audio input and receive speech-recognition transcripts. [MDN Web Speech API Documentation](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API)

- **Device, Browser, and Language Dependencies (Important Realities):**
  - **No Universal Browser Support:** The `SpeechRecognition` interface is primarily implemented in Chromium-based browsers (Google Chrome, Microsoft Edge) via the vendor-prefixed `webkitSpeechRecognition`. It is **not** supported natively in mobile Firefox or Safari on iOS without third-party polyfills.
  - **Platform Service Dependency:** In Chrome on Android, recognition is **not** performed by standalone browser code. The browser delegates recognition to the underlying OS speech engine (e.g., Google Speech Services).
  - **No Guaranteed Indian Language Availability:** While language codes such as `hi-IN` (Hindi), `kn-IN` (Kannada), `ta-IN` (Tamil), etc., are supported by Google Speech Services, actual functionality on an end-user device depends strictly on:
    1. Whether Google Speech Services is installed, enabled, and updated on the Android phone.
    2. Whether an offline language pack has been downloaded to the device by the user, or whether an active, low-latency internet connection is available to stream audio to Google servers.
    3. Low-end smartphone hardware: Inexpensive Android devices frequently feature low-quality microphones and aggressive OEM battery/memory managers that terminate audio capture unexpectedly.
  - **Architectural Conclusion:** The Web Speech API represents a high-convenience, zero-cost **progressive enhancement**, but **cannot be treated as a guaranteed input modality**. The UI must always provide tactile touch buttons and manual fallback inputs.

### Candidate Tier 2: Google Cloud Speech-to-Text (Server-Side Cloud Fallback)

- **When to Use:** Evaluated as an enhanced fallback for production scenarios where client-side browser recognition fails, or when custom vocabulary and background noise suppression are required in noisy rural bazaar environments.
- **Verified Indian Language Locales (from Google Cloud Documentation):**
  - Hindi (`hi-IN`), Kannada (`kn-IN`), Tamil (`ta-IN`), Telugu (`te-IN`), Bengali (`bn-IN`), Malayalam (`ml-IN`), Marathi (`mr-IN`), Gujarati (`gu-IN`), Punjabi (`pa-IN`), Urdu (`ur-IN`).
  - *Source & Verification:* Verify current language codes and transcription features at [Google Cloud STT Supported Languages](https://cloud.google.com/speech-to-text/docs/speech-to-text-supported-languages).
- **Pricing & Quotas Notice:**
  - Billed on a per-second audio transcription basis, with promotional free allowances available for new Google Cloud accounts. Specific rate cards are subject to change.
  - *Source & Verification:* Consult [Google Cloud Speech-to-Text Pricing](https://cloud.google.com/speech-to-text/pricing).

---

## 6. Voice Interaction: Text-to-Speech (TTS)

### Candidate Tier 1: Client-Side Web Speech API (`SpeechSynthesis`)

- **What it is:** Browser-native interface used to speak text aloud using synthesized speech voices installed on the operating system. [MDN SpeechSynthesis Documentation](https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis)
- **Dependencies & Limitations:**
  - Voice naturalness and language availability are entirely dependent on the specific voices installed on the user's Android phone.
  - While Hindi voices are widely present on modern Android devices, regional language voices (such as Kannada or Telugu) are often absent unless explicitly installed by the user in Android Text-to-Speech settings.

### Candidate Tier 2: Google Cloud Text-to-Speech (Cloud Audio Synthesis)

- **When to Use:** Evaluated as the reliable source for natural-sounding spoken audio feedback in regional Indian languages.
- **Verified Indian Language Coverage (from Google Cloud Documentation):**
  - Supports Hindi (`hi-IN`), Kannada (`kn-IN`), Tamil (`ta-IN`), Telugu (`te-IN`), Bengali (`bn-IN`), Malayalam (`ml-IN`), Marathi (`mr-IN`), Gujarati (`gu-IN`), Punjabi (`pa-Guru-IN`), and Urdu (`ur-IN`).
  - Voice tiers range across Standard, WaveNet, and Neural2 models with varying acoustic naturalness.
  - *Source & Verification:* Inspect available voices, genders, and audio sample previews at [Google Cloud TTS Voice List](https://cloud.google.com/text-to-speech/docs/voices).
- **Pricing Notice:**
  - Cloud TTS pricing is based on character volume synthesized per month, segmented by voice tier (Standard vs. Neural2/WaveNet).
  - *Source & Verification:* Check active pricing tables at [Google Cloud Text-to-Speech Pricing](https://cloud.google.com/text-to-speech/pricing).

### Additional Vernacular Services Evaluated:
- **Microsoft Azure AI Speech:** Evaluated as an enterprise alternative providing neural speech synthesis across Indian locales. [Azure Speech Language Support](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/language-support)
- **Karya Language Solutions:** Evaluated for domain-specific Indian vernacular datasets and regional dialect nuances. [Karya Documentation](https://languageserver.karya.in/documentation/text_to_speech/)

---

## 7. Offline Storage & Synchronization

### 7.1 Verified Browser Capabilities (Technical Reality)

| Capability | Browser Support Status | Practical Application in Angadi Mitra |
|---|---|---|
| **IndexedDB via Dexie.js** | ✅ Widely supported across modern browsers, subject to browser-specific storage limits and platform restrictions. | Provides reliable client-side transactional storage. Can cache thousands of inventory records, product image URLs, regional aliases, and local mutation queues. [Dexie.js Documentation](https://dexie.org/) |
| **Cache API & Service Workers** | ✅ Widely supported in modern browsers that support the relevant PWA capabilities. | Caches HTML, CSS, JavaScript bundles, and static UI icons so the application loads instantly even when completely disconnected from cellular networks. [MDN Cache API Documentation](https://developer.mozilla.org/en-US/docs/Web/API/Cache) |
| **Network Status Detection** | ✅ Standard `navigator.onLine` and event listeners. | Provides baseline network presence indication, supplemented with lightweight application ping endpoints to detect captive portals or zero-bandwidth cellular drops. |

### 7.2 Proposed Design vs. Browser Limitations

- **Background Sync API (`SyncManager`):**
  - *Proposed Workflow:* When offline, stock adjustments are written to a local `pending_mutations` IndexedDB table. A Background Sync registration (`sync.register('sync-inventory')`) attempts to replay updates to the backend when connectivity returns.
  - *Verified Platform Limitation:* The [W3C Background Synchronization API](https://developer.mozilla.org/en-US/docs/Web/API/Background_Synchronization_API) is supported in Chromium-based browsers on Android, but is **not supported on Apple Safari / iOS** or desktop Firefox. Furthermore, on Android, execution frequency is subject to OS battery optimization policies.
  - *Fallback Design:* In browsers without native Background Sync, Angadi Mitra proposes an in-app sync loop triggered whenever the web page detects an active `online` event or user interaction.

- **Offline Behavior & Storage Testing Requirement:**
  - Actual offline behavior, local storage persistence, quota eviction thresholds, and synchronization reliability cannot be assumed from desktop specifications and require empirical validation through hands-on testing on target entry-level Android devices and varied mobile browsers.

- **Offline AI Processing Reality:**
  - Complex Agentic AI analysis (e.g., generating multi-item restocking recommendations via Gemini) **requires an active internet connection** to communicate with cloud inference endpoints.
  - *Proposed Graceful Degradation:* When offline, the app displays the last cached AI recommendation. Dynamic stock balance updates and low-stock threshold badges continue functioning offline using deterministic local JavaScript logic.

- **Conflict Resolution Strategy (Proposed):**
  - For single-shopkeeper stores, data conflicts are rare. If a conflict occurs upon reconnecting (e.g., stock was adjusted from two devices), the system proposes a deterministic **timestamp-based last-write-wins** approach, with an audit log notification presented to the shopkeeper for transparency.

---

## 8. Summary of Technology Recommendations

| Architecture Layer | Proposed Candidate | Role in Solution | Official Reference URL |
|---|---|---|---|
| **Frontend Framework** | React 18+ & TypeScript | Reactive, type-safe mobile UI | [https://react.dev/](https://react.dev/) |
| **Build Tool** | Vite | Ultra-fast development & PWA bundling | [https://vite.dev/](https://vite.dev/) |
| **Styling** | Tailwind CSS + shadcn/ui | High-contrast, accessible touch components | [https://tailwindcss.com/](https://tailwindcss.com/) |
| **PWA Engine** | `vite-plugin-pwa` (Workbox) | Offline caching & installability | [https://vite-pwa-org.netlify.app/](https://vite-pwa-org.netlify.app/) |
| **Localization** | `react-i18next` | Multi-vernacular Indian language strings | [https://react.i18next.com/](https://react.i18next.com/) |
| **Local Storage** | Dexie.js (IndexedDB) | Client-side offline database | [https://dexie.org/](https://dexie.org/) |
| **Backend & DB** | Supabase (PostgreSQL) | Multi-tenant database & OTP Auth | [https://supabase.com/](https://supabase.com/) |
| **AI Agent** | Google Gemini (Candidate: `gemini-3.8-flash`) | Agentic planning & tool function calling | [https://ai.google.dev/](https://ai.google.dev/) |
| **Voice STT (Primary)** | Web Speech API | Client-side speech recognition | [https://developer.mozilla.org/](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API) |
| **Voice STT (Enhanced)** | Google Cloud Speech-to-Text | Verified server-side vernacular speech | [https://cloud.google.com/speech-to-text](https://cloud.google.com/speech-to-text) |
| **Voice TTS (Enhanced)** | Google Cloud Text-to-Speech | Verified Indian regional voice synthesis | [https://cloud.google.com/text-to-speech](https://cloud.google.com/text-to-speech) |

---

## 9. Technologies Explicitly Avoided & Why

| Technology | Reason for Exclusion at this Stage |
|---|---|
| **Native Android (Java / Kotlin)** | Higher development time and rigid store update cycles compared to a nimble Progressive Web App. |
| **Self-Hosted LLMs (Llama, Mistral)** | Infeasible on low-end mobile hardware without dedicated GPU infrastructure; high operational cost. |
| **NoSQL Database (MongoDB / DynamoDB)** | Lacks native ACID transaction guarantees and relational schema enforcement needed for financial ledgers. |
| **Complex Multi-Agent Frameworks (CrewAI, AutoGen)** | Introduces unnecessary abstraction overhead; direct Gemini API function calling provides superior determinism and traceability. |
| **Heavy Desktop ERP Frameworks (Electron, SAP, Odoo)** | Incompatible with low-end mobile phones and rural shopkeeper usability realities. |

---

*This document is a research-backed technology evaluation prepared for the Tech4Bharat 2026 hackathon documentation portfolio. All technology decisions remain proposed recommendations subject to practical validation during future prototyping phases.*
