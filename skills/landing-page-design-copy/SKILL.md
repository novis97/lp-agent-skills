---
name: "landing-page-design-copy"
description: "Rancang dan tulis landing page dari nol sampai jadi — arah visual unik (Vibe Discovery), copy konversi (hero sampai CTA), SEO + GEO lewat landing-page-seo, build, dan QA. Untuk landing page, sales page, atau product page baru maupun redesign."
---

# Landing Page: Desain + Copy + SEO/GEO

Satu halaman, satu tujuan konversi: signup, pembelian, demo request, download, atau lead capture.

Tiga hal menentukan halaman itu bekerja atau tidak — **tampilannya** (kelihatan ada yang bikin, atau template generik?), **kata-katanya** (pengunjung paham kamu jual apa dan kenapa harus bertindak?), dan **bisa ditemukan atau tidak** (mesin pencari dan AI answer engine tahu halaman ini ada?). Skill ini menjalankan ketiganya dalam satu alur, dengan gate sebelum satu baris kode atau copy final ditulis.

---

## Hubungan dengan `landing-page-seo`

Skill ini **pintu masuknya**. `landing-page-seo` adalah **mesin teknis** yang dipanggil di Fase 4.

Skill ini memutuskan halaman ini *terasa seperti apa* dan *bilang apa*. `landing-page-seo` memutuskan halaman ini *ditemukan bagaimana* — semantic HTML, meta tag, structured data, Core Web Vitals, llms.txt, robots.txt, copy answer-first. Jangan salin isinya ke sini; panggil file referensinya saat dibutuhkan.

**Kalau user cuma minta audit atau perbaikan SEO halaman yang sudah jadi**, tanpa menyentuh desain dan copy — langsung ke `landing-page-seo`, lewati skill ini.

### Resolusi konflik

Dua skill ini bertabrakan di tujuh tempat. Saat bertabrakan, ikuti kolom "yang dipakai".

| Titik | Skill ini bilang | `landing-page-seo` bilang | Yang dipakai |
|---|---|---|---|
| **Posisi social proof** | Section 2, di scroll pertama | Section 5, setelah fitur | **Section 2.** Kepercayaan adalah rintangan pertama. Bukti tambahan tetap ditaruh lagi di section 4–5 dekat klaim yang didukungnya — bukti boleh muncul dua kali. |
| **Isi subheadline** | Mekanisme — bagaimana janji ditepati | Menjawab keberatan terbesar | **Mekanisme.** Keberatan terbesar punya tempatnya sendiri di section 6. Subheadline yang berdebat sebelum janjinya kredibel terasa defensif. |
| **Headline vs keyword** | Lolos litmus test — pengunjung tahu kamu jual apa dari headline saja | Primary keyword ada di H1 | **Dua-duanya wajib.** Cari frasa yang memenuhi keduanya. Kalau benar-benar tidak bisa: litmus test menang di H1, keyword pindah ke title tag dan H2 pertama. Halaman yang ranking tapi membingungkan tidak mengonversi. |
| **Data yang belum ada** | Nyatakan kekosongannya, `[BUKTI KOSONG: ...]` | Tulis placeholder realistis lalu tandai ke user | **Nyatakan kekosongannya.** Tidak bisa dinegosiasi untuk testimoni, logo klien, angka hasil, nama pelanggan — itu klaim tentang pihak ketiga. Placeholder realistis hanya untuk data milik user sendiri (harga, jam buka, alamat), tetap ditandai. |
| **Struktur section** | 7 section Fase 3 | Narrative arc 7 langkah | **Struktur Fase 3 skill ini**, karena sudah memuat semua elemen arc `landing-page-seo` plus penanganan keberatan eksplisit. Ritme open-loop → payoff antar section dari `landing-page-seo` tetap dipakai. |
| **Arah desain** | Vibe Discovery Q1–Q4 | "Ajukan arah desain yang khas" | **Vibe Discovery.** Lebih spesifik dan punya gate. Abaikan saran "propose a distinctive direction" di `landing-page-seo` langkah 6. |
| **Anti-AI-slop** | Tingkat visual (font, warna, tabrakan) | `skills/landing-page-seo/references/human-feel.md` — tingkat copy Bahasa Indonesia | **Dua-duanya.** Saling melengkapi, tidak bertabrakan. Jalankan de-AI audit `human-feel.md` untuk copy, Freshness Check untuk visual. |

---

## Jangan pakai skill ini untuk

- Audit atau perbaikan SEO halaman yang sudah jadi, tanpa sentuh desain/copy → `landing-page-seo` langsung
- Konten blog / editorial panjang, email sequence, definisi brand voice, website multi-halaman, atau A/B testing halaman yang sudah jalan → **di luar cakupan skill ini.** Bilang terus terang ke user bahwa tugas itu tidak ditangani skill ini, jangan memaksakan alur landing page ke sana.

---

## Langkah pertama: tentukan mode deliverable

Tanya kalau belum jelas. Ini mengubah alur kerjanya.

| Mode | Output | Fase yang dijalankan |
|---|---|---|
| **Copy-only** | Markdown terstruktur + peta keyword + blok metadata, siap masuk CMS atau diserahkan ke desainer | 0 → 1 → 2 → 3 → 4 (bagian copy saja) → 7 |
| **Full build** | Halaman HTML/React jadi + robots.txt + llms.txt | Semua fase 0 → 7 |

Di mode copy-only, Vibe Discovery tetap dijalankan singkat — tone copy dan tone visual tidak boleh bertabrakan — tapi Freshness Check dan fase build dilewati. SEO/GEO tetap jalan di level copy dan struktur heading; yang dilewati cuma implementasi HTML-nya.

---

## Persamaan konversi

```
Purchase Rate = Desire − (Labor + Confusion)
```

Setiap keputusan di halaman — satu kata, satu field form, satu section, satu animasi — harus menaikkan *desire* atau menurunkan *labor/confusion*. Kalau tidak dua-duanya, buang.

---

## Aturan 50%

Separuh total effort masuk ke hero. Hero adalah preview waktu di-share, kesan pertama, dan bagian yang mungkin satu-satunya dibaca mayoritas pengunjung. Berlaku untuk **dua-duanya**: desain hero dan copy hero. Semua yang di bawah fold cuma mewarisi janji yang dibuat hero.

---

# FASE 0 — Input wajib

Kumpulkan sebelum apa pun. Jangan dikarang.

**Penawaran**
- Apa yang dijual, harganya berapa (kalau ada), pengunjung dapat apa persisnya
- Satu tujuan konversi (satu aksi — bukan tiga)

**Audiens**
- Segmen spesifik, bukan "pelaku usaha"
- Kekhawatiran spesifik yang mereka bawa saat mendarat di halaman

**Voice dan bukti**
- Brand voice, kalau sudah didefinisikan
- Bahasa pelanggan asli: testimoni, tiket support, transkrip sales call, chat WhatsApp, review, thread forum
- **Voice sample mentah** — minta user menjelaskan produknya dalam 2–3 kalimat "seperti kalau cerita ke teman", plus satu keyakinan yang tidak dipegang kompetitor. Bahan mentah ini yang membuat copy tidak terdengar seperti tulisan AI.
- Bukti nyata: logo klien, angka, studi kasus, sertifikasi

**Penemuan (SEO/GEO)**
- **Primary keyword + 2–4 secondary keyword.** Kalau user tidak tahu, ajukan usulan berdasarkan produknya — apa yang benar-benar akan diketik audiensnya di Google. Primary keyword mengarahkan H1, title tag, URL slug, dan 100 kata pertama.
- **Bahasa dan lokal** — memengaruhi atribut `lang`, hreflang, pilihan keyword, dan tone
- **Domain dan URL tujuan**, kalau sudah ada
- Apakah halaman ini perlu dikutip AI answer engine (ChatGPT, Perplexity, Gemini). Untuk mayoritas klien jawabannya ya — ini default, bukan tambahan.

**Constraint**
- Aset brand yang terkunci (logo, warna wajib, design system yang sudah ada)
- Tech stack, batas panjang, format, aturan regulasi

Kalau audiens atau keberatan belum jelas, **berhenti dan minta ke user**: rekaman atau ringkasan sales call, chat WhatsApp pelanggan, review, atau tiket support. **Jangan menebak keberatan** — keberatan hasil tebakan menghasilkan halaman yang berdebat dengan orang yang tidak ada.

---

# FASE 1 — Dua spec (gate keras)

**Tulis kedua spec sebelum kode apa pun dan sebelum copy final apa pun.** Tidak ada "nanti gayanya sambil jalan." Jalankan dua discovery ini paralel; keduanya saling memberi input.

## 1A. Vibe Discovery → Vibe Spec

Ajukan empat pertanyaan ini. Minta jawaban asli dari user; jangan dijawab sendiri kecuali user memang tidak ada.

**Q1 — Jangkar dunia nyata.**
"Kalau halaman ini berwujud tempat, benda, atau era — apa?"
Katalog hi-fi Jepang 1970-an. Buku catatan lapangan. Apotek Mediterania. Pit lane balapan di malam hari.
→ **Dari sinilah palet warna diturunkan.** Generate nilai hex baru dari referensi itu. Jangan pernah mengambil palet yang kamu ingat dari proyek lain.

**Q2 — Rasa tiga detik.**
"Siapa yang mendarat di sini, dan mereka harus merasa apa dalam tiga detik pertama?"
Tenang dan terkendali. Terkejut. Merasa menemukan sesuatu sebelum orang lain. Aman menyerahkan uang.
→ Menentukan skala tipografi, kepadatan, intensitas gerak, dan seberapa "kencang" hero-nya.

**Q3 — Tabrakan.**
"Sebutkan dua pengaruh yang harus bertabrakan di halaman ini — dan yang jelas-jelas tidak nyambung satu sama lain."
Grid Swiss × coretan tangan di margin. Beton brutalis × ilustrasi botani lembut. Tampilan terminal × editorial cetak mewah.
→ **Keduanya wajib terlihat di halaman jadi.** Satu pengaruh saja = template. Tabrakannya itulah identitasnya.

**Q4 — Terkunci dan bebas.**
"Apa yang tidak bisa diganggu gugat (logo, warna brand, stack, kepatuhan), dan di bagian mana aku boleh melanggar aturan?"
→ Menentukan area main si wildcard.

**Format Vibe Spec** — tulis eksplisit:

```markdown
## Vibe Spec: [KASIH NAMA]

- Jangkar (Q1): [referensi] → palet diturunkan: [nilai hex + perannya]
- Rasa (Q2): [target emosi 3 detik] → kepadatan: [rapat/lapang], gerak: [tertahan/ekspresif]
- Tabrakan (Q3): [pengaruh A] × [pengaruh B]
  - A muncul sebagai: [elemen konkret]
  - B muncul sebagai: [elemen konkret]
- Terkunci (Q4): [constraint]
- Wildcard: [satu elemen yang tidak nyambung — dan alasan dia tetap ada]
- Tipografi: [font display] / [font body] — kenapa pasangan ini, bukan default
- Ikon: [set] — bukan Lucide
- Elemen memorable: [satu hal yang bisa diceritakan pengunjung ke rekannya setelah menutup tab]
```

**Aturan 5 — kasih nama vibe-nya.** Vibe tanpa nama akan melenceng balik ke generik di section ketiga. "Pit Lane Editorial." "Brutalisme Apotek." Sebut namanya tiap kali mengambil keputusan.

## 1B. Copy Discovery → Copy Spec

**Langkah 1 — Temukan 3 keberatan pembeli teratas.** Dari sumber nyata (sales call, tiket support, wawancara churn, review kompetitor). Urutkan berdasarkan seberapa sering keberatan itu membunuh deal.

**Langkah 2 — Tulis headline** dengan formula **Value Prop + Hook**:
- *Value prop:* hasil konkret yang didapat pengunjung
- *Hook:* alasan untuk percaya, kejutannya, atau rasa sakit yang dibalik

Buat 5–10 variasi. Sisir mana yang bisa memuat primary keyword secara wajar — keyword yang dipaksa masuk terdengar seperti robot dan merusak litmus test.

**Langkah 3 — Definisikan CTA sebagai kelanjutan narasi.** Tombol menyelesaikan kalimat hero. Kalau hero bilang "Temukan makan malam di dekatmu dalam 30 detik," tombolnya **"Cari makanan di dekat saya"** — bukan "Mulai sekarang."

**Langkah 4 — Tulis kalimat definisi brand.** Satu kalimat, format: `{Brand} adalah {kategori} yang {pembeda} untuk {audiens}.` Ini yang akan dikutip AI answer engine saat ditanya "apa itu {brand}". Kalau kamu tidak menuliskannya, mesin akan mengarangnya sendiri dari potongan halaman.

**Format Copy Spec:**

```markdown
## Copy Spec

- Penawaran: [apa, harga, dapat apa]
- Audiens: [segmen spesifik]
- Tujuan konversi: [SATU aksi]
- Keberatan 1: [teks] → dijawab oleh: [section/mekanisme]
- Keberatan 2: [teks] → dijawab oleh: [section/mekanisme]
- Keberatan 3: [teks] → dijawab oleh: [section/mekanisme]
- Headline: [pilihan] (value prop: [x] + hook: [y])
- Subheadline: [mekanismenya — bagaimana janji itu ditepati]
- CTA utama: [teks tombol] ← melanjutkan headline dengan cara: [satu baris]
- Frasa pelanggan yang dipakai apa adanya: [daftar]
- Bukti yang tersedia: [daftar] / Bukti yang belum ada: [daftar]

### Peta keyword
- Primary: [keyword] → H1: [ya/tidak + alasan kalau tidak] · title tag · 100 kata pertama · H2 ke-[n] · URL slug
- Secondary 1–4: [keyword] → [section mana]
- Kalimat definisi brand: [satu kalimat]
- 3–5 fakta keras untuk blok ringkasan: [daftar — ini yang dikutip AI]
```

---

# FASE 2 — Gate

Jangan lanjut sebelum semuanya lolos.

## Gate A — Freshness Check (visual)

Jawab jujur. Satu "tidak" berarti balik ke Fase 1A.

- [ ] Warna diturunkan dari jangkar Q1, bukan dari ingatan atau proyek sebelumnya
- [ ] Font display belum dipakai di proyek terbaru, dan tidak ada di daftar terlarang
- [ ] **Kedua** pengaruh Q3 terlihat oleh orang yang tidak membaca spec
- [ ] Wildcard-nya ada dan terasa sedikit mengganggu
- [ ] Vibe-nya punya nama
- [ ] Screenshot hero-nya tidak akan tertukar dengan empat halaman lain yang dibuat bulan ini

## Gate B — Litmus Test headline (copy)

> Kalau pengunjung hanya melihat **headline saja** — tanpa logo, tanpa gambar, tanpa subheadline — apakah mereka langsung tahu kamu jual apa?

Tidak → tulis ulang. Gate ini tidak ada nilai setengah.

Cek kedua: apakah CTA utama melanjutkan cerita headline, atau cuma kata kerja generik yang ditempel?

## Gate C — Penemuan (SEO/GEO)

- [ ] Primary keyword sudah ditetapkan, bukan diasumsikan
- [ ] Peta keyword terisi — tiap keyword punya rumah, tidak menumpuk di satu section
- [ ] Kalimat definisi brand sudah ditulis
- [ ] 3–5 fakta keras sudah terdaftar dan **semuanya bisa diverifikasi** — fakta karangan yang dikutip AI answer engine akan beredar tanpa bisa ditarik kembali
- [ ] Headline lolos Gate B *dan* memuat primary keyword — atau ada keputusan sadar kenapa tidak, dengan keyword dipindahkan ke title tag dan H2 pertama

---

# FASE 3 — Struktur halaman

Tujuh tugas berurutan. Strukturnya boleh lentur — digabung, ditukar, diperluas — tapi semua elemen tetap ada, dan **social proof tetap di awal**.

Di antara section, jaga ritme **open-loop → payoff**: setiap section membuka pertanyaan yang dijawab section berikutnya. Orang tidak scroll karena ada konten; mereka scroll karena ada yang belum selesai.

| # | Section | Tugasnya | Beban SEO/GEO |
|---|---|---|---|
| 1 | Hero | Menentukan mereka bertahan atau pergi (3–5 detik) | H1 + primary keyword |
| 2 | Social proof awal | Membuktikan ada orang lain yang sudah percaya | Review/Organization schema |
| 3 | Masalah / janji | Menunjukkan kamu paham situasi mereka | Bahasa audiens = keyword long-tail alami |
| 4 | Solusi / mekanisme | Apa yang kamu lakukan, dibingkai sebagai hasil | Product schema, H2 answer-first |
| 5 | Bukti dan detail | Mengonversi pembaca yang sudah serius | Blok ringkasan 3–5 fakta keras |
| 6 | Menjawab keberatan | Menjawab tiga alasan mereka bilang tidak | FAQPage schema + keyword long-tail |
| 7 | CTA penutup | Menutup. Mengulang aksinya. | — |

**Blok layout opsional**, ditaruh hanya kalau memang layak:
- **Cara kerja** — urutan 3 langkah. Tempatnya *di dalam* section 4, bukan halte terpisah, kecuali kerumitan setup memang salah satu keberatan utama. Kandidat kuat untuk HowTo schema.
- **Pricing** — antara 5 dan 6 kalau harga masuk 3 keberatan teratas; setelah 6 kalau tidak.
- **Footer** — navigasi dan legal. Jangan pernah jadi CTA kedua yang bersaing.

**Aturan answer-first**: setiap H2/H3 menyatakan klaim utamanya di 1–2 kalimat pertama, sebelum penjelasan apa pun. Ini yang diekstrak mesin, dan kebetulan juga yang dibaca manusia yang memindai. Satu aturan, dua audiens.

## 1. Hero

Tiga komponen, tidak lebih: **Headline** (janji) · **Subheadline** (mekanisme) · **CTA utama** (satu tombol, label deskriptif).

Opsional: satu penanda pendukung ("Tanpa kartu kredit"), satu visual hero, satu petunjuk visual bahwa konten berlanjut di bawah fold.

Headline = satu-satunya `<h1>` di halaman, memuat primary keyword, dibingkai sebagai hasil yang diinginkan pengunjung — bukan nama perusahaan.

**Pola kuat**
- *Hasil + audiens + mekanisme* — "Rilis fitur 3x lebih cepat, untuk tim engineering yang benci rapat, lewat perencanaan async-first."
- *Pembalikan rasa sakit* — "Berhenti kehilangan pelanggan gara-gara halaman lambat."
- *Klaim mengejutkan* — "Aplikasi catatan yang benar-benar dipakai. Datanya ada."
- *Sapaan langsung* — "Ada 47 pesan Slack yang belum kamu baca. Ini yang harus dilakukan."

**Pola lemah**
- Tumpukan kata sifat: "Powerful, intuitif, scalable"
- "Selamat datang di platform kami"
- Headline nama brand saja: "Acme: Masa Depan X" — "PT Maju Jaya Teknologi" bukan headline; "Kelola stok toko tanpa spreadsheet" baru headline
- Manfaat kabur: "Sederhanakan alur kerja Anda"

## 2. Social proof (awal)

Di scroll pertama, sebelum pengunjung menginvestasikan perhatian. Logo pelanggan (yang dikenal lebih kuat dari yang asing) · sinyal kepercayaan berangka ("Lebih dari 10.000 tim") · satu testimoni kuat dengan nama dan jabatan · logo media.

**Jangan pernah dipalsukan.** Kalau bukti belum ada, hilangkan section ini secara sadar dan pikul beban kepercayaan lewat spesifisitas plus risk reversal.

Bukti tambahan tetap ditaruh lagi di dekat klaim yang didukungnya di section 4 dan 5 — bukti tidak harus menumpuk di satu blok.

## 3. Masalah / janji

1–3 paragraf menyebut masalah spesifik, dalam bahasa pengunjung — hasil menggali, bukan karangan. Berhenti sebelum menjual. Resonansi dulu.

**Tes:** bacakan keras-keras. Audiens targetnya mengangguk? Kalau belum, kamu belum paham mereka.

## 4. Solusi / mekanisme

Satu headline yang merangkum solusi, lalu 3–5 kemampuan, masing-masing 1–2 kalimat, masing-masing dibingkai sebagai hasil yang dihasilkan. Didukung visual: screenshot, ilustrasi, klip pendek.

**Setiap fitur harus nyambung balik ke value prop hero.** Kalau tidak, tempatnya di halaman dokumentasi.

**Mode gagal:** "Kolaborasi real-time" itu fitur. "Edit bareng tanpa copy-paste dari email" itu hasil.

## 5. Bukti dan detail

1–3 studi kasus (pelanggan spesifik, hasil spesifik, angka spesifik) · testimoni beratribusi · data point · penghargaan atau validasi pihak ketiga.

Pembaca sekilas tidak akan sampai sini. Yang sampai sini sudah siap beli — kasih semuanya.

Di section ini juga tempat **blok ringkasan**: kalimat definisi brand plus 3–5 fakta keras dalam format yang mudah diekstrak. Untuk manusia ini ringkasan; untuk AI answer engine ini sumber kutipan.

## 6. Menjawab keberatan

Jawab tiga keberatan dari Copy Spec, secara eksplisit. Formatnya: FAQ (mudah dipindai), tabel perbandingan (vs kompetitor atau vs tidak melakukan apa-apa), risk reversal (garansi uang kembali, free trial, tanpa kontrak), bukti effort rendah ("Setup 5 menit, bukan 5 minggu").

Format FAQ punya bonus: pertanyaan pengunjung biasanya persis keyword long-tail yang mereka ketik, dan section ini jadi FAQPage structured data tanpa kerja tambahan.

## 7. CTA penutup

Ulangi penawaran, ulangi aksinya. Pakai teks CTA yang sama dengan hero supaya konsisten. Bingkai dalam situasi pengunjung ("Siapkan tim Anda dalam 5 menit"). Hilangkan friksi. **Satu aksi saja.**

Hindari: tombol yang saling bersaing, penawaran baru yang muncul tiba-tiba di bawah, form yang meminta lebih banyak dari yang dibutuhkan aksinya.

---

# FASE 4 — SEO + GEO (delegasi)

Sampai titik ini kamu sudah punya struktur, copy, dan arah visual. Sekarang pastikan halaman ini bisa ditemukan.

**Baca file referensi `landing-page-seo` sebelum menulis kode.** Buka dengan filesystem tool — jangan menulis dari ingatan. Kalau salah satu file tidak bisa dibuka, berhenti dan laporkan ke user.

- `skills/landing-page-seo/references/seo-technical.md` — semantic HTML, meta tag, structured data, Core Web Vitals
- `skills/landing-page-seo/references/ai-readiness.md` — llms.txt, robots.txt untuk AI crawler, copy answer-first, blok ringkasan
- `skills/landing-page-seo/references/human-feel.md` — aturan voice Bahasa Indonesia dan de-AI audit tingkat copy
- `skills/landing-page-seo/references/scroll-engagement.md` — mekanik open-loop dan momentum scroll
- `skills/landing-page-seo/references/checklist.md` — audit akhir

**Yang tidak bisa ditawar, apa pun stack-nya:**

- Struktur semantik: `<header>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<nav>`; tepat satu `<h1>`; hierarki h2/h3 yang mengikuti struktur Fase 3
- Semua copy bermakna ada di HTML asli — tidak ditanam di gambar, tidak hanya dirender JS
- `<head>` lengkap: title tag (≤60 karakter, keyword di depan), meta description (≤155 karakter, ditulis seperti copy iklan), canonical, Open Graph + Twitter card (preview WhatsApp klien kamu bergantung pada ini), atribut `lang`
- JSON-LD sesuai jenis halaman: Organization/LocalBusiness, Product, FAQPage, Review
- `alt` deskriptif di setiap gambar; lazy-load di bawah fold; width/height eksplisit supaya tidak layout shift
- Mobile-first — mayoritas trafik landing page dari HP, dan Google mengindeks mobile lebih dulu
- `robots.txt` (AI crawler diizinkan eksplisit) dan `llms.txt` ikut dikirim bersama halaman

**Mode copy-only:** yang dikerjakan di fase ini hanya bagian copy — struktur heading, copy answer-first, blok ringkasan, teks title tag dan meta description. Serahkan sisanya lewat checklist di Fase 7.

**Jangan keyword stuffing.** Primary keyword muncul di H1, title tag, 100 kata pertama, satu H2, lalu seperlunya secara alami. Lebih dari itu terbaca spam oleh Google maupun manusia.

---

# FASE 5 — Build (khusus mode full build)

1. **Riset & kumpulkan** — kumpulkan referensi, kunci font, ikon, dan palet hasil turunan Q1
2. **Kembangkan hero** — bangun dan iterasi sampai benar-benar khas. 50% effort mendarat di sini.
3. **Bangun section** — satu per satu, berurutan. Jangan bikin tujuh section kosong lalu diisi belakangan.
4. **Layer engagement** — latar section berselang-seling, reveal saat scroll pakai IntersectionObserver (hormati `prefers-reduced-motion`), CTA bertahap (lunak di tengah, kuat di akhir, opsional sticky bar mobile), petunjuk arah, lapisan skimmable (frasa tebal, pull-quote). **Jangan pernah mengunci konten di balik interaksi** — crawler dan manusia tidak sabar harus melihat semuanya.
5. **Poles** — responsif, performa, aksesibilitas
6. **Presentasi** — screenshot cover, layout infinity canvas untuk halaman penuh

Sistem warna masuk CSS variables sejak baris pertama — bukan hex hardcoded yang berserakan.

---

# FASE 6 — Quality gate

**Kekhasan visual**
- [ ] Tidak ada gradien ungu generik
- [ ] Set ikon bukan default
- [ ] Pasangan font khas
- [ ] Minimal satu elemen memorable
- [ ] CSS variables untuk sistem warna
- [ ] Kedua pengaruh Q3 masih terlihat setelah dipoles

**Teknis**
- [ ] Responsif — tes di 375px **dulu**, bukan terakhir
- [ ] Semua gambar termuat
- [ ] Animasi performan (transform/opacity, tanpa layout thrash)
- [ ] Kontras aksesibel (4,5:1 teks body, 3:1 teks besar)
- [ ] Load awal cepat
- [ ] Semua URL tujuan berfungsi

**Konversi**
- [ ] Headline lolos litmus test
- [ ] CTA utama adalah kelanjutan narasi, bukan "Mulai Sekarang"
- [ ] Ketiga keberatan dijawab di halaman
- [ ] Social proof ada — atau sengaja dihilangkan, tidak pernah dipalsukan
- [ ] Setiap fitur nyambung balik ke value prop hero
- [ ] Hierarki logis; tidak ada CTA yang bersaing
- [ ] Bacakan seluruh halaman keras-keras: di akhir, aksi berikutnya sudah jelas?

**Penemuan (SEO/GEO)**
- [ ] Tepat satu `<h1>`, memuat primary keyword
- [ ] Title tag ≤60 karakter, meta description ≤155 karakter, canonical, `lang`, Open Graph — cek preview link WhatsApp-nya beneran
- [ ] JSON-LD ada dan lolos validator
- [ ] Setiap H2/H3 menyatakan klaimnya di 1–2 kalimat pertama
- [ ] Blok ringkasan ada: kalimat definisi brand + 3–5 fakta terverifikasi
- [ ] `robots.txt` dan `llms.txt` ikut dikirim
- [ ] Semua copy terlihat di HTML asli tanpa JS
- [ ] De-AI audit `human-feel.md` dijalankan — tidak ada "di era digital yang serba cepat", tidak ada tumpukan kata kerja kosong (wujudkan/optimalkan/elevate), tidak ada heading tiga-serangkai di mana-mana, tidak ada bullet emoji
- [ ] Tidak ada keyword stuffing

---

# FASE 7 — User test dan serah terima

## User test (6 pertanyaan)

Jalankan dengan **dua tipe reviewer**: satu orang dari audiens target, satu orang yang belum pernah dengar produknya.

Tunjukkan hero selama lima detik, lalu tutup:

1. Perusahaan ini jual apa?
2. Untuk siapa?
3. Kamu akan klik apa, dan kamu berharap terjadi apa?
4. Apa yang bikin kamu ragu?
5. Apa yang kamu ingat soal tampilannya?
6. Apa yang kurang sebelum kamu mau bertindak?

Q1 gagal = masalah headline. Q3 gagal = masalah CTA. Q4 = ada keberatan yang belum dijawab. Q5 kosong = Freshness Check-nya bohong.

## Serah terima

**Mode copy-only.** Deliverable-nya dokumen markdown, bukan halaman jadi. Spell-check copy-nya sendiri, lalu lampirkan checklist pasca-import untuk siapa pun yang membangun halamannya.

**Mode full build.** Jalankan checklist Fase 6 sendiri. Serahkan halamannya plus Vibe Spec, Copy Spec, robots.txt, dan llms.txt, supaya orang berikutnya yang mengedit tahu aturan yang dia warisi.

**Selalu tutup dengan tiga hal** ke user:
1. Peta keyword — keyword mana mendarat di elemen mana
2. Struktur naratif yang dipakai dan alasannya
3. "Yang masih perlu kamu kerjakan" — hal di luar kendali halaman: kecepatan hosting, testimoni asli yang belum ada, setup Google Search Console, verifikasi Google Business Profile

---

# REFERENSI — Anti-AI-slop

Halaman buatan AI selalu bertemu di titik yang sama: gradien ungu, Inter, ikon Lucide, bento grid generik, fade-up-on-scroll yang itu-itu saja. Vibe Spec ada untuk memutus konvergensi itu.

Ini sisi **visual**. Sisi **copy** ditangani `skills/landing-page-seo/references/human-feel.md` milik `landing-page-seo` — jalankan dua-duanya.

**Lima aturan anti-konvergensi**

1. **Jangan mengingat kode hex** — generate warna baru dari jangkar Q1
2. **Wajib rotasi font** — font display tidak boleh diulang antar proyek
3. **Tabrakan harus terlihat** — kedua pengaruh Q3 kelihatan di halaman jadi
4. **Wildcard wajib** — setiap vibe perlu satu elemen yang tidak nyambung
5. **Kasih nama** — vibe tanpa nama membusuk jadi generik

**Hindari** — Font: Inter, Roboto, Open Sans, Lato · Ikon: Lucide · Warna: gradien ungu, "palet Stripe", biru-ke-ungu · Layout: hero rata tengah + gradien + tiga kartu ikon

**Pakai sebagai gantinya** — Font: Newsreader, Playfair Display, Clash Display, Outfit, Manrope, Satoshi · Ikon: Iconify Solar, Heroicons, Phosphor · Warna: diturunkan dari jangkar Q1 · Layout: satu pelanggaran grid yang disengaja

**Kosakata animasi**
- *Entrance:* fade-in, blur-in, slide-in, scale-in, stagger
- *Continuous:* marquee, beam, pulse, float, rotate
- *Interactive:* hover-lift, hover-glow, hover-reveal, click-ripple
- *Decorative:* garis grid, kurva/noodle, gradient orb, tekstur grain

Intensitas gerak berasal dari Q2. Halaman yang rasa tiga detiknya "tenang dan terkendali" tidak dapat delapan animasi masuk.

**Inspirasi:** superhero.design · Dribbble ("hero section") · Awwwards · H1 Gallery
**Aset:** Google Fonts / Fontshare · Iconify · Simple Icons

---

# REFERENSI — Formula headline hero

| Formula | Bentuk | Contoh |
|---|---|---|
| Hasil + audiens + mekanisme | "[Hasil], untuk [siapa], lewat [caranya]" | "Rilis fitur 3x lebih cepat, untuk tim yang benci rapat, lewat perencanaan async-first." |
| Pembalikan rasa sakit | "Berhenti [hal mahal yang sedang terjadi]" | "Berhenti kehilangan pelanggan gara-gara halaman lambat." |
| Klaim mengejutkan + hook bukti | "[Klaim berlawanan intuisi]. [Bocoran buktinya]." | "Aplikasi catatan yang benar-benar dipakai. Datanya ada." |
| Sapaan langsung | "[Realitas mereka sekarang]. [Apa yang harus dilakukan]." | "Ada 47 pesan Slack yang belum kamu baca. Ini yang harus dilakukan." |
| Hasil tanpa ongkosnya | "Dapat [X] tanpa [ongkos biasa dari X]" | "Dapat search kelas enterprise tanpa kontrak enterprise." |
| Waktu dipadatkan | "[Tugas] dalam [waktu yang mengejutkan singkat]" | "Tutup buku dalam satu sore." |
| Musuh bernama | "[Hal yang semua orang tolerir] itu [tidak bisa diterima]" | "Payroll pakai spreadsheet itu liabilitas, bukan sistem." |
| Angka spesifik | "[Angka presisi] [hasil]" | "Pangkas onboarding dari 14 hari jadi 4." |

**Aturan memilih:** pilih formula yang membawa *hal terkuat yang bisa kamu buktikan*. Klaim mengejutkan tanpa bukti di bawahnya lebih buruk daripada headline hasil yang datar.

**Menyelipkan keyword:** kata benda keyword biasanya muat di posisi "hasil" atau "tugas" tanpa memaksa. "Kelola stok toko tanpa spreadsheet" memuat *kelola stok toko* secara alami. Kalau keyword hanya bisa masuk dengan merusak kalimat, pindahkan ke title tag dan H2 pertama — headline yang canggung merugikan lebih banyak daripada untung peringkatnya.

**Tugas subheadline:** headline membuat janji; subheadline menyebut mekanisme yang membuat janji itu kredibel. Kalau subheadline cuma mengulang headline dengan kata lebih banyak, hapus dan tulis mekanismenya.

---

# REFERENSI — Library keberatan

| Tipe | Bunyinya | Cara menjawab |
|---|---|---|
| **Harga** | "Sepadan tidak ya?" | Bingkai biaya kalau tidak bertindak, ROI dengan angka nyata, harga diadu dengan alternatifnya (termasuk jam kerja staf kalau dikerjakan manual), pricing transparan di halaman |
| **Waktu** | "Setup-nya lama tidak?" | Sebut waktu setup eksplisit, cara kerja 3 langkah, bantuan migrasi/impor, bukti "jalan dalam sehari" dari pelanggan nyata |
| **Kepercayaan** | "Cocok tidak untuk kasus *saya*?" | Studi kasus dari segmen yang sama, spesifik ketimbang serba bisa, testimoni bernama lengkap dengan jabatan dan perusahaan, badge keamanan/kepatuhan bila relevan |
| **Risiko** | "Kalau sudah komit ternyata salah?" | Free trial, garansi uang kembali, kontrak bulanan, ekspor data saat berhenti, "batalkan kapan saja, data tetap milikmu" |
| **Perbandingan** | "Bedanya apa dengan [kompetitor]?" | Tabel perbandingan jujur, pernyataan eksplisit kamu *bukan* untuk siapa, satu hal yang kamu bisa dan mereka secara struktural tidak bisa |
| **Implementasi** | "Tim saya sanggup adaptasi tidak?" | Onboarding yang jelas siapa penanggung jawabnya, materi pelatihan, angka adopsi, integrasi dengan tool yang sudah mereka pakai |
| **Otoritas** | "Saya tidak bisa putuskan sendiri." | One-pager yang bisa diteruskan, ringkasan ROI untuk atasan, fitur "undang rekan tim" di alurnya |
| **Prioritas** | "Belum sekarang." | Biaya penundaan yang nyata, kaitan momen musiman atau kontrak — jangan pernah countdown timer palsu |

**Aturan:** jawab tiga teratas di halaman, urut berdasarkan yang paling sering membunuh deal. Sisanya masuk FAQ, kalau memang perlu. Halaman yang menjawab delapan keberatan tidak meyakinkan di satu pun.

---

# REFERENSI — Pola kegagalan

- **Hero yang menjelaskan, bukan menjual.** "Kami adalah X untuk Y" itu deskripsi. "Dapat X tanpa Y" itu jualan.
- **Daftar fitur tanpa hasil.** Terbaca seperti lembar spesifikasi.
- **Testimoni generik.** "Produknya bagus!" nilainya di bawah nol. "Onboarding kami turun dari 2 minggu jadi 4 hari" itu emas.
- **Beberapa CTA yang bersaing.** Pilih satu aksi utama. Sisanya kebisingan.
- **Dinding teks.** Pengunjung memindai. Paragraf pendek (maksimal 3 baris di mobile), poin, jeda visual.
- **Tidak ada social proof.** Kepercayaan adalah rintangan pertama; tanpa itu halamannya tidak pernah dapat kesempatan dibaca.
- **Headline dan CTA tidak nyambung.** Hero menjanjikan X, tombol meminta Y.
- **Menulis untuk semua orang.** "Cocok untuk semua jenis usaha" tidak menarik bagi siapa pun. Spesifisitas yang mengonversi.
- **Mengabaikan mobile.** Mayoritas pengunjung pakai HP. 375px dulu.
- **Vibe melenceng.** Hero-nya khas; section 3–7 diam-diam balik ke template default. Cek ulang Vibe Spec di setiap section.
- **Copy dan desain berkelahi.** Copy bilang "tenang, hati-hati, matang"; halamannya punya enam animasi masuk dan gradien neon.
- **SEO ditempel belakangan.** Keyword yang diputuskan setelah copy jadi berarti copy-nya ditulis ulang atau keyword-nya dipaksa masuk. Keyword ditetapkan di Fase 0, bukan Fase 4.
- **Satu CTA raksasa di atas saja.** Pengunjung yang scroll sampai bawah dan sudah yakin tapi tidak menemukan tombol tidak akan scroll balik ke atas.
- **Halaman cantik yang tidak terindeks.** Copy ditanam di gambar, konten hanya muncul setelah JS jalan, tidak ada `<h1>`. Desain khas tidak ada gunanya kalau tidak ada yang menemukan halamannya.

---

# Format output

## Deliverable copy-only

```markdown
# [Judul Halaman]

## Vibe Spec: [nama]
[sesuai format Fase 1A]

## Copy Spec
[sesuai format Fase 1B, termasuk peta keyword]

---

## Metadata
- URL slug: [teks]
- Title tag: [≤60 karakter]
- Meta description: [≤155 karakter]
- Open Graph title / description / gambar: [teks + catatan]
- Structured data yang perlu dipasang: [Organization / Product / FAQPage / Review]

---

## SECTION: Hero  `<h1>`
- Headline: [teks]
- Subheadline: [teks]
- CTA utama: [teks tombol]
- Penanda pendukung: [opsional]
- Catatan visual hero: [bila ada]

## SECTION: Social proof (awal)
- Baris logo: [daftar]
- Statistik kepercayaan: [bila ada]

## SECTION: Masalah / janji  `<h2>`
[2–3 paragraf — kalimat pertama menyatakan klaimnya]

## SECTION: Solusi  `<h2>`
- Headline: [teks]
- Fitur 1: [headline + deskripsi + janji hero mana yang dilayani]
- Fitur 2: [...]
- Fitur 3: [...]

## SECTION: Bukti  `<h2>`
- Blok ringkasan: [kalimat definisi brand + 3–5 fakta keras]
- Studi kasus 1: [pelanggan, hasil, angka — atau nyatakan kekosongannya]
- Testimoni: [daftar]

## SECTION: Menjawab keberatan  `<h2>` → FAQPage
- Keberatan 1 [tipe]: [cara menjawab]
- Keberatan 2 [tipe]: [cara menjawab]
- Keberatan 3 [tipe]: [cara menjawab]

## SECTION: CTA penutup  `<h2>`
- Headline: [teks]
- Tombol CTA penutup: [teks]
- Penanda pendukung: [opsional]

---

## Varian untuk testing
- Headline alternatif: [3–5]
- CTA alternatif: [3–5]
- Framing bukti alternatif: [2–3]

## Checklist pasca-import
- [ ] URL berfungsi · [ ] preview 375px · [ ] analytics di kedua CTA
- [ ] `<head>` lengkap terpasang · [ ] JSON-LD lolos validator · [ ] preview link WhatsApp dicek
- [ ] robots.txt + llms.txt di-deploy · [ ] halaman didaftarkan di Search Console
```

## Deliverable full build

Halamannya (file `.html` mandiri kecuali user minta framework), plus `robots.txt`, `llms.txt`, kedua spec, dan checklist Fase 6 yang sudah dicentang.

Pakai copy asli yang ditulis penuh — tidak pernah lorem ipsum, tidak pernah `[isi testimoni di sini]`.

---

# Kalau data yang dibutuhkan tidak tersedia

Output skill ini bergantung pada bahasa pelanggan asli, bukti asli, dan angka asli yang tidak bisa dihasilkan sendiri.

Kalau input wajib tidak tersedia atau tidak bisa diverifikasi, output yang sah adalah **deliverable dengan kekosongannya dinyatakan terbuka**: apa yang dibutuhkan, apa yang sebenarnya didapat, dan section mana yang terdampak. Tandai inline — `[BUKTI KOSONG: angka studi kasus belum ada]` — supaya tidak bisa naik tayang karena kelalaian.

**Dua tingkat, jangan dicampur:**

- **Klaim tentang pihak ketiga** — testimoni, nama pelanggan, logo klien, angka hasil, rating, jumlah pengguna. **Tidak pernah boleh dikarang, bahkan sebagai placeholder.** Kosongkan dan tandai. Berlaku juga untuk fakta di blok ringkasan: fakta karangan yang dikutip AI answer engine akan beredar tanpa bisa ditarik kembali.
- **Data milik user sendiri** — harga, jam operasional, alamat, nomor kontak. Boleh diisi placeholder realistis supaya halamannya bisa dilihat utuh, tapi wajib ditandai jelas ke user di chat, satu per satu.

Kekosongan yang dinyatakan terbuka adalah jawaban yang lengkap.