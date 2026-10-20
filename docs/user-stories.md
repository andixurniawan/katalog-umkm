# User Story

Setiap user story diberi nomor. Pakai nomor ini di prompt ("kerjakan US-01") dan di pesan commit (`US-01: katalog dari database`).

Setiap kriteria selesai diberi poin, dan jumlahnya sama dengan poin user story. User story dinyatakan selesai kalau semua kriterianya terpenuhi.

## Cara penilaian

- **Lulus:** US-01 sampai US-06 selesai (semua kriteria terpenuhi).
- **Bonus:** US-07 sampai US-50 hanya dihitung kalau kamu sudah lulus. Kerjakan berurutan sampai waktu atau kuota AI-mu habis; tidak semua harus selesai.
- **Poin:** US-01 sampai US-14 masing-masing 10 poin. US-15 sampai US-50 bernilai 5, 10, atau 15 poin sesuai beban kerjanya.
- Selain user story, ada penilaian keamanan dan jurnal prompt (`PROMPTS.md`). Panitia menjelaskan rinciannya terpisah.

## Wajib

### US-01 Katalog dari database

Sebagai pengunjung, saya ingin melihat semua produk toko dalam satu halaman, supaya saya tahu apa saja yang dijual.

Bernilai 10 poin.

Kriteria selesai:

- Halaman `/` menampilkan semua produk dari tabel `produk` di Supabase, bukan dari `lib/data-contoh.js`. Kalau kamu mengerjakan paginasi (US-16) atau menyembunyikan produk nonaktif (US-32), kriteria ini tetap terpenuhi. (3 poin)
- Data diambil di sisi server. (2 poin)
- Setiap kartu menampilkan foto, kategori, nama, dan harga dalam format rupiah. (3 poin)
- Jika belum ada produk, halaman menampilkan pesan yang jelas. (2 poin)

### US-02 Detail produk

Sebagai pengunjung, saya ingin melihat detail satu produk, supaya saya yakin sebelum memesan.

Bernilai 10 poin.

Kriteria selesai:

- Halaman `/produk/[id]` menampilkan foto, kategori, nama, harga, dan deskripsi dari database. (6 poin)
- Produk yang tidak ada menampilkan halaman "tidak ditemukan". (4 poin)

### US-03 Pesan via WhatsApp

Sebagai pengunjung, saya ingin menekan satu tombol untuk memesan lewat WhatsApp, supaya saya tidak perlu mengetik ulang nama produk.

Bernilai 10 poin.

Kriteria selesai:

- Tombol "Pesan via WhatsApp" membuka WhatsApp ke nomor di `lib/toko.js`. (4 poin)
- Pesan sudah terisi otomatis dengan nama dan harga produk. (4 poin)
- Berfungsi di HP dan di laptop. (2 poin)

### US-04 Login admin

Sebagai admin, saya ingin masuk dengan email dan password, supaya hanya saya yang bisa mengelola toko.

Bernilai 10 poin.

Kriteria selesai:

- Login memakai Supabase Auth, diproses di server. (4 poin)
- Login berhasil mengarah ke `/admin`; login gagal menampilkan pesan yang jelas. (3 poin)
- Tombol "Keluar" mengakhiri sesi dan kembali ke halaman login. (3 poin)

### US-05 Ganti password

Sebagai admin, saya ingin mengganti password, supaya password bawaan tidak bisa dipakai orang lain.

Bernilai 10 poin.

Kriteria selesai:

- Form di `/admin/password` mengganti password admin yang sedang login. (4 poin)
- Password baru minimal 8 karakter dan harus sama dengan konfirmasinya. (3 poin)
- Menampilkan pesan berhasil atau pesan error yang jelas. (3 poin)

### US-06 Proteksi halaman admin

Sebagai admin, saya ingin halaman admin tertutup untuk orang lain, supaya data toko aman.

Bernilai 10 poin.

Kriteria selesai:

- Membuka halaman `/admin` mana pun tanpa login akan dialihkan ke `/admin/login`. (5 poin)
- Setiap aksi yang mengubah data memeriksa login di server. (5 poin)

## Bonus

### US-07 List Produk

Sebagai admin, saya ingin produk pada page `/admin` mengambil data dari database.

Bernilai 10 poin.

Kriteria selesai:

- Daftar produk di `/admin` diambil dari database, bukan data contoh. (10 poin)

### US-08 Tambah produk

Sebagai admin, saya ingin menambah produk baru dari halaman admin.

Bernilai 10 poin.

Kriteria selesai:

- Form di `/admin/produk/baru` menyimpan produk ke database. (5 poin)
- Setelah menyimpan, halaman kembali ke `/admin`. (2 poin)
- Aksinya terlindungi login: tanpa login ditolak oleh server. (3 poin)

### US-09 Ubah produk

Sebagai admin, saya ingin mengubah data produk.

Bernilai 10 poin.

Kriteria selesai:

- Form di `/admin/produk/[id]/ubah` terisi data lama. (4 poin)
- Perubahan tersimpan ke database. (3 poin)
- Aksinya terlindungi login: tanpa login ditolak oleh server. (3 poin)

### US-10 Hapus produk

Sebagai admin, saya ingin menghapus produk.

Bernilai 10 poin.

Kriteria selesai:

- Tombol "Hapus" meminta konfirmasi. (4 poin)
- Produk terhapus dari database. (3 poin)
- Aksinya terlindungi login: tanpa login ditolak oleh server. (3 poin)

### US-11 Filter kategori atau pencarian

Sebagai pengunjung, saya ingin menyaring produk berdasarkan kategori atau mencari nama produk.

Bernilai 10 poin.

Kriteria selesai:

- Pengunjung bisa menyaring produk per kategori atau mencari nama produk, dan hasilnya sesuai. (10 poin)

### US-12 Pilih jumlah atau varian

Sebagai pengunjung, saya ingin memilih jumlah atau varian sebelum memesan, dan pilihan itu ikut tertulis di pesan WhatsApp.

Bernilai 10 poin.

Kriteria selesai:

- Pengunjung bisa memilih jumlah atau varian sebelum memesan. (5 poin)
- Pilihan itu ikut tertulis di pesan WhatsApp. (5 poin)

### US-13 PWA

Sebagai pengunjung, saya ingin memasang katalog di layar HP seperti aplikasi. Ikon tersedia di `public/icons`.

Bernilai 10 poin.

Kriteria selesai:

- Ada web app manifest yang ditautkan di halaman. (4 poin)
- Ikon tersedia di `public/icons` dan dirujuk di manifest. (3 poin)
- Katalog bisa di-install ke layar utama HP. (3 poin)

### US-14 Deskripsi produk dibuat AI

Sebagai admin, saya ingin membuat deskripsi produk secara otomatis dengan AI (Gemini API) dari nama dan kategori produk.

Bernilai 10 poin.

Kriteria selesai:

- Admin bisa membuat deskripsi otomatis dari nama dan kategori produk. (4 poin)
- Gemini API dipanggil dari server, kunci tidak ada di browser. (3 poin)
- Hasilnya mengisi kolom deskripsi sebelum produk disimpan. (3 poin)

Catatan: bonus US-08, US-09, dan US-10 hanya dihitung jika aksinya terlindungi login.

## Bonus lanjutan

### US-15 Urutkan produk

Sebagai pengunjung, saya ingin mengurutkan produk, supaya cepat menemukan yang murah atau yang terbaru.

Bernilai 5 poin.

Kriteria selesai:

- Ada pilihan urutan: termurah, termahal, terbaru. (3 poin)
- Urutan diterapkan saat mengambil data (query), bukan hanya di tampilan. (2 poin)

### US-16 Paginasi atau muat lebih banyak

Sebagai pengunjung, saya ingin daftar produk tidak terlalu panjang, supaya halaman cepat dibuka.

Bernilai 10 poin.

Kriteria selesai:

- Daftar produk dipecah per halaman atau ada tombol "muat lebih banyak". (4 poin)
- Pembatasan jumlah dilakukan di query database, bukan hanya disembunyikan. (3 poin)
- Navigasi antar halaman berfungsi dan jumlah halaman benar. (3 poin)

### US-17 Produk terkait di halaman detail

Sebagai pengunjung, saya ingin melihat produk lain yang mirip, supaya saya punya pilihan lain.

Bernilai 5 poin.

Kriteria selesai:

- Halaman detail menampilkan beberapa produk lain dari kategori yang sama. (3 poin)
- Produk yang sedang dibuka tidak ikut ditampilkan, dan data diambil dari database. (2 poin)

### US-18 Galeri beberapa foto produk

Sebagai pengunjung, saya ingin melihat beberapa foto satu produk, supaya saya tahu bentuk produknya dari berbagai sisi.

Bernilai 10 poin.

Kriteria selesai:

- Satu produk bisa punya lebih dari satu foto. (4 poin)
- Halaman detail menampilkan galeri dengan foto utama dan gambar kecil. (3 poin)
- Pengunjung bisa berganti foto, dan produk dengan satu foto tetap tampil normal. (3 poin)

### US-19 Status stok

Sebagai pengunjung, saya ingin tahu produk yang habis, supaya saya tidak memesan produk yang tidak ada.

Bernilai 5 poin.

Kriteria selesai:

- Produk punya status atau jumlah stok di database. (2 poin)
- Produk yang habis diberi penanda "Habis" dan tombol pesan WhatsApp dinonaktifkan atau disembunyikan. (3 poin)

### US-20 Harga coret dan badge

Sebagai pengunjung, saya ingin melihat harga diskon dan label produk, supaya saya tahu mana yang sedang promo atau baru.

Bernilai 5 poin.

Kriteria selesai:

- Produk bisa punya harga diskon, dan harga normal tampil dicoret di kartu dan halaman detail. (3 poin)
- Badge "Baru" atau "Terlaris" tampil berdasarkan data produk. (2 poin)

### US-21 Keranjang, pesan semua via WhatsApp

Sebagai pengunjung, saya ingin memesan beberapa produk sekaligus, supaya tidak perlu mengirim pesan satu per satu.

Bernilai 15 poin.

Kriteria selesai:

- Ada tombol "Tambah ke keranjang" di kartu atau halaman detail. (4 poin)
- Keranjang bisa mengubah jumlah dan menghapus item, dan total harga benar. (4 poin)
- Isi keranjang bertahan saat pindah halaman. (4 poin)
- Satu tombol mengirim seluruh isi keranjang dalam satu pesan WhatsApp ke nomor di `lib/toko.js`. (3 poin)

### US-22 Halaman Tentang dan kontak toko

Sebagai pengunjung, saya ingin tahu siapa pemilik toko dan cara menghubunginya, supaya saya percaya pada toko ini.

Bernilai 5 poin.

Kriteria selesai:

- Ada halaman (misalnya `/tentang`) berisi profil toko, alamat, jam buka, dan kontak. (3 poin)
- Halaman tertaut dari navigasi atau footer. (2 poin)

### US-23 Bagikan atau salin link produk

Sebagai pengunjung, saya ingin membagikan produk ke teman, supaya mereka bisa melihatnya.

Bernilai 5 poin.

Kriteria selesai:

- Halaman detail punya tombol bagikan atau salin link (Web Share API atau clipboard). (3 poin)
- Ada umpan balik setelah ditekan, misalnya "Link tersalin". (2 poin)

### US-24 Favorit tersimpan di browser

Sebagai pengunjung, saya ingin menandai produk favorit, supaya mudah menemukannya lagi.

Bernilai 10 poin.

Kriteria selesai:

- Ada tombol favorit di kartu atau halaman detail. (4 poin)
- Favorit tersimpan di browser dan bertahan setelah halaman dimuat ulang. (3 poin)
- Ada tampilan yang hanya berisi produk favorit. (3 poin)

### US-25 Mode gelap

Sebagai pengunjung, saya ingin memilih tampilan gelap, supaya nyaman dilihat di malam hari.

Bernilai 10 poin.

Kriteria selesai:

- Ada tombol untuk berpindah antara mode terang dan gelap. (4 poin)
- Pilihan diingat setelah halaman dimuat ulang. (3 poin)
- Semua teks tetap terbaca di kedua mode. (3 poin)

### US-26 Metadata SEO dan Open Graph

Sebagai pemilik toko, saya ingin link produk tampil rapi saat dibagikan, supaya menarik pembeli.

Bernilai 5 poin.

Kriteria selesai:

- Halaman detail memakai `generateMetadata` untuk judul dan deskripsi yang sesuai produk. (3 poin)
- Open Graph memuat nama dan foto produk. (2 poin)

### US-27 sitemap.xml dan robots.txt

Sebagai pemilik toko, saya ingin mesin pencari menemukan semua produk, supaya toko lebih mudah ditemukan.

Bernilai 5 poin.

Kriteria selesai:

- `sitemap.xml` dibuat dari database dan memuat halaman produk. (3 poin)
- `robots.txt` valid dan menunjuk ke sitemap. (2 poin)

### US-28 Halaman 404 dan loading kustom

Sebagai pengunjung, saya ingin pesan yang ramah saat halaman tidak ada atau sedang dimuat.

Bernilai 5 poin.

Kriteria selesai:

- Ada `not-found.jsx` kustom dengan tautan kembali ke beranda. (3 poin)
- Ada `loading.jsx` atau skeleton di halaman yang mengambil data. (2 poin)

### US-29 Upload foto ke Supabase Storage

Sebagai admin, saya ingin mengunggah foto produk dari komputer, supaya tidak perlu mengisi link foto manual.

Bernilai 15 poin.

Kriteria selesai:

- Form produk punya input file foto. (4 poin)
- File diunggah ke Supabase Storage dari server, kunci tidak ada di browser. (4 poin)
- URL foto tersimpan di produk dan foto tampil di katalog. (4 poin)
- Tipe file (gambar) dan ukuran maksimal divalidasi dengan pesan error yang jelas. (3 poin)

### US-30 Dashboard ringkasan admin

Sebagai admin, saya ingin melihat ringkasan toko, supaya saya tahu kondisi katalog sekilas.

Bernilai 10 poin.

Kriteria selesai:

- `/admin` menampilkan jumlah produk dari database. (4 poin)
- Menampilkan jumlah produk per kategori. (3 poin)
- Hanya bisa dibuka setelah login. (3 poin)

### US-31 Kelola kategori

Sebagai admin, saya ingin mengatur daftar kategori, supaya produk terkelompok rapi.

Bernilai 15 poin.

Kriteria selesai:

- Admin bisa menambah kategori. (4 poin)
- Admin bisa mengubah nama kategori. (3 poin)
- Admin bisa menghapus kategori, dan kategori yang masih dipakai produk ditolak atau ditangani dengan jelas. (4 poin)
- Daftar kategori di form produk berasal dari data ini, dan semua aksi memeriksa login di server. (4 poin)

### US-32 Aktif atau nonaktifkan produk

Sebagai admin, saya ingin menyembunyikan produk tanpa menghapusnya, supaya bisa ditampilkan lagi nanti.

Bernilai 10 poin.

Kriteria selesai:

- Ada tombol aktif atau nonaktif untuk produk di halaman admin. (4 poin)
- Produk nonaktif tidak muncul di katalog publik, dan halaman detailnya menampilkan "tidak ditemukan". (3 poin)
- Aksinya memeriksa login di server. (3 poin)

### US-33 Cari dan paginasi di list admin

Sebagai admin, saya ingin mencari produk di halaman admin, supaya cepat menemukan yang saya cari.

Bernilai 10 poin.

Kriteria selesai:

- Ada kolom cari di `/admin` yang menyaring lewat query database. (4 poin)
- Daftar produk dipaginasi. (3 poin)
- Kata kunci dan nomor halaman tersimpan di URL, jadi tetap ada setelah dimuat ulang. (3 poin)

### US-34 Validasi form admin di server

Sebagai admin, saya ingin form menolak data yang salah, supaya katalog tidak berisi data rusak.

Bernilai 10 poin.

Kriteria selesai:

- Server memvalidasi input: nama wajib, harga angka positif. (4 poin)
- Pesan error tampil per field di bawah input yang salah. (3 poin)
- Nilai yang sudah diisi tidak hilang saat terjadi error. (3 poin)

### US-35 Ekspor produk ke CSV

Sebagai admin, saya ingin mengunduh daftar produk, supaya bisa dibuka di spreadsheet.

Bernilai 10 poin.

Kriteria selesai:

- Ada tombol "Ekspor CSV" yang mengunduh semua produk. (4 poin)
- CSV dibuat di server, kolom dan header jelas, dan karakter khusus (koma, kutip) aman. (3 poin)
- Endpoint memeriksa login: tanpa login ditolak. (3 poin)

### US-36 Terakhir dilihat

Sebagai pengunjung, saya ingin melihat produk yang baru saya buka, supaya mudah kembali ke sana.

Bernilai 5 poin.

Kriteria selesai:

- Produk yang dibuka tersimpan di browser dengan batas jumlah tertentu. (3 poin)
- Bagian "Terakhir dilihat" tampil di beranda dan tidak muncul bila masih kosong. (2 poin)

### US-37 Bandingkan 2 produk

Sebagai pengunjung, saya ingin membandingkan dua produk, supaya saya bisa memilih yang cocok.

Bernilai 15 poin.

Kriteria selesai:

- Pengunjung bisa memilih dua produk untuk dibandingkan. (4 poin)
- Halaman perbandingan menampilkan kedua produk berdampingan: foto, kategori, harga, deskripsi. (4 poin)
- Memilih lebih dari dua ditolak dengan pesan atau menggantikan pilihan lama. (4 poin)
- Produk yang tidak ada ditangani dengan jelas, misalnya halaman "tidak ditemukan". (3 poin)

### US-38 Ulasan dan rating

Sebagai pengunjung, saya ingin memberi ulasan dan rating, supaya pembeli lain terbantu.

Bernilai 15 poin.

Kriteria selesai:

- Form ulasan (nama, rating 1 sampai 5, komentar) tampil di halaman detail. (4 poin)
- Ulasan disimpan ke database lewat Server Action dengan validasi di server. (4 poin)
- Daftar ulasan dan rata-rata rating tampil di halaman detail. (4 poin)
- Ada perlindungan spam dasar: batas panjang dan honeypot atau batas kiriman. (3 poin)

### US-39 Moderasi ulasan di admin

Sebagai admin, saya ingin mengelola ulasan, supaya ulasan yang tidak pantas tidak tampil.

Bernilai 10 poin.

Kriteria selesai:

- Ada halaman admin yang menampilkan semua ulasan. (4 poin)
- Admin bisa menyembunyikan atau menghapus ulasan, dengan login diperiksa di server. (3 poin)
- Ulasan yang disembunyikan tidak tampil di halaman publik dan tidak dihitung di rata-rata rating. (3 poin)

### US-40 Catat klik pesan WhatsApp

Sebagai pemilik toko, saya ingin tahu produk mana yang sering dipesan, supaya saya bisa menyiapkan stok.

Bernilai 10 poin.

Kriteria selesai:

- Klik tombol pesan WhatsApp tercatat di tabel database (produk dan waktu). (4 poin)
- Pencatatan lewat Server Action atau route handler dan tidak menghambat pembukaan WhatsApp. (3 poin)
- Tidak menyimpan data pribadi pengunjung. (3 poin)

### US-41 Produk terlaris di dashboard

Sebagai admin, saya ingin melihat produk yang paling sering dipesan, supaya saya tahu produk andalan.

Bernilai 10 poin.

Kriteria selesai:

- Dashboard menampilkan 5 produk dengan klik pesan terbanyak. (4 poin)
- Angkanya dihitung dari tabel pencatatan klik di database. (3 poin)
- Jika belum ada data, tampil pesan yang jelas. (3 poin)

### US-42 Banner promo di beranda

Sebagai admin, saya ingin memasang banner promo, supaya pengunjung tahu ada penawaran.

Bernilai 10 poin.

Kriteria selesai:

- Admin bisa membuat dan mengubah banner (judul, teks, gambar, tautan), dengan login diperiksa di server. (4 poin)
- Beranda menampilkan banner aktif dari database. (3 poin)
- Banner bisa dinonaktifkan, dan banner nonaktif tidak tampil. (3 poin)

### US-43 Pengaturan toko dari admin

Sebagai admin, saya ingin mengubah data toko tanpa mengedit kode, supaya mudah diperbarui.

Bernilai 15 poin.

Kriteria selesai:

- Halaman admin mengubah nama toko, nomor WhatsApp, jam buka, dan alamat, tersimpan di database. (4 poin)
- Tombol pesan WhatsApp memakai nomor dari pengaturan ini, dengan `lib/toko.js` sebagai cadangan. (4 poin)
- Halaman publik (header, footer, tentang) memakai nama dan jam buka dari database. (4 poin)
- Nomor WhatsApp divalidasi, dan aksinya memeriksa login di server. (3 poin)

### US-44 Kelola akun admin

Sebagai admin, saya ingin menambah admin lain, supaya pengelolaan toko bisa dibagi.

Bernilai 15 poin.

Kriteria selesai:

- Admin bisa menambah admin baru lewat Supabase Auth. (4 poin)
- Daftar admin tampil di halaman admin. (4 poin)
- Admin bisa menonaktifkan atau menghapus admin lain, tapi tidak akunnya sendiri. (4 poin)
- Semua aksi diperiksa di server. (3 poin)

### US-45 Log aktivitas admin

Sebagai admin, saya ingin melihat riwayat perubahan, supaya tahu siapa mengubah apa.

Bernilai 10 poin.

Kriteria selesai:

- Tambah, ubah, dan hapus produk mencatat log: siapa, aksi, dan kapan. (4 poin)
- Halaman admin menampilkan 50 log terakhir. (3 poin)
- Tanpa login log tidak bisa diakses. (3 poin)

### US-46 Impor produk dari CSV

Sebagai admin, saya ingin memasukkan banyak produk sekaligus, supaya tidak mengetik satu per satu.

Bernilai 15 poin.

Kriteria selesai:

- Ada form unggah CSV di admin, dengan login diperiksa di server. (4 poin)
- Setiap baris divalidasi (kolom wajib, harga angka), dan baris yang salah dilaporkan beserta nomor barisnya. (4 poin)
- Baris yang valid disimpan sekaligus ke database. (4 poin)
- Ringkasan hasil (berhasil dan gagal) ditampilkan. (3 poin)

### US-47 Atur urutan tampil produk

Sebagai admin, saya ingin mengatur urutan produk, supaya produk unggulan tampil lebih dulu.

Bernilai 10 poin.

Kriteria selesai:

- Produk punya kolom urutan di database. (4 poin)
- Admin bisa menaikkan dan menurunkan urutan produk. (3 poin)
- Katalog publik mengikuti urutan tersebut. (3 poin)

### US-48 Varian harga per ukuran

Sebagai pengunjung, saya ingin memilih ukuran dengan harga yang sesuai, supaya saya memesan yang tepat.

Bernilai 15 poin.

Kriteria selesai:

- Ada tabel varian di database (produk, nama varian, harga). (4 poin)
- Admin bisa mengelola varian per produk. (4 poin)
- Halaman detail menampilkan pilihan varian, dan harga berubah sesuai pilihan. (4 poin)
- Pesan WhatsApp memuat varian dan harga yang dipilih. (3 poin)

### US-49 Halaman per kategori

Sebagai pengunjung, saya ingin membuka halaman khusus satu kategori, supaya bisa dibagikan dan mudah ditemukan.

Bernilai 10 poin.

Kriteria selesai:

- Halaman `/kategori/[slug]` menampilkan produk kategori itu dari database. (4 poin)
- Kategori yang tidak ada menampilkan "tidak ditemukan". (3 poin)
- Nama kategori di kartu atau halaman detail tertaut ke halaman tersebut. (3 poin)

### US-50 Asisten AI tanya jawab produk

Sebagai pengunjung, saya ingin bertanya tentang produk, supaya saya mendapat jawaban tanpa menunggu pemilik toko.

Bernilai 15 poin.

Kriteria selesai:

- Ada kotak tanya di halaman detail produk. (4 poin)
- Jawaban dari LLM dipanggil dari server, kunci tidak ada di browser, dan jawabannya hanya berdasar data produk. (4 poin)
- Panjang pertanyaan dibatasi, dan error atau timeout ditangani dengan pesan yang jelas. (4 poin)
- Ada pembatasan kiriman dasar agar tidak disalahgunakan. (3 poin)
