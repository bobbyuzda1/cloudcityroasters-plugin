# Changelog

## 1.1.0 — 2026-07-23
Flow rework from live user feedback — faster, smoother, enforced discount:
- **Opening now explains the process** (pick a bean → secure Stripe checkout, ~a minute)
  and presents a menu — Order coffee / Reorder my usual / Manage orders & subscriptions —
  via the AskUserQuestion tool.
- **Ordering starts with one open question** ("how do you like your coffee?"); Lando
  infers brew/flavor/caffeine and only asks for what's missing. Size, grind, quantity, and
  one-time-vs-monthly are collected in a single batched question — the whole happy path is
  ~4 exchanges.
- **Real coffee talk:** recommendations now cite origin, roast profile, and tasting notes
  (Huila Colombia, Mount Meru, Fazenda Bom Jesus, sugarcane-EA decaf…) from the live catalog.
- **The terminal never asks for your email.** Checkout links now go to a secure order page
  on cloudcityroasters.com where you enter your email once; the server verifies whether
  it's your first order and applies the 10% automatically — enforced against real customer
  records, not claimed. Newsletter is an unchecked opt-in on that page.
- **Less salesy:** value hints (5 lb per-ounce savings, Subscribe & Save) live inside the
  option descriptions; one quip max per message; no repeated pitches.
- Manifest polish: displayName, homepage, author contact, marketplace description,
  category/tags; `allowed-tools` pre-approves the plugin's curl calls so the flow isn't
  interrupted by permission prompts; `when_to_use` + `argument-hint` added.

## 1.0.2 — 2026-07-23
- Hardened the quiet-shelf rule: explicit deflection script for direct menu-count
  interrogation ("a fifth coffee?"), near-name unlock examples ("the Tanzanian one",
  the raw slug), and a cap on repeat deflections.
- Order recap now ends in a single grand total and calls out the $5.99 shipping on a
  lone 12 oz bag.
- Dedicated no-discount wording for guests who decline to share an email (plus a heads-up
  that Stripe asks for an email on the secure page).
- Subscription copy now reads its percent from the catalog (`subscriptionDiscountPercent`).
- Clarified upsell pacing: one beat per turn, each beat once per order.

## 1.0.1 — 2026-07-23
- Tanzanian Peaberry rule promoted to a top-level HARD RULE with broadened verbs
  (never name/list/describe/recommend/allude), a Morning Flow steering script, and a
  no-flat-lies clause; explicit by-name requests are honored without comment.
- Returning-guest flow fixed: catalog still fetched first, greeting includes quantity,
  "yes" goes straight to checkout with the saved email (no email or newsletter re-asks),
  remember-me only offered when the order changed.
- Added an order-confirmation recap before any checkout session is created.
- Checkout link is printed first; opening the browser now requires a yes.
- First-order discount percent read from the catalog's `firstOrderDiscountPercent`.
- POST curls no longer use `-f`, so error bodies stay readable for graceful fallbacks.

## 1.0.0 — 2026-07-23
- Initial release: `/coffee` — Lando the barista recommends a Cloud City Roasters bean
  (3 quick taste questions), builds the order (size, grind, one-time or Subscribe & Save),
  captures email + separate newsletter consent, auto-applies the CODE10 first-order
  discount for new customers, and hands off to Stripe's secure hosted checkout. Local
  consent-gated reorder memory (`~/.cloud-city-coffee.json`, `/coffee forget` to wipe)
  and Stripe Customer Portal access by email for managing subscriptions.
