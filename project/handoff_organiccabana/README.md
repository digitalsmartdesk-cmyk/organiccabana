# Handoff: Organic Cabana — D2C Organic Foods Website

## Overview
A complete marketing + commerce website for **Organic Cabana**, a premium direct-to-consumer organic foods brand. Tagline: *"Nurture by Nature, Trusted by You."* The range covers organic attas, ancient grain flours, rice, dals and superfoods — all USDA and Jaivik Bharat certified, chemical-free.

The package covers the full shopping journey: homepage → shop → product detail → checkout, plus account flows (login/register, account dashboard, order tracking).

## About the Design Files
These are **high-fidelity HTML design references** — not production code to copy. Recreate them in the target framework (React, Next.js, etc.) using its component patterns, routing and styling system. Forms and interactions are illustrative; no backend is wired. Open `Homepage.html` in a browser to walk the full cross-linked flow.

---

## Design Tokens

### Colors
| Token | Hex | Usage |
|---|---|---|
| `--green` | `#5A9E2F` | Primary brand — leaf green from logo. Buttons, tags, icons, links |
| `--green-deep` | `#2D5A16` | Dark green — headings, hover states, deep accents |
| `--green-soft` | `#72B848` | Light green — on dark backgrounds, hover accents |
| `--green-tint` | `#EEF5E4` | Very light sage — hero bg, card fills, tint blocks |
| `--green-tint-2` | `#D4E9BF` | Sage border — card borders on tint bg |
| `--red` | `#C0272D` | Cabana red — primary CTA buttons, prices, status pills, active states |
| `--red-deep` | `#96181D` | Red hover/pressed state |
| `--red-tint` | `#FBEAEA` | Red wash — wishlist hover, destructive action bg |
| `--cream` | `#F7F2E8` | Page background — warm linen |
| `--cream-warm` | `#EDE5D0` | Slightly deeper cream — input fills, section alternates, card bg |
| `--white` | `#FFFFFF` | Cards, header, form panels |
| `--ink` | `#2C1F0F` | Primary text — dark warm brown |
| `--ink-soft` | `#6B5744` | Secondary text, captions, labels |
| `--rule` | `rgba(44,31,15,.09)` | Hairline borders |
| `--rule-strong` | `rgba(44,31,15,.16)` | Stronger borders, input outlines |

### Typography
- **Headings:** `'Lora', serif` — weights 400/500/600/700. Italics (`font-style: italic`) for brand emphasis, often colored `--red` (on light) or `--green-soft` (on dark).
- **Body / UI:** `'Nunito', sans-serif` — weights 300–700. Heavier weights (700/800) used for labels, buttons, eyebrows.
- **Eyebrow labels:** Nunito, 11–12px, `font-weight: 800`, `letter-spacing: .24em–.28em`, `text-transform: uppercase`, color `--green`.
- **Type scale (desktop):** Hero H1 72px. Interior H1 40–52px. Section H2 36–48px. Card H3 16–20px. Body 14–15px. Captions 10–12px.
- **Mobile H1:** scales to 26–34px. Minimum body 14px.

### Spacing & Layout
- Container: `max-width: 1100–1200px`, side padding `40px` desktop → `28px` tablet → `18px` mobile.
- Section padding: `100px` desktop → `72px` tablet → `52px` mobile.
- Card gap: `24px` desktop → `18px` tablet → `14px` mobile.

### Borders & Radius
- Page/section cards: `12–16px`
- Product cards: `12px`
- Buttons: `8px` (rectangular — NOT pill-shaped)
- Inputs: `8px`
- Tags/pills: `6px`
- Trust strip icons: `10px`

### Shadows
- Card resting: `0 6–8px 20–28px -16px rgba(44,31,15,.18)`
- Card hover: `0 16–20px 36–48px -18px rgba(44,31,15,.2)` + `translateY(-3px to -5px)`
- Red CTA: `0 8px 24px -10px rgba(192,39,45,.45)`
- Green CTA: `0 4px 18px -6px rgba(45,90,22,.4)`

### Buttons
All buttons use `border-radius: 8px` with `text-transform: uppercase` and `letter-spacing: .08em–.14em`.
- **Primary CTA:** Red `#C0272D`, white text, shadow — "Add to Cart", "Place Order", "Subscribe"
- **Secondary CTA:** Dark green `#2D5A16`, white text — "Our Story", sign-in secondary
- **Ghost:** White bg, `border: 1.5px solid --rule-strong`, dark text — "Invoice", "Download"
- **Add to cart (card):** Green `#5A9E2F`, white, smaller — 11px uppercase

### Breakpoints
- **≤ 900px** (tablet): nav → hamburger; multi-col grids → 2-col; 2-col layouts stack.
- **≤ 600px** (mobile): single-column everything; CTAs full-width; type steps down; newsletter form stacks.

---

## Screens / Views

### 1. Homepage (`Homepage.html`)
- **Purpose:** Brand introduction, trust-building, conversion to Shop.
- **Hero:** Light sage `#EEF5E4` background (NOT dark) — dark green headline, floating product pack with green glow, USDA/Jaivik Bharat cert badges, organic blob shapes, red "100% No Pesticides" circular badge, two CTAs (red "Shop Now" + dark green "Our Story"), 3 stats.
- **Sections:** Trust bar (4 items) · Featured products (4 of 9) · Brand story (2-col: image + text with certifications row) · Why Organic Cabana (3 cards on sage tint) · Testimonials (3 quotes on dark green bg) · Newsletter (red bg, product image right) · Footer (dark brown, 5 columns).
- **Taglines:** "Nurture by Nature, Trusted by You" · "Start Organic Living" · "Grown clean. Processed pure. Delivered honest."

### 2. Shop (`Shop.html`)
- **Purpose:** Browse and filter the full 9-product catalog.
- **Layout:** Dark green page-hero · Sticky filter bar (category tabs: All / Atta & Flours / Organic Rice / Dals & Lentils / Superfoods; certification pill filters; sort dropdown) · 9-product grid (4→2→1 col) · Assurance strip (4 items) · Footer.
- **Product tags:** Bestseller (green) · USDA Organic (red) · Gluten Free (dark green) · Superfood (amber).
- **JS filter:** Category tabs hide/show cards by `data-cat` attribute client-side.

### 3. Product Detail (`OC Product.html`)
- **Purpose:** Single product page — Organic Whole Wheat Atta.
- **Layout:** Breadcrumb · 2-col PDP (gallery left: main image + 4 thumbnails with swap, cert overlay badges; info right: category, H1, star rating, price block with savings badge, description, size selector, stepper + Add to Cart, wishlist, cert pills) · Full description band (2-col: left sticky pull-quote + heading, right body text + 8-cell specs grid) · Related products (4-col grid) · Footer.
- **JS:** Thumbnail click swaps main image; size buttons toggle `.on`; qty stepper clamps 1–10.
- **Mobile:** Gallery on top, info below; stepper full-width; specs → single column.

### 4. Checkout (`Checkout.html`)
- **Purpose:** Complete the order.
- **Layout:** Logo-only header with "Secure Checkout" + SSL label · 4-step indicator (Cart → Details → Payment → Confirm) · 2-col: left = form cards (contact, address with 2-col rows, delivery option radios, payment method tabs + card fields, red "Place Order" button); right = sticky order summary (line items, totals, coupon, payment badges, trust list) · Mini dark footer.
- **Mobile:** Summary un-sticks and drops below form; 2-col form rows → 1-col; step labels hidden.

### 5. Login / Register (`Login.html`)
- **Purpose:** Authenticate or create account.
- **Layout:** Split screen — left dark green brand panel (tagline, 3 stats, quote, faded product pack); right form panel with pill tab toggle (Sign In ↔ Create Account), Google button, email/password fields with eye toggle, remember checkbox, red submit.
- **Behavior:** Tabs swap forms; submit navigates to `Account.html`. Brand panel hides on mobile.

### 6. Account Dashboard (`Account.html`)
- **Purpose:** Post-login hub.
- **Layout:** Green account-hero (avatar, welcome headline, 3 quick stats) · 2-col body: left sidebar nav (My Orders, Addresses, Wishlist, Profile & Settings, Track an Order, Sign Out), right swappable panels.
  - **Orders:** order cards with status pill (transit animated dot / delivered check), product thumbnails, Track/Reorder/Invoice actions.
  - **Addresses:** 2-col grid (Home default + Office), dashed "Add new address" tile.
  - **Wishlist:** 3-col product grid with filled hearts + Add buttons.
  - **Profile:** name/email/phone/DOB form + notification preference toggles.
- **Mobile:** Sidebar → horizontal scroll tab row; grids stack.

### 7. Order Tracking (`Order Tracking.html`)
- **Purpose:** Track a placed order.
- **Layout:** Dark green page-hero · Lookup card (order # + email + red Track button) · Results: order status banner (red "Out for delivery" pill + ETA), 2-col grid — left = 6-step timeline (active step has red icon + expanded green detail note) + map placeholder with red pin + action buttons (Reorder / Invoice / Support) + storage reminder; right = order summary card · Full footer.

---

## Certifications to Display
These are central to the brand and must appear prominently on every product:
- **USDA Organic** — on product cards, PDP, footer
- **Jaivik Bharat** — India's national organic certification
- **India Organic** — secondary cert badge
- **Non-GMO** — footer, PDP
- **100% Veg** — footer copyright bar
- **FSSAI Lic. 11417010000412** — footer copyright bar

---

## Products (All 9)
| # | Name | Category | Size | Price |
|---|---|---|---|---|
| 1 | Organic Whole Wheat Atta | Atta | 5 kg | ₹349 |
| 2 | Organic Multigrain Atta | Atta | 5 kg | ₹399 |
| 3 | Organic Basmati Rice | Rice | 1 kg | ₹279 |
| 4 | Organic Sona Masoori Rice | Rice | 1 kg | ₹229 |
| 5 | Organic Toor Dal | Dal | 1 kg | ₹199 |
| 6 | Organic Moong Dal (Split) | Dal | 1 kg | ₹189 |
| 7 | Organic Besan (Gram Flour) | Flour | 1 kg | ₹149 |
| 8 | Organic Ragi Flour | Ancient Grain | 1 kg | ₹179 |
| 9 | Organic Quinoa (White) | Superfood | 500 g | ₹349 |

---

## Interactions & Behavior
- **Hamburger nav:** ≤900px. Cream overlay with large Lora nav links + action buttons. Locks body scroll; closes on link tap.
- **Hover states:** Cards lift `translateY(-4px)` + shadow; product images scale `1.05`; red CTAs darken to `#96181D`; green CTAs darken to `#2D5A16`; trust strip rows get green-tint fill.
- **Filter tabs (Shop):** Click sets `.on` on tab, shows/hides `.product` cards by `data-cat`. Pill filters toggle `.on` independently.
- **Gallery (PDP):** Thumbnail click updates main image `src`; `.on` border highlights active thumb.
- **Size selector (PDP):** Toggle `.on` on clicked size button.
- **Qty stepper (PDP):** Clamps 1–10.
- **Account panels:** Sidebar links toggle `.on`; panels toggle `.on` class. Page scrolls to top.
- **Toggles (Profile):** Click flips `.on` (knob slides via CSS transform).
- **Login tabs:** Buttons + in-form cross-links swap `.hidden` on form bodies.
- **Password eye:** Toggles `input.type` between password/text.
- **Checkout radio/pay tabs:** Toggle `.on` class on click.
- **Order tracking:** Track button adds `.visible` to results section.
- **Transitions:** `.15s–.25s` ease on all color/transform/shadow changes.

## State to Implement
- **Cart:** items (product, size, qty, price), subtotal, delivery, total, coupon. Badge count in header.
- **Auth:** signed-in user, profile, addresses (with default flag), wishlist, notification prefs, rewards balance.
- **Catalog:** products with name, category (`atta`/`rice`/`dal`/`super`), size, price, compare-at price, images, rating, review count, tags, certifications, stock.
- **Orders:** list with status enum (`placed → confirmed → packed → dispatched → out_for_delivery → delivered`), timeline timestamps, courier + tracking ID, items, totals, delivery address.

## Assets
Located in `assets/`:
- `logo.png` — Organic Cabana full logo (script "Organic" + slab "Cabana" + leaf icons + "Start Organic Living" tagline). Always on white/cream bg — do not place on dark without a white container.
- `wheat-atta.jpg`, `multigrain-atta.jpg`, `basmati-rice.jpg`, `sona-masoori.jpg`, `toor-dal.jpg`, `moong-dal.jpg`, `besan.jpg`, `ragi-flour.jpg`, `quinoa.jpg` — product pack photography.
- **Icons:** all inline SVG (stroke style, 2px weight, `stroke-linecap: round`). Replace with Lucide or Feather in implementation.
- **Fonts:** Google Fonts — Lora + Nunito. Self-host or load via app font pipeline.
- **Leaf/wheat patterns:** inline SVG `<pattern>` defs on hero/section backgrounds.

## Files
| File | Screen |
|---|---|
| `Homepage.html` | Homepage |
| `Shop.html` | Shop / catalog |
| `Product.html` | Product detail (Whole Wheat Atta) |
| `Checkout.html` | Checkout |
| `Login.html` | Login / Register |
| `Account.html` | Account dashboard |
| `Order Tracking.html` | Order tracking |
| `assets/` | Logo + product photography |

Open `Homepage.html` in a browser to navigate the full site — all pages are cross-linked.
