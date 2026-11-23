# Panduan Publish

Aplikasi ini adalah static site. Tidak ada build command, tidak ada dependency, dan tidak perlu server khusus.

## Opsi 1 — Netlify Drop (paling cepat)

1. Buka https://app.netlify.com/drop
2. Tarik folder `site-netlify` atau file `tabungan-site.zip` ke halaman tersebut.
3. Setelah upload selesai, kamu mendapat URL seperti `https://nama-acak.netlify.app`.
4. Buat akun Netlify gratis lalu **Claim site** agar URL permanen.
5. Di **Site settings → Change site name**, ganti nama menjadi misalnya `tabungan-alfi`.

## Opsi 2 — Netlify dari GitHub

1. Push repository ini ke GitHub.
2. Di Netlify, pilih **Add new site → Import an existing project → GitHub**.
3. Pilih repository `tabungan`.
4. Biarkan build command kosong.
5. Publish directory: `.` (sudah diatur di `netlify.toml`).
6. Klik **Deploy site**.

Setiap push ke branch utama akan otomatis di-deploy ulang.

## Opsi 3 — Vercel

### Lewat dashboard

1. Buka https://vercel.com/new
2. Import repository GitHub `tabungan`.
3. Framework preset: **Other**.
4. Root directory: `.`
5. Build command kosong, output directory kosong.
6. Deploy.

### Lewat CLI

```bash
npm install -g vercel
cd "lokasi\folder\tabungan"
vercel
vercel --prod
```

## Opsi 4 — GitHub Pages (auto deploy)

Workflow sudah disiapkan di `.github/workflows/deploy.yml`.

1. Push kode ke GitHub (branch `main` atau `master`).
2. Buka repository → **Settings → Pages**.
3. Di **Build and deployment → Source**, pilih **GitHub Actions**.
4. Tunggu workflow `Deploy ke GitHub Pages` selesai.
5. URL aktif di `https://<username>.github.io/<nama-repo>/`.

Catatan: kalau repository bernama `tabungan`, URL-nya `https://<username>.github.io/tabungan/`.

## Opsi 5 — Server lokal satu jaringan

Kalau hanya ingin diakses orang yang satu Wi-Fi:

```bash
python -m http.server 8000 --bind 0.0.0.0
```

Lalu bagikan `http://IP-LAN-kamu:8000`. Pastikan firewall mengizinkan port 8000.

## Inisialisasi Git pertama kali

Kalau folder ini belum menjadi repository:

```bash
git init
git config user.name "Nama Kamu"
git config user.email "emailkamu@example.com"
git add .
git commit -m "Initial commit: aplikasi tabungan"
git branch -M main
git remote add origin https://github.com/<username>/tabungan.git
git push -u origin main
```

Buat repository kosong di GitHub terlebih dahulu tanpa README/LICENSE agar tidak konflik saat push pertama.
