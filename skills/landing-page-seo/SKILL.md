---
name: landing-page-seo
description: Technical SEO + GEO engine for landing pages — semantic HTML, meta tags, structured data, Core Web Vitals, llms.txt, robots.txt, answer-first copy. For NEW pages or redesigns, start from landing-page-design-copy (it calls this skill in Phase 4). Use this skill directly only to audit or fix SEO/GEO of an existing page without touching its design or copy. Also trigger when the user mentions SEO optimization for a page, improving conversion or bounce rate, "membuat landing page", "halaman penjualan", making a page visible to AI assistants or answer engines (AEO/GEO, ChatGPT/Claude/Gemini/Perplexity citations), or wants a page that makes visitors read all the content. Covers content strategy, section structure, semantic HTML, meta tags, structured data, Core Web Vitals, AI-readiness (llms.txt, robots.txt for AI crawlers, quotable answer-first copy), and scroll-engagement techniques.
---

# SEO-Friendly, Scroll-Worthy Landing Pages

A landing page has three audiences that must all be satisfied: **search engine crawlers** (who decide whether anyone finds the page), **AI assistants and answer engines** (ChatGPT, Claude, Gemini, Perplexity — who decide whether the page gets quoted when people ask them instead of Google), and **human visitors** (who decide whether to keep reading and eventually convert). These goals are complementary, not conflicting — engagement signals feed rankings, and the same clean, extractable HTML that ranks well is what AI models can quote. This skill builds pages that win on all three fronts.

## Workflow

Follow these phases in order. Do not skip Phase 1 — a landing page built without knowing the audience and target keyword is decoration, not marketing.

### Phase 1: Gather strategy inputs

Before writing any code, establish (ask the user if not provided, but make reasonable assumptions for anything minor):

1. **Product/service and its single core promise** — one page = one goal. If the user wants to sell three things, recommend three pages.
2. **Target audience and their pain point** — what problem brings them to search?
3. **Primary keyword + 2-4 secondary keywords** — if the user doesn't know, propose them based on the product (what would the audience actually type into Google?). The primary keyword drives the H1, title tag, URL slug, and opening copy.
4. **Desired action (CTA)** — buy, sign up, book a demo, contact via WhatsApp, etc.
5. **Language and locale** — affects `lang` attribute, hreflang, keyword choice, and copy tone.
6. **Brand assets** — colors, logo, existing tone of voice. If none, propose a distinctive direction (generic-looking pages kill trust and engagement). If this skill was entered through `landing-page-design-copy`, skip this and use its Vibe Discovery instead.
7. **Voice sample** — ask the user to describe their product in 2-3 unpolished sentences "the way you'd say it to a friend", plus any real customer quotes (reviews, WhatsApp chats) and one belief competitors don't share. This raw material is what keeps the copy from sounding AI-generated — see `skills/landing-page-seo/references/human-feel.md`.

### Phase 2: Design the narrative arc (this is what makes people scroll)

People don't scroll because content exists — they scroll because each section opens a loop that the next section closes. Plan the page as a story before building it. Read `skills/landing-page-seo/references/scroll-engagement.md` for the full technique catalog and `skills/landing-page-seo/references/human-feel.md` for voice rules (banned AI-sounding constructions, how to write copy that sounds like the founder, not a brochure), then draft a section outline using this proven arc:

1. **Hero** — the promise. Primary keyword in the H1, phrased as the visitor's desired outcome (not the product name). Subheadline handles the biggest objection. One CTA. A visual cue that content continues below the fold.
2. **Problem agitation** — mirror the visitor's pain in their own words. This earns the right to be read further ("this page understands me").
3. **Solution reveal** — introduce the product as the bridge from problem to outcome.
4. **How it works / features-as-benefits** — every feature stated as what the visitor gains.
5. **Social proof** — testimonials, logos, numbers, case results. Place proof near the claims it supports, not only in one block.
6. **Objection handling / FAQ** — doubles as long-tail keyword coverage and FAQPage structured data.
7. **Final CTA** — restate the promise, add urgency or risk-reversal (guarantee, free trial).

Adjust the arc to the product (a SaaS demo page differs from a local service page), but keep the open-loop → payoff rhythm between sections.

### Phase 3: Build with semantic, crawlable, AI-extractable HTML

Read `skills/landing-page-seo/references/seo-technical.md` AND `skills/landing-page-seo/references/ai-readiness.md` before writing code, then build the page. Non-negotiables:

- Semantic structure: `<header>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<nav>`; exactly one `<h1>`; logical h2/h3 hierarchy that mirrors the narrative arc.
- All meaningful copy in real HTML text — never baked into images, never rendered only by JS.
- Complete `<head>`: title tag (≤60 chars, keyword near front), meta description (≤155 chars, written as ad copy with a hook), canonical, Open Graph + Twitter cards, `lang` attribute.
- JSON-LD structured data appropriate to the page (Organization/LocalBusiness, Product, FAQPage, Review as applicable).
- Descriptive `alt` text on every image; lazy-load below-the-fold images; explicit width/height to prevent layout shift.
- Mobile-first responsive layout — most landing page traffic is mobile, and Google indexes mobile-first.
- Answer-first copy: every H2/H3 section states its key claim in the first 1-2 sentences; include a short summary block with 3-5 hard facts and a one-sentence brand definition ("{Brand} adalah {category} yang {differentiator} untuk {audience}"). This is what AI engines extract and quote — see `skills/landing-page-seo/references/ai-readiness.md`.

### Phase 4: Layer in engagement mechanics

Apply the techniques from `skills/landing-page-seo/references/scroll-engagement.md` in code, and follow the anti-template design rules in `skills/landing-page-seo/references/human-feel.md` section 2 (characterful typography, opinionated palette, one deliberate grid break — never the centered-hero + gradient + three-icon-cards default):

- **Visual momentum**: alternate section backgrounds/layouts so each scroll reveals something visually new; use generous whitespace; keep paragraphs ≤3 lines on mobile.
- **Scroll-triggered reveals**: subtle fade/slide-in animations via IntersectionObserver (CSS-driven, respecting `prefers-reduced-motion`). Never gate content behind interaction — crawlers and impatient humans must see everything.
- **Progressive CTAs**: a soft CTA mid-page, the strong CTA at the end, optionally a sticky mobile CTA bar after the hero.
- **Directional cues**: arrows, angled section dividers, images of people looking downward, numbered steps — anything that says "there's more".
- **Skimmability layer**: bolded key phrases, pull-quotes, icons — a skimmer reading only headings + bold text should still get the full pitch.

### Phase 5: Verify against the checklist

Before delivering, audit the page against `skills/landing-page-seo/references/checklist.md` (which includes the de-AI audit from `skills/landing-page-seo/references/human-feel.md`). Fix every failure. Then tell the user which items require action on their side (hosting speed, real testimonials, Google Search Console setup, etc.).

## Output format

- Default deliverable: a single self-contained `.html` file (inline CSS + JS) saved to the `output/` folder of the workspace, unless the user requests a framework (React/Next.js/etc.) or multi-file project. Also generate `robots.txt` (with AI crawlers explicitly allowed) and `llms.txt` per `skills/landing-page-seo/references/ai-readiness.md` and deliver them alongside the page.
- Use real copy, fully written out — never lorem ipsum, never `[insert testimonial here]`. If facts are unknown (prices, testimonial names), write realistic placeholders and flag them clearly to the user in the chat message.
- Include the full `<head>` metadata and JSON-LD even in drafts; these are the parts users most often forget to add later.
- After delivering, summarize: target keyword mapping (which keyword landed in which element), the narrative arc used, and a short "what you still need to do" list.

## Common failure modes to avoid

- **Keyword stuffing** — mention the primary keyword in H1, title, first 100 words, one H2, and naturally a few more times. Density beyond that reads as spam to both Google and humans.
- **Wall-of-features pages** — features listed without benefits or narrative order make visitors bounce at section 2.
- **Hero that says the company name instead of the visitor's outcome** — "PT Maju Jaya Teknologi" is not a headline; "Kelola stok toko tanpa spreadsheet" is.
- **All content visible only after JS runs** — if the copy isn't in the initial HTML, assume crawlers may not see it.
- **One giant CTA at the top only** — visitors who scroll to the bottom convinced but find no button will not scroll back up.
- **Design so generic it looks like a template** — distrust kills conversion; follow the anti-template rules in `skills/landing-page-seo/references/human-feel.md` section 2.
- **Copy that sounds AI-generated** — "di era digital yang serba cepat", empty power verbs (wujudkan/optimalkan/elevate), tricolon headings everywhere, emoji bullets. Visitors bounce from pages that feel machine-written; follow `skills/landing-page-seo/references/human-feel.md` and run its de-AI audit.
