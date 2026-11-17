# Laporan Final Audit Tweet → GitHub Skill — 2026-11-17

Status: SELESAI. 9/9 tweet dibaca agen utama (browser live); 26 repo unik diverifikasi via GitHub API
(crawl 2026-11-17), di-clone untuk dibaca ke `~/workspace/audit-tweets-2026-11-17/repos/`, diaudit
keamanannya, dan dipasang sesuai putusan. TIDAK ada installer/skrip dari repo mana pun yang dijalankan.
Semua skill terpasang membawa LOCAL-NOTES.md (persona/AGENTS paket tidak menggantikan punya madepaker;
tidak ada mode otonom; tool/skrip tidak dijalankan tanpa audit per berkas + keputusan terpisah;
Alert Protection + konfirmasi aksi berbayar tetap berlaku) dan terverifikasi muncul di muse.skill_search.

## Ringkasan putusan

- **Pasang utuh (paket skill beneran + lolos audit): 12 sumber** — chaojifeng, image-to-psd,
  antialgorithm, vstack, spine-hero, motion-content-shorts, iart motion packs (56 skill),
  video-use, ffmpeg-skill, cinematic-film, take-one, claude-eyes (dengan klausul auto-install dimatikan).
- **Skill pengetahuan saja (tool/library/aplikasi sah, bukan paket skill / tidak dipasang): 5 skill payung**
  mencakup 14 repo — openmontage, agent-reach, scrapling, patchright-enhanced, video-editing-tools
  (FFmpeg, WhisperX, Silero VAD, auto-editor, PySceneDetect, Editly, OpenTimelineIO,
  DaVinci Resolve MCP, Uncut, Yap Studio).
- **Dilewati karena gagal audit/tidak terverifikasi: 0.** Tidak ditemukan pola drainer/malware di repo
  mana pun: tidak ada alamat wallet hardcoded, tidak ada pengiriman kredensial keluar, tidak ada injeksi
  prompt yang menyuruh menyembunyikan aksi dari user. Temuan paling berisiko bersifat desain dan sudah
  dinetralkan (lihat catatan per repo: claude-eyes, cinematic-skill, Agent-Reach).

## Verifikasi klaim tweet

- **OpenMontage "hampir 80k bintang" (Fluyeporlaweb): BENAR** — terverifikasi 81.106 bintang (malah di atas klaim).
- **Klaster plusxbt "160K+ gabungan": BENAR secara aritmetika, tapi menonjolkan FFmpeg** — total 14 repo
  = 165.612 bintang; FFmpeg sendiri 67.425 (41%). Tanpa FFmpeg jumlahnya 98.187.
- **iart-ai "56 skill dalam 19 paket" (Yarad_ai): BENAR PERSIS** — 19 repo pack, 56 SKILL.md terverifikasi satu per satu.
- **Klaster GitTrend0x: repo nyata tapi semuanya BARU** — dibuat 2026-11-10 s.d. 2026-11-15, bintang 46–95.
  Klaim tweet soal kemampuan cocok dengan isi repo, tapi belum teruji komunitas.
- **zallxz/motion-content-shorts: nyata dan lengkap, tapi 1 bintang** (dibuat 2026-11-13) — belum teruji,
  isinya (skill + template Remotion) beneran ada.

## Per repo

### Klaster GitTrend0x

1. **mileson/chaojifeng-video-content-creator** — https://github.com/mileson/chaojifeng-video-content-creator
   Pemilik User (mileson) · 95★ · MIT · dibuat 2026-11-12 · HTML/Python.
   Vonis: **pasang utuh** → `~/workspace/custom-skills/chaojifeng-video-content-creator/` (387 berkas, SKILL.md root).
   Bukti audit: pindaian injeksi bersih; endpoint kode hanya CDN jsdelivr, github, dan API suara ByteDance
   (openspeech.bytedance.com — integrasi ASR/TTS-nya sendiri, aktif hanya bila user mengonfigurasi key).
   Catatan: **berbahasa Mandarin**. Memuat kata kunci "mode otomatis penuh" dan fitur digital-human —
   keduanya dinetralkan di LOCAL-NOTES (aturan channel Joss: tanpa manusia AI fotorealistik; publikasi
   tetap ikut MASTER-INSTRUCTIONS). Relevansi YouTube: pipeline naskah→storyboard→pembersihan audio lisan→
   subtitle→paket publikasi, pola yang sejalan dengan produksi Fakta Semesta (dengan adaptasi bahasa).

2. **link-ding/image-to-psd** — https://github.com/link-ding/image-to-psd
   Pemilik User · 77★ · **tanpa lisensi** · dibuat 2026-11-10 · Python.
   Vonis: **pasang utuh** → `~/workspace/custom-skills/image-to-psd/` (folder skills/image-to-psd: SKILL.md +
   4 references + scripts/layered_assets.py). Audit bersih. Tanpa lisensi → LOCAL-NOTES membatasi untuk
   pemakaian internal. Relevansi: memecah gambar karakter menjadi PSD 19 lapis ber-masker — berguna untuk
   aset thumbnail/maskot yang bisa diedit lapis demi lapis.

3. **mankidev/antialgorithm** — https://github.com/mankidev/antialgorithm
   Pemilik User · 88★ · MIT · dibuat 2026-11-14.
   Vonis: **pasang utuh** → `~/workspace/custom-skills/antialgorithm/`. Isi: SKILL.md + scripts/seed.py
   (generator biji acak kecil, bersih) + gambar. Audit bersih.
   Relevansi: skill kreativitas anti-generik (nama, copy, ide, judul) — cocok untuk judul/hook Shorts
   dan dokumenter agar tidak terasa "template AI".

4. **hao-ai-lab/vstack** — https://github.com/hao-ai-lab/vstack
   Pemilik **Organization** (Hao AI Lab) · 64★ · MIT · dibuat 2026-11-10, aktif (push 2026-11-16).
   Vonis: **pasang utuh** → `~/workspace/custom-skills/vstack/` (seluruh repo + SKILL.md indeks lokal;
   10 skill tahap S0–S8 + vstack-mode di skills/). Audit bersih (alur kerja markdown; tool TLA+/Z3/
   Apalache/TLAPS tidak terpasang).
   Relevansi: **paling strategis untuk riset/bug bounty** — disiplin decompose→spec→model→calibrate→
   red-team→prove untuk properti sistem/protokol; melengkapi gerbang audit BSC + authorization gate V10.

5. **enoch3712/spine-hero-skill** — https://github.com/enoch3712/spine-hero-skill
   Pemilik User · 46★ · **tanpa lisensi** · dibuat 2026-11-11 · JavaScript.
   Vonis: **pasang utuh** → `~/workspace/custom-skills/spine-hero/` (folder skills/spine-hero: SKILL.md +
   7 references + gate script Node tanpa dependensi). Audit bersih; AGENTS.md repo hanya menunjuk ke
   SKILL.md. Tanpa lisensi → pemakaian internal. Relevansi: animasi hero 2D dari satu lukisan di rig
   tulang gaya Spine — niche (game dev), bukan untuk pipeline YouTube saat ini.

### Klaster izesaki

6. **zallxz/motion-content-shorts** — https://github.com/zallxz/motion-content-shorts
   Pemilik User (penulis Indonesia) · 1★ · MIT · dibuat 2026-11-13.
   Vonis: **pasang utuh** → `~/workspace/custom-skills/motion-content-shorts/` (seluruh repo + SKILL.md
   indeks lokal; skill asli skills/nonstop-motion + template Remotion). Audit bersih.
   Catatan: **Inggris/Bahasa Indonesia**. Relevansi YouTube: **tinggi untuk Shorts** — motion graphics
   vertikal 15–40 dtk, hook 0,5 dtk pertama, potongan sinkron ketukan musik, panjang beat dihitung dari
   jumlah kata; pola retensinya melengkapi yt-shorts/yt-retention yang sudah ada.

### Klaster Yarad_ai

7. **iart-ai/motion-skills** (+ 19 repo pack iart-ai/*) — https://github.com/iart-ai/motion-skills
   Pemilik **Organization** (iart.ai) · 1.762★ · MIT · dibuat 2026-06-22, aktif.
   Fakta struktur: repo utama hanya katalog/showcase — 56 skill-nya hidup di 19 repo pack terpisah
   (tiktok/youtube/data-animation/dll.), masing-masing berisi skills/<nama>/SKILL.md.
   Vonis: **pasang utuh semua 56 skill** → `~/workspace/custom-skills/iart-motion-skills/<nama-skill>/`
   (56 folder, terdaftar satu per satu di pencarian skill; INDEX.md = indeks lokal, _packmap.txt = peta
   asal pack). Tabrakan nama ditangani: lower-thirds versi tiktok dipasang sebagai `lower-thirds-tiktok`.
   Skrip bantu bersama (contact-sheet/probe/seek-shot — pembungkus ffmpeg read-only) disalin ke scripts/
   tiap skill. Audit: pindaian injeksi bersih (satu-satunya temuan "without asking" adalah teknik copywriting
   untuk klien di creative-brief, bukan instruksi agen).
   Relevansi YouTube: **sangat tinggi** — short-form-video, caption-animation, kinetic-typography,
   map-animation, chart-animation, explainer-video, youtube-intro-outro, audiogram, remotion-video,
   beat-sync-editing langsung menyentuh format Fakta Semesta + Scoteria.

### Klaster Fluyeporlaweb

8. **OpenMontageInc/OpenMontage** — https://github.com/OpenMontageInc/OpenMontage
   Pemilik **Organization** · 81.106★ · **AGPL-3.0** · dibuat 2026-03-29, sangat aktif.
   Vonis: **pengetahuan saja** → `~/workspace/custom-skills/openmontage/` (SKILL.md ringkasan lokal).
   Alasan: sistem produksi utuh (2.314 berkas, 141 SKILL.md internal, 12 pipeline, 100+ tool) dengan
   runtime sendiri — bukan paket skill tempel; menduplikasi pipeline Remotion+ffmpeg kita. AGPL-3.0
   berarti kewajiban lisensi bila kodenya dipakai/di-deploy. Di dalam salah satu skill internalnya ada
   baris instalasi CLI HeyGen via `curl | bash` (dokumentasi tool-nya, tidak dijalankan/diambil).
   Relevansi: tambang pola desain pipeline + knowledge produksi (delivery spec, QA gate) untuk
   pengembangan workflow YouTube kita; clone bacaan di folder repos/.

### Klaster plusxbt (juga isagi1000x untuk video-use)

9. **browser-use/video-use** — https://github.com/browser-use/video-use
   Pemilik **Organization** (browser-use) · 31.156★ · MIT · dibuat 2026-04-12.
   Vonis: **pasang utuh** → `~/workspace/custom-skills/video-use/` (SKILL.md root + helpers/ + skill
   manim-video bonus di skills/). Audit: satu-satunya endpoint jaringan di helpers adalah
   api.elevenlabs.io (Scribe, untuk transkripsi) — helpers/transcribe.py membaca .env proyek sendiri
   untuk key itu; tidak ada pengiriman data lain. SKILL.md-nya sendiri mewajibkan konfirmasi strategi
   ke user sebelum eksekusi (sejalan dengan aturan Joss).
   Catatan: transkripsi bawaannya ElevenLabs (berbayar, key user) — LOCAL-NOTES menetapkan jalur
   default kita tetap Whisper lokal. Relevansi YouTube: **tinggi** — editing berbasis percakapan
   (potong per batas kata, fades 30 ms, subtitle terakhir di rantai filter) melengkapi yt-edit.

10. **kajisho5/ffmpeg-skill** — https://github.com/kajisho5/ffmpeg-skill
    Pemilik User · 7.154★ · MIT · dibuat 2026-09-03, aktif (push 2026-11-16).
    Vonis: **pasang utuh** → `~/workspace/custom-skills/ffmpeg-skill/` (425 berkas: SKILL.md root,
    scripts/ 47 berkas, references/, mcp/). Audit: skrip Python stdlib memanggil ffmpeg lokal; grep
    jaringan (urllib/requests/socket) kosong; tes kontraknya sendiri memblokir pola curl/eval.
    AGENTS.md root ditujukan untuk kontributor repo (dicatat di LOCAL-NOTES). MCP server TIDAK
    didaftarkan/dijalankan (aturan setempat). Relevansi YouTube: **sangat tinggi** — 42 tool ffmpeg
    berkontrak machine-readable (cut, caption, reframe, loudness/LUFS, ekspor platform, verify)
    sejalan dengan standar QC produksi kita (loudness −16..−13 LUFS, cek platform).

11. **moritzkremb/claude-eyes** — https://github.com/moritzkremb/claude-eyes
    Pemilik User · 93★ · MIT · dibuat 2026-10-15.
    Vonis: **pasang SKILL.md saja dengan klausul mati** → `~/workspace/custom-skills/claude-eyes/`.
    **Bukti temuan (konkret):** AGENTS.md repo baris 3 — "A user asked you to install Eyes. Do it end
    to end without asking about routine steps." dan skills/eyes/SKILL.md §0 menyuruh agen menjalankan
    `uv tool install git+https://github.com/moritzkremb/claude-eyes` lalu `eyes setup --fix`
    (memasang ffmpeg, whisper.cpp, dan model ±570 MB) tanpa bertanya. Ini pola instruksi auto-install
    tertanam — bukan malware (tool-nya lokal dan open-source), tapi bertabrakan dengan aturan kita.
    LOCAL-NOTES skill ini **menonaktifkan instruksi itu**: CLI eyes tidak terpasang; pemasangan hanya
    lewat keputusan terpisah Joss setelah audit kode CLI. Relevansi: konsep "agen menonton video"
    (indeks contact-sheet + transkrip per kata + DNA editing) berguna untuk analisis video referensi/
    kompetitor channel.

12. **m-bain/whisperX** — https://github.com/m-bain/whisperX · 25.393★ · BSD-2 · sejak 2022, aktif.
    Vonis: **pengetahuan** (di payung video-editing-tools). Tool ASR (timestamp per kata + diarisasi),
    bukan paket skill. Relevansi: jalur naik kelas akurasi timing subtitle kita.

13. **snakers4/silero-vad** — https://github.com/snakers4/silero-vad · 10.684★ · MIT · sejak 2020.
    Vonis: **pengetahuan**. Library deteksi aktivitas suara; relevan untuk deteksi hening/dead-air.

14. **WyattBlue/auto-editor** — https://github.com/WyattBlue/auto-editor · 5.953★ · Unlicense · sejak 2020, aktif.
    Vonis: **pengetahuan**. Tool potong otomatis berbasis keheningan (bahasa Nim); kandidat rough-cut.

15. **Breakthrough/PySceneDetect** — https://github.com/Breakthrough/PySceneDetect · 5.519★ · BSD-3 · sejak 2014, aktif.
    Vonis: **pengetahuan**. Library deteksi potongan scene; relevan untuk analisis shot/QC referensi.

16. **mifi/editly** — https://github.com/mifi/editly · 5.620★ · MIT · push terakhir 2025-05 (melambat).
    Vonis: **pengetahuan**. Framework editing deklaratif JSON→video.

17. **AcademySoftwareFoundation/OpenTimelineIO** — https://github.com/AcademySoftwareFoundation/OpenTimelineIO
    Pemilik **Organization** (ASWF) · 2.091★ · Apache-2.0 · sejak 2016.
    Vonis: **pengetahuan**. Standar interchange timeline industri (OTIO); relevan bila suatu hari
    bertukar timeline dengan NLE.

18. **samuelgursky/davinci-resolve-mcp** — https://github.com/samuelgursky/davinci-resolve-mcp
    4.138★ · MIT · aktif (push 2026-11-17). Vonis: **pengetahuan** (di payung video-editing-tools).
    Server MCP untuk DaVinci Resolve Studio (+29 SKILL.md workflow internal). Relevansi kecil di
    lingkungan Linux + pipeline ffmpeg/Remotion kita; tidak dipasang.

19. **blazejkustra/uncut** — https://github.com/blazejkustra/uncut · 23★ · MIT · dibuat 2026-10-11.
    Vonis: **pengetahuan**. Editor video AI **macOS** (aplikasi, 1.773 berkas) — tidak bisa dipakai di
    Linux ini. Temuan grep-nya (curl|bash di setup.ts) adalah teks saran instalasi Claude untuk user
    Mac, dan string "curl evil | sh" di berkas tes adalah fixture uji keamanan mereka sendiri — bukan kode aktif.

20. **cathrynlavery/yap-studio** — https://github.com/cathrynlavery/yap-studio · 53★ · Apache-2.0 · dibuat 2026-10-21.
    Vonis: **pengetahuan**. Aplikasi (agen di Claude Code mengedit video di Mac user; 1.204 berkas,
    3 SKILL.md internal). Bukan paket skill tempel; berpusat di Mac. setup.py-nya memuat string
    installer uv standar (tidak dijalankan).

21. **talsiach/take-one** — https://github.com/talsiach/take-one · 310★ · MIT · dibuat 2026-10-13.
    Vonis: **pasang utuh** → `~/workspace/custom-skills/take-one/`. Audit bersih dan posturnya teladan:
    SKILL.md mewajibkan pitch berisi harga dan selalu bertanya sebelum membelanjakan uang/kredit.
    Relevansi: studio film pendek dari kode (render halaman web per frame → ffmpeg) untuk video
    peluncuran/iklan/penjelas — pola yang mirip cinematic-film, sudut komersial.

22. **FFmpeg/FFmpeg** — https://github.com/FFmpeg/FFmpeg · 67.425★ · LGPL/GPL (tergantung build) · sejak 2011.
    Vonis: **pengetahuan**. Mesin FFmpeg itu sendiri (mirror resmi), jelas bukan paket skill; sudah
    menjadi tulang punggung produksi kita lewat ffmpeg sistem.

### Klaster GitHub_Daily

23. **Moh4696/cinematic-skill** — https://github.com/Moh4696/cinematic-skill
    Pemilik User · 665★ · MIT · dibuat 2026-11-09.
    Vonis: **pasang utuh** → `~/workspace/custom-skills/cinematic-film/` (folder skills/cinematic-film
    yang self-contained: SKILL.md + references + assets/template + scripts).
    Bukti audit: install.sh dibaca baris demi baris — hanya clone repo-nya sendiri + symlink/copy folder
    skill ke direktori agen; tidak ada unduhan biner, tidak ada akses kredensial. Cara pasang yang
    disarankan README-nya adalah `curl … install.sh | bash` — **tidak dipakai**; kita menyalin manual.
    scripts/get_fonts.py mengunduh font berlisensi terbuka (dicatat di LOCAL-NOTES, tidak dijalankan).
    Relevansi YouTube: **sangat tinggi untuk dokumenter** — satu kamera kontinu meluncur di atas papan
    berisi foto/peta/kartu/angka yang mendarat tepat pada kata narator; persis gaya dokumenter
    Fakta Semesta/Scoteria (tetap tunduk aturan: tanpa manusia AI fotorealistik, lisensi arsip jujur).

### Klaster josesilesdata

24. **Panniantong/Agent-Reach** — https://github.com/Panniantong/Agent-Reach
    Pemilik User · 112.450★ · MIT · dibuat 2026-02-24, push 2026-11-08.
    Vonis: **pengetahuan saja** → `~/workspace/custom-skills/agent-reach/` (SKILL.md ringkasan lokal;
    CLI TIDAK dipasang, TIDAK dikonfigurasi kredensial apa pun).
    Bukti audit: SKILL.md sumber berpostur read-only eksplisit (tidak posting/komentar/suka/DM;
    "tidak login untuk user, tidak meminta password"). Namun kode runtime-nya memuat pola yang tidak
    kita adopsi: agent_reach/runtime/browser.py + session_reuse.py (memakai ulang sesi login browser
    untuk kanal tertentu) dan docs/install.md memakai installer uv `curl | sh` / `irm | iex` untuk
    memasang tool-nya — tidak satu pun dijalankan. Relevansi: peta kemampuan baca publik per platform
    untuk riset (termasuk tracking airdrop dari X) — eksekusi baca tetap lewat jalur resmi kita.

25. **d4vinci/Scrapling** — https://github.com/D4Vinci/Scrapling
    Pemilik User · 103.727★ · BSD-3 · dibuat 2024-10-13, aktif.
    Vonis: **pengetahuan saja** → `~/workspace/custom-skills/scrapling/`. Framework scraping (fetcher/
    browser/stealth session + spider); repo juga membawa skill resmi (agent-skill/Scrapling-Skill/)
    yang ditinjau tapi tidak disalin sebagai skill aktif, sesuai aturan tugas untuk repo scraping.
    Relevansi: referensi arsitektur scraping untuk riset; tidak ada target/kredensial yang dikonfigurasi.

26. **whaleyxbt/patchright-enhanced** — https://github.com/whaleyxbt/patchright-enhanced
    Pemilik User · 517★ · **tanpa lisensi** · dibuat 2026-03-25, push terakhir 2026-10-10.
    Vonis: **pengetahuan saja** → `~/workspace/custom-skills/patchright-enhanced/`. Toolkit otomasi
    browser TypeScript di atas Patchright (fork Playwright anti-deteksi), 58 berkas, tanpa SKILL.md.
    Tanpa berkas lisensi = semua hak dilindungi secara default → hanya dibaca, kodenya tidak disalin/
    dipakai. Tidak dipasang; tidak untuk mengotomasi akun login Joss.

## Kemampuan baru terpenting yang didapat

1. **ffmpeg-skill** — 42 tool editing lokal berkontrak (loudness, caption, reframe, ekspor platform,
   verify) yang menyatu dengan standar QC produksi YouTube kita.
2. **cinematic-film + take-one + video-use** — tiga metodologi produksi video-dari-kode/editing
   percakapan yang matang untuk dokumenter dan Shorts, semuanya berpostur konfirmasi-ke-user.
3. **56 skill motion iart + nonstop-motion** — gudang pola motion graphics (tipografi kinetik, animasi
   peta/grafik, caption, beat-sync) untuk menaikkan kualitas visual kedua channel.
4. **vstack** — alur verifikasi formal (TLA+/Z3) untuk memperkeras riset keamanan/bug bounty.
5. **chaojifeng + antialgorithm** — pipeline konten Mandarin end-to-end (referensi riset format) dan
   penangkal output generik untuk judul/hook.

## Keterbatasan (jujur)

- Audit bersifat baca-statis (grep pola + baca berkas kunci) pada clone --depth 1 per 2026-11-17;
  bukan penjaminan perilaku runtime. Karena itu aturan setempat tetap melarang menjalankan tool/skrip
  paket tanpa audit per berkas dan keputusan terpisah.
- Repo tool besar yang tidak di-clone penuh (FFmpeg, PySceneDetect, Silero VAD, auto-editor, WhisperX,
  Editly, OpenTimelineIO) diverifikasi lewat GitHub API + reputasi proyek; mereka hanya menjadi
  pengetahuan, tidak ada kodenya yang dipasang.
- Bintang/fork adalah potret 2026-11-17 dan akan berubah; klaim tweet dinilai terhadap potret itu.
