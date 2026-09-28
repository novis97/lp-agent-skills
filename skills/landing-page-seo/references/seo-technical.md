# Technical SEO Reference for Landing Pages

Everything here goes into the code. Treat this as the implementation spec for Phase 3.

## 1. Head metadata

```html
<!DOCTYPE html>
<html lang="id"> <!-- match content language: id, en, etc. -->
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <!-- Title: ≤60 chars, primary keyword near the front, brand at the end -->
  <title>Jasa Desain Interior Rumah Minimalis | NamaBrand</title>

  <!-- Meta description: ≤155 chars. Written as AD COPY: hook + benefit + implicit CTA.
       It doesn't affect ranking directly but controls click-through rate. -->
  <meta name="description" content="Wujudkan rumah minimalis impian tanpa ribet. Konsultasi gratis, desain 3D dalam 7 hari, garansi revisi. Lihat portofolio kami.">

  <!-- Canonical: always, even if it's the only URL -->
  <link rel="canonical" href="https://example.com/jasa-desain-interior">

  <!-- Open Graph (controls how the link looks when shared) -->
  <meta property="og:type" content="website">
  <meta property="og:title" content="...">
  <meta property="og:description" content="...">
  <meta property="og:image" content="https://example.com/og-image.jpg"> <!-- 1200x630 -->
  <meta property="og:url" content="https://example.com/...">
  <meta property="og:locale" content="id_ID">

  <!-- Twitter -->
  <meta name="twitter:card" content="summary_large_image">
  <meta name="twitter:title" content="...">
  <meta name="twitter:description" content="...">
  <meta name="twitter:image" content="...">
</head>
```

Rules:
- One title formula that works: `{Primary Keyword} — {Differentiator/Benefit} | {Brand}`.
- Never duplicate title and meta description text.
- If the user has no domain yet, use a clearly-marked placeholder URL and tell them to replace it.

## 2. Heading hierarchy

- Exactly **one `<h1>`**, containing the primary keyword, phrased as the visitor's outcome.
- `<h2>` per major section; secondary keywords live naturally in H2s.
- `<h3>` for sub-points (individual features, FAQ questions).
- Never skip levels (h1 → h3) and never choose a heading tag for its font size — style with CSS.
- Headings must make sense read in isolation: the h1+h2 outline is what crawlers and skimmers both consume.

## 3. Semantic structure skeleton

```html
<body>
  <header>          <!-- logo + minimal nav + header CTA -->
  <main>
    <section id="hero">
    <section id="masalah">      <!-- problem agitation -->
    <section id="solusi">
    <section id="fitur">        <!-- or "cara-kerja" -->
    <section id="testimoni">
    <section id="faq">
    <section id="cta-akhir">
  </main>
  <footer>          <!-- NAP (name-address-phone) if local business, links, legal -->
</body>
```

- Section `id`s double as anchor-link targets for the nav — internal anchors improve UX and give crawlers structure hints.
- Use `<figure>/<figcaption>` for annotated images, `<blockquote>` + `cite` for testimonials, `<address>` for contact info.

## 4. Structured data (JSON-LD)

Place in `<head>` or before `</body>`. Choose types that match the page — do not mark up content that isn't visibly on the page (that's a penalty risk).

Almost always applicable:
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",   // or LocalBusiness / ProfessionalService
  "name": "...",
  "url": "...",
  "logo": "...",
  "sameAs": ["https://instagram.com/...", "..."]
}
</script>
```

If the page has an FAQ section (it should — see narrative arc):
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "Berapa lama proses pengerjaannya?",
      "acceptedAnswer": { "@type": "Answer", "text": "..." }
    }
  ]
}
</script>
```

Other useful types: `Product` (with `offers` and `aggregateRating` if real reviews exist), `Service`, `BreadcrumbList` (multi-page sites), `Review`. For LocalBusiness include `address`, `geo`, `openingHours`, `telephone`.

## 5. Images

- Descriptive filenames (`desain-interior-ruang-tamu.jpg`, not `IMG_2041.jpg`) and `alt` text that describes the image while naturally including a keyword where honest.
- Always set `width` and `height` attributes (prevents CLS — Cumulative Layout Shift).
- `loading="lazy"` on all images **below the fold**; the hero image loads eagerly (and can be preloaded with `<link rel="preload" as="image">`).
- Recommend WebP/AVIF to the user; use `<picture>` with fallbacks when multiple formats are provided.
- Decorative images: empty `alt=""` so screen readers skip them.

## 6. Performance / Core Web Vitals

Targets: LCP < 2.5s, CLS < 0.1, INP < 200ms. In a single-file landing page:

- Inline critical CSS in `<head>` (a single-file deliverable does this automatically — keep total CSS lean).
- Defer all non-essential JS (`defer` attribute or scripts at end of body). Animation JS must never block first paint.
- System font stack or at most 1-2 web fonts with `font-display: swap` and preconnect to the font host.
- No render-blocking third-party scripts in drafts. If the user needs analytics/pixels, add them with `defer`/`async` and note the tradeoff.
- Avoid layout-shifting patterns: reserve space for images, don't inject banners above content after load.

## 7. Content-level SEO rules

- Primary keyword placement: title tag, H1, first 100 words of body copy, at least one H2, one image alt, URL slug. After that, use synonyms and natural variants (Google understands semantics; exact-match repetition is counterproductive).
- Secondary keywords: one per section heading where natural, plus FAQ questions (FAQs are the perfect home for long-tail queries like "berapa biaya...", "apakah bisa...").
- Minimum ~500-800 words of real indexable text on the page. Landing pages that are all images/hero-taglines have nothing to rank with.
- Outbound links to genuinely relevant authority sources are fine; internal links to other site pages (if they exist) help. All links get descriptive anchor text, never "klik di sini".
- Write for reading level ~grade 7-8: short sentences, active voice, concrete nouns.

## 8. Crawlability & indexing notes to pass to the user

These are outside the HTML file but the user must know:
- Submit the URL in Google Search Console; create/update `sitemap.xml` and `robots.txt`.
- HTTPS is mandatory (ranking factor + trust).
- Clean URL slug containing the primary keyword: `/jasa-desain-interior`, not `/page?id=17`.
- If content is translated/multi-locale later: `hreflang` tags.
- Real page speed depends on hosting + CDN; the HTML can be perfect and still slow on bad hosting.
