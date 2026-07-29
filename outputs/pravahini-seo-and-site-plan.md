# Pravahini Wellness — Site Architecture, SEO & Copy Spec

Prepared from the 7 product labels supplied. Read Section 0 before anything else — it contains problems that must be fixed before the site goes live, not after.

---

## 0. Blockers found in the label copy

### 0.1 Claims that are legally risky in India

Under the Cosmetics Rules, 2020, a product sold as a cosmetic **cannot carry drug claims**. Products with drug claims cannot be registered as cosmetics, and CDSCO can reject registration on labelling grounds alone. Several of your front-panel claims read as therapeutic, not cosmetic:

| SKU | Claim on label | Risk | Safer wording |
|---|---|---|---|
| Topical Hair Serum | "Stimulates new hair growth" | **High** — hair growth is generally treated as a drug claim | "Supports the look of fuller, thicker hair" |
| Topical Hair Serum | "Reduces hair fall" | **High** — implies treatment of a condition | "Helps reduce hair breakage during styling" |
| Pain Relief Herbal Oil | "Relieves Muscle Pain", "Eases Joint Stiffness" | **High** — this is a therapeutic claim; the product name itself says "Pain Relief" | Either reposition as a massage oil, or license it properly as an Ayurvedic proprietary medicine under AYUSH |
| Silk Saffron Glow | "Anti-aging" / "Anti-ageing" | **Medium** — widely used but contested; "anti-ageing" is tolerated more than "reverses ageing" | "Helps reduce the appearance of fine lines" |
| Avarampoo Cream | "Clean + Detoxify (Dual Action)" | **Medium** — "detoxify" is a physiological claim with no cosmetic basis | "Deep-cleansing" |

**This matters for the website more than for the box.** Your product page H1s and H2s are the most-indexed, most-screenshotted copy you own. If you put "stimulates new hair growth" in an H1, you have published a drug claim at scale and made it trivially discoverable by a regulator or a competitor filing an ASCI complaint.

**Decision you need to make:** is "Pain Relief Herbal Oil" a licensed Ayurvedic medicine or a cosmetic massage oil? The answer changes the product name, the label, the collection it sits in, and the entire keyword strategy for that SKU. I am not able to answer this for you and you should confirm it with a regulatory consultant — I am not a lawyer.

### 0.2 Contradiction: two different formulas under one product name

The Silk Saffron Glow Face Serum appears twice with **completely different ingredient lists**:

- **Version A:** Aqua, Aloe barbadensis, Hydrolyzed Silk, Crocus sativus, natural oils and butters, emulsifiers, humectants, stabilisers, preservative, tocopherol, perfume. Best before **24 months**.
- **Version B:** Manjistha root extract, Yashtimadhu root extract, Vetiver root extract, Rosmarinus officinalis leaf oil, Vitamin E. Best before **12 months**.

These are not the same product. Version B contains no saffron and no silk despite being named "Silk Saffron Glow." Version A contains no Yashtimadhu or Vetiver despite the front panel advertising "Power of Yashtimadhu and Vetivera." **Both versions have a front panel that contradicts their own back panel.** Resolve this before writing a single line of product copy.

### 0.3 Shelf-life inconsistencies

Avarampoo Infused Cream says 22 months. Saffron Infused Cream says 12 months. Same base formula, same pack, same manufacturer. "22" looks like a typo for 12 or 24 — worth confirming with whoever ran the stability testing.

### 0.4 Typos to fix before print and before they get copy-pasted onto the site

- "Sesanum indicum" → **Sesamum** indicum (Hair Serum)
- "Eclipta Prostrata Extrct" → **Extract** (Botanical Hair Oil)
- "Enhancec natural radiance" → **Enhances** (Face Serum, both versions)
- "Rebalancing skin tone" → **Rebalances** skin tone (parallel with the other bullets)
- "Vetivera" → **Vetiver** (Face Serum front panel)
- "200 ml e 6.76" → **6.76 fl oz** (Pain Relief Oil — unit is missing)
- "Officinalis" is inconsistently capitalised across labels; INCI convention is *Rosmarinus officinalis*, species name lowercase

### 0.5 Legal Metrology gaps

Under the Legal Metrology (Packaged Commodities) Rules, retail packs generally require the **full address of the manufacturer/packer**, **net quantity**, **month and year of manufacture**, **retail sale price marked "Maximum Retail Price ₹… incl. of all taxes"**, and a **consumer care contact — name, phone number and email**. Your labels carry "Pravahini Wellness Pvt. Ltd., Made in India" but I see **no street address and no consumer care phone or email** on any of the seven. Confirm this with your packaging consultant; e-commerce listings have their own mandatory disclosure set on top of the physical label.

Note also that the Kids Oil and Pain Relief Oil labels show **no ingredient list, no net quantity block on the panel supplied, and no batch/MFG/MRP block** — those may be on panels not shared, but if they aren't, they're missing.

---

## 1. Positioning read

What you actually have is not a generic "ayurvedic brand." It's a **South Indian botanical range with two genuinely defensible assets**:

1. **Avarampoo (Senna auriculata).** This is the interesting one. It's a Tamil household botanical with real cultural recognition and almost no serious D2C brand owning the search term in English. Low competition, high intent, and it gives you a story no Delhi-based dropshipper can copy credibly.
2. **A coherent full-family range.** Kids oil, adult hair oil, face serum, pain oil, creams — you can build a "whole household" narrative that most single-hero-product brands cannot.

Your weakest positioning asset is saffron. "Saffron face serum India" is saturated by Kama, Forest Essentials, Just Herbs and a hundred Amazon sellers. Do not lead with saffron. Lead with Avarampoo.

---

## 2. Site architecture

```
/                                  Home
/collections/hair-care             Botanical Hair Oil, Topical Hair Serum
/collections/skin-care             Silk Saffron Glow, Saffron Cream, Avarampoo Cream
/collections/baby-kids             Multipurpose Kids Oil
/collections/body-massage          Pain Relief Herbal Oil   ← name depends on §0.1 decision
/collections/all
/pages/our-ingredients             Ingredient glossary — this is your SEO engine
/pages/about-pravahini
/pages/avarampoo-guide             Pillar content, see §5
/blogs/journal/*
/policies/*                        Shipping, returns, privacy, T&C
/pages/contact                     Must carry the Legal Metrology consumer care details
```

**Collection handles should be product-language, not category-language.** `/collections/hair-care` is fine but `/collections/ayurvedic-hair-oil` will rank better if you only have two hair SKUs. Decide once you know whether the range expands.

---

## 3. Keyword map

**Read this honestly:** these are keyword *hypotheses* built from Indian search patterns and the ingredient set. I have not pulled volume data. Before you build pages around them, validate each in Google Keyword Planner (set to India), and cross-check with Amazon.in autocomplete, which is closer to purchase intent than Google for this category. Anyone who hands you a keyword list with confident volume numbers and no tool access is guessing.

### Priority tier 1 — build these first

| SKU | Primary keyword hypothesis | Secondary | Why |
|---|---|---|---|
| Avarampoo Infused Cream | avarampoo cream | avarampoo face cream, senna auriculata skin benefits, avarampoo poo face pack | Almost certainly low competition; brand-definable |
| Botanical Hair Oil | ayurvedic hair oil for hair fall | bhringraj amla hair oil, herbal hair oil 200ml | High volume, high competition — needs content support |
| Multipurpose Kids Oil | baby massage oil natural | kids hair and body oil, chemical free baby oil india | Parents search cautiously and read labels; your ingredient transparency wins here |

### Priority tier 2

| SKU | Primary keyword hypothesis | Secondary |
|---|---|---|
| Topical Hair Serum | hair serum for thinning hair | ayurvedic hair serum, non sticky hair serum india |
| Saffron Infused Cream | saffron face cream | kesar cream for glowing skin, crocus sativus cream |
| Silk Saffron Glow Serum | saffron face serum | manjistha face serum, yashtimadhu skin serum |
| Pain Relief Herbal Oil | ayurvedic pain relief oil | herbal massage oil for joint pain, warming body oil |

### Hindi/Tamil transliteration opportunity

A meaningful share of Indian search is transliterated. Worth testing as blog content or alt-language product page copy, not as your primary H1s:

- `kesar cream` (saffron), `bhringraj tel`, `amla hair oil`, `avarampoo podi`, `nalangu maavu`

---

## 4. H1 / H2 specification

**Rules applied throughout:**

- Exactly **one H1 per page.** Shopify themes commonly render the logo as an H1 on the homepage — check yours and fix it, because that wastes your single most valuable tag on the word "Pravahini."
- H2s carry the secondary keywords and structure the page for both readers and featured snippets.
- **No drug claims in any heading.** See §0.1.
- Headings are sentence-level, not label-level. "Reduces hair fall" is a label bullet; it is not a heading.

### Homepage

```
H1:  Ayurvedic Skin, Hair and Body Care — Handcrafted in India
H2:  Shop by concern
H2:  Avarampoo: the South Indian flower behind our bestselling cream
H2:  What goes in — and what never does
H2:  Made in India, formulated for Indian skin and hair
H2:  What our customers say
```

Why this H1: it carries category (ayurvedic / skin, hair, body care), geography (India), and differentiation (handcrafted) in under 60 characters of visible weight. It does not carry the brand name — your brand name is in the title tag and the logo, and spending H1 real estate on a brand nobody is searching for yet is a beginner mistake.

### Collection: Hair Care

```
H1:  Ayurvedic Hair Oils & Serums
H2:  Botanical hair oil with bhringraj, amla and black seed
H2:  Lightweight hair serum for daily use
H2:  How to build an oiling routine that you'll actually keep up
H2:  Frequently asked questions about ayurvedic hair oiling
```

### Collection: Skin Care

```
H1:  Ayurvedic Face Creams & Serums
H2:  Avarampoo infused cream — our South Indian hero
H2:  Saffron infused cream for radiance
H2:  Silk Saffron Glow face serum
H2:  Choosing between a cream and a serum
```

### Collection: Baby & Kids

```
H1:  Natural Baby & Kids Oil
H2:  One oil for hair, skin and massage
H2:  Every ingredient, explained for parents
H2:  How to massage your child safely
```

### Product: Botanical Hair Oil (200 ml)

```
H1:  Botanical Hair Oil — Bhringraj, Amla & Black Seed | 200 ml
H2:  What's inside
H2:  How to use botanical hair oil
H2:  Who this hair oil is for
H2:  Ingredients in full
H2:  Care, storage and shelf life
H2:  Questions about our botanical hair oil
```

Meta title: `Botanical Hair Oil with Bhringraj & Amla | 200ml | Pravahini` (58 chars)
Meta description: `Cold-pressed sesame and coconut base with bhringraj, amla and black seed. Nourishes hair and supports healthy-looking roots. 200ml. Made in India.` (147 chars)

### Product: Topical Hair Serum (50 ml)

```
H1:  Topical Hair Serum with Bhringraj & Amla | 50 ml
H2:  A lighter alternative to oiling
H2:  How to use
H2:  What's inside
H2:  Serum or oil — which one do you need?
H2:  Ingredients in full
H2:  Questions about our hair serum
```

Meta title: `Ayurvedic Hair Serum with Bhringraj & Amla | 50ml | Pravahini`
Meta description: `A lightweight topical serum in a coconut and almond oil base with bhringraj, amla and vitamin E. For scalp and lengths. 50ml. Made in India.`

⚠️ Note the H1 does **not** say "for hair growth" or "for hair fall." That is deliberate. See §0.1.

### Product: Avarampoo Infused Cream (50 g)

This is your flagship SEO page. Treat it as a mini pillar, not a product page.

```
H1:  Avarampoo Infused Cream — Senna Auriculata for Skin | 50 g
H2:  What is avarampoo?
H2:  Why South Indian households have used avarampoo for generations
H2:  How to use avarampoo cream
H2:  What's inside — and why
H2:  Avarampoo cream vs avarampoo powder
H2:  Ingredients in full
H2:  Questions about avarampoo
```

Meta title: `Avarampoo Infused Cream | Senna Auriculata Face Cream | 50g`
Meta description: `A rejuvenating cream infused with avarampoo (Senna auriculata) flower extract, shea butter and almond oil. A South Indian botanical tradition. 50g.`

### Product: Saffron Infused Cream (50 g)

```
H1:  Saffron Infused Cream — Kesar & Silk Powder | 50 g
H2:  Saffron, and what it actually does for skin
H2:  How to use
H2:  What's inside
H2:  Ingredients in full
H2:  Questions about our saffron cream
```

### Product: Silk Saffron Glow Face Serum (30 ml)

Hold this page until §0.2 is resolved. Once you know which formula ships:

```
H1:  Silk Saffron Glow Face Serum | 30 ml
H2:  Manjistha, yashtimadhu and vetiver — the root blend
H2:  How to use a face serum
H2:  What's inside
H2:  Ingredients in full
H2:  Questions about our face serum
```

### Product: Multipurpose Kids Oil

```
H1:  Multipurpose Kids Oil — Hair, Skin & Massage
H2:  One oil, three uses
H2:  Every ingredient, explained for parents
H2:  How to massage your child
H2:  What age is this suitable for?
H2:  Ingredients in full
```

⚠️ You must publish an ingredient list and an age recommendation for this SKU. Parents will not buy a children's product with an undisclosed formula, and you will get returns and bad reviews if you ship one.

### Product: Pain Relief Herbal Oil (200 ml)

**Do not publish this page until §0.1 is resolved.** If it stays a cosmetic, it becomes:

```
H1:  Warming Herbal Massage Oil | 200 ml
H2:  A traditional warming oil for tired muscles
H2:  How to use
H2:  What's inside
H2:  Ingredients in full
```

If it's licensed as an Ayurvedic proprietary medicine, it can keep the therapeutic language — and it will need a licence number displayed, which changes the label too.

---

## 5. Content that will actually move rankings

Heading tags are hygiene. They will not, on their own, get you traffic. These will:

1. **`/pages/avarampoo-guide` — 1,500+ words.** What avarampoo is, botanical identity, traditional South Indian use, how it's used as a powder vs a cream, sourcing. Internally link to the product. This is your single highest-leverage page because you can plausibly rank #1 in India for a term nobody has claimed.
2. **`/pages/our-ingredients` — a glossary.** One anchor-linked entry per botanical you use: bhringraj, amla, avarampoo, manjistha, yashtimadhu, vetiver, kalonji, saffron. Each product page links into it. This builds topical authority and is the kind of page that earns links.
3. **Google Merchant Center feed + Shopping.** For a 7-SKU D2C brand in India, paid Shopping and Meta will outperform organic search for the first 12 months. Budget accordingly and treat SEO as the compounding asset, not the launch channel.
4. **Product schema (JSON-LD)** on every product page: name, brand, image, description, offers, aggregateRating once you have real reviews. **Never fabricate ratings** — Google penalises it and it's straightforwardly dishonest.

---

## 6. Technical SEO checklist for the Shopify build

- [ ] Confirm the theme renders exactly one H1 per template. Many premium themes get this wrong.
- [ ] Canonical tags on collection-filtered URLs (`?filter=`) pointing to the clean collection URL.
- [ ] `noindex` on `/collections/all` if it duplicates other collections.
- [ ] Image alt text on every product image, describing the product, not stuffed with keywords.
- [ ] Compress label and lifestyle imagery — these labels are line art, so SVG or high-compression WebP will be tiny.
- [ ] `hreflang` only if you sell outside India. Skip it otherwise.
- [ ] Structured data: Product, BreadcrumbList, Organization, FAQPage on pages with a real FAQ H2.
- [ ] Mobile Core Web Vitals — over 80% of Indian D2C traffic is mobile and often on mid-tier Android. Test on a throttled 4G profile, not your laptop.
- [ ] Shopify's default `/products/handle` URLs are fine. Do not build a custom URL scheme.
- [ ] Set up Search Console and Bing Webmaster Tools on day one, before launch.

---

## 7. What I still need from you

1. The Shopify theme name and store URL.
2. The §0.1 decision on Pain Relief Oil — cosmetic or AYUSH-licensed medicine.
3. The §0.2 resolution on which Silk Saffron Glow formula is real.
4. Ingredient lists and net quantities for the Kids Oil.
5. Your consumer care phone and email, and the registered manufacturer address.
6. Whether you sell only in India, or also export.

---

*Regulatory notes in this document are general information based on publicly available summaries of the Cosmetics Rules, 2020 and the Legal Metrology (Packaged Commodities) Rules. I am not a lawyer and this is not legal advice. Have a regulatory consultant review your labels before you print a production run.*
