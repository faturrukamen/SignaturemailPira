# Piranusa Email Signature Generator

Generator email signature untuk PT. Piranti Teknologi Nusantara (Piranusa) dengan fitur **banner event seasonal**.

🔗 **Live:** https://faturrukamen.github.io/SignaturemailPira/

---

## Cara Update Banner Event

### 1. Tambah gambar banner
Upload gambar banner ke folder `banners/` (format: JPG/PNG, lebar ideal 600px).

### 2. Edit `events.json`

```json
{
  "events": [
    {
      "id": "nama-event-tahun",
      "name": "Nama Event",
      "date": "19–23 Mei 2026",
      "banner_url": "https://raw.githubusercontent.com/faturrukamen/SignaturemailPira/main/banners/nama-file.jpg",
      "link": "https://website-event.com",
      "active": true,
      "is_new": true
    }
  ]
}
```

| Field | Keterangan |
|-------|-----------|
| `id` | ID unik event (huruf kecil + tanda hubung) |
| `name` | Nama event yang tampil di generator |
| `date` | Tanggal event (teks bebas) |
| `banner_url` | URL gambar banner (gunakan raw.githubusercontent.com) |
| `link` | URL tujuan saat banner diklik (opsional) |
| `active` | `true` = tampil, `false` = sembunyikan |
| `is_new` | `true` = badge AKTIF + default dicentang |

### 3. Push ke GitHub → otomatis live

```bash
git add banners/nama-file.jpg events.json
git commit -m "Add event banner: Nama Event"
git push
```

### Contoh: 2 event berdekatan
Jika 2 event aktif bersamaan, keduanya muncul di panel kiri dengan checkbox masing-masing. User bisa pilih salah satu atau keduanya.

---

## Struktur Repo

```
SignaturemailPira/
├── index.html        ← Generator (deploy via GitHub Pages)
├── events.json       ← Config banner aktif
└── banners/          ← Folder gambar banner event
    └── .gitkeep
```
