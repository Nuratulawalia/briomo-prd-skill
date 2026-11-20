# PRD: Penanganan Transaksi Gagal pada BRImo

| | |
|---|---|
| **Penulis** | Nuratul Awalia (NIM 202110370311145, Kelas B) |
| **Mata Kuliah** | Rekayasa Interaksi (UX), Universitas Muhammadiyah Malang |
| **Produk** | BRImo (BRI Mobile), aplikasi mobile banking Bank BRI |
| **Status** | Draft v1 (proyek akademik, bukan dokumen resmi Bank BRI) |
| **Sumber** | Worksheet 8 (UX Requirements), yang merangkum Worksheet 2, 3, 5, 6, 7 |

## 1. Latar Belakang dan Masalah

Saat transaksi di BRImo gagal, pengguna tidak mendapat informasi yang jelas. Pada skenario utama, Putri (mahasiswa, 19-23 tahun) membayar lewat QRIS di toko dekat kosan. Transaksi gagal tanpa penjelasan, antrean di belakangnya panjang, lalu ia membayar tunai.

Empat bentuk masalah dari wawancara (R1, R2, R3):

| Kode | Masalah |
|---|---|
| M1 | Tidak ada penjelasan penyebab yang jelas saat transaksi gagal (kejelasan hanya 2 dari 5 pada R1 dan R3). |
| M2 | Tidak ada informasi lebih awal bahwa layanan terganggu dan kapan pulih. |
| M3 | Tidak ada petunjuk langkah berikutnya, sehingga pengguna memutuskan sendiri di bawah tekanan waktu. |
| M4 | Kegagalan saat mendesak menimbulkan kerugian nyata (waktu terbuang, denda). |

Pembanding: R2 mendapat penjelasan penyebab dan batas waktu perbaikan, menilai kejelasan 5 dari 5, dan dampaknya kecil.

## 2. Tujuan

**Tujuan produk:** pengguna selalu tahu apa yang terjadi, apakah uangnya aman, dan apa yang harus dilakukan saat transaksi gagal atau layanan terganggu.

**Tujuan pengguna:** T1 membayar cepat tanpa menahan antrean, T2 uang tetap aman, T3 bisa memakai BRImo lagi dengan tenang.

**Indikator keberhasilan** (target awal, diuji pada tahap evaluasi):
- Kejelasan pesan gagal dinilai minimal 4 dari 5 oleh peserta uji.
- 100% peserta uji dapat menyebutkan langkah berikutnya dan status uang setelah membaca layar gagal, tanpa bertanya.
- 100% peserta uji tahu layanan terganggu sebelum memulai transaksi pada skenario gangguan.

## 3. Pengguna Sasaran

**Persona: Putri**, mahasiswa nasabah BRImo, 19-23 tahun, sering membayar QRIS dan transfer, sering dalam situasi terburu-buru. Responden wawancara: dua mahasiswa dan satu pekerja muda (R1, R2, R3).

## 4. Ruang Lingkup

**Dalam cakupan:** layar transaksi gagal, status layanan pada menu transaksi, perkiraan waktu pulih, pilihan cara bayar alternatif, status dana, pintasan bantuan.

**Di luar cakupan:**
- Kebijakan bebas denda keterlambatan (bergantung pihak lain, dicatat sebagai masukan stakeholder).
- Masalah verifikasi login di ponsel baru.
- Perbaikan teknis penyebab gangguan di sisi server.

## 5. Kebutuhan Fungsional dan UX

Kode mengikuti Worksheet 8. Prioritas: Tinggi = harus ada, Sedang = sebaiknya ada, Rendah = boleh menyusul.

| ID | User Story | Functional Requirement | Kriteria UX (acceptance) | Prioritas |
|---|---|---|---|---|
| UX-01 | Sebagai nasabah, saya ingin melihat penyebab transaksi gagal dalam bahasa awam agar tidak menebak-nebak. | Tampilkan penyebab kegagalan (gangguan sistem, gangguan antarbank, data tidak sesuai) pada layar gagal. | Kejelasan minimal 4 dari 5. | Tinggi |
| UX-02 | Sebagai nasabah, saya ingin melihat langkah berikutnya agar bisa memutuskan cepat. | Tampilkan pilihan: coba lagi nanti, pakai cara lain, hubungi bantuan. | Semua peserta uji menyebutkan langkah berikutnya tanpa bertanya dan tanpa mencoba ulang berkali-kali. | Tinggi |
| UX-03 | Sebagai nasabah, saya ingin tahu lebih awal bahwa QRIS terganggu agar tidak telanjur mengantre. | Tampilkan status layanan (normal/terganggu) di menu transaksi sebelum transaksi dimulai. | Semua peserta uji tahu layanan terganggu sebelum memulai. | Tinggi |
| UX-04 | Sebagai nasabah, saya ingin melihat perkiraan waktu pulih yang akurat agar bisa memilih menunggu atau tidak. | Tampilkan perkiraan waktu pulih dan perbarui jika berubah. | Peserta uji menyebutkan perkiraan waktu; kejelasan minimal 4 dari 5. | Sedang |
| UX-05 | Sebagai nasabah, saya ingin melihat cara bayar lain agar pembayaran tetap selesai. | Tawarkan metode alternatif yang tersedia (misalnya transfer, Top Up/saldo). | Semua peserta uji menemukan dan memakai cara lain tanpa bantuan. | Sedang |
| UX-06 | Sebagai nasabah, saya ingin melihat status uang saya agar tidak khawatir. | Tampilkan status dana (belum terpotong / sudah terpotong) di layar gagal. | Semua peserta uji menyebutkan status uang setelah membaca layar. | Sedang |
| UX-07 | Sebagai nasabah, saya ingin menemukan jalur bantuan dengan mudah agar masalah bisa dilaporkan. | Sediakan pintasan ke Pusat Bantuan/laporan di layar gagal. | Peserta uji menemukan jalur bantuan tanpa dibantu. | Rendah |

## 6. Alur Utama (User Flow)

1. **Menu Transaksi:** pengguna melihat status layanan QRIS (UX-03).
2. **Pindai QRIS dan konfirmasi pembayaran.**
3. **Transaksi gagal:** layar gagal menampilkan penyebab (UX-01), status dana (UX-06), perkiraan waktu pulih (UX-04).
4. **Pilih langkah berikutnya** (UX-02): coba lagi nanti, pilih cara bayar lain (UX-05), atau buka bantuan (UX-07).
5. **Cara bayar lain berhasil:** layar sukses, atau pengguna selesai dan kembali ke beranda.

## 7. Kebutuhan Layar (untuk wireframe/prototipe, minimal 5 layar)

| No | Layar | Tujuan | Komponen utama | UX |
|---|---|---|---|---|
| 1 | Beranda / Menu Transaksi | Memulai transaksi dan melihat status layanan | Menu QRIS, Transfer, Top Up; penanda status hijau/merah | UX-03 |
| 2 | Pindai QRIS dan Konfirmasi | Memastikan nominal dan merchant | Kamera/QR, nominal, tombol Bayar | - |
| 3 | Transaksi Gagal | Menjelaskan apa yang terjadi | Penyebab, status dana, perkiraan pulih, tombol langkah berikutnya | UX-01, 04, 06 |
| 4 | Pilih Cara Bayar Lain | Menyelesaikan pembayaran dengan cara lain | Daftar metode alternatif, tombol Lanjut | UX-02, 05 |
| 5 | Pembayaran Berhasil | Konfirmasi selesai | Ringkasan, bukti transaksi, tombol Selesai | - |
| 6 | Bantuan / Laporkan Masalah | Melaporkan masalah | Form singkat, tombol Kirim, kontak | UX-07 |

## 8. Persyaratan Non-Fungsional

- Bahasa awam, istilah konsisten (misalnya selalu "Transaksi Gagal", "Cara Bayar Lain").
- Informasi terpenting (penyebab, status uang, langkah berikutnya) terlihat tanpa menggulir.
- Tombol aksi utama jelas dan mudah dijangkau ibu jari.
- Layar bisa dipahami dalam beberapa detik, karena pengguna sering di bawah tekanan waktu.

## 9. Pertimbangan Stakeholder (asumsi Worksheet 3)

- **Bank BRI (tim produk):** kepercayaan nasabah terjaga, keluhan berkurang.
- **Unit Layanan Nasabah / Pusat Bantuan:** laporan jelas dan beban keluhan terkelola.

## 10. Risiko, Keterbatasan, dan Asumsi

- Data dari 3 responden, belum mewakili semua pengguna BRImo.
- UX-04 dan UX-07 sebagian masih asumsi.
- Kriteria UX adalah target awal peneliti dan perlu diuji pada evaluasi.
- Penyebab kegagalan yang ditampilkan bergantung pada ketersediaan data dari sistem; pada prototipe, data berupa simulasi.
- Dokumen ini adalah proyek akademik dan bukan data internal Bank BRI.

## 11. Pertanyaan Terbuka

- Seberapa akurat perkiraan waktu pulih yang bisa diberikan sistem?
- Metode alternatif apa saja yang tersedia di tiap jenis gangguan?
- Apakah status layanan perlu ditampilkan juga sebagai notifikasi, bukan hanya di menu?
