# PRD: Katalog UMKM + Order WhatsApp

## Tujuan

Membuat katalog produk online untuk satu UMKM, yang bisa dibagikan sebagai satu link, dengan pemesanan langsung lewat WhatsApp.

## Pengguna

| Pengguna | Kebutuhan |
| --- | --- |
| Pengunjung (calon pembeli) | Melihat produk, harga, dan deskripsi; memesan dengan cepat lewat WhatsApp |
| Admin (pemilik toko) | Masuk dengan aman, mengganti password, mengelola produk |

## Ruang lingkup

### Wajib (jalur offline)

| Fitur | User story |
| --- | --- |
| Katalog produk dari database | US-01 |
| Halaman detail produk | US-02 |
| Pesan via WhatsApp dengan pesan otomatis | US-03 |
| Login admin | US-04 |
| Ganti password admin | US-05 |
| Halaman admin hanya untuk admin yang login | US-06 |

### Bonus (jalur offline)

| Fitur | User story |
| --- | --- |
| Tambah produk | US-07 |
| Ubah produk | US-08 |
| Hapus produk | US-09 |
| Filter kategori atau pencarian | US-10 |
| Pilih jumlah atau varian sebelum pesan | US-11 |
| Aplikasi bisa di-install di HP (PWA) | US-12 |
| Deskripsi produk dibuat AI | US-13 |

Pada jalur online, US-07 sampai US-13 menjadi wajib (kecuali US-11), ditambah fitur sesuai kebutuhan klien UMKM masing-masing.

## Di luar ruang lingkup

- Keranjang belanja dan pembayaran online
- Pendaftaran akun pengunjung
- Pendaftaran akun admin dari aplikasi (akun admin dibuat dari dashboard Supabase)

## Kriteria keberhasilan

- Aplikasi dapat dibuka siapa saja melalui link Vercel.
- Pengunjung bisa memesan produk lewat WhatsApp dalam maksimal 3 klik dari halaman katalog.
- Data produk tidak dapat dibaca atau diubah langsung dari luar aplikasi.
- Password admin bawaan sudah diganti.

## Batasan teknis

- Stack: Next.js 16, Tailwind CSS 4, Supabase, Vercel (seluruhnya paket gratis).
- Akses database hanya dari server; tidak ada kunci Supabase di browser.
- Foto produk memakai link gambar (upload foto ke Supabase Storage hanya di jalur online).
