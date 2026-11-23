# Tabungan

Web statis, ringan, dan sederhana untuk merencanakan target tabungan. Pengguna cukup menjawab dua pertanyaan di awal, lalu aplikasi menghitung kapan target tercapai.

## Fitur

- Pertanyaan awal:
  1. Jumlah yang ingin ditabung.
  2. Nominal setoran per hari **atau** per minggu.
- Perhitungan otomatis:
  - lama menabung dalam hari,
  - perkiraan tanggal target tercapai,
  - nominal setara per hari.
- Pencatatan setoran dengan **nominal bebas** kapan saja.
- Perkiraan tanggal diperbarui otomatis dari sisa target dan rencana setoran.
- Ubah rencana setoran (harian/mingguan) langsung dari kartu target.
- Progres bar, total terkumpul, dan status target tercapai.
- Data tersimpan di browser masing-masing (`localStorage`), aman setelah refresh.
- Tanpa backend, tanpa dependensi, tanpa build step.
- Responsif di HP, mode gelap otomatis, dan ramah keyboard/screen reader.

## Cara menjalankan

Cukup buka `index.html` di browser.

Alternatif lewat server lokal:

```bash
python -m http.server 8000
```

Lalu buka http://localhost:8000

## Deploy

Lihat [DEPLOY.md](DEPLOY.md) untuk langkah lengkap:

- Netlify (drag-and-drop atau terhubung dengan repo)
- Vercel
- GitHub Pages (lewat GitHub Actions yang sudah disiapkan)

## Penyimpanan data

Data disimpan di `localStorage` browser pengunjung. Artinya:

- aman dari refresh dan saat web dibuka ulang di browser/perangkat yang sama,
- tiap pengunjung punya data sendiri-sendiri,
- data tidak berpindah ke perangkat lain,
- mode incognito/private biasanya menghapus data saat jendela ditutup.

Kalau dibutuhkan login dan sinkron lintas perangkat, aplikasi ini perlu ditambah backend/database seperti Firebase atau Supabase.

## Struktur file

```text
.
├── index.html                  # seluruh aplikasi (HTML + CSS + JS)
├── netlify.toml                # konfigurasi deploy Netlify
├── .github/workflows/deploy.yml # auto deploy ke GitHub Pages
├── DEPLOY.md                   # panduan publish
└── README.md
```

## Lisensi

MIT. Lihat [LICENSE](LICENSE).
