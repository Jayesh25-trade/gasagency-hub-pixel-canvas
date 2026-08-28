# GasAgency Hub: Pixel Canvas

BUILD: GasAgency Hub — Cinematic Scroll-Storytelling Homepage
Build a single-page, scroll-driven storytelling homepage for GasAgency Hub, an LPG Gas Agency ERP for India. This must be a premium, buttery-smooth, cinematic scroll experience — not a generic SaaS landing page. Every button must work. Every section must be responsive. No placeholder links.

STACK & TECHNICAL REQUIREMENTS
TanStack Start + React + Tailwind + Motion (framer-motion) for all animation
Use motion for scroll-linked animation (useScroll, useTransform, useSpring), sticky positioning, and viewport-triggered reveals
All scroll animations must be spring-smoothed — no janky, instantly-snapping values
Respect prefers-reduced-motion: disable transforms, keep content fully readable
Fully responsive: on mobile, horizontal-scroll and pinned sections degrade to clean vertical stacks
All colors, fonts, shadows, gradients as semantic design tokens in the global CSS — no hardcoded color utilities in components
SEO: unique title, meta description, og:title, og:description, og:type, twitter:card. Single H1. Semantic HTML. Alt text everywhere.
BRAND SYSTEM
Name: GasAgency Hub Tagline: Smart. Simple. Secure. / Built for India's LPG Agencies. Audience: LPG Gas Agency owners, distributors, managers across India (Indane, Bharatgas, HP Gas). Aesthetic: Swiss Minimalist + Teenage Engineering hardware HMI + modern 8-bit retro pixel art.

Colors:

Primary accent: Brand Orange #FF6B00 + orange glow
Light background: #FAFAFA / #F3F3F3
Dark sections: Charcoal #111111 / #1A1A1A
Success/inflow/paid: Green #10B981
Danger/udhari/dues: Red #EF4444
Typography (load via <link> in the root route head, not a CSS @import):

Headings: Space Grotesk
Pixel accents / section tags: Silkscreen
Data, numbers, currency, mono labels: JetBrains Mono
Body: Inter
Tone of voice: Confident, technical, hardware-manual style. Use mono prefixes like 01 //, ▶, > .

GLOBAL: THE FLAME PIPELINE (signature element)
A persistent thin vertical "gas pipeline" line runs down the left edge of the entire page (right edge on mobile, or hidden below md). A small glowing orange ember travels down this pipe, its position tied directly to scroll progress.

The pipe has 9 nodes (chapter dots), one per act. Passed nodes glow orange with a soft halo; upcoming nodes are dim grey.
Nodes are clickable — smooth-scroll to that section.
The ember leaves a faint heat trail that cools to grey behind it.
Show the current act label in tiny Silkscreen text next to the ember.
This is the scroll progress indicator AND the story's main character. Build it as one reusable component.

ACT 0 — NAVIGATION BAR (sticky)
Transparent over the hero, then on scroll becomes a frosted-glass bar with a subtle bottom border and slight shadow. Smooth transition, no layout shift.

Left: Flame icon inside a solid orange rounded box + wordmark GasAgency Hub, with tiny subtitle underneath: Smart. Simple. Secure.

Center nav links (smooth-scroll with offset for the sticky header):

Features → #features
How It Works → #how
App Workbench → #workbench
Right actions:

Login — ghost/text button → /login
Start Free Trial — solid orange button → https://wa.me/918605601801 (opens new tab, rel="noopener noreferrer")
Mobile: hamburger opening a full-screen dark overlay menu with the same links stacked large, plus both CTAs. Animate items in with stagger.

ACT 1 — HERO: THE IGNITION (above the fold)
Light background #FAFAFA. Two-column on desktop, stacked on mobile.

Cold open sequence on mount (runs once, ~1.6s total):

Screen near-empty. A single pixel flame flickers on a charcoal pedestal, center.
Above it, mono text types out character by character: > booting agency.os ...
The flame flares — and that flare sweeps a warm orange glow left-to-right across the headline, "lighting" the letters into existence rather than fading them in.
Trust pills pop in one by one, staggered, like hardware LEDs turning green.
A soft pulsing down-arrow appears at the bottom.
Left column content:

Category badge pill: ● BUILT FOR INDIA'S LPG AGENCIES (Silkscreen, orange dot with slow pulse)
H1: RUN YOUR LPG AGENCY SMARTER, FASTER & MORE PROFITABLE.
Sub: Manage bookings, customers, payments, stock, udhari, and reports from one powerful platform. Designed for India. Built for growth.
Primary CTA: Start Free Trial → → https://wa.me/918605601801
Secondary CTA: Watch Workbench → smooth-scrolls to #workbench
Trust pills row: 🛡️ 100% Secure Data · 📱 Works Offline · ☁️ Any Device · 🇮🇳 Made for India
Right column — the Studio Stage:

A charcoal pedestal with an animated floating pixel LPG cylinder (slow bob loop + soft orange ground glow that breathes in sync)
Floating HMI Card #1 (top-right): TODAY'S COLLECTION · ₹24,580 · ▲ 12% in green · caption Real-time daily inflow
Floating HMI Card #2 (bottom-left): PENDING UDHARI · ₹8,240 · ▼ 6% in red · caption 12 active customers
Floating mobile phone frame playing /promo-video.mp4 on autoplay, muted, loop, playsInline
All three floating elements drift on subtle independent parallax tied to both scroll and mouse position
Card styling: white, thin border, chunky rounded corners, JetBrains Mono numerals, tiny Silkscreen labels, soft layered shadow. Hardware-panel feel.

ACT 2 — INFINITE MARQUEE TICKER
Full-width strip, charcoal background, orange top and bottom hairline borders. Continuous seamless horizontal scroll (CSS/transform-based, never a scrollbar). Pauses on hover. Second row scrolls the opposite direction at a slightly different speed.

Badges, separated by •: LPG Sales Management • Customer Ledger • Udhari Tracking • Delivery Management • Stock Inventory • Cashbook • Business Reports • Multi-User Access • Works on Mobile • Made for India

ACT 3 — THE OLD WAY (dark, emotional low point)
Full-bleed charcoal #111111 with a subtle CRT scanline overlay and slight vignette.

A pixel-art paper register notebook sits open, center. As the user scrolls through this pinned section, the pages flip, and each flip reveals a handwritten-style pain point in pixel text:

"Ramesh — 2 cylinder — paisa baad me"
"Kitna stock bacha? Pata nahi."
"Delivery boy ka hisaab?"
"Month end… 3 din ka kaam."
Then, at the end of the pin, the pipeline ember jumps into the notebook and it burns away in a pixel dissolve — ash particles scatter, drift, and re-form into a clean ERP dashboard card.

Overlay headline appearing after the burn: THE REGISTER IS DEAD. LONG LIVE THE LEDGER.

This is the site's signature moment. Make the burn transition genuinely beautiful — staggered pixel-cell opacity + upward drift + orange-to-grey color decay.

ACT 4 — THE ASSEMBLY LINE (horizontal scroll lock)
Vertical scroll pins and translates the content horizontally — the user side-scrolls a conveyor belt. On mobile, this becomes a vertical stack of the same 9 cards.

A plain pixel LPG cylinder rides the belt. At each of 9 stations, a module bolts onto it and the cylinder becomes progressively more instrumented, ending fully glowing.

Each station shows a Teenage-Engineering-style HMI panel — chunky bezel, labeled knobs, small inset screen with live mock data:

SALES MANAGEMENT — screen shows a bill being created, total ticking to ₹24,580
CUSTOMER LEDGER — Dr/Cr rows scrolling, running balance
UDHARI / CREDIT BOOK — red dues list counting
CASHBOOK & PAYMENTS — inflow ₹4,000 green / outflow ₹2,500 red / net ₹1,500
DELIVERY MANAGER — staff pins moving along a mini route
PRODUCT & STOCK — three capacity gauges filling: 142/200, 28/60, 15/40
INFLOW & OUTFLOW — twin arrows, green up / red down
REPORTS & ANALYTICS — a bar chart drawing in
MULTI-USER & STAFF ROLES — role chips lighting up
Station index shown as 01 / 09 in Silkscreen, top-left of each panel.

ACT 5 — INTERACTIVE APP WORKBENCH (#workbench, #features)
The centerpiece. A hardware console UI — thick bezel, screw details in the corners, an inset screen, and a status LED strip. Fake browser URL bar at the top of the screen showing the current module's URL.

9 chunky physical-feeling tabs down the left (horizontal scrollable pill row on mobile). Clicking a tab: satisfying press animation (translate-y + shadow collapse), LED changes, screen content crossfades + slight scale.

Each tab renders a genuinely interactive mock — real state, real clicks:

1. Sales Management — gasagency.app/sales Record every cylinder & regulator sale instantly. View daily summaries, print receipts, and track order statuses dynamically. Working mock: customer dropdown → cylinder type selector (14.2kg Domestic ₹950, 19kg Commercial ₹1850, 5kg Chotu ₹420) → quantity stepper → payment mode toggle (Cash / UPI / Udhari) → live-calculating total → Generate Receipt button that animates a receipt printing out of the bottom of the console with a paper-tear edge.

2. Customer Ledger — gasagency.app/customers Maintain digital profiles for every customer. Check complete history of refuels, payments, and running debit/credit statements. Mock: selectable customer list — Ramesh Patil, Sunita Sharma, Amit Verma — each opening a Dr/Cr transaction table with a running balance column, green for Cr, red for Dr.

3. Udhari / Credit Book — gasagency.app/udhari Know who owes you outstanding balance at all times. Log credit receipts, collect pending dues, and send WhatsApp reminders. Mock: active dues list with amounts and days-overdue chips. Two working buttons per row: Collect Payment (row animates to paid, green, and the total drops) and Send WhatsApp Reminder (a green message bubble flies off-screen + toast confirmation).

4. Cashbook & Payments — gasagency.app/cashbook Record all incoming cash collections and outgoing expenses. Check daily cash-in-hand totals and net bank balances. Mock metrics, count-up animated: Cash Inflow ₹4,000 (green) · Cash Outflow ₹2,500 (red) · Net Cash Balance ₹1,500 · plus a small entry list.

5. Delivery Manager — gasagency.app/delivery Assign orders to delivery boys. Track active pending deliveries, route coordinates, and staff refill commissions. Mock: Raju Kumar — 3 Done, 2 Pending · Santosh Patil — All Done. Status chips, mini route line with animated moving dot, assign-order button.

6. Product & Stock Monitor — gasagency.app/products Monitor live stock levels for 14.2kg domestic, 19kg commercial, and 5kg cylinders. Auto-calculate available empty inventory. Mock: three animated capacity gauges — 14.2kg Domestic 142/200, 19kg Commercial 28/60, 5kg Cylinder 15/40. Bars fill on tab-enter; low stock turns amber/red.

7. Inflow & Outflow — gasagency.app/payments Track full cash entries separated into customer payments received (inflow) and supplier/vendor expenditures paid (outflow). Mock: split two-column ledger, green inflow left / red outflow right, with a net summary footer.

8. Reports & Analytics — gasagency.app/reports Generate professional monthly sales statements. Track revenue and credit changes, and export clean PDF/Excel documents. Mock: Monthly Revenue ₹3,24,580 · Cylinders Sold 428 · Total Udhari ₹18,240 · Net Revenue ₹3,06,340. Animated bar chart. Export PDF and Export Excel buttons showing a progress bar then a success toast.

9. Multi-User & Staff Roles — gasagency.app/users Manage permission levels for agency staff. Add managers with select reports access or operators with bill-only roles. Mock: user rows with role dropdowns (Owner / Manager / Operator) and a permission matrix of toggles that visibly change when the role changes.

Every button must do something visible. No dead buttons anywhere in the workbench.

ACT 6 — PIXEL ART DARK SHOWCASE
Full-bleed #111111, CRT scanlines, orange border accent framing the section like rack-mounted equipment.

Section tag: ▶ POWERFUL FEATURES
H2: ALL THE TOOLS YOU NEED, ONE POWERFUL PLATFORM
Copy: Designed pixel-perfect for India's LPG distributors. Web, Mobile & Tablet — all synced in real time. Works offline. Start your agency running same day.
The pipeline ember splits into three sparks that fly to three positions and ignite odometer-style count-up counters:

500+ Agencies Onboarded
99.9% System Uptime
₹0 Upfront Setup Fee
Visual: retro pixel art dashboard preview /pixel-dashboard.png, with a slow parallax float and a soft orange glow beneath it.

ACT 7 — SCROLL-DRIVEN VIDEO DEMO
A dark browser-chrome mockup — traffic-light dots, URL bar reading gasagency.app/dashboard — starts small and centered.

As the user scrolls through this pinned section, the frame zooms and scales up until it fills the viewport, and the demo video's playhead is tied to scroll position (scroll down = advance, scroll up = rewind). Once fully expanded, it releases and plays on its own autoplay loop.

Section tag: ▶ // PRODUCT DEMO
H2: See GasAgency Hub In Action.
Copy: Watch how your agency operations transform — from billing and udhari tracking to delivery management and reports. All in one dashboard, built for India.
Video source: /promo-video.mp4
Mobile fallback: standard autoplay muted loop video in the frame, no scroll scrubbing.
ACT 8 — HOW IT WORKS (#how, sticky stacked cards)
Four cards that pin and stack — each card sticks, is read, then the next slides up and covers it, like dealing cards onto a table. Slight scale-down and dim on the card being covered.

Section tag: 02 // SIMPLE PROCESS
H2: Up & Running In 4 Easy Steps.
Cards:

01 // SETUP — Register Your Agency — Create your agency account with a unique code in minutes. Zero technical overhead required.
02 // INGEST — Add Customer Profiles — Import or quickly add existing customer ledgers with contact info and running balance history.
03 // ENGINE — Record Cylinder Sales — Log daily refill bookings, collect payments, and auto-track credit udharis across any device.
04 // REPORT — Export & Audit Dues — Monitor real-time cash flow, print statement PDFs, and keep your agency 100% audit compliant.
Each card: huge ghosted pixel numeral in the background, Silkscreen tag, Space Grotesk title, Inter body, orange accent edge. The pipeline ember pulses harder with each step — the fire strengthens as the agency gets organized.

Below the stack: pixel art feature icon grid banner /pixel-features.png.

ACT 9 — FINAL CTA: THE CITY LIGHTS UP
Three-layer parallax over a pixel-art city skyline with all windows initially dark. A pixel LPG delivery truck /pixel-truck.png drives in from the left on a loop across /pixel-cityscape.png.

As the user scrolls the final stretch, the pipeline ember reaches the bottom, enters the truck, and the truck's route lights the city — windows flick on house by house, block by block, in warm orange, staggered along the truck's path.

Over the lit city:

Section tag: 03 // READY TO START
H2: READY TO TRANSFORM YOUR GAS AGENCY?
Sub: Start your free trial today. No credit card required. No setup fees. Just your agency, running smarter.
Compact embedded demo video with a ● LIVE DEMO pill badge (red pulsing dot)
Badge row: No Credit Card · Works Offline · Any Device · Made in India
Primary button: Start Free Trial → → https://wa.me/918605601801?text=Hello%20Jayesh%2C%20I%20want%20to%20start%20a%20free%20trial%20for%20LPG%20Agency%20ERP.
Secondary button: Agency Login → /login
ACT 10 — FOOTER
The city continues down into the footer at ground level. Charcoal background.

Brand block: Flame logo + GasAgency Hub · India's trusted LPG gas agency management platform. Engineered for speed, reliability, and growth. · Status badge: LIVE SYS.ACTIVE with a blinking green dot.

Columns:

Product: Features (#features), Live Demo (#demo), Analytics (#workbench), How It Works (#how)
Support: Contact Us → https://wa.me/918605601801 · Email Support → mailto:jayeshneo07@gmail.com · Documentation
Made in India: Designed & built for Indian LPG distributors + pixel India flag badge /pixel-india.png
Bottom bar: © 2026 GasAgency Hub. All rights reserved. | Agency Login (/login) | Start Free Trial (WhatsApp)

Pipeline pipe terminates here with a final node labeled EOF.

ASSETS TO GENERATE
Generate these as pixel-art / retro 8-bit style images matching the orange-on-charcoal brand:

/pixel-dashboard.png — retro pixel ERP dashboard preview
/pixel-features.png — pixel feature icon grid banner
/pixel-cityscape.png — pixel Indian city skyline, windows dark
/pixel-truck.png — pixel LPG delivery truck, side view, transparent background
/pixel-india.png — small pixel India flag badge, transparent background
Pixel LPG cylinder sprite for the hero and assembly line, transparent background
Pixel paper register notebook for Act 3, transparent background
If /promo-video.mp4 is not present, use an elegant animated dashboard mock in the video frames instead of a broken video element — never show a broken player.

QUALITY BAR — NON-NEGOTIABLE
Every single button, link, tab, and toggle must work. Zero dead controls.
All external links open in a new tab with rel="noopener noreferrer".
All anchor links smooth-scroll with correct sticky-header offset.
Scroll animations must be spring-damped and 60fps — only animate transform and opacity.
Fully responsive at 360px, 768px, 1024px, 1440px, 1920px.
No layout shift on load. Reserve space for images and video.
No generic AI aesthetic — no Inter-only headings, no purple gradients, no interchangeable card grids. Commit to the Swiss + hardware-HMI + pixel-art direction on every single section.
Add toast notifications (sonner) for the workbench actions, mounted once in the root route.
Every currency figure in JetBrains Mono with proper Indian formatting (₹3,24,580 style).
Build it act by act and verify each act renders correctly before moving to the next.

This project was built with [Lovable](https://lovable.dev).

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/ecf85c4f-2e10-4610-b030-c414c19daf70).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```
