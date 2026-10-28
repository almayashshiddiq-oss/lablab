# Lab4Web - Praktikum 4: CSS Layout

Modul Praktikum Pemrograman Web - Universitas Pelita Bangsa

Dosen: Sufajar Butsianto (sufajar@pelitabangsa.ac.id)

## Tujuan Praktikum

1. Memahami struktur dasar pembuatan Layout
2. Memahami konsep Box Element
3. Memahami CSS Floating
4. Memahami HTML5 Semantics Element
5. Membuat Layout Web Sederhana

## Daftar Isi

- [Materi](#materi)
- [Struktur File](#struktur-file)
- [Langkah Praktikum](#langkah-praktikum)
- [Hasil](#hasil)
- [Tugas](#tugas)

## Materi

### Web Layout
Web layout merupakan kerangka yang mengatur penempatan tata letak sebuah elemen pada halaman web. Halaman web sering kali dibagi menjadi header, menu, konten, dan footer.

### Box Element
Setiap elemen HTML dianggap sebagai sebuah Box atau kotak. Konsep box element terdiri dari:
- **Margin** - jarak antar elemen
- **Border** - garis tepi elemen
- **Padding** - jarak antara content dan border
- **Content** - isi dari elemen

### CSS Float Property
CSS Float memungkinkan elemen HTML dibuat seolah-olah mengambang di antara elemen lainnya. Property yang digunakan:
- `float` - mengatur elemen mengambang (left, right, none)
- `clear` - mengatur elemen setelah float element (left, right, both)

### HTML5 Semantic Elements
| Tag | Fungsi |
|-----|--------|
| `<header>` | Mendefinisikan header untuk dokumen atau bagian |
| `<nav>` | Mendefinisikan satu set link navigasi |
| `<section>` | Mendefinisikan bagian dalam dokumen |
| `<article>` | Mendefinisikan konten artikel |
| `<aside>` | Mendefinisikan konten selain dari konten (sidebar) |
| `<footer>` | Mendefinisikan footer untuk dokumen atau bagian |

## Struktur File

```
Lab4Web/
├── lab4_box.html
├── lab4_layout/
│   ├── home.html
│   ├── artikel.html
│   ├── about.html
│   ├── kontak.html
│   └── style.css
└── README.md
```

## Langkah Praktikum

### Latihan 1: Box Element (`lab4_box.html`)

1. Buat file baru dengan nama `lab4_box.html`
2. Buat struktur HTML dasar
3. Tambahkan elemen `div` dengan class `div1`, `div2`, dan `div3`
4. Tambahkan CSS `float: left` pada semua `div`
5. Berikan background warna berbeda untuk setiap div
6. Tambahkan `div4` dengan `clear: left` untuk mengatur clearfix
7. Buka file di browser untuk melihat hasilnya

**Hasil:** Elemen-elemen div akan berjajar secara horizontal (float) dan div4 akan muncul di baris baru (clear).

### Latihan 2: Layout Sederhana (`lab4_layout/`)

1. Buat folder baru dengan nama `lab4_layout`
2. Buat file `home.html` dan `style.css`
3. Buat kerangka layout menggunakan semantic elements:
   ```html
   <div id="container">
     <header>
     <nav>
     <section id="hero">
     <section id="wrapper">
       <section id="main">
       <aside id="sidebar">
     </section>
     <footer>
   </div>
   ```
4. Tambahkan CSS secara bertahap:
   - Reset CSS dan import Google Font
   - Style container (width 980px, margin auto)
   - Style header
   - Style navigasi (background biru)
   - Style hero panel
   - Style main content dan sidebar (float left)
   - Style sidebar widget
   - Style footer (clear both)
   - Style box content (3 kolom)
   - Style artikel entry

**Hasil:** Layout web sederhana dengan header, navigasi, hero panel, konten utama 3 kolom, sidebar widget, artikel, dan footer.

## Hasil

### Tampilan Home
- Header dengan judul "Layout Sederhana"
- Navigasi dengan menu Home, Artikel, About, Kontak
- Hero panel dengan tombol "Learn more"
- 3 box content dengan gambar bulat dan tombol
- 2 artikel dengan gambar (kiri dan kanan)
- Sidebar dengan widget header dan widget text
- Footer

### Halaman Lainnya
- **Artikel** - daftar artikel dengan gambar
- **About** - profil, deskripsi, portfolio, dan skill bar
- **Kontak** - form kontak (nama, email, subjek, pesan)

## Tugas

1. **Layout About** - halaman single layout yang berisi deskripsi, portfolio, dll
2. **Layout Kontak** - halaman yang berisi form isian: nama, email, message, dll

## Cara Menjalankan

1. Clone repository ini:
   ```bash
   git clone <url-repository>
   ```
2. Buka folder `Lab4Web`
3. Buka `lab4_box.html` di browser untuk melihat hasil latihan 1
4. Buka `lab4_layout/home.html` di browser untuk melihat hasil latihan 2

## Validasi

Validasi dokumen HTML menggunakan: [http://validator.w3.org](http://validator.w3.org)

## Referensi

- Modul Praktikum Pemrograman Web - Sufajar Butsianto
- Universitas Pelita Bangsa, Bekasi
