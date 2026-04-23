# 🦁 Wildlife Monitoring System - Frontend

Frontend aplikasi berbasis web untuk **Sistem Pelacakan Pergerakan Satwa Liar Berbasis GPS**. Dibangun menggunakan Next.js 14 (App Router) sebagai bagian dari tugas mata kuliah **Pemrograman Berorientasi Objek (PBO)**.

Sistem ini berarsitektur Client-Server dan berkomunikasi dengan backend Spring Boot melalui REST API.

## 👥 Tim Pengembang
| Nama | NIM | Fokus Modul |
|------|-----|-------------|
| Farrellino Ulung Satya Amando | 103072400005 | IoT & Device Manager (Manajemen Perangkat GPS) |
| Yohana Sinaga | 103072400009 | Entity Manager (CRUD Satwa & Validasi) |
| Laura Chyndearni Saragih | 103072400049 | Account & Security Engineer (Autentikasi & Role) |
| Nuevalen Refitra Alswando | 103072430008 | Real-Time Tracking Engineer (Peta & Live GPS) |
| Yohanna Purnomo | 103072400127 | Data Historis Specialist (Filter & Export Data) |
| Haniel Juanta Sembiring | 103072400145 | Data & Statistik Analyst (Grafik & Laporan) |

## ️ Tech Stack
- **Framework**: Next.js 14+ (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **State & HTTP**: React Context API + Axios
- **Maps**: Leaflet + React Leaflet
- **Charts**: Recharts
- **Tooling**: ESLint, Prettier, Git & GitHub

## 📁 Struktur Proyek
```
src/
├── app/                 # Routing berbasis file (Next.js 14)
├── components/          # Komponen UI (Map, Table, Form, Chart, dll)
├── context/             # Global state (AuthContext)
├── services/            # API calls (axios instance & endpoints)
├── types/               # TypeScript interfaces/types
├── lib/                 # Utility & helper functions
└── hooks/               # Custom React hooks
```

## 🚀 Cara Menjalankan (Development)

1. **Clone & Install Dependencies**
   ```bash
   git clone https://github.com/<username>/wildlife-monitoring-system-app-frontend.git
   cd wildlife-monitoring-system-app-frontend
   npm install
   ```

2. **Setup Environment**
   Buat file `.env.local` di root project:
   ```env
   NEXT_PUBLIC_API_URL=http://localhost:8080/api
   NEXT_PUBLIC_MAP_CENTER_LAT=-7.2575
   NEXT_PUBLIC_MAP_CENTER_LNG=112.7521
   ```

3. **Jalankan Development Server**
   ```bash
   npm run dev
   ```
   Buka browser di `http://localhost:3000`

> 💡 **Catatan**: Pastikan backend Spring Boot sudah berjalan di `http://localhost:8080` agar API dapat diakses. Jika backend belum siap, gunakan mock data di `src/services/`.

## 🌿 Git Workflow & Branching Strategy

Agar kolaborasi 6 anggota berjalan lancar selama 4 minggu, ikuti aturan branching berikut:

###  Struktur Branch
| Branch | Fungsi |
|--------|--------|
| `main` | Versi stabil & siap deploy (hanya menerima merge dari `develop`) |
| `develop` | Branch integrasi harian & testing (target utama Pull Request) |
| `feat/<nama>-<modul>` | Branch kerja individual per anggota |

### 🔄 Alur Kerja Harian
1. **Sebelum mulai kerja**, selalu pull branch `develop` terbaru:
   ```bash
   git checkout develop
   git pull origin develop
   ```
2. **Buat branch fitur** sesuai modul kamu:
   ```bash
   git checkout -b feat/nama-modul
   # Contoh: git checkout -b feat/laura-auth
   ```
3. **Commit secara berkala** dengan pesan yang jelas:
   ```bash
   git add .
   git commit -m "feat(auth): implement login form & JWT storage"
   ```
4. **Push & Buat Pull Request (PR)** ke branch `develop`:
   ```bash
   git push origin feat/nama-modul
   ```
   Buka GitHub → Pull Requests → New Pull Request → Base: `develop`, Compare: `feat/nama-modul`
5. **Code Review & Merge**: Minta review singkat dari anggota lain, lalu merge ke `develop`.
6. **Hapus branch lokal** setelah merge berhasil:
   ```bash
   git checkout develop
   git branch -d feat/nama-modul
   ```

### 📋 Pemetaan Branch per Anggota
| Anggota | Nama Branch yang Disarankan |
|---------|-----------------------------|
| Laura | `feat/laura-auth` |
| Yohana | `feat/yohana-satwa` |
| Farrellino | `feat/farrellino-device` |
| Nuevalen | `feat/nuevalen-tracking` |
| Yohanna | `feat/yohanna-historis` |
| Haniel | `feat/haniel-statistik` |

## 🔗 Integrasi API dengan Backend
- Endpoint API disepakati di repository backend: `wildlife-monitoring-system-app-backend`
- Format request/response mengikuti standar REST JSON
- Autentikasi menggunakan JWT Bearer Token (dikelola di `AuthContext`)
- CORS sudah dikonfigurasi di backend untuk mengizinkan `http://localhost:3000`

## 📝 Konvensi Penulisan Kode
- Gunakan **TypeScript** untuk semua komponen & services
- Component harus bersifat **reusable** & diletakkan di `src/components/`
- Gunakan **Tailwind CSS** untuk styling (hindari inline CSS/file CSS terpisah)
- Jalankan `npm run lint` sebelum commit untuk memastikan tidak ada error syntax

## 📄 Lisensi
Proyek ini dibuat untuk keperluan akademik. Penggunaan ulang kode disarankan dengan mencantumkan sumber.
