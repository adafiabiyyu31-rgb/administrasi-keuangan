# 💰 ADMINISTRASI KEUANGAN - Financial Health Checker

Aplikasi web untuk manajemen keuangan usaha kecil dan menengah (PT/UMKM) dengan fitur pencatatan transaksi, monitoring cash flow, dan rekomendasi finansial berbasis AI.

## ✨ Fitur Utama

- 📊 **Dashboard Interaktif** - Monitoring financial health score secara real-time
- 💵 **Pencatatan Transaksi** - Catat pemasukan dan pengeluaran dengan kategori
- 📸 **Upload Foto Nota** - Kompresi otomatis ke Base64 dan disimpan lokal
- 🎯 **Target Omzet** - Tracking progress mencapai target bulanan
- 👥 **Multi-Role Access** - Admin, Owner, Mentor, Akuntan, Manager
- 📈 **Analisis Cash Flow** - Visualisasi dengan Chart.js
- 💾 **Backup & Restore** - Cadangkan data ke file SQLite
- 🔐 **Local-First** - Semua data tersimpan di device (SQLite WASM)

## 🔐 Akun Demo

| Email | Password | Role |
|-------|----------|------|
| admin@umkmcoach.id | admin123 | Administrator |
| umkm@umkmcoach.id | pt123 | Pemilik PT |
| pendamping@umkmcoach.id | damping123 | Pendamping PT |
| akuntan@umkmcoach.id | akuntan123 | Akuntan |
| manajer@umkmcoach.id | manajer123 | Manajer |

## 🏗️ Teknologi

- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Database**: SQLite WASM (sql.js)
- **Charts**: Chart.js
- **Storage**: IndexedDB + LocalStorage
- **Responsive**: Mobile-first design

## 📋 Struktur Database

```
users
├── id, name, email, password, role, region
├── role: admin | owner | mentor | accountant | manager

businesses
├── id, owner_id, name, monthly_target, initial_score, status, mentor_id

transactions
├── id, business_id, type (income/expense), category_id, amount, description
├── transaction_date, receipt_base64, created_by, created_at

health_scores
├── id, business_id, score, status, recommendation, created_at

mentor_notes
├── id, business_id, mentor_id, note, created_at

categories
├── id, name, type (income/expense)
```

## 🎯 Fitur Setiap Role

**Administrator**
- Kelola semua user dan PT
- Atur kategori transaksi
- Set parameter skor
- Lihat data seluruh PT

**Pemilik PT**
- Input transaksi (income/expense)
- Upload foto nota
- Set target omzet bulanan
- Lihat dashboard & rekomendasi

**Pendamping PT**
- Lihat data PT binaan
- Beri catatan/saran
- Tidak bisa ubah transaksi

**Akuntan**
- Lihat riwayat transaksi
- Kelola kategori
- Monitor health score

**Manajer**
- Monitoring struktur kerja
- Pantau kinerja staf
- Laporan operasional

## 🚀 Deployment

Website ini sudah siap diakses di GitHub Pages:

📱 **URL**: `https://adafiabiyyu31-rgb.github.io/administrasi-keuangan`

Karena menggunakan SQLite WASM dan IndexedDB, **tidak perlu backend server**. Semua data tersimpan lokal di browser Anda.

## 💻 Cara Menggunakan Lokal

1. Clone repository ini
```bash
git clone https://github.com/adafiabiyyu31-rgb/administrasi-keuangan.git
cd administrasi-keuangan
```

2. Buka dengan local server (penting untuk WASM):
```bash
# Gunakan Python
python -m http.server 8000

# Atau gunakan Node.js http-server
npx http-server
```

3. Akses di browser: `http://localhost:8000`

## 📝 Catatan Penting

- ⚠️ **Data lokal**: Semua data disimpan di IndexedDB browser, bukan di cloud
- 🔄 **Sinkronisasi**: Gunakan fitur Backup/Restore untuk transfer antar device
- 🗑️ **Clear Cache**: Jika cache dibersihkan, data akan hilang (selalu backup terlebih dahulu)
- 📱 **Mobile**: Sudah responsif untuk semua ukuran layar

## 🔧 Customization

Edit file `index.html` untuk mengubah:
- Nama PT / Logo
- Data demo awal
- Warna tema (CSS variables)
- Kategori transaksi default
- Rumus perhitungan skor

## 📞 Support

Untuk masalah atau saran, buat issue di repository GitHub ini.

---

**Created with ❤️ for UMKM Indonesia**