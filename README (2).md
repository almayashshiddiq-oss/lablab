# Lab2Web - Praktikum Layout Sederhana (HTML & CSS)

**NAMA : ASH SHIDDIQ AL MAY**

**KELAS : I253B**

**NIM : 312510072**

**Program Studi : Teknik Informatika - Universitas Pelita Bangsa**

---

## Deskripsi Praktikum

Praktikum ini membuat website multi-halaman dengan layout sederhana memakai **HTML5** dan **CSS eksternal**. Website terdiri dari empat halaman (`home.html`, `artikel.html`, `about.html`, `kontak.html`) yang semuanya memakai satu file `style.css`. Pada bagian pertama, file CSS dibangun **bertahap** dan setiap penambahan diamati langsung lewat screenshot di browser.

### Struktur Folder

```
Lab2Web/
├── home.html
├── artikel.html
├── about.html
├── kontak.html
├── style.css
├── PP_pemerograman.png
├── images/              <- screenshot hasil praktikum
└── README.md
```

---

# A. Membangun Halaman Home Secara Bertahap

## 1. Membuat dokumen HTML tanpa CSS

File `home.html` dibuat dengan struktur semantik: `header`, `nav`, `section#hero`, `section#wrapper` (berisi `section#main` dan `aside#sidebar`), serta `footer`. File `style.css` belum dihubungkan, sehingga browser menampilkan elemen dengan gaya bawaan: teks tersusun dari atas ke bawah, link bergaris bawah berwarna biru, dan gambar berukuran asli.

```html
<link rel="stylesheet" href="style.css">   <!-- belum ditambahkan -->
```

![image](images/01-html-tanpa-css.png)

## 2. Menambahkan Reset CSS, font, dan container

File `style.css` dibuat lalu dihubungkan ke HTML lewat tag `<link>`. Isi tahap ini:

- `@import` Google Font **Open Sans**.
- **Reset CSS**: `* { margin: 0; padding: 0; }` menghapus margin dan padding bawaan browser, sehingga semua elemen menjadi rapat.
- `body` diberi `font-family`, ukuran font `100%`, dan warna teks `#5a5a5a`.
- `#container` selebar `980px`, rata tengah (`margin: 0 auto`), dan diberi bayangan (`box-shadow`).

```css
* { margin: 0; padding: 0; }

#container {
  width: 980px;
  margin: 0 auto;
  box-shadow: 0 0 1em #cccccc;
}
```

Hasil: halaman terpusat di tengah dengan bayangan di tepinya, tetapi isinya masih rapat karena semua margin dihapus.

![image](images/02-reset-css-container.png)

## 3. Menambahkan style header dan navigasi

- `header` diberi `padding: 20px`, judul `h1` berwarna abu-abu `#b5b5b5`.
- `nav` diberi latar biru `#1f5faa`.
- Link `nav a` dijadikan `inline-block` dengan padding `15px 30px`, teks putih dan tebal.
- `nav a.active` dan `nav a:hover` berlatar `#2b83ea` untuk menandai menu aktif dan efek hover.

```css
nav { display: block; background-color: #1f5faa; }
nav a { padding: 15px 30px; display: inline-block; color: #fff; text-decoration: none; font-weight: bold; }
nav a.active, nav a:hover { background-color: #2b83ea; }
```

![image](images/03-header-navigasi.png)

## 4. Menambahkan Hero Panel

Bagian `#hero` diberi latar abu-abu `#e4e4e5`, padding `50px 20px`, dan margin bawah `20px`. Judul `h1` berukuran `35px`, paragraf berukuran `18px` dengan `line-height: 25px`. Tombol *Learn more* masih tampil sebagai link biasa karena class `.btn` belum dibuat.

![image](images/04-hero-panel.png)

## 5. Membuat layout dua kolom: main content, sidebar, dan widget

Layout dua kolom dibuat dengan properti **`float: left`**:

- `#main` selebar `640px` dengan padding `20px`.
- `#sidebar` selebar `260px` dengan padding `20px`.
- Total lebar `640 + 260 + (20 x 4) = 980px`, sama dengan lebar container.
- `.widget-box` diberi border tipis. Judul widget (`.title`) berlatar biru `#428bca` dengan teks putih, daftar link tanpa bullet (`list-style-type: none`), dan efek hover abu-abu.

```css
#main    { float: left; width: 640px; padding: 20px; }
#sidebar { float: left; width: 260px; padding: 20px; }
```

Pada tahap ini sidebar sudah berada di kanan konten. Perhatikan bahwa footer belum diberi style, sehingga bagian bawah halaman terlihat belum rapi karena elemen yang di-float tidak ikut menghitung tinggi container.

![image](images/05-main-sidebar-widget.png)

## 6. Membuat kotak (box), row, dan garis pemisah (divider)

- `.box` selebar `33.333333%` dengan `float: left`, `box-sizing: border-box`, dan teks rata tengah, sehingga tiga kotak tampil sejajar.
- `.image-circle` memakai `border-radius: 50%` untuk membuat gambar menjadi lingkaran.
- `.row` memakai margin negatif `0 -10px` untuk mengimbangi padding kotak.
- `.row:after` dan `.entry:after` (clearfix) memakai `clear: both` agar container tidak "runtuh" akibat elemen yang di-float.
- `.divider` adalah garis pemisah tipis dengan margin `40px 0`.

```css
.box { float: left; width: 33.333333%; box-sizing: border-box; padding: 0 10px; text-align: center; }
.image-circle { border-radius: 50%; }
.row:after, .entry:after { clear: both; }
```

![image](images/06-box-row-divider.png)

## 7. Menambahkan style artikel (entry)

`.entry` dipakai untuk artikel dengan gambar dan teks berdampingan. Gambar di dalam `.entry` diberi `float: left` dengan sudut membulat dan margin kanan `15px`. Class `.right-img` membalik posisi gambar ke kanan (`float: right`), sehingga artikel pertama bergambar di kiri dan artikel kedua bergambar di kanan.

```css
.entry img { float: left; border-radius: 5px; margin-right: 15px; }
.entry .right-img { float: right; }
```

![image](images/07-entry.png)

## 8. Menambahkan footer dan tombol (button)

- `footer` diberi `clear: both` agar tampil di bawah kolom yang di-float, dengan latar gelap `#1d1d1d` dan teks terang `#eee`.
- `.btn` membuat link tampil seperti tombol (latar biru, teks putih, sudut membulat). `.btn-large` memperbesar tombol, sedangkan `.btn-default` membuat tombol abu-abu untuk *View detail*.

```css
footer { clear: both; background-color: #1d1d1d; padding: 20px; color: #eee; }
.btn   { display: inline-block; padding: 10px 20px; background-color: #428bca; color: #fff; border-radius: 3px; }
```

Hasil akhir halaman **Home** sudah lengkap: header, navigasi, hero, tiga kotak, dua artikel, sidebar, dan footer.

![image](images/08-footer-button.png)

---

# B. Halaman Lainnya

Tiga halaman berikut memakai `style.css` yang sama dan mengganti `#main` menjadi satu kolom penuh dengan style inline `float:none; width:auto; padding:30px;`. Menu yang sedang dibuka ditandai dengan `class="active"`.

## 9. Halaman Artikel (`artikel.html`)

Berisi tiga artikel: **Memahami CSS Box Model**, **CSS Float untuk Layout**, dan **HTML5 Semantic Elements**. Tiap artikel memakai `<article class="entry">` dan dipisahkan `<hr class="divider">`. Posisi gambar bergantian kiri dan kanan memakai class `.right-img`.

![image](images/09-halaman-artikel.png)

## 10. Halaman About (`about.html`)

CSS tambahan untuk halaman ini ditulis di tag `<style>` pada `<head>`. Isi halaman:

- **Profil**: foto bulat `150x150px` (`border-radius: 50%`), nama, dan asal kampus.
- **Deskripsi** singkat tentang diri.
- **Portfolio**: tiga kartu proyek memakai **Flexbox** (`display: flex; flex-wrap: wrap; gap: 20px`).
- **Keahlian**: progress bar HTML (90%), CSS (85%), dan JavaScript (70%) yang lebarnya diatur lewat `style="width:...%"`.

```css
.portfolio-grid { display: flex; flex-wrap: wrap; gap: 20px; }
.portfolio-item { flex: 1 1 280px; }
```

![image](images/10-halaman-about.png)

## 11. Halaman Kontak (`kontak.html`)

Berisi kotak informasi kontak (email dan alamat) serta **form** dengan field Nama Lengkap, Email, Subjek, dan Pesan.

- Field nama, email, dan pesan memakai atribut `required`.
- Field email memakai `type="email"` sehingga browser memvalidasi format email.
- Efek `:focus` mengubah warna border input menjadi biru `#428bca`.

![image](images/11-halaman-kontak.png)

Tampilan form setelah diisi (kolom Pesan sedang aktif, border berwarna biru):

![image](images/13-kontak-form-terisi.png)

## 12. Menguji navigasi antar halaman

Menu **Home -> Artikel -> About -> Kontak** diklik satu per satu untuk memastikan semua link berfungsi, menu aktif berpindah sesuai halaman, dan efek hover berjalan. Contoh efek hover pada menu *About*:

![image](images/12-navigasi-hover.png)

---

# C. Commit ke Repository

## 13. Commit dan push hasil praktikum

Jalankan perintah berikut di terminal pada folder proyek:

```bash
git init
git add .
git commit -m "Menambahkan website layout sederhana (home, artikel, about, kontak)"
git branch -M main
git remote add origin https://github.com/<username>/Lab2Web.git
git push -u origin main
```

> **Tempel screenshot terminal / halaman GitHub kamu di sini**, simpan sebagai `images/14-commit.png`, lalu aktifkan baris di bawah ini.

<!-- ![image](images/14-commit.png) -->

---

## Kesimpulan

Dari praktikum ini dipelajari cara membangun layout website beberapa halaman memakai HTML5 semantic elements dan CSS eksternal, termasuk `float`, clearfix, `flexbox`, dan pseudo-class (`:hover`, `:focus`), serta cara menyimpan hasilnya ke repository dengan Git.
