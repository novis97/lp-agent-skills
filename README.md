# lp-agent-skills

Paket skill landing page (desain + copy + SEO/GEO) untuk **Google AI Studio → Agents**.

Folder skill sengaja bernama `skills/` (bukan `.agents/skills/`) karena upload lewat browser GitHub menolak folder berawalan titik. Akibatnya skill tidak terdeteksi otomatis — System instructions di AI Studio wajib menyuruh agent membaca `/lp-agent-skills/AGENTS.md`.

## Isi

```
AGENTS.md                                   ← system instruction + aturan keras agent
skills/landing-page-design-copy/    ← pintu masuk (7 fase + gate)
skills/landing-page-seo/            ← mesin teknis SEO/GEO + 5 file referensi
output/                                     ← tempat agent menyimpan hasil
```

## Pasang di AI Studio

1. Push folder ini ke repo GitHub (private boleh).
2. AI Studio → **Agents** → Environment → **Add Sources** → GitHub Repository → pilih repo ini.
3. Aktifkan tool: **Filesystem Tools** (wajib — tanpa ini referensi Fase 4 tidak bisa dibaca) dan **Code Execution** (untuk mode full build). Google Search opsional.
4. Uji dengan brief singkat, misalnya: *"Buatkan landing page copy-only untuk jasa laundry kiloan di Bogor."*

## Checklist uji pertama

- [ ] Agent membuka `skills/landing-page-design-copy/SKILL.md` sebelum mulai
- [ ] Agent bertanya mode (copy-only / full build)
- [ ] Agent **berhenti dan menunggu** jawaban Vibe Discovery Q1–Q4, tidak menjawab sendiri
- [ ] Agent melaporkan hasil Gate A, B, C sebelum menulis copy final
- [ ] Di Fase 4 agent membuka file di `landing-page-seo/references/`
- [ ] Testimoni/logo/angka yang tidak ada ditandai `[BUKTI KOSONG: ...]`, bukan dikarang
- [ ] Hasil tersimpan di `output/<slug-klien>/`

Kalau satu poin gagal, perketat aturan terkait di `AGENTS.md`, push, lalu uji lagi.

## Merawat

Repo ini satu-satunya sumber. Revisi skill di sini, lalu push — jangan edit salinan di tempat lain.
Hasil kerja klien di `output/` sebaiknya tidak di-commit ke repo yang sama (tambahkan ke `.gitignore` kalau repo dibagikan).
