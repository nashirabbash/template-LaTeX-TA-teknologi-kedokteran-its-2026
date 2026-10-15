# Skill Tugas Akhir Teknologi Kedokteran ITS

Skill AI untuk memulai dan mengerjakan proposal serta buku tugas akhir di folder kerja pengguna. Sumber LaTeX berada di [`skills/tugas-akhir/template/`](./skills/tugas-akhir/template/); pengguna tidak perlu meng-clone repo ini ke folder TA.

## Instalasi

Pasang skill dari repo ini melalui [CLI skills](https://github.com/vercel-labs/skills). Perintah berikut memasang skill secara global, sehingga bisa dipakai dari folder kerja mana pun:

```bash
npx skills add Aisarsyb/template-LaTeX-TA-teknologi-kedokteran-its-2026 --skill tugas-akhir -g
```

Pengguna Bun dapat mengganti `npx` dengan `bunx`. Jalankan tanpa `-g` bila skill hanya ingin dipasang untuk proyek saat ini. Instalasi skill **belum menyalin template** ke folder TA; penyalinan dilakukan saat pengguna meminta agent memulai proyek.

## Contoh pemakaian

Buka folder kerja sendiri di agent yang mendukung pemanggilan skill dengan garis miring, lalu ketik:

> /tugas-akhir Buat proyek TA di folder ini.

Agent memeriksa folder, menunjukkan tujuan, dan meminta izin sebelum menyalin isi template. Pilih folder kosong; jika folder kerja sudah berisi berkas lain, minta agent memakai subfolder baru yang kosong. Setelah proyek dibuat, lanjutkan misalnya dengan:

> /tugas-akhir Bantu tulis Bab 1 berdasarkan rumusan masalah dan sumber yang saya berikan. Target saya proposal.

> /tugas-akhir Periksa PDF proposal saya.

Sesudah satu permintaan penulisan selesai, skill menginstruksikan agent membangun PDF dokumen target dan melaporkan hasil serta lokasi PDF untuk dibuka. Jika berkas bersama berubah tanpa target dokumen yang disebut, agent membangun proposal dan buku. Proses ini memerlukan perangkat LaTeX terpasang; skill tidak menyediakan compiler atau membuka preview PDF otomatis.

Hasil proyek memiliki `sempro.tex` (proposal Bab 1–3), `buku-ta.tex` (buku Bab 1–5), dan `main.tex` (alternatif proposal). Bab 1–3 dipakai kedua dokumen. Ganti identitas di `pustaka/variables.tex`, isi di `bab/` dan `abstrak/`, serta rujukan di `pustaka/pustaka.bib`. Contoh identitas, data, dan isi bukan naskah siap serah. Hasil AI perlu diperiksa terhadap data penelitian, sumber asli, ketentuan resmi prodi, dan arahan pembimbing.

## Bangun PDF secara manual

Siapkan distribusi TeX dengan `pdflatex`, `biber`, `biblatex-apa`, `txfonts`, dan paket LaTeX lain yang dipakai naskah. Dari akar proyek hasil salinan, jalankan:

```bash
latexmk -pdf -halt-on-error sempro.tex
latexmk -pdf -halt-on-error buku-ta.tex
```

Jika `latexmk` belum tersedia, jalankan `pdflatex -halt-on-error sempro.tex`, `biber sempro`, lalu `pdflatex -halt-on-error sempro.tex` dua kali; ganti `sempro` dengan `buku-ta` untuk buku. Di Overleaf, unggah proyek hasil salinan dan pilih berkas utama sesuai dokumen. Perubahan format template dicatat di [CHANGELOG.md](./CHANGELOG.md). Lisensi: [MIT](./LICENSE).
