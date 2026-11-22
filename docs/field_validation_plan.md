# Field Validation Plan — Angadi Mitra

> **Status:** Proposed plan — no field research has yet been conducted.
> All content below is a planned methodology, not reported results.
> **Last updated:** November 2026

---

## 1. Purpose

Before building a product for kirana shopkeepers, we must understand their real practices, needs, and constraints. This document defines how we propose to conduct field research.

**Goal:** Validate that Angadi Mitra's proposed features address real shopkeeper needs in the right way.

---

## 2. Target Research Participants

| Type | Description | Sample Size (Target) |
|---|---|---|
| Village kirana owners | Store serving 50–300 households in rural areas | 5–8 |
| Small town kirana owners | Store in a town of 5,000–50,000 | 3–5 |
| Provision store owners | Mixed goods store in semi-urban area | 2–3 |
| Regular shopkeepers with some digital use | Already using UPI or basic phone apps | 2–3 |

**Selection criteria:**
- No existing inventory or billing software (or minimal use)
- Willing to participate in a 30–45 minute interview
- Consenting adults (no minors)

---

## 3. Ethical and Privacy Principles

- All participation is voluntary and can be stopped at any time
- No personal information is recorded without explicit consent
- Shop names and locations are not published without permission
- No photographs of financial documents, bills, or sensitive records
- No customer personal data is collected
- Interview notes are stored securely and not shared

---

## 4. Interview Questions — Shopkeeper Interviews

### Section A: Current Stock Management Practices

1. How do you currently keep track of which products you have in stock?
2. Do you write anything down, or do you rely on memory?
3. How often do you check your shelves to understand what you need?
4. How do you decide when it is time to reorder a product?
5. Have you ever run out of a product that was selling well? What happened?
6. Have products ever gone unsold and expired in your shop? How often?
7. How much do you think you lose per month because of expired products? (Rough estimate)
8. Do you feel your money is sometimes stuck in products that are not selling? Can you give an example?

### Section B: Distributor and Purchasing Practices

9. How do distributors usually come to your shop? Do they visit, or do you call them?
10. How do you decide what to buy when a distributor visits?
11. Do you have a fixed budget for buying stock each week or month?
12. If a distributor suggests a new product, how do you decide whether to buy it?
13. Do you get credit from distributors? How does that work?
14. How do you keep track of what you owe to distributors?

### Section C: Product Names and Records

15. Do customers ask for products by brand name or by a local name? Can you give examples?
16. Are there products that go by different names in different communities or seasons?
17. Do you have any existing records — bills, notebooks, or lists? Can I see the kind of information recorded? (Do not photograph without consent)

### Section D: Technology and Device Access

18. Do you have a smartphone? What kind? (Android/iPhone, rough idea of age)
19. How do you use your phone for the shop? (UPI payments, WhatsApp orders, anything else)
20. Is there stable internet connectivity in your area? Or does it come and go?
21. Have you used any app for the shop before? What was your experience?
22. What is the main reason you haven't used inventory software before?

### Section E: Language Preferences

23. Which language do you prefer to use for reading and writing?
24. If an app spoke to you in [local language], would that make it easier to use?
25. Would you be comfortable using voice commands to update stock, or do you prefer tapping buttons?

### Section F: Trust and Privacy

26. Would you feel comfortable sharing your stock details with an app?
27. Are there things you would not want an app to know about your business?
28. If you had a problem with the app, who would you trust to help you — a local person, a phone helpline, or someone at a government service centre?
29. Would you pay a small monthly fee (e.g., ₹99–₹199) for a tool that helped you manage stock better?

---

## 5. Observation Checklist

During a shop visit (with consent), observe and note:

- [ ] Type of shop (kirana, provision, general)
- [ ] Approximate number of product categories
- [ ] Whether any written records are visible (notebook, bills, etc.)
- [ ] Whether products have price stickers or handwritten labels
- [ ] Language used on labels and bills
- [ ] Type of phone visible
- [ ] Whether UPI QR code is visible
- [ ] Any indication of which products are selling fast (empty shelves, prominent display)
- [ ] Evidence of expired or damaged products
- [ ] How the shopkeeper handles a customer asking for a product they don't have
- [ ] Network connectivity indicator on the shopkeeper's phone

---

## 6. Usability Testing Plan (Post-Prototype)

Once a working prototype exists, conduct usability sessions:

| Session | Activity | Goal |
|---|---|---|
| Task 1 | Select language and add first 5 products | Test onboarding flow |
| Task 2 | Record "10 Parle-G packets arrived" by voice | Test voice update flow |
| Task 3 | View which products are low in stock | Test dashboard clarity |
| Task 4 | Understand and act on an expiry alert | Test alert usefulness |
| Task 5 | Review and approve a restocking suggestion | Test recommendation flow |

**Observation focus:**
- Did the shopkeeper understand what to do without instruction?
- Were there moments of confusion or hesitation?
- Did the voice recognition understand the shopkeeper correctly?
- Was the language of the UI appropriate and understandable?
- Did the shopkeeper trust the app's recommendation?

---

## 7. What We Expect to Learn

| Question | Validation Method |
|---|---|
| Do shopkeepers actually lose money to expiry? | Interview Section A |
| Is dead stock a real and significant problem? | Interview Section A |
| Do distributors influence purchasing more than data? | Interview Section B |
| Are regional product names a real barrier? | Interview Section C |
| Is internet connectivity reliably available? | Interview Section D |
| Will voice commands work in the target language? | Usability Task 2 |
| Is the image-first dashboard understood? | Usability Task 3 |
| Is ₹99–₹199/month a realistic price? | Interview Section F |

---

## 8. Research Disclaimers

> **Important:** No field research has been conducted as of November 2026. All assumptions about shopkeeper behaviour, losses, and product preferences are drawn from the Tech4Bharat 2026 problem statement and publicly available secondary research. These must be validated before any product decision is treated as confirmed.

> Any figures cited in the problem statement (e.g., 15–20% working capital in dead stock, ₹5,000–₹10,000 monthly expiry losses) are from the official hackathon document and have not been independently verified through primary research.

---

## 9. How to Use This Plan

1. Print or use this document as a guide during interviews
2. Take handwritten notes — do not record audio without explicit consent
3. After each interview, write up key findings within 24 hours
4. Mark each finding as: **Confirmed** / **Contradicted** / **Needs more data**
5. Update the requirements traceability matrix if findings change priorities

---

*All research activities described in this document are proposed plans. No interviews, observations, or usability tests have been conducted yet.*
