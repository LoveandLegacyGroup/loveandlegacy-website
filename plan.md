# plan.md

## 1) Objectives
- Deliver a **luxury cinematic** Love & Legacy website with strict ecosystem adherence (Deep Black dominance, Gold accents, Royal Purple sections, elegant serif + clean sans).
- Implement core flows: **Book Now**, **Contact**, **Corporate Inquiry** → save to MongoDB + **admin email notification**.
- Provide MVP admin access to view bookings/inquiries (simple token/JWT).
- Ship all **17 routes** with provided verbatim copy, CTAs, mobile sticky bar, and smooth cinematic animation system.

---

## 2) Implementation Steps

### Phase 1 — Core Integration POC (Isolation): Email + DB notification loop
**Goal:** prove the most failure-prone dependency (email service) works end-to-end before building full UI.
1. **Web research (best practice)**: confirm SendGrid API patterns for Python/FastAPI (API key, from/to verification, sandbox mode).
2. Use `integration_playbook_expert_v2` to finalize email approach (SendGrid preferred; fallback SMTP/Resend).
3. Create minimal **Python test script**:
   - Connect to MongoDB, insert a sample `booking` document.
   - Send an email notification to admin with booking summary.
4. Validate failure modes:
   - Missing/invalid API key, rate limits, bad sender identity.
   - Ensure retries/logging strategy (simple + safe for MVP).
5. Exit criteria: **script consistently inserts into DB and sends email**.

**User stories (Phase 1)**
1. As an admin, I receive an email when a new booking is submitted so I can respond quickly.
2. As an admin, I receive an email when a corporate inquiry is submitted so I can follow up.
3. As the system, if email fails, the booking is still stored so no lead is lost.
4. As the system, booking emails include all critical trip details so I can confirm efficiently.
5. As the system, the integration is configurable via env vars so it works across environments.

---

### Phase 2 — V1 App Development (Full MVP build)
**A) Design system + UI architecture**
1. Run `design_agent` to produce a **cinematic luxury blueprint** (layout rules, spacing, section patterns, component tokens).
2. Frontend setup: React + Tailwind + Framer Motion + react-router-dom.
3. Global theme:
   - Colors: #0B0B0B / #D4AF37 / #4B1E78 / #F6F1E6 / #C8B98A.
   - Fonts: Cormorant Garamond (headlines) + Inter (body).
4. Component kit (MVP): Header/Nav + Gold CTA button + Section wrappers + Service tiles + Review cards + Forms + Footer + Mobile sticky CTA bar.

**B) Backend (FastAPI + MongoDB)**
1. Data models (Pydantic): `Booking`, `ContactMessage`, `CorporateInquiry` (+ timestamps, status).
2. Endpoints:
   - `POST /api/bookings` (creates booking + sends email)
   - `POST /api/contacts` (creates message + sends email)
   - `POST /api/corporate-inquiries` (creates inquiry + sends email)
   - `GET /api/admin/bookings` (protected)
   - `GET /api/admin/contacts` (protected)
   - `GET /api/admin/corporate-inquiries` (protected)
3. Simple admin protection (MVP): bearer token via env var OR JWT (no user accounts yet).
4. Email service module: SendGrid (from Phase 1 proven), clean templates.

**C) Frontend pages (17 routes)**
1. Build routes and page shells with SEO meta per doc.
2. Home page: all 10 sections + dividers, parallax hero, fade-up scroll, service tile hover behavior, reviews carousel.
3. Services hub + 6 service pages (verbatim copy).
4. Fleet, Experience, Reviews (5–6 cinematic placeholder testimonials), Book Now, About (founder story verbatim), Contact, Corporate Inquiry, Thank You, Privacy Policy, Terms.
5. Forms:
   - Booking form (11 fields, conditional flight number, validation, submit states).
   - Contact + Corporate Inquiry forms (simple, luxury UI).
6. Mobile:
   - Sticky bottom bar: [CALL NOW] + [RESERVE YOUR EXPERIENCE].

**D) Visual assets**
1. Use `vision_expert_agent` to source/select imagery strictly per constraints.
2. Apply consistent treatments: dark overlay (20–40%), slight desaturation, Netflix-grade composition.

**E) V1 testing**
1. Run `testing_agent_v3` for one full end-to-end pass:
   - Navigation across all routes
   - Booking submit → DB save → email received → redirect /thank-you
   - Contact + Corporate inquiry submit flows
   - Mobile sticky bar + CTA routing

**User stories (Phase 2)**
1. As a luxury client, I see a cinematic hero that instantly conveys discretion, reliability, and presence.
2. As an airport traveler, I book an airport transfer and receive a confirmation experience without friction.
3. As a corporate executive, I review the Executive Transportation page and submit a booking in under 60 seconds.
4. As a high-profile client, I can submit a confidential protection request without exposed details.
5. As a mobile user, I always have Call Now + Reserve available without scrolling.

---

### Phase 3 — Feature Expansion + Hardening
1. Add a simple **Admin UI page** (optional) to list bookings/inquiries with filters (status/date/service type).
2. Improve deliverability + observability:
   - Email retry strategy + logging
   - Store `email_status` on documents
3. Content enhancements:
   - Add “Journal” route scaffold for future SEO.
   - Add schema.org LocalBusiness + Service schema.
4. Second full pass with `testing_agent_v3`.

**User stories (Phase 3)**
1. As an admin, I can view all bookings in one place and track follow-ups.
2. As an admin, I can filter bookings by service type so I can prioritize airport runs.
3. As the system, I track whether emails were delivered so leads aren’t silently dropped.
4. As a user, pages load fast and animations stay smooth (no jank) on mobile.
5. As a user, I can trust the brand because consistency is maintained on every page.

---

### Phase 4 — Future Integrations (Optional)
- Instagram feed live embed/API.
- Google Reviews API live feed.
- Analytics (GA4 + Search Console) and conversion tracking.
- If requested: real authentication for admin + role-based access.

---

## 3) Next Actions
1. Run Phase 1 POC: choose email provider via playbook + verify working script.
2. Generate design blueprint with `design_agent` and lock UI tokens.
3. Build backend + frontend in one integrated sprint (minimize bulk file writes).
4. Source imagery with `vision_expert_agent` and apply strict treatments.
5. Execute Phase 2 end-to-end testing with `testing_agent_v3` and fix until green.

---

## 4) Success Criteria
- All **17 routes** render with correct copy, CTAs, and brand styling.
- Booking/Contact/Corporate Inquiry submissions:
  - Persist to MongoDB
  - Trigger admin email notification reliably
  - Redirect to /thank-you with polished UX
- Animations match spec (parallax hero, fade-up, no bouncy transitions) and stay performant.
- Mobile sticky CTA bar works across pages.
- Testing agent confirms end-to-end flows without critical bugs.