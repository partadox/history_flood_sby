# 🌊 Flood Data Viewer - Surabaya

Visualisasi data banjir Surabaya hasil ekstraksi dari berita online menggunakan LLM.

## 📋 Fitur

- **🗺️ Map Visualization** (`index.html`) - Peta interaktif dengan marker lokasi banjir
- **📊 Data Table** (`index2.html`) - Tabel data lengkap dengan fitur search, sort, dan export
- **🔄 Navigasi Mudah** - Tombol navigasi antar halaman
- **📱 Responsive** - Tampilan optimal di berbagai device

## 🚀 Deployment dengan Docker/Podman

### Prasyarat
- Docker atau Podman terinstall di server
- Docker Compose atau Podman Compose

### Cara Deploy

#### Menggunakan Docker Compose:
```bash
# Clone atau upload folder ke server
cd history_flood_sby_v1

# Jalankan container
docker-compose up -d

# Cek status
docker-compose ps

# Lihat logs
docker-compose logs -f
```

#### Menggunakan Podman Compose:
```bash
# Clone atau upload folder ke server
cd history_flood_sby_v1

# Jalankan container
podman-compose up -d

# Cek status
podman-compose ps

# Lihat logs
podman-compose logs -f
```

### Akses Aplikasi

Setelah container berjalan, akses melalui browser:
- **Default**: http://localhost:8080
- **Server**: http://your-server-ip:8080

**Halaman yang tersedia:**
- `http://localhost:8080/index.html` - Peta Visualisasi
- `http://localhost:8080/index2.html` - Tabel Data

## 🔧 Konfigurasi

### Ubah Port (Opsional)

Edit file `docker-compose.yml`, ubah bagian ports:
```yaml
ports:
  - "8080:80"  # Ganti 8080 dengan port yang diinginkan
```

### Custom Domain/Reverse Proxy

Jika menggunakan Nginx reverse proxy atau Traefik, edit `nginx.conf` dan sesuaikan `server_name`.

## 🛑 Menghentikan Container

```bash
# Docker
docker-compose down

# Podman
podman-compose down
```

## 🔄 Update Data

Untuk update data banjir:
1. Ganti file `data.json` dengan data terbaru
2. Restart container:
   ```bash
   docker-compose restart
   # atau
   podman-compose restart
   ```

## 📁 Struktur File

```
history_flood_sby_v1/
├── index.html           # Peta visualisasi
├── index2.html          # Tabel data
├── data.json           # Data banjir
├── docker-compose.yml  # Docker/Podman configuration
├── nginx.conf          # Nginx server configuration
└── README.md           # Dokumentasi
```

## 🐛 Troubleshooting

### Container tidak bisa diakses
```bash
# Cek status container
docker ps
# atau
podman ps

# Cek logs untuk error
docker-compose logs
# atau
podman-compose logs
```

### Port sudah digunakan
Edit `docker-compose.yml` dan ubah port ke port lain yang tersedia.

### Data tidak muncul
Pastikan file `data.json` ada di folder yang sama dan formatnya valid JSON.

## 📝 Lisensi

Data visualisasi banjir Surabaya untuk keperluan riset.

## 📧 Kontak

Untuk pertanyaan atau masalah, silakan hubungi tim developer.
