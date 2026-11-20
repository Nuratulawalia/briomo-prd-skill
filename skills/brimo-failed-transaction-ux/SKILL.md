---
name: brimo-failed-transaction-ux
description: Panduan merancang dan membangun layar penanganan transaksi gagal pada prototipe BRImo (mobile banking). Gunakan saat membuat, mengubah, atau mereview layar transaksi gagal, status layanan, cara bayar lain, status dana, atau bantuan, berdasarkan PRD.md di repositori ini.
---

# Skill: UX Transaksi Gagal BRImo

Dibuat oleh Nuratul Awalia (NIM 202110370311145), Rekayasa Interaksi, Universitas Muhammadiyah Malang.

Skill ini memandu pembuatan prototipe yang konsisten dengan `PRD.md`. Baca `PRD.md` lebih dulu (bagian 5 dan 7) sebelum menulis kode atau desain apa pun.

## Prinsip inti

Saat transaksi gagal, pengguna (persona: Putri, mahasiswa 19-23 tahun, sering terburu-buru) harus langsung tahu tiga hal tanpa bertanya:

1. **Apa yang terjadi** (penyebab, bahasa awam) - UX-01
2. **Apakah uangnya aman** (status dana) - UX-06
3. **Apa yang harus dilakukan sekarang** (langkah berikutnya) - UX-02

## Aturan layar

| Layar | Wajib ada |
|---|---|
| Beranda / Menu Transaksi | Penanda status layanan per menu (hijau = normal, merah = terganggu) sebelum transaksi dimulai (UX-03) |
| Pindai QRIS dan Konfirmasi | Nominal, nama merchant, tombol Bayar |
| Transaksi Gagal | Judul "Transaksi Gagal", penyebab, status dana, perkiraan waktu pulih bila ada (UX-04), tombol "Pilih Cara Bayar Lain" (aksi utama), tombol "Coba Lagi Nanti", pintasan "Bantuan" (UX-07) |
| Pilih Cara Bayar Lain | Daftar metode alternatif yang tersedia, tombol Lanjut (UX-05) |
| Pembayaran Berhasil | Ringkasan, bukti transaksi, tombol Selesai |
| Bantuan / Laporkan Masalah | Form singkat, tombol Kirim |

## Aturan konten

- Pakai bahasa awam. Hindari kode error atau istilah teknis di teks utama. Contoh: "Layanan QRIS sedang gangguan. Ini bukan kesalahan Anda." Bukan: "Error 503 timeout".
- Status dana selalu eksplisit: "Uang Anda aman, saldo belum terpotong." atau "Saldo sudah terpotong. Silakan hubungi Bantuan jika belum kembali." Jangan membuat janji pengembalian dana yang tidak ada di PRD.
- Perkiraan waktu pulih ditampilkan hanya bila ada dan diberi tanda bila diperbarui. Jangan mengarang angka.
- Istilah konsisten di semua layar: "Transaksi Gagal", "Cara Bayar Lain", "Coba Lagi Nanti", "Bantuan".
- Jangan menyalahkan pengguna.

## Aturan interaksi dan tata letak

- Penyebab, status dana, dan langkah berikutnya terlihat tanpa menggulir.
- Satu aksi utama per layar. Aksi sekunder tampil lebih ringan.
- Tombol aksi di area yang mudah dijangkau ibu jari (bagian bawah).
- Alur utama harus bisa diikuti dari awal sampai akhir: Beranda → Pindai/Konfirmasi → Gagal → Cara Bayar Lain → Berhasil. Bantuan dapat dibuka dari layar Gagal dan bisa kembali.
- Jangan menambah layar di luar tabel di atas.

## Data simulasi

Prototipe memakai data simulasi, bukan sistem BRI sungguhan. Skenario yang dipakai: QRIS terganggu dengan perkiraan pulih sekitar 30 menit.

## Checklist sebelum selesai

- [ ] Minimal 5 layar saling terhubung dan alur utama bisa dijalankan sampai akhir.
- [ ] Layar Gagal memuat penyebab, status dana, langkah berikutnya.
- [ ] Status layanan terlihat di menu transaksi sebelum memulai.
- [ ] Cara bayar lain bisa dipilih dan menyelesaikan pembayaran.
- [ ] Jalur bantuan tersedia dari layar Gagal.
- [ ] Istilah dan tombol konsisten.
- [ ] Setiap kebutuhan UX-01 sampai UX-07 punya tempat di rancangan.
