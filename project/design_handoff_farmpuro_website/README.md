# Handoff: Farm Puro Chutneys — D2C Website

## Overview
A complete marketing + commerce website for **Farm Puro**, a premium direct-to-consumer Indian chutney brand. The package covers the full shopping journey: homepage → shop listing → product detail → checkout, plus account flows (login/register, account dashboard, order tracking). The brand positioning is premium, authentic, and rooted in Indian tradition — built around three pillars: *Purity you can taste · Recipes with a regional soul · Made this week, not months ago.*

## About the Design Files
The files in this bundle are **design references created in HTML** — high-fidelity prototypes showing the intended look, layout, and behavior. They are **not** production code to copy directly. The task is to **recreate these designs in the target codebase's existing environment** (React, Vue, Next.js, Astro, etc.) using its established component patterns, routing, and styling system. If no front-end environment exists yet, choose an appropriate modern framework (e.g. Next.js + a commerce backend) and implement the designs there.

All pages are static mockups with realistic placeholder content (Indian names, cities, INR pricing, real product copy). Forms and interactions are illustrative — no backend is wired.

## Fidelity
**High-fidelity (hifi).** Final colors, typography, spacing, and interaction states are specified. Recreate the UI pixel-faithfully using the codebase's libraries, then wire it to real data and a commerce backend. Exact hex values, font stacks, and the spacing rhythm are given in **Design Tokens** below.

---

## Design Tokens

### Colors
| Token | Hex | Usage |
|---|---|---|
| `--green` | `#2D6A2D` | Primary brand. Hero bg, primary buttons, headings accents |
| `--green-deep` | `#234E22` | Button hover, testimonial bg, dark green sections |
| `--green-soft` | `#3D7A3D` | Lighter green accents |
| `--green-tint` | `#EBF2E5` | Status pills, info blocks, selected nav bg |
| `--green-tint-2` | `#DDE8D2` | Borders on tint blocks |
| `--brown` | `#6B3A1F` | Secondary brand. Links, newsletter bg, prices |
| `--brown-deep` | `#4E2A14` | Prices, strong text, dark brown |
| `--cream` | `#FAF7F2` | Page background |
| `--cream-warm` | `#F1EBDF` | Cards, input fills, alt section bg |
| `--gold` | `#C8860A` | Accent. CTAs ("Shop Now"), eyebrows, badges |
| `--gold-soft` | `#E0A93C` | Gold on dark backgrounds, hero italics |
| `--chilli` | `#E8531A` | "Hot"/"Limited" product tags, destructive actions only |
| `--ink` | `#1F1A14` | Primary text |
| `--ink-soft` | `#5B5347` | Secondary text, captions |
| `--rule` | `rgba(31,26,20,.10)` | Hairline borders |
| `--rule-strong` | `rgba(31,26,20,.18)` | Stronger borders, input outlines |

### Typography
- **Headings:** `'Playfair Display', serif` — weights 400/500/600/700, used with `letter-spacing: -.01em` to `-.02em`. Italics (`font-style: italic`) used for emphasis words, often colored `--gold-soft` (on dark) or `--green-deep` (on light).
- **Body / UI:** `'DM Sans', sans-serif` — weights 300–700.
- **Eyebrow labels:** DM Sans, 11–12px, `font-weight: 600`, `letter-spacing: .22em–.24em`, `text-transform: uppercase`, color `--gold`.
- **Type scale (desktop):** Hero H1 80px (homepage) / 34–56px (interior). Section H2 48px. Card H3 18–24px. Body 14–16px. Captions 11–13px.
- **Mobile H1:** scales to 30–38px; section H2 to 28px. Minimum body 14px.

### Spacing & Layout
- Container: `max-width: 1100–1200px`, side padding `40px` desktop → `28px` tablet → `18px` mobile.
- Section vertical padding: `110px` desktop → `72px` tablet → `56px` mobile.
- Card gap in grids: `28px` desktop → `20px` tablet → `14–16px` mobile.

### Border radius
- Buttons / pills: `999px` (fully rounded) for CTAs; `10–12px` for rectangular buttons.
- Cards: `6px` (product cards) to `14–16px` (account/summary cards).
- Inputs: `10px`.

### Shadows
- Card resting: `0 10–12px 28–32px -20px rgba(31,26,20,.15)`
- Card hover: `0 18px 40px -16px rgba(31,26,20,.18–.2)` with `translateY(-3px to -4px)`
- Gold CTA: `0 16px 32px -14px rgba(200,134,10,.6)` + inset bottom highlight

### Breakpoints
- **≤900px** — tablet: nav → hamburger; multi-col grids → 2-col; 2-col layouts stack.
- **≤600px** — mobile: everything single-column; CTAs full-width; type steps down.

---

## Screens / Views

### 1. Homepage (`Homepage.html`)
- **Purpose:** Brand introduction + conversion to Shop.
- **Sections (in order):** Sticky header (logo left, centered nav, sign-in + cart right) · Full-viewport hero (deep-green bg, gold SVG leaf pattern, Playfair headline with gold italic, two CTAs — gold "Shop Now" + outline "Our Story", three stat counters, floating product jar with rotating "₹100 off" badge) · Trust bar (4 items: Made Fresh / No Preservatives / Natural Ingredients / Authentic Taste, each icon + title + subcopy) · Featured products (4-card grid) · Brand story (2-col: image with circular "9 Regional Recipes" stamp + heading, two paragraphs with drop-cap, CTA link) · Why Farm Puro (3 cards on cream — the three brand pillars, numbered) · Testimonials (3 quote cards on deep-green, star ratings, name + city) · Newsletter (brown bg, email input + Subscribe) · Footer (logo, brand blurb, socials, 4 link columns, copyright + payment badges + FSSAI license).
- **Hero headline:** "From the farm. Fresh to your table. *Always pure.*"

### 2. Shop (`Shop.html`)
- **Purpose:** Browse/filter the catalog.
- **Layout:** Green page-hero with title + result-count meta · Sticky filter bar (category tabs that scroll horizontally on mobile, spice-level pills, sort dropdown) · Product grid (4-col → 2-col → 1-col) · Assurance strip (4 items) · Footer.
- **Product card:** square image with region eyebrow, Playfair name, short description, star rating, INR price (with struck-through "was" price), tag badge (Bestseller green / Hot chilli), heart/save button, "Add to Cart" pill.

### 3. Product Detail (`Product.html`)
- **Purpose:** Single product, add to cart.
- **Layout:** Breadcrumb · 2-col PDP (left gallery with thumbnails, right info: region eyebrow, H1 name, star rating, price block, description, ingredient highlight row, quantity stepper + Add to Cart, "paired with" suggestions) · Full description band (2-col: pull-quote left, body + specs table right) · Related products (4-col grid) · Footer.
- **Mobile:** PDP stacks (gallery on top); stepper + CTA go full-width; specs table → single-column list.

### 4. Checkout (`Checkout.html`)
- **Purpose:** Complete the order.
- **Layout:** Header with "Secure checkout" title + SSL strip (hidden on mobile) · Step indicator (Cart → Details → Payment → Done) · 2-col grid: left = forms (contact, shipping address with 2-col rows, delivery options, payment), right = sticky order summary (line items, totals, coupon, payment badges, trust list) · Mini footer.
- **Mobile:** Summary un-sticks and drops below the form; all 2-col form rows collapse to 1-col; step labels hide, leaving numbered circles.

### 5. Login / Register (`Login.html`)
- **Purpose:** Authenticate or create an account.
- **Layout:** Split screen — left deep-green brand panel (tagline, stat row, quote, faded jar image), right form panel. Form has a pill tab toggle (Sign In ↔ Create Account), "Continue with Google" button, email/password fields with show/hide toggle, "remember me", gold submit, SSL trust strip.
- **Behavior:** Tabs swap the two forms; submitting Sign In navigates to `Account.html`. On mobile the brand panel hides and the form goes full-width.

### 6. Account Dashboard (`Account.html`)
- **Purpose:** Post-login hub.
- **Layout:** Green account-hero (avatar, "Welcome back" greeting, 3 quick stats: Orders / Wishlist / Rewards) · 2-col body: left sticky sidebar nav (My Orders, Addresses, Wishlist, Profile & Settings, Track an Order, Sign Out), right swappable panels.
  - **Orders panel:** order cards with order #, date, total, status pill (Out-for-delivery animated dot / Delivered check), stacked product thumbnails, Track/Reorder/Invoice actions.
  - **Addresses panel:** 2-col card grid (Home default + Office), each with edit/set-default/delete; dashed "Add new address" tile.
  - **Wishlist panel:** 3-col product card grid with heart + Add.
  - **Profile panel:** profile form (name/email/phone/DOB) + notification preference toggles.
- **Behavior:** Sidebar items switch panels client-side. On mobile the sidebar becomes a horizontal scroll tab bar and grids stack.

### 7. Order Tracking (`Order Tracking.html`)
- **Purpose:** Track a placed order.
- **Layout:** Green page-hero + breadcrumb · Lookup card (order number + email + Track button) · Results: order banner (status pill + ETA), 2-col grid — left = vertical 6-step delivery timeline (Placed → Confirmed → Made & Packed → Dispatched → **Out for Delivery (active)** → Delivered, each with timestamp; active step expands a detail note) + map placeholder + action buttons (Reorder / Invoice / Support) + freshness reminder; right = order summary card (items, totals, delivery address) · Full footer.
- **Behavior:** "Track Order" reveals the results section.

---

## Interactions & Behavior
- **Header nav:** sticky, blurred translucent cream bg. Desktop centered nav; ≤900px collapses to a hamburger that opens a full-screen cream overlay with large Playfair links + action buttons. Overlay locks body scroll; closes on link tap. (See the shared script at the bottom of every page.)
- **Hover states:** cards lift (`translateY(-3px/-4px)` + deeper shadow); product image scales `1.04`; gold CTA lifts 1px + darkens to `#A66E07`; nav links get a 2px gold underline.
- **Buttons:** primary green → `--green-deep` on hover; gold → `#A66E07`; outline → subtle tint fill.
- **Account dashboard:** sidebar links toggle `.on` class on both the link and the matching `#panel-*` section; page scrolls to top on switch.
- **Login:** tab toggle + in-form cross-links swap forms; password eye-button toggles input type; Sign In submit → `Account.html`.
- **Order tracking:** Track button adds `.visible` to results section.
- **Toggles (profile):** click flips `.on` class (animated knob).
- **Transitions:** `.15s–.25s` ease on color/transform/shadow; hamburger bars animate into an X over `.25s`.
- **Reduced motion:** decorative animations are minimal (a pulsing status dot); honor `prefers-reduced-motion` when reimplementing.

## State Management
For a real implementation you will need:
- **Cart:** line items (product, variant/size, qty, price), subtotal, delivery, total, coupon. Cart badge count in header.
- **Auth/session:** signed-in user, profile fields, addresses (with default flag), wishlist items, notification preferences, rewards balance.
- **Catalog:** products (name, region, spice level, description, price, compare-at price, images, rating, review count, tags, stock/limited flags). Filters: category, spice level, sort.
- **Orders:** order list with status enum (`placed → confirmed → packed → dispatched → out_for_delivery → delivered`), timeline timestamps, courier + tracking ID, items, totals, delivery address, batch/made date.
- **UI state:** mobile-nav open, active account panel, lookup-results visibility, toggle states.

## Responsive Behavior
Two breakpoints (900px, 600px) on every page. Grids degrade 4→2→1 col; 2-col layouts stack; nav → hamburger ≤900px; type and section padding step down ≤600px; CTAs and form rows go full-width on mobile. No horizontal overflow at 360px+.

## Assets
Located in `assets/`:
- `logo.png` — Farm Puro wordmark/logo (provided by client).
- `coriander-mint.jpg`, `tamarind-date.jpg`, `coconut.jpg`, `garlic-red.jpg` — product jar photography (client-provided).
- `story.jpg` — brand-story lifestyle image.
- **Icons:** all inline SVG (stroke style, ~1.6–1.8 stroke width) — no icon library dependency. Replace with the codebase's icon set (Lucide/Feather match the stroke aesthetic well).
- **Fonts:** Google Fonts — Playfair Display + DM Sans. Self-host or load via the app's font pipeline.
- **Leaf patterns:** inline SVG `<pattern>` definitions in the hero/section backgrounds.

## Files
Each page is a self-contained HTML file (scoped `<style>` in head, shared header/hamburger/footer markup, small vanilla-JS script at the bottom). The design tokens are duplicated as CSS custom properties in each file's `:root` — when reimplementing, lift them into a single shared theme.

| File | Screen |
|---|---|
| `Homepage.html` | Homepage |
| `Shop.html` | Shop / catalog |
| `Product.html` | Product detail |
| `Checkout.html` | Checkout |
| `Login.html` | Login / Register |
| `Account.html` | Account dashboard |
| `Order Tracking.html` | Order tracking |
| `assets/` | Logo + product/story imagery |

Open `Homepage.html` in a browser to walk the full flow — all pages are cross-linked.
