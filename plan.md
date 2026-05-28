# plan.md (Updated)

## 1) Objectives
- Deliver a **luxury cinematic** Love & Legacy website with strict ecosystem adherence (Deep Black dominance, Gold accents, Royal Purple feature sections, elegant serif + clean sans).
- Implement core flows: **Book Now**, **Contact**, **Corporate Inquiry** → **persist to MongoDB** + **admin email notification** (SendGrid; graceful no-op if not configured).
- Provide MVP admin access to view submissions (token-protected list endpoints).
- Ship a complete, cohesive brand experience across **17 routes**, including **Home (10 cinematic sections)**, all service pages, and legal/thank-you states.
- Ensure a luxury mobile experience via **sticky bottom CTA bar**: **[CALL NOW] + [RESERVE]**.
- Validate end-to-end stability via automated testing (backend + frontend) with **zero critical bugs**.

---

## 2) Implementation Steps

### Phase 1 — Core Integration POC (Isolation): Email + DB notification loop
**Goal:** prove the most failure-prone dependency (email service) works end-to-end before building full UI.

**Status: COMPLETED (implemented directly in backend with best-effort email sending)**
1. Confirmed SendGrid API patterns and configuration approach via `integration_playbook_expert_v2`.
2. Implemented a clean email service module with luxury HTML formatting and strict error handling:
   - If `SENDGRID_API_KEY` or `SENDER_EMAIL` is missing → **log warning and skip** (no blocking).
3. Validated failure modes:
   - Missing/invalid key does **not** prevent database persistence.

**User stories (Phase 1) — Completed**
1. As an admin, I receive an email when a new booking is submitted so I can respond quickly.
2. As an admin, I receive an email when a corporate inquiry is submitted so I can follow up.
3. As the system, if email fails, the booking is still stored so no lead is lost.
4. As the system, booking emails include all critical trip details so I can confirm efficiently.
5. As the system, the integration is configurable via env vars so it works across environments.

---

### Phase 2 — V1 App Development (Full MVP build)

**Status: COMPLETED (Ready to ship)**

**A) Design system + UI architecture**
1. Ran `design_agent` to produce a **cinematic luxury blueprint** (layout rules, spacing, section patterns, component tokens).
2. Frontend built with React + Tailwind + Framer Motion + react-router-dom.
3. Global theme locked:
   - Colors: #0B0B0B / #D4AF37 / #4B1E78 / #F6F1E6 / #C8B98A.
   - Fonts: Cormorant Garamond (headlines) + Inter (body).
4. Component kit delivered:
   - Header/Nav (transparent → solid on scroll)
   - Primary/secondary/ghost CTAs
   - Section dividers (gold rules + ornamental divider)
   - Service tiles (gold top border, hover purple shift)
   - Review cards (dark luxury cards + gold stars)
   - Luxury forms (dark inputs, gold focus ring)
   - Footer (3-column, legal links)
   - Mobile sticky CTA bar: **Call Now + Reserve**

**B) Backend (FastAPI + MongoDB)**
1. Data models (Pydantic): `Booking`, `ContactMessage`, `CorporateInquiry` (+ timestamps, status).
2. Endpoints implemented:
   - `POST /api/bookings` (creates booking + best-effort email)
   - `POST /api/contacts` (creates message + best-effort email)
   - `POST /api/corporate-inquiries` (creates inquiry + best-effort email)
   - `GET /api/admin/bookings` (token-protected)
   - `GET /api/admin/contacts` (token-protected)
   - `GET /api/admin/corporate-inquiries` (token-protected)
   - `GET /api/health` (db ping)
   - `GET /api/services`
3. Admin protection (MVP): header-based token via env var (`ADMIN_TOKEN`).
4. Email module: SendGrid (best-effort) with graceful fallback behavior.
5. Minor enhancement applied post-test:
   - Backend enforces data consistency: **`flight_number` is nullified unless `service_type == "Airport Transfer"`.**

**C) Frontend pages (17 routes)**
**Delivered routes:**
1. Home (10 cinematic sections)
2. Services hub
3. Airport Transfers
4. Executive Transportation
5. VIP & Event Transportation
6. Executive Protection
7. Production Transportation
8. Corporate Accounts
9. Fleet
10. Experience
11. Reviews
12. Book Now
13. About
14. Contact
15. Corporate Inquiry
16. Thank You
17. Privacy Policy, Terms of Service, + 404

**Key UX behaviors delivered:**
- Home hero: parallax + overlays + luxury CTA hierarchy.
- Scroll animations: fade-up (no bouncy transitions).
- Service tiles: gold top border + hover lift + purple shift.
- Reviews: luxury cards with gold stars.
- Mobile: sticky CTA bar persists and routes correctly.

**Forms delivered:**
- Booking form (11 fields) with conditional flight number display and inline validation.
- Contact form + Corporate inquiry form with submission → thank-you redirect.

**D) Visual assets**
1. Cinematic imagery sourced and applied with consistent treatments:
   - dark overlays, slight desaturation, premium composition.
2. Strict brand constraints honored:
   - black luxury SUVs, Atlanta skyline, executive protection, private aviation, premium hotel/valet.

**E) V1 testing**
**Status: COMPLETED**
1. Ran `testing_agent_v3` end-to-end:
   - Backend: **100% (13/13 tests passed)**
   - Frontend: **95%** (all routes functional; minor selector observations only)
2. No critical bugs.
3. Post-test fix applied: backend flight_number nullification.

**User stories (Phase 2) — Completed**
1. As a luxury client, I see a cinematic hero that instantly conveys discretion, reliability, and presence.
2. As an airport traveler, I can book an airport transfer with flight number support.
3. As a corporate executive, I can review executive transport and submit a booking quickly.
4. As a high-profile client, I can request protection service discreetly.
5. As a mobile user, Call Now + Reserve is always available.

---

### Phase 3 — Ship + Hardening
**Status: NEXT**
1. Replace placeholders with production values:
   - **Phone number** and **email address** (currently placeholders in constants).
   - Update `SENDER_EMAIL` + `ADMIN_EMAIL` to the real admin inbox.
2. Configure SendGrid for production deliverability:
   - Add `SENDGRID_API_KEY`.
   - Verify sender/domain alignment (SPF/DKIM) if using custom domain.
3. Add basic operational observability:
   - Persist `email_status` / `email_error` (optional) to each document.
   - Add lightweight request logging for submissions.
4. (Optional) Admin UI:
   - Simple internal admin page to view bookings/inquiries with filters.

**User stories (Phase 3)**
1. As an admin, I receive reliable email alerts in production for every lead.
2. As an admin, I can quickly review bookings in a dashboard (optional).
3. As the system, I track email send success so leads aren’t silently dropped.
4. As a user, performance stays smooth on mobile and transitions remain cinematic.
5. As a user, trust increases because all contact details are real and consistent.

---

### Phase 4 — Future Integrations (Optional)
- Instagram feed live embed/API.
- Google Reviews API live feed.
- Analytics (GA4 + Search Console) and conversion tracking.
- If requested: real authentication for admin + role-based access.

---

## 3) Next Actions
1. Swap in real **phone number** and **email** in `frontend/src/constants/brand.js`.
2. Configure SendGrid env vars in backend `.env`:
   - `SENDGRID_API_KEY`
   - `SENDER_EMAIL`
   - `ADMIN_EMAIL`
3. Optional: rotate `ADMIN_TOKEN` to a secure value and store safely.
4. Final QA pass (visual + forms) in production environment.

---

## 4) Success Criteria
- All **17 routes** render with correct copy, CTAs, and brand styling.
- Booking/Contact/Corporate Inquiry submissions:
  - Persist to MongoDB
  - Trigger admin email notification when SendGrid is configured
  - Redirect to /thank-you with polished UX
- Animations match spec (parallax hero, fade-up, no bouncy transitions) and remain performant.
- Mobile sticky CTA bar works across the site.
- Testing confirms end-to-end flows with **zero critical bugs** and consistent data handling (including flight number rules).
