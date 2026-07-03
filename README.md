# 🌙 DreamyKids – Baju Tidur Anak Premium

Landing page & mini e-commerce single-page untuk toko baju tidur anak, lengkap dengan katalog produk, keranjang belanja, dan alur checkout multi-step. Dibangun murni dengan **HTML, CSS, dan JavaScript vanilla** — tanpa framework, tanpa build tool.

## ✨ Fitur

- **Header sticky** dengan navigasi dan tombol keranjang (menampilkan jumlah item).
- **Hero section** dengan judul, deskripsi, CTA, dan statistik toko.
- **Katalog produk** dinamis (grid responsif) dengan badge "Baru" / "Sale", ukuran (S/M/L/XL), harga, dan tombol tambah ke keranjang.
- **Keranjang belanja (side panel)**:
  - Tambah / kurangi jumlah item
  - Hapus item
  - Kalkulasi total otomatis
- **Alur checkout 3 langkah** (modal):
  1. Data pengiriman (nama, telepon, alamat)
  2. Pilih metode pembayaran (Transfer Bank, GoPay, OVO, QRIS, COD) + info rekening/nomor & tombol salin
  3. Konfirmasi pesanan berhasil dengan nomor order acak
- **Ongkos kirim otomatis**: gratis ongkir jika subtotal ≥ Rp150.000, selain itu Rp15.000.
- **Notifikasi toast** untuk aksi seperti tambah ke keranjang, validasi form, dan penyalinan nomor rekening.
- **Desain tema pink pastel** yang lembut dan ramah anak, menggunakan font Google Fonts (`Playfair Display` & `Nunito`).

## 📂 Struktur File

```
index.html   → Seluruh halaman (HTML + CSS + JS) dalam satu file
```

Semua styling ditulis inline di dalam tag `<style>`, dan seluruh logika interaktif (keranjang, checkout, render produk) ditulis di dalam tag `<script>` menggunakan JavaScript vanilla — tidak ada dependensi eksternal selain Google Fonts.

## 🛠️ Cara Menjalankan

Karena tidak ada proses build, cukup buka file secara langsung di browser:

1. Download / clone project ini.
2. Buka file `index.html` dengan browser (double click, atau klik kanan → *Open with Browser*).
3. Selesai — halaman langsung berjalan tanpa server.

> Tips: untuk pengalaman terbaik (misalnya menghindari isu CORS saat pengembangan lanjutan), Anda juga bisa menjalankannya lewat local server sederhana, contohnya:
> ```bash
> npx serve .
> ```

## 🧩 Menambah / Mengubah Produk

Daftar produk didefinisikan sebagai array JavaScript `products` di dalam tag `<script>` pada `index.html`. Setiap produk memiliki struktur:

```js
{
  id: 4,
  name: "Piyama Animal",
  desc: "Desain lucu dan bahan lembut",
  price: 130000,
  image: "https://url-gambar.jpg",
  sizes: ["S", "M", "L", "XL"],
  badge: "sale" // opsional: "new" | "sale" | (kosongkan jika tidak ada)
}
```

Tambahkan/ubah item pada array ini, lalu simpan — produk akan otomatis dirender ulang oleh fungsi `renderProducts()`.

## 💳 Metode Pembayaran

Detail rekening/nomor untuk setiap metode pembayaran diatur pada objek `bankDetails` di dalam `<script>`. Sesuaikan nomor rekening/QR sebelum digunakan secara nyata (saat ini masih berisi data contoh/dummy).

## ⚠️ Catatan

- Ini adalah **prototipe front-end saja** — belum terhubung ke backend, database, payment gateway, atau sistem pengiriman nyata. Cocok untuk demo, portofolio, atau mockup toko online.
- Nomor rekening, harga, dan gambar produk yang tersedia adalah data contoh dan perlu diganti dengan data asli sebelum digunakan untuk bisnis nyata.
- Semua data (keranjang, pesanan) disimpan sementara di memori browser (variabel JavaScript) dan akan hilang saat halaman di-refresh.

## 📄 Lisensi

Bebas digunakan dan dimodifikasi sesuai kebutuhan Anda.
