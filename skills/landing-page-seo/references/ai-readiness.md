# AI-Readiness Reference (AEO/GEO)

Goal: make the page easy for AI assistants and answer engines (ChatGPT, Claude, Gemini, Meta AI, Perplexity, Copilot) to crawl, extract, quote, and cite. This traffic channel grows every quarter — pages that AI can't parse are invisible to it. Apply during Phase 3-4; the principles overlap heavily with good SEO, so most of this is refinement, not extra work.

## 1. The one rule that matters most

**Most AI crawlers do not execute JavaScript.** Everything — copy, FAQ answers, prices, stats, contact info — must exist in the initial HTML response. This skill already requires it for SEO; treat it as doubly non-negotiable. Quick test: view-source (not DevTools) and confirm every claim on the page is findable as plain text.

## 2. Answer-first writing ("quotability")

AI engines extract passages, not pages. Write so any section can be lifted out and still make sense:

- **BLUF (bottom line up front)**: the first sentence of each section states the answer/claim; explanation follows. AI models strongly prefer extracting from the first 1-2 sentences under a heading.
- **Standalone sentences**: each key claim should survive being quoted alone. "Prosesnya memakan waktu 7 hari kerja" is extractable; "Prosesnya secepat itu" (referring to a previous paragraph) is not. Repeat the subject noun instead of leaning on pronouns in key sentences.
- **Question-shaped headings**: H2/H3 phrased as the questions people ask AI ("Berapa biaya jasa desain interior per meter?") with a direct answer in the first sentence below. The FAQ section is the highest-value real estate for this.
- **Facts with numbers and dates**: "Sejak 2019, 1.200+ proyek" is citation bait; vague superlatives get skipped. Where a stat has a source, name it inline.
- **A summary block**: a short "Ringkasan" section (3-5 bullet facts: what it is, who it's for, price range, timeline, guarantee) near the top or bottom of the page. This is often the exact passage an AI will quote.
- **Tables and lists for comparisons/specs**: models extract structured text far more reliably than prose paragraphs for pricing tiers, package comparisons, and step sequences.

## 3. Entity clarity (so the AI knows *who* to attribute)

- Consistent exact brand name across title, H1 area, footer, and schema — no alternating between "MajuJaya", "PT Maju Jaya", "majujaya.id" as if they're different things.
- `Organization`/`LocalBusiness` JSON-LD with `sameAs` links to real profiles (Instagram, LinkedIn, Google Business Profile, Wikipedia if any). Cross-platform consistency is how models resolve the entity.
- One-sentence self-definition early on the page: "{Brand} adalah {category} yang {differentiator} untuk {audience}." This exact sentence-shape is what AI answers reuse when describing a business.
- Author/company credentials visible in text (years operating, certifications, address) — answer engines weigh verifiable-looking entities.

## 4. Crawler access (user-side, but generate the files)

Tell the user, and generate these files alongside the HTML when delivering:

**robots.txt** — AI crawlers must be explicitly allowed (many hosts/CDN presets block them). Letting them in is a business decision; the default recommendation for a landing page is allow-all, since being cited *is* the marketing:

```
User-agent: *
Allow: /

# AI assistant & answer-engine crawlers (explicit allow)
User-agent: GPTBot
User-agent: OAI-SearchBot
User-agent: ChatGPT-User
User-agent: ClaudeBot
User-agent: Claude-User
User-agent: anthropic-ai
User-agent: Google-Extended
User-agent: Gemini-Deep-Research
User-agent: PerplexityBot
User-agent: Perplexity-User
User-agent: meta-externalagent
User-agent: Bingbot
Allow: /

Sitemap: https://example.com/sitemap.xml
```

(Also warn: Cloudflare and some hosts now block AI bots by default — the user must check their firewall/bot-management settings, not just robots.txt.)

**llms.txt** — emerging convention (like robots.txt for LLMs) at `https://domain.com/llms.txt`: a short markdown file describing the site for AI consumption. Adoption is uneven, but it costs one small file:

```markdown
# {Brand}
> {One-sentence definition: category, differentiator, audience.}

## Layanan Utama
- [Jasa Desain Interior](https://example.com/): {one-line description, price range, timeline}

## Kontak
- WhatsApp: +62..., Email: ..., Alamat: ...
```

## 5. Freshness & maintenance signals

- Visible "Diperbarui: {bulan tahun}" date near the top or in the footer, plus `dateModified` in schema where applicable. AI engines prefer citing content with recency signals, especially for prices.
- Prices/promos stated with validity context ("harga per Juli 2026") so an AI quoting the page months later carries the caveat along.

## 6. What NOT to do

- No content hidden behind tabs/carousels/hover states that omit it from the DOM — collapsed-but-present (accordion with content in HTML, `<details>`) is fine; lazy-injected on click is not.
- No text-in-images for anything an AI should know (prices in a promo banner image = invisible prices).
- No hard paywalls/interstitials/aggressive cookie walls that serve crawler traffic a different empty page.
- Don't fabricate stats to be "citation bait" — AI answers now often surface alongside source links, and false claims attached to a brand name are permanent reputation damage.
- Don't stuff question-headings that the section doesn't actually answer; extraction models detect and skip bait.

## 7. AI-readiness quick audit

- [ ] View-source test: all claims, prices, FAQ answers present as plain text in initial HTML
- [ ] Every H2/H3 section answers within its first 1-2 sentences (BLUF)
- [ ] Key claims are standalone-quotable (no pronoun-dependent facts)
- [ ] Summary/Ringkasan block with 3-5 hard facts exists
- [ ] One-sentence brand definition present ("{Brand} adalah...")
- [ ] Organization schema has `sameAs` profile links; brand name consistent everywhere
- [ ] Numbers + dates on major claims; visible last-updated date
- [ ] robots.txt (AI crawlers allowed) and llms.txt generated and handed to user
- [ ] (user) Host/CDN bot-blocking checked; sitemap submitted; Google Business Profile consistent with page
