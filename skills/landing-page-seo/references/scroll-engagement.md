# Scroll Engagement Reference

Why visitors stop scrolling: they got the answer, they got bored, they got confused, or nothing signaled that continuing is worth it. Every technique here attacks one of those four causes. Use this file during Phase 2 (planning the arc) and Phase 4 (implementing mechanics).

## 1. Copywriting techniques that pull readers down the page

**Open loops.** End sections with an unresolved tension the next section resolves. The hero promises an outcome → "but why do most people fail at this?" → problem section. The problem section ends with "there's a simpler way" → solution section. Each seam of the page should make stopping feel like leaving a story mid-scene.

**The slippery slide (Sugarman).** The only job of each sentence is to get the next sentence read. First sentences of every section must be short and punchy — under 10 words. Long explanations come after the reader is already moving.

**PAS rhythm (Problem-Agitate-Solve).** Don't jump from problem to solution too fast. Agitation ("dan setiap bulan, biaya itu terus bertambah...") is what makes the solution feel earned and the reader feel understood. But keep agitation honest — exaggerated pain reads as manipulation.

**"You" density.** Count the yous (kamu/Anda) vs the wes (kami). If "kami/we" wins, the page is about the company, and visitors don't scroll for other people's stories about themselves. Aim for 2-3x more second-person than first-person.

**Specificity beats superlatives.** "Menghemat 11 jam per minggu" scrolls better than "sangat efisien". Numbers, names, and concrete scenarios create the credibility that keeps people reading. Every claim without a number is an invitation to bounce.

**Subheads as a parallel story.** A skimmer reading only H2s + bolded phrases must receive the complete pitch. Write the heading outline first, read it alone, and check: does it sell by itself?

**Objection sequencing.** Order sections by the objection timeline in the visitor's head: "do I have this problem?" → "does this actually solve it?" → "does it work for people like me?" → "is it worth the price?" → "what if it doesn't work?" (guarantee). Answering objections out of order confuses; confusion stops scrolls.

## 2. Visual & layout techniques

**Fold teasing.** Let the next section visibly peek above the fold boundary — a heading half-visible, an image edge, a diagonal divider pointing down. If the viewport bottom coincides exactly with a section boundary, the page looks finished.

**Pattern interrupts every 2-3 sections.** Alternate: light background → dark background → image-led section → text-led section. Two identical-looking sections in a row read as "same content, skip". Alternate left/right image placement in feature rows.

**Directional cues.** Down-arrows after the hero, numbered steps (1 → 2 → 3 implies "find 3"), photos of people gazing downward/toward the CTA, angled/curved section dividers. Eye-tracking consistently shows gaze follows depicted gaze.

**Whitespace as pacing.** Dense sections feel like work. Generous vertical padding (6-8rem desktop, 4rem mobile between sections) makes each scroll feel light. Line length ≤ 65-75 characters; paragraphs ≤ 3 lines on mobile.

**Progress signals.** For long pages: a slim scroll-progress bar, or "Langkah 2 dari 4" style labels in a how-it-works flow. Knowing how much remains reduces abandonment.

**Typography hierarchy that rewards skimming.** Big section heads (clamp(1.8rem, 4vw, 3rem)), clearly bolded key phrases (1-2 per paragraph max), pull-quote testimonials at larger size. The skim layer and the deep-read layer are two different products on the same page.

## 3. Motion & interaction (implementation patterns)

Subtlety rule: motion should whisper "alive", never shout "look at me". All motion must respect `prefers-reduced-motion` and never hide content from crawlers — animate from `opacity: 0` only via a JS-added class so no-JS environments (and bots) see everything.

```css
.reveal { opacity: 0; transform: translateY(24px); transition: opacity .6s ease, transform .6s ease; }
.reveal.visible { opacity: 1; transform: none; }
@media (prefers-reduced-motion: reduce) {
  .reveal { opacity: 1; transform: none; transition: none; }
}
```

```html
<!-- no-JS / crawler safety: only apply hidden state when JS runs -->
<script>
  document.documentElement.classList.add('js');
  // CSS: html.js .reveal { opacity: 0; ... }  html:not(.js) .reveal { opacity: 1; }
  const io = new IntersectionObserver((entries) => {
    entries.forEach(e => e.isIntersecting && e.target.classList.add('visible'));
  }, { threshold: 0.15 });
  document.querySelectorAll('.reveal').forEach(el => io.observe(el));
</script>
```

Other patterns worth using when they fit:
- **Count-up numbers** for stats sections (animate 0 → 2.500 when scrolled into view) — but the real number must be in the HTML as text content, JS only animates it.
- **Sticky mobile CTA bar** that appears after the visitor scrolls past the hero (visitors mid-page shouldn't need to hunt for the button).
- **Accordion FAQ** — but render answers in the HTML (visible to crawlers), collapsed via CSS/JS. Use `<details>/<summary>` for a zero-JS version.
- **Micro-interactions on CTA hover** (slight lift, shadow) — buttons that respond feel clickable.
- Avoid: scroll-jacking, autoplaying video with sound, parallax that causes jank on mid-range phones, entrance animations longer than ~700ms.

## 4. CTA strategy across the scroll

- **Hero CTA**: low-commitment framing for cold traffic ("Lihat Cara Kerjanya", "Cek Harga") — most visitors aren't ready to buy at pixel 0.
- **Mid-page soft CTA**: after social proof, when belief is forming.
- **Final CTA section**: the strongest ask, restating the core promise + risk reversal (garansi, trial gratis, konsultasi gratis) + a reason to act now that is true (limited slots, price change date — never fake countdown timers).
- CTA copy = first person outcome, not command: "Mulai Hemat Waktu Saya" outperforms "Submit". Keep one primary action per page; secondary CTAs (WhatsApp link) visually subordinate.
- Repeat the CTA roughly every 1.5-2 viewport heights on long pages.

## 5. Trust accelerants (placed to sustain momentum)

- Logo strip / "dipercaya oleh" immediately under the hero — borrowed credibility before the first claim.
- Testimonials adjacent to the claims they prove, with full name + photo + specific result. One great specific testimonial beats five generic ones.
- Numbers bar (klien dilayani, tahun pengalaman, rating) as a pattern interrupt between sections.
- Guarantee/risk-reversal near every hard CTA.
- Footer with real address, phone, legal pages — bounce insurance for skeptics who scroll to the bottom checking legitimacy.

## 6. Mobile-specific rules

- Thumb-reachable CTAs (bottom-anchored sticky bar), tap targets ≥ 44px.
- Hero must communicate the full promise in one phone viewport: headline + subhead + CTA + trust hint, no more.
- Test copy at 360px width mentally: a 12-word headline can wrap to 5 lines and die. Mobile headlines ≤ 8 words.
- Disable/simplify heavy animations on mobile; scroll performance is the engagement feature.
