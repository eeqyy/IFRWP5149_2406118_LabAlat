<!-- deskripsi -->
Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap
pengajuan menjalankan validasi KRS yang memeriksa kelengkapan,
prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil,
sistem menyimpan pengajuan berstatus menunggu persetujuan dosen
wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih
mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS
dan memberikan catatan keputusan.

<!-- tabel kebutuhan -->
| ID      | Kebutuhan Tugas                                                           |
|:--------|:--------------------------------------------------------------------------|
| SIA-R02 | Admin akademik dapat mengelola jadwal kuliah                              |
| SIA-R06 | Dosen wali dapat memproses persetujuan atau penolakan KRS                 |
| SIA-R01 | Mahasiswa dapat melihat jadwal kuliah                                     |
| SIA-R03 | Mahasiswa dapat mengajukan KRS                                            |
| SIA-R05 | Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasi pengajuan |
| SIA-R04 | Sistem memvalidasi KRS sebagai bagian pengajuan                           |

<!-- batas sistem dan aturan -->
• Pengguna telah terautentikasi.
• Data mata kuliah, prasyarat, dan jadwal tersedia.
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
• KRS tersimpan belum berarti disetujui.
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar
tugas.

<!-- tabel identifikasi aktor -->
| Aktor             | Tujuan terhadap sistem                                                |
|:------------------|:--------------------------------------------------------------------- |
| Admin akademik    | Mengelola jadwal kuliah                                               |
| Dosen wali        | Memproses persetujuan atau penolakan KRS                              |
| Mahasiswa         | Melihat jadwal kuliah, mengajukan KRS, dan mengunduh bukti pengajuan  |

<!-- tabel katalog usecase -->
| ID         | Nama fungsi                      | Aktor terkait     | Sumber kebutuhan |
| :--------- | :------------------------------- | :---------------- | :--------------- |
| SIA-UC01   | Lihat jadwal kuliah              | Mahasiswa         | SIA-R01          |
| SIA-UC02   | Kelola jadwal kuliah             | Admin akademik    | SIA-R02          |
| SIA-UC03   | Ajukan KRS                       | Mahasiswa         | SIA-R03          |
| SIA-UC04   | Validasi KRS                     | Sistem            | SIA-R04          |
| SIA-UC05   | Unduh bukti pengajuan            | Mahasiswa         | SIA-R05          |
| SIA-UC06   | Proses persetujuan/penolakan KRS | Dosen wali        | SIA-R06          |

<!-- relasi usecase include-->
SIA-UC03 «include» SIA-UC04
Alasan: pemeriksaan kelengkapan, prasyarat mata kuliah, dan benturan jadwal menjadi bagian validasi pengajuan.

<!-- relasi usecase extend -->
SIA-UC05 «extend» SIA-UC03
Extension point: Bukti pengajuan tersedia.
Kondisi: [mahasiswa memilih mengunduh bukti].
Alasan: pengajuan tetap berhasil tanpa pengunduhan bukti.