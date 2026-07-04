# Portal Pangan — #SemuaBisaDihitung

Dasbor analitik pangan terpadu (Kemenko Pangan RI) dengan gerbang login.
Menyatukan 4 dasbor: Koefisien Variasi Harga Beras, Neraca Pangan Regional, Rice Journey, Dampak Ekonomi KDMP.

## Struktur
- `index.html` — shell: login, portal, manajemen user (super admin)
- `dashboards/cv.html`, `peta.html`, `rice.html`, `kdmp.html` — dasbor (dengan guard login)
- `dashboards/kdmp.html` — Dampak Ekonomi Pembangunan KDMP (multiplier ekonomi desa)
- `vercel.json` — konfigurasi deploy

## Kredensial awal (WAJIB diganti)
- `aliftowew` / `SemuaBisaDihitung2026`  — super admin
- `admin` / `KemenkoPangan2026`          — admin biasa

## Menjalankan
Login butuh konteks aman (`crypto.subtle`), jadi JANGAN buka via file://.
- Lokal:  `python3 -m http.server 8000` lalu buka http://localhost:8000
- Deploy: drag folder ini ke Vercel / push ke GitHub lalu import di Vercel.

## Menambah admin permanen (lintas perangkat)
1. Login sebagai super admin → Manajemen User → + Tambah user.
2. Klik "Export konfigurasi" → salin blok SEED_USERS.
3. Tempel menggantikan blok `SEED_USERS` di `index.html` → deploy ulang.

## Catatan keamanan
Ini gerbang client-side: mencegah akses kasual, BUKAN benteng. Data & logika
ada di browser. Untuk keamanan sungguhan diperlukan backend + database.
