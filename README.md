build this site; use the theme from the attachments; also incorporate them - turn some of the images into interactive components - il give you lots to play with

# Veda Labs — Site Spec

> Hand this file to any AI with a visual direction and say "build this site."
> Everything structural is here. Nothing visual is decided.

---

## Identity

- Name: Veda Labs (or just "Veda")
- Tagline: "Your biology, optimized."
- Domain: Peptide wellness / biohacking / longevity
- Tone: Clinical confidence, not hype. Evidence-first. Premium.
- Audience: Health-conscious adults (30-55), biohackers, longevity-curious, athletes

---

## Navigation

### Header (sticky)
- Logo (left) -- links to home
- Nav links: Catalog, Advisor
- CTA button: "Build Your Stack" -> /advisor
- Mobile: hamburger collapse

### Footer
- Brand column: Logo + tagline
- Products column: Full Catalog, Skin & Anti-Aging, Recovery, Fat Loss (each filters catalog by goal)
- Company column: About, Our Science, Partner Clinicians
- Support column: Contact, Shipping & Returns, Privacy Policy
- Legal row: FDA disclaimer + Rx disclaimer

---

## Pages

### Home /

Full marketing landing page. One long scroll with distinct sections.

#### Hero
- Headline: "Your biology, optimized."
- Subheadline: 1-sentence value prop
- 2 CTAs: "Build Your Stack" (primary, /advisor) + "Browse Catalog" (secondary, /catalog)
- Visual: product/molecule image (right on desktop, below on mobile)
- Scroll indicator at bottom
- Layout: asymmetric 2-col (text 45%, image 55%). Stacked on mobile.

#### Trust Strip
4 trust signals in a row:
1. "Clinically Formulated" -- compounded in licensed pharmacies
2. "Evidence-Graded" -- every product carries a transparency grade
3. "Made in USA" -- domestic manufacturing
4. "Physician Oversight" -- certain items require physician sign-off

Layout: 4-col grid (2-col on mobile).

#### Goal Showcase
8 goal cards, alternating image/text sides. Each card is roughly screen-height.

Goals (in order): Recovery, Fat Loss, Cognition, Sleep, Longevity, Skin, Athletic Performance, Sexual Health

Each card:
- Eyebrow label (goal name, uppercase)
- Headline (outcome-focused, includes a stat)
- Description (1-2 sentences)
- Evidence stat (e.g., "73% improvement in recovery markers")
- Link: "View protocols ->" -> /catalog?goal=X
- Large product/lifestyle image

Layout: alternating left-image/right-text, right-image/left-text. Stacked on mobile.

#### How It Works
3 steps:
1. Tell us your goal -- 60-second intake quiz, select primary + secondary goals
2. Get your stack -- AI advisor builds personalized protocol from the full catalog
3. Start your protocol -- ships in 2-3 days, physician oversight where needed

Each step: icon/image + step number + title + short description.
Layout: 3-col grid (stacked on mobile).

#### Testimonials
Auto-scrolling horizontal marquee of testimonial cards (6 testimonials, doubled for seamless loop).

Each card:
- Star rating (4-5 stars)
- Quote (1-3 sentences)
- Name (first name + last initial)
- Context tag (e.g., "Recovery stack - 6 weeks")

Behavior: continuous scroll animation, no user interaction required.

#### FAQ
Left column: section header + short intro. Right column: 6 accordion items (click to expand/collapse).

Topics: what peptides are, medical advice disclaimers, AI advisor methodology, physician process, shipping, international availability.

Layout: 2-col (35% / 60%). Stacked on mobile.

#### Bottom CTA
- Full-width banner with background image
- Eyebrow: "Ready to start"
- Headline: "Build your protocol in 2 minutes"
- Description: 1 sentence
- 2 CTAs: "Start now" (primary, /advisor) + "Browse catalog" (secondary, /catalog)

---

### Catalog /catalog

Filterable product grid. All products shown by default.

#### Header
- Eyebrow: "Full catalog"
- Headline: "Peptide protocols"
- Description: brief explanation of what's available

#### Filters
One row of pill/chip toggle buttons:
- Goal filter: All Goals + 8 goal pills (Recovery, Fat Loss, Cognition, Sleep, Longevity, Skin, Athletic Performance, Sexual Health)

Filters update the grid. URL updates with ?goal=X for shareable links.

#### Results Count
"Showing X of Y protocols"

#### Product Grid
Responsive grid: 3 cols desktop, 2 tablet, 1 mobile.

Each product card:
- Product image (square, contained)
- Evidence badge ("Well-studied" / "Emerging" / "Anecdotal")
- Product name
- Subtitle (short tagline)
- Price
- Hover: "View ->" label appears

Card links to /product/[id].

---

### Product Detail /product/[id]

Individual product page.

#### Breadcrumb
Catalog -> Product Name

#### Product Hero (2-col)

Left (~45%):
- Product image (large, contained)

Right (~55%):
- Goal tags (colored pills)
- Brand name (if applicable)
- Product name (large)
- Subtitle
- Price
- Short description (1-2 sentences)
- CTA button: "Add to cart" (or "Book consultation" for Rx items, or "Learn more" for research-only items)
- Specs table (see below)
- Disclaimer box if needed

#### Specs Table
| Field              | Notes                              |
|--------------------|------------------------------------|
| Format             | topical / oral / nasal / injectable |
| Evidence grade     | well-studied / emerging / anecdotal |
| Dosage             | Dosing instructions                |
| Protocol           | Usage protocol                     |
| Cycle              | Only shown if cycle data exists    |
| Contraindications  | Only shown if any exist            |

#### Related Products
3 products from the same primary goal (excluding current). Each: image + name + subtitle. Links to product detail.

---

### Advisor Intake /advisor

Multi-part form that feeds the AI advisor.

#### Left Column (~35%)
- Eyebrow: "Peptide advisor"
- Headline: "Build your stack"
- Description: what the advisor does
- 3 info bullets: "Takes 60 seconds" / "Personalized to your biology" / "Your data stays private"

#### Right Column (~60%) -- The Form
Fields in order:
1. Primary goal (required) -- 8 goal buttons in grid, select one
2. Secondary goals (optional) -- same 8 goals as multi-select (minus the primary)
3. Age (optional) -- number input
4. Sex (optional) -- dropdown: male / female
5. Current stack (optional) -- textarea: "What are you currently taking?"
6. Contraindications (optional) -- textarea: "Any conditions or medications?"
7. Anything else (optional) -- textarea
8. Submit: "Get my protocol" (disabled until primary goal selected)

Behavior: submits to API, stores response, redirects to /advisor/results.

---

### Advisor Results /advisor/results

Displays the AI-generated protocol.

#### Header
- Eyebrow: "Your protocol"
- Headline: "Here is your stack"
- Goal summary (e.g., "Optimized for: Recovery")

#### Primary Recommendation
Single large card for the lead peptide:
- Product image
- Evidence badge
- Product name + subtitle
- Role description (why this was chosen)
- Price
- Link to product page

#### Supporting Stack
Grid (2-col) of smaller cards for supporting peptides. Same structure as primary.

#### Important Notes
Bulleted list of caveats/disclaimers from the AI.

#### Considered & Excluded
List of peptides the AI considered but filtered out, each with a reason.

#### Why This Stack
Highlighted box with the AI's optimization rationale (1-2 paragraphs).

#### Next Steps
- Primary CTA: "Proceed to checkout" or "Book consultation" (depending on product types)
- Secondary: "Retake advisor" -> /advisor

---

## Data Model

### Product (Peptide)
```json
{
  "id": "string",
  "name": "string",
  "brand": "string (optional)",
  "subtitle": "string",
  "description": "string",
  "price": "number (USD)",
  "format": "topical | oral | nasal | injectable",
  "goals": ["Goal[]"],
  "dosage": "string",
  "protocol": "string",
  "cycle": "string (optional)",
  "contraindications": ["string[]"],
  "evidence": "well-studied | emerging | anecdotal"
}
```

### Goals (8)
recovery | fat-loss | cognition | sleep | longevity | skin | athletic-performance | sexual-health

### Testimonial
```json
{
  "name": "string",
  "context": "string",
  "quote": "string",
  "stars": "number (4 or 5)"
}
```

### FAQ Item
```json
{ "q": "string", "a": "string" }
```

---

## Assets

All in /brand/ as .png files:

| Category             | Count | Usage                                    |
|----------------------|-------|------------------------------------------|
| product-shot-vial    | 1     | Injectable vial image                    |
| product-shot-cream   | 1     | Cream jar image                          |
| product-shot-capsule | 4     | Capsule/supplement bottle images         |
| product-shot-dropper | 1     | Dropper bottle image                     |
| product-shot-nasal   | 1     | Nasal spray image                        |
| product-shot-lineup  | 1     | Full product lineup contact sheet        |
| lifestyle-image      | 5     | Lifestyle photography                    |
| label-design         | 1     | Pump mist label                          |

---

## Theming Guide

This version uses the **Performance Recovery** theme:

- Palette: graphite/ice-blue/red/aluminum (dark mode)
- Typography: clean sans (display + body) + monospace (data)
- Spacing: athletic, high-density
- Borders: minimal radius, clean edges
- Animation: dynamic, performance-driven
- Cards: elevated, subtle shadows
- Images: contained, high-contrast on dark
- CTA buttons: red primary with graphite outline
- Posture: athletic, dark, data-driven, high-performance

Things that stay constant across all themes:
- Page structure and section order
- Data model and product catalog
- Navigation structure
- User flows
- Advisor form fields and response shape
- Legal disclaimers
