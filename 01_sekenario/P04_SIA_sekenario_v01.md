<!-- deskripsi -->
Mahasiswa dan dosen sama-sama merupakan Civitas Akademika yang
dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang
diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu
Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin
Akademik mengelola data mahasiswa: menambah data mahasiswa baru,
mengubah data mahasiswa, dan menghapus data mahasiswa. Dua use case
utama, Input Nilai Mata Kuliah dan Lihat KHS, ditunjukkan realisasinya oleh
collaboration yang bersesuaian.


<!-- batas sistem dan aturan -->
• Kode kebutuhan dimulai dari SIA-R07 agar SIA-R01 dan SIA-R02
(Pertemuan 2) serta SIA-R03 sampai SIA-R06 (Pertemuan 3) tetap
mempunyai identitas berbeda.
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran.
• Kalender akademik pada tugas ini adalah agenda resmi institusi (awal
semester, batas KRS, masa ujian, dan sejenisnya); jangan
menyamakannya dengan jadwal kuliah pada Pertemuan 2.
• Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. Nilai
yang diinput belum terpublikasi sebelum dinyatakan resmi oleh ketentuan
tugas ini: KHS hanya menampilkan nilai yang sudah dipublikasikan.
• Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki data
akademik aktif. Ketentuan ini fiktif untuk latihan.
• Pengajuan KRS tetap digambar sebagai bagian diagram kumulatif dari
Pertemuan 3. Pembayaran dan perancangan basis data berada di luar
tugas ini.

<!-- tabel identifikasi aktor -->
| Aktor                 | Kedudukan                                                      | Tujuan terhadap Sistem                                                                                                                                    |
|-----------------------|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Civitas Akademika** | Umum (general), baru pada Pertemuan 4                          | Peran umum bagi Mahasiswa dan Dosen. Mewariskan fungsinya (melihat kalender akademik) kepada Mahasiswa dan Dosen.                                         |
| **Mahasiswa**         | Khusus dari Civitas Akademika, tetap dari pertemuan sebelumnya | Melihat jadwal kuliah, mengajukan KRS, mengunduh bukti pengajuan KRS, dan melihat KHS, serta melihat kalender akademik (diwarisi dari Civitas Akademika). |
| **Dosen**             | Khusus dari Civitas Akademika, tetap dari pertemuan sebelumnya | Menginput nilai mata kuliah yang diampunya, serta melihat kalender akademik (diwarisi dari Civitas Akademika).                                            |
| **Admin Akademik**    | Utama, tetap dari pertemuan sebelumnya                         | Mengelola jadwal kuliah serta mengelola data mahasiswa (tambah, ubah, dan hapus data mahasiswa).                                                          |
| **Dosen Wali**        | Utama, tetap dari pertemuan sebelumnya                         | Memproses keputusan KRS (menyetujui atau menolak pengajuan KRS mahasiswa).                                                                                |


<!-- tabel katalog usecase -->
| ID       | Nama use case             | Peran dalam model                                                         | Sumber kebutuhan |
|----------|---------------------------|---------------------------------------------------------------------------|------------------|
| SIA-UC01 | Lihat Jadwal Kuliah       | Tetap dari Pertemuan 2; fungsi khusus Mahasiswa                           | SIA-R01          |
| SIA-UC02 | Kelola Jadwal Kuliah      | Tetap dari Pertemuan 2; fungsi utama Admin Akademik                       | SIA-R02          |
| SIA-UC03 | Ajukan KRS                | Tetap dari Pertemuan 3; fungsi khusus Mahasiswa; menyertakan SIA-UC04     | SIA-R03          |
| SIA-UC04 | Validasi KRS              | Tetap dari Pertemuan 3; perilaku yang disertakan SIA-UC03                 | SIA-R04          |
| SIA-UC05 | Unduh Bukti Pengajuan KRS | Tetap dari Pertemuan 3; tambahan bersyarat pada SIA-UC03 melalui «extend» | SIA-R05          |
| SIA-UC06 | Proses Keputusan KRS      | Tetap dari Pertemuan 3; fungsi utama Dosen Wali                           | SIA-R06          |
| SIA-UC07 | Lihat Kalender Akademik   | Baru pada Pertemuan 4; fungsi aktor umum Civitas Akademika                | SIA-R07          |
| SIA-UC08 | Input Nilai Mata Kuliah   | Baru pada Pertemuan 4; fungsi khusus Dosen; direalisasikan SIA-CO01       | SIA-R08, SIA-R12 |
| SIA-UC09 | Lihat KHS                 | Baru pada Pertemuan 4; fungsi khusus Mahasiswa; direalisasikan SIA-CO02   | SIA-R09, SIA-R12 |
| SIA-UC10 | Kelola Data Mahasiswa     | Baru pada Pertemuan 4; use case UMUM bagi SIA-UC11, SIA-UC12, SIA-UC13    | SIA-R10, SIA-R11 |
| SIA-UC11 | Tambah Data Mahasiswa     | Baru pada Pertemuan 4; use case KHUSUS dari SIA-UC10                      | SIA-R11          |
| SIA-UC12 | Ubah Data Mahasiswa       | Baru pada Pertemuan 4; use case KHUSUS dari SIA-UC10                      | SIA-R11          |
| SIA-UC13 | Hapus Data Mahasiswa      | Baru pada Pertemuan 4; use case KHUSUS dari SIA-UC10                      | SIA-R11          |


<!-- relasi usecase include-->
SIA-UC03 «include» SIA-UC04
Alasan: pemeriksaan kelengkapan, prasyarat mata kuliah, dan benturan jadwal menjadi bagian validasi pengajuan.

<!-- relasi usecase extend -->
SIA-UC05 «extend» SIA-UC03
Extension point: Bukti pengajuan tersedia.
Kondisi: [mahasiswa memilih mengunduh bukti].
Alasan: pengajuan tetap berhasil tanpa pengunduhan bukti.

<!-- collaboration & realitatioin -->
| ID Collaboration | Nama Collaboration | Use Case yang Direalisasikan |
| --- | --- | --- |
| **SIA-CO01** | Input Nilai Mata Kuliah | SIA-UC08 Input Nilai Mata Kuliah |
| **SIA-CO02** | Lihat KHS | SIA-UC09 Lihat KHS |
