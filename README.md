# IFRWP5149 — Lab Alat

Repositori tugas praktikum **Analisis dan Desain Berorientasi Objek**
(Institut Teknologi Garut, S1 Teknik Informatika).

- **Nama:** Rizki Dzulfikar Al-Qatiri
- **NIM:** 2406118
- **GitHub:** [@eeqyy](https://github.com/eeqyy)

## Struktur Folder

| Folder | Isi |
| --- | --- |
| `00_administrasi/` | Logbook per pertemuan (`P01`–`P05`) |
| `01_sekenario/` | Skenario studi kasus, kebutuhan, batas sistem, aktor, dan katalog use case untuk kasus LAB dan SIA |
| `02_template/` | Template metadata artefak dan turunannya per pertemuan |
| `03_latihan_tools/` | Latihan notasi/diagram (`.drawio` + `.png`) dan deskripsi use case, dipisah per pertemuan dan per kasus (`LAB`/`SIA`) |
| `04_model_analisis/` | Model analisis per pertemuan: tabel relasi, use case, dan diagram skenario |
| `05_model_desain/` | Model desain per pertemuan |
| `06_laporan/` | Laporan singkat dan jobsheet review |

## Konvensi Penamaan

```
P<pertemuan>_<NIM>_<LAB|SIA>_<jenis-artefak>_v<versi>.<ext>
```

Contoh: `P04_2406118_LAB_model_analisis_v01.md`

Setiap pertemuan menggunakan subfolder `LAB/` dan `SIA/` agar berkas kedua
kasus tidak tercampur.

## Catatan

- Berkas sementara dari tooling (`.playwright-mcp/`, `.opencode/`, `.DS_Store`,
  `node_modules/`) tidak ikut di-commit; lihat `.gitignore`.
- Berkas `.drawio` adalah sumber yang dapat disunting; berkas `.png` adalah hasil
  ekspor dengan nomor versi yang sama.
