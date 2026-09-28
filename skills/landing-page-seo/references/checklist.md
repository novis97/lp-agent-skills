# Pre-Delivery Checklist

Audit the finished page against every item. Fix failures before delivering. Items marked (user) can't be fixed in the HTML — report them to the user as next steps.

## SEO — on-page
- [ ] Exactly one `<h1>` containing the primary keyword, phrased as visitor outcome
- [ ] Title tag ≤60 chars, keyword near front, unique from meta description
- [ ] Meta description ≤155 chars, written as ad copy with a hook
- [ ] Canonical URL present
- [ ] `lang` attribute matches content language
- [ ] Open Graph + Twitter card tags complete (title, description, image, url)
- [ ] Primary keyword appears in: H1, title, first 100 words, ≥1 H2, ≥1 image alt
- [ ] Secondary keywords distributed across H2s/H3s/FAQ naturally (no stuffing)
- [ ] ≥500 words of real indexable text
- [ ] JSON-LD present and matches visible content (Organization/LocalBusiness + FAQPage at minimum)
- [ ] Heading hierarchy valid (no skipped levels); outline reads as a complete pitch alone
- [ ] All copy is real HTML text — nothing critical baked into images or JS-only rendering
- [ ] Descriptive anchor text on all links (no "klik di sini")

## SEO — technical/performance
- [ ] All images have alt text (empty alt for decorative), width + height set
- [ ] Below-fold images `loading="lazy"`; hero image eager/preloaded
- [ ] JS deferred / at end of body; no render-blocking scripts
- [ ] ≤2 web fonts, `font-display: swap`
- [ ] Content fully visible with JS disabled (reveal animations default to visible without JS)
- [ ] No layout shift patterns (reserved image space, no injected banners)
- [ ] (user) HTTPS, clean keyword slug, sitemap + Search Console submission, fast hosting/CDN

## Engagement / scroll
- [ ] Narrative arc present: hero → problem → solution → proof → objections → final CTA
- [ ] Each section seam has an open loop or directional cue pulling downward
- [ ] Hero communicates full promise within one mobile viewport; visual cue that content continues
- [ ] Pattern interrupt at least every 2-3 sections (background/layout alternation)
- [ ] Skim test passes: reading only headings + bolded phrases delivers the complete pitch
- [ ] "You" (kamu/Anda) outnumbers "we" (kami) roughly 2:1 in body copy
- [ ] Claims are specific (numbers, names, timeframes) — no bare superlatives
- [ ] Paragraphs ≤3 lines mobile; mobile headline ≤8 words
- [ ] Reveal animations respect `prefers-reduced-motion` and no-JS fallback
- [ ] No scroll-jacking, no fake urgency (fake timers/fake stock counters)

## AI-readiness (AEO/GEO) — full detail in references/ai-readiness.md
- [ ] View-source test: all claims, prices, FAQ answers exist as plain text in initial HTML (no JS-only content)
- [ ] Answer-first: every H2/H3 section states its key point in the first 1-2 sentences
- [ ] Summary block with 3-5 hard facts; one-sentence brand definition present
- [ ] Key claims standalone-quotable (numbers + dates, no pronoun-dependent facts)
- [ ] Brand name consistent everywhere; Organization schema includes `sameAs` links
- [ ] Visible last-updated date; prices stated with validity context
- [ ] robots.txt (AI crawlers allowed) and llms.txt generated and delivered
- [ ] (user) Host/CDN AI-bot blocking checked (Cloudflare etc.)

## Human feel (de-AI) — full detail in references/human-feel.md
- [ ] No AI-tell openers ("di era digital...", "solusi terpadu", "wujudkan impian")
- [ ] "Bukan hanya... tapi juga" + tricolon headings: max one each per page
- [ ] Abstract benefits rewritten as concrete scenarios (real objects, numbers, times)
- [ ] At least one opinionated line competitors wouldn't copy
- [ ] Register consistent (Anda XOR kamu); sentence lengths varied; read-aloud test passed
- [ ] No emoji bullets; icons only where they earn their place
- [ ] Typography has character (not one geometric sans for everything); palette brand-derived, not default gradient
- [ ] At least one deliberate grid break or authored detail; testimonials sound like real speech

## Conversion
- [ ] One primary goal/CTA for the whole page
- [ ] CTA appears: hero (soft), mid-page, final section (strong); sticky mobile bar if page is long
- [ ] CTA copy is outcome-oriented, not "Submit"
- [ ] Risk reversal (guarantee/trial/free consult) near the strongest CTA
- [ ] Social proof adjacent to the claims it supports; at least one specific testimonial
- [ ] Footer trust block: contact/address/legal
- [ ] (user) Placeholder testimonials/prices/URLs flagged for replacement with real data

## Accessibility (also an engagement + SEO factor)
- [ ] Color contrast ≥ 4.5:1 for body text
- [ ] Tap targets ≥44px; form inputs labeled
- [ ] Focus states visible; page navigable by keyboard
