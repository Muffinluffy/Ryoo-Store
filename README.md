# NeonOrder OS

Aplikasi order full-stack dengan desain futuristik, login email/password dan Google, dashboard admin untuk memantau order, serta receipt customer yang siap dicetak.

## Fitur

- Login dan register via email/password.
- Login Google OAuth 2.0.
- Dashboard customer untuk membuat order dan melihat receipt.
- Dashboard admin untuk memantau semua order dan mengubah status.
- Penyimpanan data lokal berbasis file JSON.
- Password di-hash, akses admin dibatasi role, dan sesi memakai cookie HTTP-only.

## Stack

- Frontend: React + TypeScript + Vite + Tailwind CSS + Zustand
- Backend: Express + TypeScript
- Auth: JWT cookie + bcryptjs + Google OAuth

## Cara Menjalankan

1. Install dependency:

```bash
npm install
```

2. Jalankan aplikasi:

```bash
npm run dev
```

3. Buka browser:

- Frontend: [http://localhost:5173](http://localhost:5173)
- API health check: [http://localhost:3001/api/health](http://localhost:3001/api/health)

## Akun Demo Admin

- Email: `admin@neonorder.local`
- Password: `Admin123!`

## Login Google

Buat file `.env` dari `.env.example`, lalu isi `GOOGLE_CLIENT_ID` dan `GOOGLE_CLIENT_SECRET` milik kamu. Agar login Google berhasil, pastikan di Google Cloud Console kredensial OAuth kamu memiliki konfigurasi berikut:

- Authorized JavaScript Origins: `http://localhost:5173`
- Authorized Redirect URIs: `http://localhost:3001/api/auth/google/callback`

Jika konfigurasi Google belum cocok, aplikasi tetap bisa dipakai memakai login email/password biasa.

## Script Penting

```bash
npm run dev
npm run check
npm run test
npm run lint
npm run build
```

## Struktur Utama

- `src/`: frontend React
- `api/`: backend Express
- `.data/neon-order-db.json`: data lokal aplikasi
- `.trae/documents/`: PRD dan arsitektur teknis

## Catatan Keamanan

- Untuk produksi, ganti `JWT_SECRET`.
- Jangan expose `GOOGLE_CLIENT_SECRET` ke frontend.
- Rotasi ulang Google Client Secret jika kredensial ini pernah dibagikan ke pihak lain.
