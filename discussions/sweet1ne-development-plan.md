# Sweet1ne Internal Development Plan

Prepared for: GlobalSolutions internal use  
Project: Sweet1ne visual-menu web app  
Client: Sweet1ne, Chingford & Lewisham  
Owner: Kibiru Kelvin, Lead Developer & Systems Architect  
Date: June 2026  

Confidential: Internal GlobalSolutions planning document. Not client-facing.

---

## 1. Internal Objective

Sweet1ne is GlobalSolutions' first external client deal and should be treated as both a paid delivery project and a future case study.

The goal is to build a focused v1 visual-menu platform that is:

- Good enough to impress Sweet1ne.
- Simple enough to deliver without scope drift.
- Measurable enough to prove business value.
- Architected well enough to reuse for future restaurant clients.

The product should not be treated as a one-off restaurant menu. It should be built as the first tenant on a reusable GlobalSolutions restaurant menu platform.

---

## 2. Version 1 Scope

### Customer Side

- Mobile-first web menu opened by QR code.
- No app download.
- Branch-specific menu.
- Categories.
- Dish list.
- Dish detail page.
- Dish photo.
- Price.
- Description.
- Dietary tags.
- Allergen tags.
- Popular badge.
- Search.
- Availability status.

### Admin Side

- Secure login.
- Role-based access.
- Restaurant/branch selection.
- Add/edit/delete categories.
- Add/edit/delete dishes.
- Upload dish photos.
- Set prices.
- Mark dishes available/unavailable.
- View basic analytics.

### Analytics

- QR scans.
- Dish views.
- Category views.
- Search terms.
- Branch-level breakdown.
- Basic admin reporting.

### Excluded from Version 1

- Ordering.
- Payments.
- AR.
- AI.
- POS integration.
- Loyalty system.
- Delivery integrations.
- Complex campaign engine.

These should be positioned as v2 opportunities after the pilot.

---

## 3. Recommended Technical Stack

### Primary Recommendation

- Frontend: Next.js, React, TypeScript.
- Styling: Tailwind CSS.
- Backend/database: Supabase Postgres.
- Authentication: Supabase Auth.
- Authorization: Supabase row-level security plus app-level role checks.
- Storage: Supabase Storage or S3-compatible storage.
- Image delivery: CDN-backed optimized images.
- Hosting: Vercel or Cloudflare Pages.
- Analytics: Custom event table in Supabase.
- QR codes: Generated per branch and optionally per table.

### Why This Stack

Next.js gives a fast mobile web experience and allows quick delivery. Supabase gives managed Postgres, auth, storage, and security controls without needing to run a custom backend server. Vercel or Cloudflare keeps deployment simple and cheap at pilot scale.

This stack is also reusable. If built correctly, Sweet1ne becomes the first tenant and future restaurants can be added under the same architecture.

---

## 4. Architecture Requirements

The architecture must support multi-tenancy from day one.

Required hierarchy:

- Restaurant.
- Branch.
- Menu.
- Category.
- Dish.
- Media.
- Analytics event.

Data must be separated cleanly by restaurant and branch. Sweet1ne should not be hardcoded into the platform.

### Suggested Data Model

Core tables:

- `restaurants`
- `branches`
- `menus`
- `categories`
- `dishes`
- `dish_media`
- `allergens`
- `dietary_tags`
- `dish_allergens`
- `dish_dietary_tags`
- `admin_users`
- `analytics_events`

Important rules:

- Store prices in minor units, for example pence, not floating-point decimals.
- Store currency code, for example `GBP`.
- Store media as a separate model so photo now can become video or AR asset later.
- Store analytics as append-only events.
- Keep branch-specific menus separate.
- Use stable public slugs for QR URLs.

Example URL direction:

- `/m/sweet1ne/chingford`
- `/m/sweet1ne/lewisham`
- `/m/sweet1ne/chingford/table-05` if table-level QR tracking is needed.

---

## 5. Security Requirements

Minimum security controls:

- Secure admin authentication.
- Role-based access.
- Least-privilege permissions.
- No public write access.
- Row-level security for tenant data.
- Admin actions scoped to assigned restaurant/branch.
- Image upload validation.
- Environment variables kept out of repo.
- Private repo access.
- IP assignment and confidentiality agreement for developer.

Admin roles can start simple:

- GlobalSolutions admin.
- Restaurant owner/manager.
- Branch manager, optional for v1.

---

## 6. Delivery Timeline

Realistic delivery estimate after developer selection: 6 to 8 weeks to live pilot.

### Week 0 - Developer Selection

Duration: 3 to 5 days.

Actions:

- Source candidate.
- Review portfolio/GitHub.
- Technical screen.
- Confirm availability.
- Confirm working terms.
- Confirm confidentiality/IP requirements.
- Confirm stack and milestones.

### Week 1 - Setup & Content

Actions:

- Confirm pilot branch.
- Select 10-15 starter dishes.
- Collect descriptions, prices, allergens, dietary tags.
- Confirm photos or arrange photography.
- Capture baseline sales.
- Define menu categories.
- Create project repo and environment.
- Finalize schema.

Deliverables:

- Content pack.
- Baseline sales snapshot.
- Technical architecture confirmed.
- Repo and project board ready.

### Weeks 2-5 - Build

Actions:

- Build customer menu.
- Build branch-specific routing.
- Build admin auth.
- Build category and dish management.
- Build photo upload.
- Build availability controls.
- Build analytics event capture.
- Generate QR codes.
- Build basic analytics dashboard.

Deliverables:

- Working customer menu.
- Working admin dashboard.
- Analytics events captured.
- QR flow ready.

### Week 6 - Testing & Fixes

Actions:

- Test iPhone Safari.
- Test Android Chrome.
- Test slow connections.
- Test QR scan behavior.
- Test admin editing.
- Test image loading.
- Test analytics.
- Test tenant/branch separation.
- Fix critical issues.

Deliverables:

- Pilot-ready build.
- Known issues list.
- Launch checklist completed.

### Weeks 7-10 - Live Pilot

Actions:

- Launch in one branch.
- Monitor QR scans and dish views.
- Collect staff feedback.
- Compare selected dish performance against baseline.
- Compare pilot branch against second branch.

Deliverables:

- Pilot analytics report.
- Expansion recommendation.
- v2 backlog.

---


## 9. Measurement Plan

The case study depends on proving value, not just launching the menu.

### Baseline Before Launch

Capture for selected 10-15 dishes:

- Weekly units sold.
- Weekly revenue.
- Gross margin estimate if available.
- Branch.
- Any promotions or special events.

### During Pilot

Track:

- QR scans.
- Unique sessions.
- Dish views.
- Category views.
- Search terms.
- Most viewed dishes.
- Least viewed dishes.
- Admin updates.
- Selected dish sales.

### Comparison

Compare:

- Pilot branch before vs during pilot.
- Pilot branch vs non-pilot branch over same period.
- Featured dishes vs non-featured dishes.

This gives GlobalSolutions a stronger case study than a normal digital menu.

---

## 10. Risk Register

| Risk | Impact | Control |
|---|---|---|
| Scope creep | Delays and cost pressure | Freeze v1 and push extras to v2 |
| Weak developer | Poor delivery quality | Vet hard before selection |
| Content delays | Timeline slips | Start with only 10-15 dishes |
| Poor photos | Weak customer impact | Require proper photography |
| Analytics inaccurate | Weak case study | Define and test events early |
| Client expects ordering/payments | Misalignment | State v1 exclusions clearly |
| Admin too complex | Staff adoption drops | Keep dashboard simple |
| Data model too narrow | Cannot reuse platform | Multi-tenant from day one |

---

## 11. Quality Checklist

Before pilot launch:

- Customer menu loads fast on mobile.
- QR codes open the correct branch menu.
- Dish images are optimized.
- Prices display correctly.
- Allergens and dietary tags display clearly.
- Search works.
- Admin login works.
- Admin can update dishes without developer help.
- Analytics events are captured.
- Branch data is separated.
- No critical bugs remain.

---


## 13. Immediate Next Steps

1. Confirm first pilot branch.
2. Ask Sweet1ne for 10-15 starter dishes.
3. Confirm dish descriptions, prices, allergens, and dietary tags.
4. Confirm available photography or arrange photos.
5. Request baseline sales for selected dishes.
6. Source developer within 3-5 days.
7. Vet developer against architecture and communication requirements.
8. Confirm final stack and milestones.
9. Prepare client-facing proposal from separate client document.
10. Start build after content and developer are confirmed.
