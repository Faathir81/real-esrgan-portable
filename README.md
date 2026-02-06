# 📖 DOKUMENTASI REAL-ESRGAN NCNN VULKAN

## 🎨 Deskripsi Proyek

Proyek ini adalah implementasi **Real-ESRGAN** (Real-Time Enhanced Super-Resolution Generative Adversarial Network) yang menggunakan NCNN untuk inferensi GPU melalui Vulkan API. Aplikasi ini digunakan untuk **meningkatkan resolusi gambar dan video** secara signifikan dengan hasil yang tajam dan berkualitas tinggi.

### Fitur Utama:
- ✅ Upscaling gambar hingga **4x resolusi asli**
- ✅ Mendukung format: **JPG, PNG, WEBP**
- ✅ Mode khusus untuk **anime/kartun**
- ✅ Mendukung **batch processing** (banyak gambar sekaligus)
- ✅ Mendukung **multi-GPU**
- ✅ Portable - tidak memerlukan CUDA atau PyTorch

---

## 🚀 CARA MENDAPATKAN & MENJALANKAN

### ✨ KABAR BAIK: Tidak Perlu Instalasi!

Ini adalah **portable executable** - cukup punya filenya, langsung bisa dipakai!

| Yang Dibutuhkan | Yang TIDAK Dibutuhkan |
|-----------------|----------------------|
| ✅ File `.exe` dan `.dll` | ❌ Python |
| ✅ Folder `models/` | ❌ CUDA |
| ✅ GPU dengan Vulkan support | ❌ PyTorch |
| | ❌ Instalasi khusus |

---

### Opsi 1: Clone dari Repository (Recommended)
```powershell
# Clone repository
git clone https://github.com/Faathir81/real-esrgan-portable.git

# Masuk ke folder
cd real-esrgan-portable

# Langsung pakai!
.\realesrgan-ncnn-vulkan.exe -i gambar.jpg -o gambar_HD.png
```

### Opsi 2: Download dari GitHub Releases
1. Download dari [Real-ESRGAN Releases](https://github.com/xinntao/Real-ESRGAN/releases)
2. Pilih file: `realesrgan-ncnn-vulkan-*-windows.zip`
3. Ekstrak ke folder pilihan Anda
4. Langsung pakai!

---

### Struktur Folder
```
real-esrgan-portable/
├── realesrgan-ncnn-vulkan.exe   ← File utama (langsung jalankan!)
├── vcomp140.dll                  ← Library (jangan dihapus!)
├── vcomp140d.dll
├── models/                       ← Folder model AI (wajib ada!)
│   ├── realesrgan-x4plus.bin
│   ├── realesrgan-x4plus.param
│   └── ... (model lainnya)
├── input/                        ← Taruh gambar input di sini (opsional)
├── Real-ESRGAN/                  ← Hasil upscale akan di sini (opsional)
├── tmp_frames/                   ← Untuk frame video sementara
└── out_frames/                   ← Untuk frame hasil upscale
```

---

### Verifikasi: Cek Apakah Sudah Bisa Jalan
```powershell
.\realesrgan-ncnn-vulkan.exe -h
```
Jika muncul daftar parameter = **Berhasil!** ✅

---

### Uji Coba Pertama
```powershell
# Upscale gambar tunggal
.\realesrgan-ncnn-vulkan.exe -i gambar.jpg -o gambar_HD.png

# Atau upscale semua gambar di folder input ke folder Real-ESRGAN
.\realesrgan-ncnn-vulkan.exe -i input -o Real-ESRGAN
```

---

### ⚠️ Troubleshooting

| Masalah | Solusi |
|---------|--------|
| "VCRUNTIME140.dll not found" | Install [Visual C++ Redistributable](https://aka.ms/vs/17/release/vc_redist.x64.exe) |
| "No Vulkan device found" | Update driver GPU ke versi terbaru |
| Proses sangat lambat | Pastikan menggunakan GPU dedicated, bukan integrated |
| Out of memory | Kurangi tile size: `-t 64` atau `-t 128` |

---

## �👨‍💻 KREDIT & COPYRIGHT

### Developer Asli:

| Kontributor | Peran | Link |
|-------------|-------|------|
| **Xintao Wang (xinntao)** | Penulis utama Real-ESRGAN | [GitHub](https://github.com/xinntao/Real-ESRGAN) |
| **nihui** | Implementasi NCNN Vulkan | [GitHub](https://github.com/nihui/realsr-ncnn-vulkan) |
| **Tencent** | Framework NCNN | [GitHub](https://github.com/Tencent/ncnn) |

### Publikasi Ilmiah:
```
Real-ESRGAN: Training Real-World Blind Super-Resolution with Pure Synthetic Data
Xintao Wang, Liangbin Xie, Chao Dong, Ying Shan
arXiv:2107.10833
https://arxiv.org/abs/2107.10833
```

### Lisensi:
Proyek ini menggunakan lisensi dari Real-ESRGAN. Mohon kunjungi repositori resmi untuk informasi lisensi lengkap.

> ⚠️ **PENTING**: Proyek ini dikembangkan oleh pihak ketiga. Mohon hormati hak cipta dan berikan kredit yang sesuai jika digunakan dalam proyek lain.

---

## 📁 Struktur Proyek

```
real-esrgan-portable/
├── realesrgan-ncnn-vulkan.exe    # File executable utama
├── vcomp140.dll                   # Library Visual C++ Runtime
├── vcomp140d.dll                  # Library Visual C++ Runtime (Debug)
├── models/                        # Folder model AI
│   ├── realesr-animevideov3-x2.*  # Model anime video 2x
│   ├── realesr-animevideov3-x3.*  # Model anime video 3x
│   ├── realesr-animevideov3-x4.*  # Model anime video 4x
│   ├── realesrgan-x4plus.*        # Model umum 4x (terbaik)
│   └── realesrgan-x4plus-anime.*  # Model anime 4x
├── input/                         # Folder input gambar (opsional)
├── Real-ESRGAN/                   # Folder hasil upscaling (opsional)
└── README.md                      # Dokumentasi
```

---

## 🛠️ CARA PENGGUNAAN

### Persiapan:
1. Pastikan semua file dalam satu folder
2. Buka **Command Prompt** atau **PowerShell**
3. Navigasi ke folder proyek dengan perintah `cd`

### Model yang Tersedia:

| Model | Deskripsi | Kegunaan |
|-------|-----------|----------|
| `realesr-animevideov3` | Default model | Video anime |
| `realesrgan-x4plus` | Model real photo | Foto nyata (terbaik) |
| `realesrgan-x4plus-anime` | Model anime | Gambar anime/kartun |
| `realesrnet-x4plus` | Model alternatif | Hasil lebih natural |

---

## 📝 PERINTAH DASAR

### 1️⃣ Upscaling Gambar Tunggal (Default)
```powershell
.\realesrgan-ncnn-vulkan.exe -i input.jpg -o output.png
```

### 2️⃣ Upscaling dengan Model Tertentu
```powershell
# Untuk foto nyata (hasil terbaik)
.\realesrgan-ncnn-vulkan.exe -i Photo.jpg -o PhotoHD.png -n realesrgan-x4plus

# Untuk anime/kartun
.\realesrgan-ncnn-vulkan.exe -i Photo.jpg -o PhotoHD.png -n realesrgan-x4plus-anime
```

### 3️⃣ Upscaling Folder (Batch Processing)
```powershell
# Buat folder output terlebih dahulu!
.\realesrgan-ncnn-vulkan.exe -i folder_input -o folder_output

# Dengan model tertentu
.\realesrgan-ncnn-vulkan.exe -i lowres -o highres -n realesrgan-x4plus-anime
```

### 4️⃣ Mengatur Skala Upscaling
```powershell
# 2x upscale
.\realesrgan-ncnn-vulkan.exe -i input.jpg -o output.png -s 2

# 4x upscale (default)
.\realesrgan-ncnn-vulkan.exe -i input.jpg -o output.png -s 4
```

### 5️⃣ Mengatur Format Output
```powershell
.\realesrgan-ncnn-vulkan.exe -i input_folder -o output_folder -f jpg
```

---

## 🎬 UPSCALING VIDEO ANIME

Untuk video, gunakan **FFmpeg** dengan langkah berikut:

### Langkah 1: Ekstrak Frame dari Video
```powershell
# Buat folder tmp_frames terlebih dahulu
mkdir tmp_frames
ffmpeg -i video_anime.mp4 -qscale:v 1 -qmin 1 -qmax 1 -vsync 0 tmp_frames/frame%08d.jpg
```

### Langkah 2: Upscale Semua Frame
```powershell
# Buat folder out_frames terlebih dahulu
mkdir out_frames
.\realesrgan-ncnn-vulkan.exe -i tmp_frames -o out_frames -n realesr-animevideov3 -s 2 -f jpg
```

### Langkah 3: Gabungkan Frame Menjadi Video
```powershell
ffmpeg -i out_frames/frame%08d.jpg -i video_anime.mp4 -map 0:v:0 -map 1:a:0 -c:a copy -c:v libx264 -r 23.98 -pix_fmt yuv420p output_hd.mp4
```

---

## ⚙️ PARAMETER LENGKAP

| Parameter | Deskripsi | Default |
|-----------|-----------|---------|
| `-i` | Path gambar/folder input | (wajib) |
| `-o` | Path gambar/folder output | (wajib) |
| `-s` | Skala upscale (2, 3, 4) | 4 |
| `-n` | Nama model | realesrgan-x4plus |
| `-m` | Path folder model | models |
| `-t` | Ukuran tile (≥32, 0=auto) | 0 |
| `-g` | GPU ID (0,1,2 untuk multi-GPU) | 0 |
| `-j` | Thread count (load:proc:save) | 1:2:2 |
| `-x` | Enable TTA mode | disabled |
| `-f` | Format output (jpg/png/webp) | ext/png |
| `-v` | Verbose output | disabled |
| `-h` | Tampilkan bantuan | - |

---

## 💡 TIPS & REKOMENDASI

### Pemilihan Model:
- **Foto nyata** → Gunakan `realesrgan-x4plus`
- **Anime/kartun** → Gunakan `realesrgan-x4plus-anime`
- **Video anime** → Gunakan `realesr-animevideov3`

### Performa:
- Untuk gambar besar, kurangi tile size: `-t 64` atau `-t 128`
- Untuk multi-GPU: `-g 0,1` dan `-j 1:2,2:2`

### Catatan Penting:
- Input dan output harus berbeda (tidak bisa overwrite file yang sama)
- Folder output harus dibuat terlebih dahulu untuk batch processing
- Format PNG menghasilkan kualitas terbaik (lossless)

---

## 🔗 REFERENSI & SUMBER

| Sumber | Link |
|--------|------|
| Real-ESRGAN GitHub | https://github.com/xinntao/Real-ESRGAN |
| NCNN Vulkan | https://github.com/nihui/realsr-ncnn-vulkan |
| NCNN Framework | https://github.com/Tencent/ncnn |
| Paper ArXiv | https://arxiv.org/abs/2107.10833 |

---

## 📄 CATATAN EDITOR

Tutorial ini diedit oleh **NIHIL Project** berdasarkan halaman GitHub resmi **xinntao** tentang Real-ESRGAN.

> Dokumentasi dibuat pada: Februari 2026  
> Terakhir diperbarui: Februari 2026

---

**© 2021-2026 Xintao Wang & Kontributor Real-ESRGAN. Semua hak dilindungi.**
