# CODEX MASTER BUILD PROMPT — OASIS STAR GENERAL TRADING

> PROJECT: Premium, conversion-focused UAE B2B industrial PPE website, searchable technical catalogue, and multi-item Request for Quotation (RFQ) system.
> DELIVERY: Production-quality codebase + repository + tests + deployment configuration + clear handoff.
> INPUTS: This prompt; **two visual reference images attached to the Codex conversation**; optionally `Oasis-Star-PPE-Research.md`, the logo, and supplier PDFs/images if available.
> CRITICAL: The two reference images are design inputs, not a request to reproduce copyrighted sites verbatim. Analyze them before choosing the visual system. The research below is business/product source material, not authorization to invent facts.

## 0. YOUR ROLE, AUTONOMY, AND OPERATING RULES

You are the combined principal product designer, design-systems engineer, senior full-stack developer, CRO strategist, technical B2B copywriter, accessibility specialist, performance engineer, QA lead, and pragmatic deployment engineer for Oasis Star General Trading. Work as if this is a real client deliverable competing with the best modern industrial suppliers. Design originality, visual polish, trust, accuracy, conversion, and reliable delivery all matter.

**Do not merely outline or mock up the website. Implement it end-to-end in the workspace.** Inspect existing files before modifying them. If a repository already exists, use it unless asked otherwise. If this is a fresh project and GitHub access is authorized, create **one clean repository for this project**, with continuous deployment (not a new repository for each iteration). Make progress without asking routine questions; record reasonable decisions in `DECISIONS.md`. Ask only if a blocked external action, irreversible change, missing credential, or fact requiring business sign-off genuinely prevents the next step. Do not falsely claim to have deployed, tested, connected accounts, or received emails.

Operate in small, verifiable increments. Keep command output short; never dump full pages, source trees, PDFs, logs, or huge JSON into the chat. Aim for **<100 KB per returned tool output**, with a firm ceiling of 1 MB; prefer targeted commands, summaries, bounded file reads, and filtered searches. If a tool reports `decoded message length too large` (4 MiB), split the work and reduce tool output. Store long artifacts in files and refer to paths instead of printing their contents. Do not embed images as base64 in conversation messages.

**Hardware/budget constraint:** The project owner has a Windows 10/11 machine with very limited free C: storage and prefers a lean, free-tier-friendly workflow. Prefer cloud workspaces / hosted builds when available; do not require Docker, a local browser download, large design tools, or GB-scale installs on the owner's laptop. If a local dependency install is unavoidable, warn before it consumes disk space. Use the fewest sensible dependencies, the least JavaScript possible, and optimized static assets. Favor Vercel + Supabase free tiers unless existing connected infrastructure makes an equivalent solution clearly better. Do not incur paid charges or create billable resources without approval.

### Explicit non-goals
- NO public shopping checkout, payment gateway, public payment collection, banking details, or consumer retail workflow.
- NO fabricated live stock, prices, approved distributor status, certificates, case studies, testimonials, customer logos, delivery SLAs, product photos, or operational metrics.
- NO generic unstyled CRUD dashboard, default SaaS starter hero, or cookie-cutter safety website.
- NO copying reference image content, trademarked UI illustrations, competitors' proprietary source code, or third-party sales contact details.
- NO autonomous changes to existing production DNS, email records, existing live sites, or sensitive credentials.

## 1. PROJECT MISSION & BUSINESS REALITY

**Brand:** Oasis Star General Trading, United Arab Emirates.
**Primary domain (to be connected only with permission):** `oasisstargt.com`.
**Existing historic demo (for comparison, not a canonical source):** `https://oasis-star.netlify.app/`.
**Brand system from the source logo:** royal blue, red accents, black text; growth/bar-chart + swoosh symbol. Use the actual logo if supplied; do not invent a fake replacement. The slogan historically used is **“Choose Oasis Star. Choose Safety That Lasts.”** Another company phrase is **“Your Safety, Our Priority.”** Keep brand copy professional, credible, and restrained rather than cliché-heavy.

Oasis Star sells PPE, industrial safety products, and intrinsically safe communication devices to UAE business buyers. Main sectors: construction and infrastructure; oil and gas; refineries and petrochemicals; industrial maintenance; chemical handling; shipyards; logistics and warehousing; automotive workshops. Fast-moving commercial categories: **safety gloves, safety footwear, high-visibility vests**; featured high-value products include flame-resistant coveralls, H₂S escape equipment, and Ex-rated smartphones.

**Agreed purchasing model:** B2B digital product catalogue + **build-a-quote basket** + structured RFQ form + supplier follow-up by email/WhatsApp. Buyers select multiple products and specify quantity, sizes, and other details; the small sales team receives one coherent inquiry and responds with a formal quotation. There is no web checkout. A tiny team (approximately two staff; no in-house IT) needs an extremely simple operating model.

**Audience and jobs to be done:**
1. Procurement officer: find exact SKU and standards; assemble a multi-product bulk inquiry quickly; obtain an email trail and reference number.
2. HSE / safety manager: inspect protection class, standards, documents, size variants, and suitability without relying on unsupported marketing language.
3. Site supervisor / contractor: rapidly request replenishment or mobilization quantities from mobile, often via WhatsApp.
4. Oasis Star staff: receive complete RFQs without needless manual re-entry; track requests through a manageable free-tier backend.

**Top-level business outcomes:** Drive legitimate, qualified quote requests; make technical product discovery effortless; build trust through accurate specs and traceable PDFs; minimize operating cost; enable future updates without rebuilding the entire site.

**Commercially private information:** Past project proposals (AED 6,500 / 9,500 setup, monthly maintenance, payment splits, launch timelines) concern the WEBSITE SERVICES CONTRACT, not the PPE merchandise. They must never be exposed on the public website, in frontend code, seed data, metadata, or generated marketing copy.

## 2. REFERENCE IMAGE ANALYSIS — MANDATORY BEFORE DESIGN

**Two reference images will be attached with this prompt.** Do not claim to have seen either until you actually inspect the attachments.

For EACH image, write a concise private design observation in `DESIGN_REFERENCE_ANALYSIS.md`, including:
- What is visibly present: layout grid, content density, hero composition, navigation, typography scale, whitespace, radius, border treatment, shadows, colors, material, imagery, iconography, button hierarchy, cards, and responsive cues.
- What feels premium or memorable, what is only decorative, and what might hinder B2B clarity or accessibility.
- Reusable *principles* and the specific sections/components to which they would apply.
- Which elements must NOT be copied (logos, brand-specific assets, protected visual compositions, labels, product claims, screenshots).

Then create a **single coherent blended direction**. Do not blindly clone either image and do not build two competing styles. Unless the images make a clear better case, prefer a confident industrial/editorial aesthetic with crisp geometry, generous breathing room, premium product macro imagery, deep blue technical typography, warm white or cool neutral surfaces, highly selective red accents, and elegant restrained motion. Use Oasis Star's actual visual identity as final authority for logo and brand colors. Images are aesthetic guidance, **not** evidence of Oasis Star's products, stock, certifications, or capabilities.

If one image is a logo/product image and the other is a website screenshot, treat them according to their actual roles: brand/product truth vs. layout/mood reference. If references are unavailable in the workspace, **do not pretend**; record this as a blocker to final visual parity, proceed with a competent design baseline, and state exactly how to supply them later.

### Design quality gate
Deliver a page that a discerning creative director would call purposeful and complete, not a template. Define design tokens and a component system first. The site should feel premium in the first viewport and remain coherent on the catalogue, technical details, RFQ form, and contact pages. Maintain high contrast, semantic structure, and sensible motion; a beautiful site that frustrates a procurement buyer fails.

## 3. RECOMMENDED IMPLEMENTATION & DEPLOYMENT

Prefer the following proven, manageable stack, adjusting only if the existing project or tool capabilities strongly justify a change:
- **Next.js App Router + TypeScript**: server-rendered/SEO-friendly catalogue, dynamic metadata, API routes, Vercel integration. Pin mutually compatible current stable releases; confirm exact installed versions from package manager rather than assuming.
- **Tailwind CSS** with an organized token layer via CSS variables; build accessible reusable UI components. Use a lightweight icon library only if genuinely useful.
- Use **CSS transitions** by default and a motion library only for interactions CSS cannot implement cleanly. Respect `prefers-reduced-motion`.
- **Supabase PostgreSQL** for durable RFQ storage. Enforce RLS; use secret service-role credentials on server only. Do not expose them in client bundles.
- **Vercel** for hosting, preview deployments per PR, and production auto-deployment from the approved `main` branch. Use GitHub integration, not manual uploads as the normal workflow.
- Optional transactional email provider only if connected and configured; save to database first, then notify. Do not leak sales submissions in public logs. Email delivery failure must not destroy an RFQ.
- Use one package manager with a lockfile. No Docker, heavyweight CMS, background queue, payments SDK, or unnecessary animation frameworks.

**Alternative if storage/build cost is a hard blocker:** Use Astro or a lighter static-first framework with serverless RFQ APIs, while preserving server-rendered catalogue SEO and the same feature/acceptance requirements. Explain the tradeoff in `DECISIONS.md`. Avoid framework churn once work begins.

**Deployment scope:** If GitHub/Vercel/Supabase integrations are authorized and tools are available, create/configure only the necessary project resources and connect them. If access is missing, still create all deployable source files, schema migrations, environment variable example, workflows, and step-by-step setup instructions; distinguish **prepared** from **deployed**. Never request passwords in chat or store them in Git.

## 4. SITEMAP / NAVIGATION INFORMATION ARCHITECTURE

Required production routes, adjusting slugs while preserving navigation clarity:
- `/` — premium, purposeful homepage.
- `/products` — full searchable/filterable catalogue.
- `/products/[slug]` — fact-rich technical product page for each published SKU.
- `/categories/[slug]` — category landing pages (where useful, not a maze of duplicate SEO pages).
- `/brands` and `/brands/[slug]` — brand exploration **without implying authorized dealership** unless confirmed.
- `/industries` and optionally `/industries/[slug]` — task-oriented industry applications, careful with compliance claims.
- `/about` — what Oasis Star supplies, buyer approach, industries; no fictitious founding year, warehouse, team photos, awards, or named customers.
- `/resources` or `/certifications` — approved datasheets and evidence; clear differentiation between manufacturer standards, third-party certifications, and buyer verification.
- `/quote` — RFQ basket and request form.
- `/contact` — sales inquiries and contact preferences.
- `/privacy` and `/terms` — jurisdiction-appropriate initial drafts visibly marked for legal review before publication; do not present unreviewed legal language as final.
- Custom not-found and graceful error states.

Navigation: small, focused global header (Products, Categories/Industries, Brands, About, Contact), persistent but unobtrusive **Request Quote** control showing basket count; comprehensive footer with actual/provisionally approved contact methods and company identity. Mobile navigation must be fast and accessible. Breadcrumbs on category and product pages.

## 5. HOMEPAGE — VISUAL / CONTENT SPECIFICATION

Build an original art-directed layout using the two image references, with these conversion functions:

**A. Header:** Logo with alt text, clear navigation, menu accessible by keyboard, high-visibility `Request a Quote` CTA, optional icon-only search with proper label. Header must work when scrolled and on narrow screens; avoid giant sticky bars.

**B. Hero:** Premium industrial brand presentation, elevated product or workplace imagery only when approved/licensed; otherwise tasteful original geometry and CSS art. Specific headline such as `Industrial protection. Procurement made simpler.` or a more compelling research-consistent variant. Subheading makes UAE B2B PPE scope clear. Dual CTA: `Explore Products` and `Build a Quote`. Visually communicate technical trust without fabricated ISO claims or imaginary metrics. Use photo/image treatment, typography, and spacing derived from the two references.

**C. Fast procurement bar:** Three truthful, concise buyer advantages: standards-aware technical info, multi-item quote requests, direct sales response. Never promise `2-hour quotes`, `same-day shipping`, or `always in stock` without approval.

**D. Category navigation:** Distinct, art-directed cards for hand protection, foot protection, body/FR workwear, eye protection, respiratory/emergency escape, and hazardous-area communications. Do not invent full head protection products just to complete a grid. Category naming should reflect actual inventory.

**E. Priority products:** Feature high-demand gloves, Red Wing shoes, Taedylinn vests if confirmed SKUs, and selected documented equipment. Every featured product must have a real or expressly provisional model; missing product photos use honest branded placeholders, not misleading unrelated stock photos.

**F. Sector stories:** Construction, oil & gas, petrochemical/industrial, logistics and maintenance. Show actual problem/solution pairings, not sweeping compliance guarantees. Provide clear links to relevant categories.

**G. Technical credibility strip:** Highlight documentation/standards navigation and sourcing process. Show standards only beside matching, verified products. If certification PDFs are missing, explain `Documentation available on request` rather than a fake download icon.

**H. How RFQ works:** 3 steps: choose products -> specify quantities -> sales team provides a quote. Illustrate elegantly with UI or minimal diagrams, not busy cartoons.

**I. Brand/product discovery:** Logos and manufacturer names only where use and commercial relationship are approved; otherwise neutral text chips or approved product brand labels, without fake `Official Partner` language.

**J. Final conversion module:** Bespoke, visible CTA aimed at sourcing many PPE items in a single request; alternative WhatsApp channel if final number is approved.

Footer: succinct navigation, relevant categories, approved contact data, location only as verified, legal links. No unverified street address or social media accounts.

## 6. CATALOGUE EXPERIENCE — BUILT FOR REAL PROCUREMENT

Build robust, accessible product discovery, not a fashion shop:
- Text search across manufacturer, model number, name, categories, use cases, and selected standards. Model identifiers such as `R-267`, `48-920`, `3228`, and `Smart-Ex 03` must work.
- Filters where data exists: protection category, manufacturer, application/industry, technical standard, cut/impact class, foot size, garment size, available color, optionally pack unit.
- Filters must not show fictional options; dynamic counts, reset all, readable active chips, empty state and typo recovery. Encode state in URL parameters where practical.
- Sorting (alphabetical, category, featured) **without fake price or bestseller ranks**.
- Product cards: credible image/placeholder; product and brand; exact model; one or two verified proof points; category; `View Specs` plus `Add to Quote`/`Select Options`; never `Buy Now`.
- Product data is structured; filters derive from attributes, not a mass of ad-hoc hardcoding.
- Product page: image gallery (licensed/approved images only), accurate brand/model heading, concise application guidance, standards, detailed specifications in readable key/value table, available variants/sizes if documented, packaging quantity if known, PDF technical documents if present, compatibility/caution text, related items, persistent or nearby RFQ CTA.
- Clear distinction: product technical specs vs. test-standard information vs. formal certificate/PDF. A standard named in a brochure is NOT evidence that Oasis Star has a downloadable certificate.
- No publicly displayed numeric prices until an approved price list and pricing policy are supplied. Show `Request bulk pricing` instead.
- Avoid all-caps price-scarcity marketing and faux stock badges. New arrivals or stock information only with verified inventory and timestamps.
- On a small viewport, the catalogue must feel intentionally designed, with usable filters and persistent access to the quote basket.

### Categories (controlled taxonomy)
1. Hand Protection: impact, cut, general handling, chemical gloves.
2. Foot Protection: industrial safety boots, safety trainers.
3. Body Protection: FR/anti-static coveralls, protective coveralls, high-vis vests, jackets where applicable.
4. Eye Protection: safety eyewear; lens variants only when documented.
5. Respiratory & Emergency Escape: H₂S escape hood.
6. Intrinsically Safe Communications: hazardous-area-certified mobile devices.

Use category slugs that are descriptive and stable. Category introductions should be genuinely helpful for buyers and search, not SEO stuffing.

## 7. PRODUCT DATA — SOURCE-GROUNDED LAUNCH CONTENT

The research file describes an initial **20-model plan**: Ansell/Ringers gloves x3, ATG gloves x3, Red Wing safety shoes x3, Red Wing coveralls x3, ecom Smart-Ex 03 camera and camera-free x2, Taedylinn vests x2, Taedylinn coverall x1, Reebok Work shoes x3. Later source messages expand the potential catalogue. **DO NOT fabricate model names** to force 20 public cards. Seed all well-identified products below as candidate records, make publication contingent on verified/approved content, and maintain a separate `CONTENT_GAPS.md` for missing variants, images, PDFs, pricing, and dealer permissions. Missing-model ranges can be `draft`/`coming from supplier` in INTERNAL DATA ONLY — not fake public products.

### Foot protection
- **Red Wing Petroking 3228**, 6-inch boot: waxed Nubuck leather, waterproof, nonmetallic safety toe, puncture-resistant Swen-Flex insole, nylon shank, electrical hazard (EH), slip/heat resistant outsole; sizes EU 35-48; made in Italy. Research cites `AS 2210.3:2019`, `ASTM F2413-24`, `EN ISO 20345:2022+A1:2024`. Confirm exact rating and claims against the manufacturer datasheet before publication.
- **Red Wing Petroking 3229**, 8-inch boot: taller boot platform, black Nubuck, EH, puncture-resistant, nonmetallic toe, slip/heat/chemical resistance described in source; EU 35-48. Do not copy every 3228 feature blindly—verify model sheet.
- **Red Wing 6338**, men's athletic safety footwear: breathable nylon/mesh, aluminium safety toe, EH/slip-resistant, rubber-EVA outsole; source claims `ASTM F2413-24 I/C, EH, SR`; US size widths D/E/H with ranges D 7-15, E 7-15, H 8-13. Made in Vietnam per flyer. Verify before publishing.
- **Reebok Work**, three models proposed, but actual model names and datasheets NOT PROVIDED. Do not invent.

### Hand protection — Ansell/Ringers
Possible product records below. Publish specs only as traceable to supplied documentation and preserve exact standards character-for-character:
- **R-065 R-Flex Half-Dip**: HPPE 13-gauge knit; TPR bumpers, sandy nitrile palm, touchscreen tips; `EN 388 4X43DP`; `ANSI/ISEA 138 Level 2`, ANSI cut A4; 72 pairs/carton.
- **R-068 R-Flex Full-Dip**: double-dip nitrile; cut, impact, liquid resistance; `EN 388 4X44FP`; ANSI impact L2; 60 pairs/carton.
- **R-085 R-Flex Fleece**: fleece-lined cut/impact/cold; `EN 388 4X44FP`; impact L2; 48 pairs/carton.
- **R-176 Super Hero Insulated**: waterproof cold-protection glove, 70-g Thinsulate, gaiter cuff, `EN 511 121`, `EN 388 3X44FP`, impact L2; 50 pairs/carton.
- **R-259**: synthetic leather palm, Kevlar stitching, neoprene cuff; `EN 388 4X44EP`, impact L2; 50 pairs/carton.
- **R-259B Barrier**: waterproof barrier, reflective piping; `EN 511 021`, `EN 388 4X44FP`, ANSI cut A5, impact L2; 50 pairs/carton.
- **R-267**: TefLoc / silicone-dot grip, Kevlar liner, impact TPR, high-vis; `EN 388 4243BP`, impact L2; source lists XS-4XL; 50 pairs/carton.
- **R-297**: KevLoc palm, enhanced grip; `EN 388 4343CP`, impact L2; 50 pairs/carton.
- **R-665 R-Hide Impact**: goatskin leather, hook-and-loop cuff; `EN 388 3X42EP`; 50 pairs/carton; no impact level established in source.
- **R-840**: lightweight impact glove, 15-g nylon/spandex, FORTIX / ERGOFORM; `EN 388 4131AP`, ANSI impact L1. Research calls it CE Category III; verify brochure and exact model before using this claim.
- **R-138**: visibility/mechanics glove, touchscreen; `EN 388 2121X`.
- **R-133**: tactile mechanics glove, synthetic split leather; `EN 388 2121X`.

### General & chemical handling gloves
- **Ansell EDGE 48-123**: black, 13-g polyester, seamless dry/slightly oily handling glove.
- **Ansell EDGE 48-126**: economical black, 15-g polyester.
- **Ansell EDGE 48-920**: nitrile rubber (NBR) coating for abrasion/oily handling; research cites EN 420 / EN 388; exact edition/results need verification.
- **Ansell HyFlex 11-561**: cut-resistant, FORTIX-related design, verify model sheet and ratings.
- **Ansell HyFlex 11-840**: lightweight mechanical handling; **144 pairs/case** in the research.
- **Ansell AlphaTec Solvex 37-675**: flocked nitrile, approximately 0.38 mm, for specified chemical-handling/cleaning/maintenance applications. Do NOT assert universal chemical protection, lack of dermatitis, or compatibility without the official permeation chart and use instructions.
- **ATG**: three requested glove models, unspecified; do not invent SKU names or certification.

### Body protection and eyewear
- **Taedylinn W2849**, lightweight FR anti-static coverall, 210 gsm nominal, Bizflame Plus 99% cotton / 1% carbon fibre; EN 1149-5, EN ISO 11612 (A1+A2,B1,C1,F1), EN ISO 11611 Class 1 in technical description. Orange, royal blue and red listed; XS-4XL; reflective tape, two-way zipper, radio loops, pockets, knee-pad accommodation. **Source contains a discrepancy**: `EN ISO 11611 Class 1` in standards, but a feature line references `Class 2 welding protection`. DO NOT publish Class 2 until source is reconciled. The research contains third-party test details; use only with matching approved datasheet.
- **Taedylinn high-visibility vests**, two intended models but exact IDs not provided. Keep internal draft records only.
- **Red Wing coveralls**, three models requested but IDs/datasheets missing. Internal drafts only.
- **Red Wing insulated black jacket**: model not confirmed, optional candidate if approved; do not treat cold-weather item as a UAE fast mover.
- **Red Wing safety eyewear**: clear/yellow/smoke/indoor-outdoor lens options in source; no individual SKU IDs. Use as a category teaser or inquiry-only item until documented.

### H₂S escape and hazardous-area devices
- **Avon Protection NH15 H₂S Filter Escape Hood**: a specialized emergency escape product. Research mentions 625 g, compact pack, sizes XS/Regular/Large, 5-year shelf life, and certain test/certification claims; emergency escape capability depends on approved manufacturer instructions and service conditions. **Safety-critical claims** like protection duration/concentration, breathing-gas applicability, donning time, maintenance, regulatory approvals, and gas list MUST be validated against the official current brochure and jurisdiction-specific approvals BEFORE publication. Never portray as general respiratory protection, SCBA equivalent, or safe for all incidents. Show approved application notes and prominent `Refer to manufacturer instructions` notice.
- **ecom / Pepperl+Fuchs Smart-Ex 03 DZ1**: intrinsically safe smartphone, source claims Zone 1/21 and Division 1, Android 13 at source date, 6-inch gloved-use screen, 8GB/128GB, 5G, 4,400 mAh, programmable PTT/alarm, Lone Worker Protection. Source says two market versions: **with camera / camera-free**. Verify availability and precise certifications per regional variant; DO NOT claim a camera-free model automatically satisfies each site’s entry rules.
- **ecom Ex-Handy 10**: CLIENT EXPLICITLY SAYS **DISCONTINUED**. Never show it as an orderable product or include it in the public current catalogue. If SEO strategy includes a replacement-help page, label discontinued clearly and redirect the buyer toward Smart-Ex 03 after compatibility verification.

### Brand roster
Ansell / Ringers, ATG, Red Wing, Reebok Work, Taedylinn, Pepperl+Fuchs/ecom, Avon Protection. They are product/manufacturer names; **the business's authorized distribution rights are unverified**. Do not show official partner/dealer badges or copy official manufacturer sites without permission.

### Trust and content approval model
Every product field should have `value`, `source` or internal evidence pointer, `verificationStatus` (verified / requires-review / unavailable), and optionally `lastReviewed`. An item is publishable only when it has a reliable model name, appropriate approved copy, and no materially unresolved safety claims. Place undocumented brochure-specific details behind an internal review flag instead of displaying them automatically. Publication must be safe by default.

## 8. RFQ BASKET — COMPLETE USER FLOW

This is the central feature, NOT secondary decoration.

**Adding products:** On a product card or detail page, buyer chooses options only if they exist (size, color, model variation), specifies quantity and unit (`pairs`, `pieces`, `cartons/cases` where packaging size is known), then adds to a persistent quote basket. Defaults must be sensible (e.g. 1 piece/pair) but never silently assume carton conversion. A product can have separate line items for different sizes/variants. Display exact unit and pack ratio when documented.

**Basket:** Persistent in browser across refresh (localStorage acceptable); editable quantities, merge only genuinely identical variants, remove/undo, empty state, clear basket with confirmation, subtotal of line counts/quantities but NO prices. Show a clean summary formatted for purchasing teams. Keep sensitive buyer data out of localStorage unless there is a strong reason to persist it.

**Request form:** Company name, contact person's name, business email, phone/WhatsApp, delivery emirate/city, industry/use case (optional), company purchase requirements/notes, preferred contact method, acceptance of privacy notice. Validate both client-side and server-side. Format UAE numbers sensibly but allow international buyers. Support specific lines/requirements like `50 pairs R-267 size L` and mixed-SKU requests. Provide excellent mobile keyboard/input types and clear errors.

**Submission:** `POST /api/quotes` (or equivalent secure endpoint) -> strict schema validation -> product ID lookup/whitelist from server-trusted catalogue -> sensible max quantities/request size -> spam controls (honeypot, basic rate limiting, optional managed challenge if abuse warrants) -> store one durable record and all line items atomically in Supabase -> return a unique human-readable RFQ reference and success screen. The endpoint must not accept the unit price, inventory state, certification, or email recipient from untrusted client input as truth. Never falsely show success if persistence failed.

**Notifications:** The quote must be in Supabase even if staff email fails. If transactional email is configured and authorized, send a formatted staff alert containing reference, company/contact info, lines, qty/variant, notes, and link to a secure staff workflow. Optional buyer acknowledgement with reference number. Email must not contain supplier-only internal notes. Log notification status without leaking PII into public logs. If no email service is configured, show clearly in admin/handoff that notification is not yet live and support staff viewing RFQs via Supabase dashboard.

**WhatsApp:** Persistent secondary path, not a replacement for the structured lead. An approved company WhatsApp link may open `wa.me` with concise, URL-encoded product list, quantities, and RFQ introduction, NEVER automatically send a message. The research mentions a proposed new contact number but flags contact updates and client confirmation; treat any supplied number as **provisional** and require approval before publicly embedding it. Do not reuse a third-party showroom or supplier phone number for Oasis Star customer contact.

**Failure states:** DB outage, rate limit, invalid product, expired draft, no connectivity, missing environment config, empty basket, stale product variants, notification failure. Preserve basket and entered form fields on error; show a concrete recovery action. Do not send duplicate requests on repeated clicks. Add per-request idempotency key or equivalent duplicate mitigation. Never require a sign-in for RFQ.

**Business workflow after submission:** Status labels like `new`, `reviewing`, `quoted`, `closed` in the database. At launch, staff may manage through access-controlled Supabase dashboard; avoid building a large custom admin that a 2-person company cannot maintain. If a tiny staff interface is clearly low-risk and feasible, create it only with real authentication, verified server authorization, and no anonymous read of leads.

## 9. SUPABASE SCHEMA / SECURITY / OPERABILITY

Provide checked-in, idempotent SQL migrations (and/or Supabase CLI migrations if appropriate) for a lean schema:
- `quote_requests`: UUID primary key, public-safe unique reference, buyer/company/contact fields, delivery location, preferred channel, notes, server-recorded timestamps, status, spam metadata with minimum retention, notification status, idempotency token/hash if used.
- `quote_items`: UUID, FK to quote request, product ID/slug and snapshot brand/model/name, sanitized SKU/options, positive integer quantity, unit, documented pack size at request time, optional line note. Never mutate historical quote snapshots when catalogue changes.
- Optional: `contact_inquiries` if distinct from RFQs; avoid unnecessary tables if a quote-like inquiry can be represented safely.
- Product catalog: start with a validated, version-controlled typed dataset for the initial launch (best for low maintenance and SEO) unless verified requirements call for a database-managed catalog. Define a migration path to Supabase products later without duplicating sources of truth.

Supabase RLS: enable on all exposed tables. No unauthenticated SELECT/UPDATE/DELETE on lead data. Server submission uses service credentials from the SERVER environment only, ideally via a narrowly scoped endpoint and robust validation. If using service-role bypass, explain blast radius and keep secrets outside client. Staff access must go through Supabase auth/dashboard or a documented role-protected admin. Provide `ENVIRONMENT.md` and `.env.example` with names ONLY, never real values. Example variables: `NEXT_PUBLIC_SITE_URL`, `SUPABASE_URL`, `SUPABASE_SERVICE_ROLE_KEY`, `SALES_NOTIFICATION_EMAIL`, `EMAIL_API_KEY`, `APPROVED_WHATSAPP_NUMBER` (adjust to actual stack). Do not prefix secrets with `NEXT_PUBLIC_`.

Write a SQL schema/ERD explanation, deployment checklist, and at least one test demonstrating anonymous requests cannot enumerate stored quotes. Limit PII retention to what is required for RFQs, and include privacy disclosures about processing buyer contact details.

## 10. CONTACT, DOMAIN, DNS, EMAIL DELIVERABILITY

The research records an `info@...` Microsoft 365/Outlook address that has been landing in recipients' spam. **Its complete exact address is not provided in this prompt**; never infer it from the domain or place an invented contact email on the site. Use a clearly configurable approved address, and track final sign-off in `CONTENT_GAPS.md`.

Create a **non-destructive** domain/email checklist:
- Confirm exact domain/account ownership and approval before changes.
- Inspect current DNS records without publishing credentials. Verify MX routing, SPF **single-record** syntax and correct Microsoft 365 sender authorization, DKIM selectors and activation, DMARC record/alignment/reporting and a cautious staged policy. Assess reverse-path/sender, reputation, and bounce handling when evidence allows.
- Never overwrite unrelated MX/SPF/DKIM/DMARC records or change a live tenant blindly. Do not claim the spam problem is fixed solely because records are syntactically present.
- If using a separate transactional mail sender, document required DNS validation and SPF/DKIM interactions; prefer a distinct, verified subdomain if appropriate.
- Website domain: connect `oasisstargt.com` to the approved Vercel project with redirect/canonical host strategy, only after authorization, testing, and DNS backup. Preserve existing email MX records.

## 11. DESIGN SYSTEM / MOTION / A11Y

Build an explicit design language grounded in the references:
- Color tokens: primary royal blue (brand-appropriate), deep navy for credibility, high-contrast ink, warm white and technical neutral grays, strategic red accents. Provide exact HEX values **after examining actual logo/reference images** and checking contrast; do not choose blindly if logo is provided.
- Type: expressive but readable display typography for important headings; crisp sans for body, tables, and model IDs. Self-host/optimize fonts where legally licensed and avoid loading many families/weights. Use `font-display: swap` and native system fallback.
- Grid: 12-column desktop concept, strong alignment, editorial whitespace; responsive fluid type and sane max content widths. Grid/cards must not collapse into cramped mobile tiles.
- Components: navigation, buttons, category tiles, product cards, spec tables, standards badges (only grounded), search/filter controls, chips, toast notifications, quote drawer/cart, form controls, tabs/accordions, responsive footer, document link card, skeletons and empty states.
- Motion: elegant first-load reveal on key modules, hover/focus responsiveness, purposeful quote-add microinteraction, transitions between product/card states; no excessive parallax, scroll-jacking, sound, autoplay video or large JS animations. All effects disabled or simplified under reduced motion. Smooth, not distracting.
- Imagery: approved product photos and original/legally licensed industrial imagery; robust fallbacks with graphic texture rather than generic random safety imagery; do not remotely hotlink unlicensed manufacturer shots.
- A11y: semantic landmarks and headings, keyboard complete, proper focus order/visible focus, skip link, aria only where necessary, contrast aiming WCAG 2.2 AA, form errors announced accessibly, 44px-ish touch targets, no motion-dependent information, responsive tables scroll with visible affordance, no color-only classification.
- Internationalization: English launch now; content structure, layout, field labels, and CSS should be **Arabic/RTL-ready for phase 2** but DO NOT present an incomplete machine-translated Arabic toggle as functional. Avoid claiming bilingual launch until commissioned and reviewed.

## 12. CONTENT, CONVERSION, AND SEARCH GUIDELINES

Write as a helpful industrial supplier, not as a dropshipping storefront:
- Direct, factual, confidently understated, task- and standard-oriented.
- Button labels show consequences (`Add to Quote`, `Request Bulk Pricing`, `View Technical Details`, `Download Datasheet` only if actual file exists).
- Explain cut and impact classes accurately; don't mix EN 388 digits/letters with US ANSI A-levels.
- Include a clear `Check site-specific PPE requirements and the manufacturer's latest datasheet` cue in appropriate safety-critical contexts.
- No `completely safe`, `guaranteed protection`, `approved for all hazardous areas`, `dermatitis-free`, or absolute performance promises.
- Do not assert `authorized distributor`, `in stock`, `same day`, `largest`, `lowest price`, or quote turnaround promises without proof.
- Allow a `Bulk procurement?` CTA on every important conversion page and cross-sell relevant related items by actual use case (e.g., gloves + boots + eyewear; FR clothing + escape equipment where relevant and approved).
- SEO basics: unique titles/descriptions, canonical URLs, sensible headings, sitemap, robots, alt text, stable product slugs, Open Graph/Twitter image generated from approved branding, structured data only for factual Organization / BreadcrumbList / Product properties. Do NOT emit fake reviews, ratings, prices, offers or availability. Keep metadata readable, not keyword stuffed.
- Performance goals: target good Core Web Vitals (LCP <= 2.5 s on typical mobile, CLS <= 0.1, INP <= 200 ms as measurement objectives, not untested claims). Favor static/server-rendered content, lean JS, compressed assets, responsive `<Image>` sizes, no layout shift, lazy below-fold images, and caching appropriate to product updates.

## 13. PRODUCT MEDIA & DOCUMENT PIPELINE

Assets may arrive as the old 2025 catalogue, Ansell/Ringers catalogue `93276.pdf`, Avon NH15 brochure, Taedylinn W2849 datasheet, product/flyer JPGs, and Oasis Star logo. The research file lists them, but their presence in a different archive **does not mean they are attached now**. Inspect actual available files; never claim a document exists simply because its filename appears in research.

Create `ASSET_INVENTORY.md` showing available/needed asset, rights/approval, original filename, product mapping, alt text, publication status, and optimized output path. Optimize supplied images, keep originals out of shipping bundle when possible, preserve real product proportions, avoid visually modifying safety certification marks. Do not publish flyer imagery with Red Wing showroom phone number unless properly rebranded/authorized; do not change the underlying product specifications. Remove stray metadata and secrets from published assets. Datasheets must have real links only to approved available PDFs, with visible file size/type if known. Don't fake PDF buttons.

If supplier assets are missing, ship a strong, deliberate design with honest graphic placeholders and a concise replace-assets checklist. Do not hide incomplete pages behind fake product photography.

## 14. GIT, CI, AUTODEPLOY, DOCUMENTATION

- Create one appropriately named repo (`oasis-star-ppe` or similar) if none exists and authorization is available; otherwise use existing.
- Commit clean, reviewable stages; include `.gitignore`, `.env.example`, `README.md`, `DECISIONS.md`, `CONTENT_GAPS.md`, `ASSET_INVENTORY.md`, `DESIGN_REFERENCE_ANALYSIS.md`, `ENVIRONMENT.md`, `DEPLOYMENT.md`, and `TEST_REPORT.md`.
- GitHub PR -> preview build; approved `main` -> Vercel production automatically after pipeline checks. Include minimal CI for install-from-lockfile, lint, type check, unit tests, and production build; avoid large downloadable browser bundles on the owner's PC.
- No token/password/API key in Git history, application logs, source comments, screenshots, or public demo. Mask personally identifying data in fixtures/tests.
- Provide handoff instructions for two nontechnical employees: where RFQs appear, how to contact buyers, where product copy/images get edited, what can and cannot be changed safely, and who manages DNS/email.
- Include a low-maintenance future extension roadmap: verified inventory badges, authenticated staff RFQ status management, approved price tiers, bilingual Arabic translation, CSV product import, analytics / CRM integration. These are phase 2—not reasons to delay core launch.
- Respect existing domain/demo code if supplied, but improve architecture and UX rather than preserving a poor implementation for its own sake.

## 15. IMPLEMENTATION SEQUENCE (DO THE WORK, DON'T STOP AT PLANNING)

**Phase 0 — Audit and decisions:** inspect repo/files; view BOTH attached reference images; read provided research and approved documents; inventory assets; identify constraints. Produce short design/architecture notes; do not spend the whole session producing a speculative plan.

**Phase 1 — Foundation:** scaffold only if needed, configure typography, tokens, global shell, responsive navigation/footer, typed product schema/seed, routes, metadata, accessibility foundations, asset placeholders.

**Phase 2 — Visual system & pages:** implement art-directed homepage, catalogue/category filters/search, product detail pages, brands, industries, about/resources/contact, all core responsive states. Ensure design cohesion from images across pages.

**Phase 3 — RFQ backend:** implement quote basket, per-item options, local persistence, secure API, Supabase migration, email notification integration when configured, success/reference/error and anti-spam paths.

**Phase 4 — Hardening:** verify technical claims, remove draft-only items from public site, ensure no fake assets/downloads, run lint/type/build, add focused automated tests, spot-check mobile/tablet/desktop, accessibility, metadata and security. Use available browser/screenshot QA without installing large tooling on low-storage PC. Capture before/after screenshots if tool support exists.

**Phase 5 — Deploy/handoff:** create/connect repo and Vercel/Supabase only where authorized; configure environment without exposing secret values; verify live submission end-to-end with test RFQ if backend is active, purge test personal data; produce honest deployment status and concise next actions for any unmet precondition.

When a phase finishes, report completed deliverables, files changed, tests actually run, and the next important decision. **Do not report an unrun test as passed or an unconnected backend as operational.** Continue implementation as far as allowed without repetitive requests for permission.

## 16. ACCEPTANCE CRITERIA — MUST VERIFY

A. A buyer can find `R-267`, `Red Wing 3228`, and `Smart-Ex 03` with search and navigate to the appropriate product detail.
B. All published products have a real brand/model and no invented certification, pricing, stock, authorized-dealer status, or PDF.
C. `Ex-Handy 10` is **not orderable**; any mention is a clearly labelled upgrade/discontinued reference only.
D. Taedylinn W2849 does not repeat the contradictory Class 2 welding claim without verification.
E. Buyer can add two different products, including variants if known, edit quantities, refresh, and retain the basket.
F. The quote request form submits multiple line items and company details to the server; an actual configured environment stores them durably and returns a traceable reference.
G. Anonymous users cannot read other buyers' quote submissions from Supabase/API, and server credentials are never exposed client-side.
H. If email notification is not configured or fails, RFQ persistence and user experience remain honest and reliable.
I. No third-party showroom or supplier phone number is presented as Oasis Star's contact; actual company contact is explicitly approved.
J. All nav routes and call-to-actions function; no dummy buttons, broken downloads, fake success pages or placeholder lorem ipsum.
K. Mobile 360/390px, tablet, and desktop layouts are polished, without clipping; forms, filters and spec tables work with keyboard and touch.
L. Motion is purposeful; reduced-motion and focus-visible are respected. Check obvious contrast and semantic issues.
M. A normal build, typecheck and key tests pass **if executable environment is available**; accurately report if not.
N. SEO title/meta/canonical/sitemap/structured data are valid and make no unsupported commercial claims.
O. App can be previewed without secrets, but a disabled/unconfigured submit path states plainly why RFQ delivery requires backend setup; it never pretends delivery happened.
P. The system is straightforward enough for two staff members and costs little or nothing to operate at launch.
Q. Site visibly reflects BOTH reference images' useful visual characteristics, integrated with Oasis Star brand rather than pasted together.

### Suggested tests
- Unit: filtering/search normalization, duplicate basket variant merge, carton vs pair quantity behavior, RFQ validation, stable reference format, whitelist checks.
- Integration: valid multi-item RFQ persistence; malformed input rejected; missing secrets handled; rate limiting; duplicate submit behavior; notification failure leaves successful DB record.
- Manual: no results, quantity edits, slow mobile/network, tabbing/focus, quote submission, success reference, PDF link existence, image alt behavior, no invalid contact data.

## 17. REQUIRED OUTPUT / FINAL REPORT

At the start, briefly summarize your interpretation of BOTH references and the design direction (after inspecting the actual files), and show the initial implementation plan. Then WRITE THE CODE.

At completion, provide:
1. Live/preview URL **only if actually deployed**, and GitHub repo URL **only if actually created/known**.
2. Summary of finished pages, standout visual design decisions, and working RFQ flows.
3. File tree overview (short; do not dump dependencies) and commands to run/test/build.
4. Which tests passed, which were not run, and why.
5. Supabase schema/application state, email notification configuration state, DNS status, and any required human actions.
6. `CONTENT_GAPS.md` priority items: logo/product approvals, company phone/email, missing SKU datasheets, current certificates, distributor permissions, image licensing, stock/pricing, and legal signoff.
7. Honest punch list of unfinished work. Prefer a strong functioning core over superficial completion across too many pages.

## 18. FINAL INSTRUCTIONS — DECISION PRIORITIES

When tradeoffs arise, prioritize in this order:
1. Truthful safety/product content, security and preservation of buyer data.
2. End-to-end working RFQ and minimal staff operating burden.
3. Excellent visual quality consistent with two references and real Oasis Star branding.
4. Fast procurement discovery, accessible mobile UX and good search discoverability.
5. Performance/free-tier affordability and maintainability.
6. Extra features only after essentials actually work.

**Proceed now. Examine the workspace and the two attached reference images, make the design decisions, build the complete initial website, test what you can, and report actual delivery status.**