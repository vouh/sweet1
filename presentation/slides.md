# Project Sweet1ne - Detailed Proposal

Prepared by: GlobalSolutions
Client: Sweet1ne (Chingford & Lewisham, London)
Document: Detailed proposal narrative
Date: 2026

This document expands the client proposal into full detail. It is the written companion to the animated pitch in `sweet1ne-pitch.html` and the working prototype in `demo/`.

---

## 1. Executive summary

Sweet1ne operates two London restaurant branches and currently relies on traditional menus. Traditional menus present a list of dishes but cannot show the food, cannot adapt quickly, and cannot tell the business anything about customer behaviour.

GlobalSolutions proposes a mobile-first visual menu and ordering experience, opened by scanning a QR code at the table. Customers see real dish photography, prices, descriptions, dietary and allergen information, popular items and search. They can place an order directly from their phone. Restaurant staff manage the menu and receive orders through a simple role-based dashboard, and the business gains analytics on how customers actually use the menu.

The first version is delivered as a controlled pilot in a single branch, measured against a sales baseline, so Sweet1ne can see real evidence of impact before expanding to the second branch.

---

## 2. The problem

Sweet1ne's current menus create three specific limitations:

1. No visibility. Customers cannot see what a dish looks like before they order, so they tend to repeat familiar choices and overlook signature or higher-margin items.
2. No data. The business has no insight into which dishes attract attention, what customers search for, or which items are ignored.
3. Slow to change. Updating prices, adding specials, or marking items unavailable requires reprinting and redistributing physical menus.

These limitations mean the menu works only as a static list, not as a tool that can actively help the restaurant sell more or understand its customers.

---

## 3. The solution

The proposed solution is a visual menu web application accessed by QR code.

Core principles:

- Mobile-first and no app download. The menu opens instantly in the phone browser after a scan.
- Visual by default. Every dish is presented with photography, price, description, dietary tags and allergen information.
- Branch-specific. Each branch has its own menu content and its own QR codes.
- Live control. Staff can update content and availability in real time, and changes appear immediately for customers.
- Ordering included. Customers can build an order and send it to staff for approval.

The customer journey is deliberately short: scan, browse, order. The experience is designed to feel premium, fast and effortless.

---

## 4. How GlobalSolutions delivers

GlobalSolutions delivers this as more than a build. The approach has three stages:

1. Build it right. A focused first version covering the visual menu, ordering, a role-based staff dashboard and analytics, architected so it can scale to additional branches and clients without a rebuild.
2. Pilot one branch. The menu launches live in a single branch while the second branch continues operating normally. This creates a like-for-like comparison over the same period.
3. Measure the lift. By comparing featured-dish sales in the pilot branch against a pre-launch baseline and the comparison branch, GlobalSolutions can show whether the menu genuinely drove additional revenue.

This is the central difference: most digital menus can only report that customers used them. This solution is designed to show whether it made money.

---

## 5. User flow

The end-to-end flow has four steps:

1. Scan. The customer scans the QR code at the table.
2. Browse. The customer explores categories and dishes, opens a dish to see full detail, and can search or filter.
3. Order. The customer adds dishes to an order and submits it.
4. Kitchen. The order arrives on the staff dashboard, where floor staff approve and progress it.

Each step is intentionally simple to keep customer effort low and adoption high.

---

## 6. The customer menu

The customer-facing menu is the heart of the product. It includes:

- Real dish photography for every item.
- Clear pricing.
- Descriptions, dietary tags and allergen information.
- "Popular" badges to guide customers toward signature dishes.
- Search and category filtering, so customers can find "halal", "vegan" or "spicy" options instantly.
- Branch selection, so the correct menu is always shown.
- A dish detail view with the full information for each item.

The design goal is a menu that helps customers choose with confidence and gently steers attention toward the dishes the restaurant wants to feature.

---

## 7. Roles and the staff dashboard

The system uses a single dashboard with role-based access, so each person sees only what is relevant to them:

- Floor staff. See and approve incoming orders for their own branch. They do not see analytics.
- Branch admin. Manage their branch's menu (dishes, prices, availability, photos) and view analytics for their branch.
- Main admin. Have full visibility across every branch, including all orders, all menu management and all analytics.

This keeps day-to-day operations simple for floor staff while giving managers and ownership the oversight they need.

---

## 8. Analytics

The analytics layer turns the menu into a source of business insight. Captured per branch, it includes:

- QR scans - how often the menu is opened.
- Dish views - which items attract the most attention.
- Category views - which parts of the menu draw interest.
- Search terms - what customers are actively looking for.
- Order data - what is actually being ordered.

These metrics let Sweet1ne understand demand and customer intent, not just confirm that the menu was opened. In the pitch, these are shown as live animated charts (QR scans by week and top viewed dishes).

---

## 9. The pilot

The pilot is how value is proven rather than promised.

Method:

- The visual menu launches live in one branch.
- The other branch continues to operate normally.
- The same featured dishes are compared across both branches over the same weeks.
- Results are measured against a pre-launch sales baseline.

If featured dishes sell more in the pilot branch than in the comparison branch over the same period, that is real evidence that the menu caused the lift. This is why capturing the baseline in the setup phase is essential.

Recommended pilot length: 2 to 4 weeks, with 4 weeks preferred for stronger evidence.

---

## 10. Delivery timeline

The expected timeline, once the developer is in place and content is confirmed, is approximately 6 to 8 weeks to a live pilot.

| Phase | Focus | Duration |
|-------|-------|----------|
| 1. Setup | Confirm branch, select 10-15 dishes, photography, baseline sales | ~1 week |
| 2. Build | Menu, ordering, role-based dashboard, analytics | ~3-4 weeks |
| 3. Test | Phones, browsers, slow connections, real conditions | ~1 week |
| 4. Pilot | Live in one branch | 2-4 weeks |
| 5. Expand | Review results, roll out to second branch | ~1 week |

This timing is deliberately honest. Photography, content approval, testing and real mobile performance checks all matter for a first case study, so the plan does not over-promise.

---

## 11. Success factors

Success for the pilot is defined across a set of factors rather than a single number:

- Scan rate. Customers consistently scan and open the menu.
- Dish views. Dish pages receive meaningful engagement.
- Order rate. Customers complete orders through the system.
- Staff adoption. Staff can manage content and approve orders without difficulty.
- Sales uplift. Featured dishes show stronger sales than baseline and than the comparison branch.

In the pitch, these are presented as animated charts: a scorecard radar comparing target versus projected performance, and a projected featured-dish revenue chart comparing baseline against the pilot projection. All such figures are illustrative until the Phase 1 baseline is captured with Sweet1ne.

The pilot is considered successful when the data and the owner's experience together justify expanding to the second branch.

---

## 12. Scope discipline (version 1)

To deliver a strong, reliable first version, v1 deliberately excludes:

- Payments and card processing.
- Delivery-platform and POS integrations.
- Augmented reality and AI features.
- Loyalty programmes and complex promotions.

These are natural candidates for version 2 once the pilot has proven the core value. Note: ordering is included in the prototype to demonstrate the full experience; whether it forms part of the initial client-facing v1 or a fast-follow can be confirmed with Sweet1ne.

---

## 13. Next steps

To move from proposal to pilot:

1. Confirm the first pilot branch (Chingford or Lewisham).
2. Select the 10-15 starter dishes.
3. Confirm prices, descriptions, dietary tags and allergens.
4. Confirm or arrange dish photography.
5. Capture the current sales baseline for the selected dishes.
6. Begin the build.

Once these are in place, GlobalSolutions proceeds into Phase 1 and the pilot timeline begins.

---

## 14. Companion assets

- `index.html` - Sweet1ne visual walkthrough (9 slides). Opens with an introduction slide: image left, Sweet1ne intro text right, prepared by GlobalSolutions.
  - Slide 1: Project proposal — `images/landing.png`, pitch headline + GlobalSolutions credit.
  - Slide 2: At the table — `images/qrcode.png`.
  - Slides 3–5: Browse, dish detail, order (phone mocks with Unsplash dishes).
  - Slide 6: Kitchen — custom image slot (`images/kitchen.png`) + live order dashboard mock.
  - Slide 7: Three dashboards — floor staff, branch admin, main admin with centre dashboard image (`images/dashboard.png`, Unsplash fallback).
  - Slide 8: Next steps (modernized closing).
- `../discussions/sweet1ne-client-proposal.md` - the concise client-facing proposal.
- `../discussions/sweet1ne-development-plan.md` - the internal technical and commercial plan.
