# Praktikum HTML Lanjutan

Proyek praktikum web dasar yang mempelajari **tabel, form, semantic HTML, multimedia, dan validasi form** menggunakan HTML murni (tanpa CSS/JavaScript).

---

## 1. Struktur Proyek

```
praktek/
├── index.html          # Beranda: tabel data mahasiswa, tabel nilai, dan berbagai elemen form
├── halaman 2.html      # Portal Mahasiswa: semantic HTML + audio + video
├── halaman 3.html      # Biodata mahasiswa: tabel biodata + form biodata
├── media/
│   ├── musik.mp3       # File audio untuk elemen <audio>
│   └── video.mp4       # File video untuk elemen <video>
└── README.md           # Dokumentasi praktikum (file ini)
```

| File | Isi Utama |
|------|-----------|
| `index.html` | Navigasi, tabel dasar (`<table>`, `<tr>`, `<th>`, `<td>`), tabel lengkap (`<caption>`, `<thead>`, `<tbody>`, `<tfoot>`, `colspan`), form registrasi, radio button, checkbox, select, textarea, dan form dengan validasi |
| `halaman 2.html` | Semantic HTML (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`), `<audio>`, `<video>` |
| `halaman 3.html` | Halaman biodata: tabel data mahasiswa dan form biodata (input, email, select, textarea) |
| `media/` | Folder aset multimedia |

---

## 2. Cara Menjalankan

1. Ekstrak/salin seluruh folder proyek ke komputer.
2. Pastikan folder `media/` berisi `musik.mp3` dan `video.mp4`.
3. Buka `index.html` dengan browser (Chrome, Firefox, Edge), atau gunakan ekstensi **Live Server** di VS Code (klik kanan `index.html` → *Open with Live Server*).
4. Gunakan menu navigasi di bagian atas untuk berpindah antarhalaman.

---

## 3. Langkah-Langkah Praktikum

### Langkah 1 — Membuat Struktur Folder
Buat folder proyek, lalu buat file `index.html`, `halaman 2.html`, `halaman 3.html`, dan folder `media/` untuk menyimpan `musik.mp3` dan `video.mp4`.

### Langkah 2 — Membuat Navigasi Antarhalaman
Gunakan elemen `<nav>` berisi tautan `<a href="...">` agar pengguna dapat berpindah halaman.

```html
<nav>
    <a href="index.html">Beranda</a>
    <a href="halaman 3.html">biodata</a>
    <a href="halaman 2.html">form</a>
</nav>
```

### Langkah 3 — Membuat Tabel Data Mahasiswa (`index.html`)
Buat tabel dengan `<table border="1">`, baris `<tr>`, judul kolom `<th>` (NIM, Nama, Program Studi), dan isi sel `<td>`.

### Langkah 4 — Membuat Tabel Nilai dengan Struktur Lengkap
Tambahkan `<caption>` sebagai judul tabel, lalu kelompokkan isi tabel dengan `<thead>`, `<tbody>`, dan `<tfoot>`. Pada baris rata-rata gunakan `colspan="2"` agar sel menggabung dua kolom.

```html
<tfoot>
    <tr>
        <td colspan="2">Rata-rata</td>
        <td>87.5</td>
    </tr>
</tfoot>
```

### Langkah 5 — Membuat Form Registrasi Mahasiswa
Bungkus semua input dalam `<form>`. Gunakan `<label for="...">` yang terhubung dengan `id` input. Jenis input yang dipakai:
- `type="text"` — nama lengkap
- `type="email"` — email
- `type="password"` — kata sandi
- `type="date"` — tanggal lahir
- Tombol `type="submit"` (Daftar) dan `type="reset"` (Reset)

### Langkah 6 — Membuat Radio Button dan Checkbox
- **Radio button** (`type="radio"`) untuk jenis kelamin. Semua radio dalam satu grup memakai `name` yang sama (`jk`).
- **Checkbox** (`type="checkbox"`) untuk keahlian (HTML, CSS, JavaScript) yang bisa dipilih lebih dari satu.

### Langkah 7 — Membuat Dropdown dan Textarea
- `<select>` dengan `<option>` untuk memilih program studi.
- `<textarea rows="5" cols="40">` untuk mengisi alamat yang panjang.

### Langkah 8 — Menambahkan Validasi Form
Gunakan atribut validasi bawaan HTML5 tanpa JavaScript:

```html
<input type="text"   name="nama"  required minlength="3">
<input type="email"  name="email" required>
<input type="number" name="umur"  required min="17" max="60">
```

### Langkah 9 — Membuat Halaman Semantic HTML (`halaman 2.html`)
Susun halaman "Portal Mahasiswa" dengan elemen semantik: `<header>`, `<nav>`, `<main>` berisi `<section>` → `<article>` dan `<aside>`, serta `<footer>`.

### Langkah 10 — Menambahkan Audio dan Video
Tambahkan multimedia dengan atribut `controls` agar tombol putar/jeda tampil:

```html
<audio controls>
    <source src="media/musik.mp3" type="audio/mpeg">
    browser tidak mendukung audio
</audio>

<video controls>
    <source src="media/video.mp4" type="video/mp4">
    browser tidak mendukung video
</video>
```

### Langkah 11 — Membuat Halaman Biodata (`halaman 3.html`)
Buat tabel biodata (NIM, Nama, Program Studi) dan form biodata (nama, email, program studi, alamat) yang dibagi menjadi dua `<section>` di dalam `<main>`.

### Langkah 12 — Menguji di Browser
Buka setiap halaman, coba klik menu navigasi, isi form, kosongkan kolom `required` untuk melihat pesan validasi, lalu putar audio dan video.

---

## 4. Jawaban Pertanyaan

### 1. Apa fungsi `<table>`, `<tr>`, `<th>`, dan `<td>`?
| Elemen | Fungsi |
|--------|--------|
| `<table>` | Wadah utama untuk membuat tabel |
| `<tr>` (*table row*) | Membuat satu baris dalam tabel |
| `<th>` (*table header*) | Sel judul/kepala kolom atau baris; teks otomatis **tebal dan rata tengah** |
| `<td>` (*table data*) | Sel yang berisi data biasa |

### 2. Apa perbedaan `<th>` dan `<td>`?
`<th>` adalah sel **judul** (header) yang secara default tampil tebal dan rata tengah, serta bermakna semantik sebagai kepala kolom/baris (membantu *screen reader*). `<td>` adalah sel **data** biasa dengan teks rata kiri dan tidak tebal.

### 3. Apa fungsi `colspan` pada tabel?
`colspan` adalah atribut untuk **menggabungkan beberapa kolom** menjadi satu sel. Contoh `colspan="2"` membuat sel memanjang selama dua kolom, seperti pada baris "Rata-rata" di tabel nilai. (Untuk menggabungkan baris digunakan `rowspan`.)

### 4. Apa fungsi `<form>` dalam HTML?
`<form>` adalah wadah untuk **mengumpulkan input pengguna** dan mengirimkannya ke server. Atribut penting: `action` (tujuan pengiriman data) dan `method` (`GET` atau `POST`). Elemen di dalamnya seperti `<input>`, `<select>`, `<textarea>`, dan `<button>` dikirim bersama saat tombol *submit* ditekan.

### 5. Apa perbedaan radio button dan checkbox?
| Aspek | Radio Button | Checkbox |
|-------|--------------|----------|
| Jumlah pilihan | **Hanya satu** dalam satu grup | **Boleh lebih dari satu** |
| Pengelompokan | `name` sama membentuk satu grup | Biasanya `name` sama, tetapi tiap kotak berdiri sendiri |
| Bisa dibatalkan | Tidak (tetap terpilih satu) | Ya, klik lagi untuk membatalkan |
| Contoh | Jenis kelamin | Keahlian (HTML, CSS, JavaScript) |

### 6. Mengapa `<label>` sebaiknya terhubung dengan `id` input melalui atribut `for`?
- **Aksesibilitas**: *screen reader* dapat membacakan label yang tepat untuk setiap input.
- **Kemudahan klik**: mengklik teks label otomatis memfokuskan/memilih inputnya (sangat berguna untuk radio dan checkbox yang kecil).
- **Kejelasan struktur**: hubungan antara teks dan input menjadi eksplisit.

Contoh: `<label for="nama">Nama</label>` terhubung dengan `<input id="nama">`.

### 7. Apa perbedaan `<textarea>` dengan input type text?
| Aspek | `<textarea>` | `<input type="text">` |
|-------|--------------|-----------------------|
| Jumlah baris | **Banyak baris** | **Satu baris** |
| Penggunaan | Teks panjang (alamat, komentar) | Teks pendek (nama, username) |
| Ukuran | Diatur dengan `rows` dan `cols` | Diatur dengan `size`/CSS |
| Penulisan tag | Punya tag penutup `</textarea>` | Tag tunggal (*self-closing*) |
| Nilai awal | Ditulis di antara tag | Memakai atribut `value` |

### 8. Apa fungsi semantic HTML seperti `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, dan `<footer>`?
Semantic HTML memberi **makna pada struktur halaman** sehingga lebih mudah dibaca manusia, mesin pencari (SEO), dan *screen reader*.

| Elemen | Fungsi |
|--------|--------|
| `<header>` | Bagian kepala halaman/bagian: judul, logo |
| `<nav>` | Kumpulan tautan navigasi/menu |
| `<main>` | Konten utama halaman (hanya satu per halaman) |
| `<section>` | Pengelompokan konten yang bertema sama |
| `<article>` | Konten mandiri yang bisa berdiri sendiri (berita, postingan blog) |
| `<aside>` | Informasi tambahan/sampingan (sidebar, iklan) |
| `<footer>` | Bagian kaki halaman: hak cipta, kontak |

### 9. Apa fungsi `required`, `min`, `max`, dan `minlength`?
Semuanya adalah atribut **validasi form** bawaan HTML5:

| Atribut | Fungsi |
|---------|--------|
| `required` | Kolom **wajib diisi**; form tidak bisa dikirim jika kosong |
| `min` | **Nilai minimum** yang diperbolehkan (untuk `number`, `date`, dll.) |
| `max` | **Nilai maksimum** yang diperbolehkan |
| `minlength` | **Jumlah karakter minimum** pada input teks |

Contoh pada proyek ini: umur wajib diisi dengan `min="17"` dan `max="60"`, sedangkan nama wajib minimal 3 karakter (`minlength="3"`).

### 10. Apa perbedaan elemen `<audio>` dan `<video>`?
| Aspek | `<audio>` | `<video>` |
|-------|-----------|-----------|
| Jenis media | Suara/musik | Gambar bergerak + suara |
| Tampilan | Hanya *player* kontrol | Ada area layar tampilan video |
| Atribut ukuran | Tidak ada | Ada `width`, `height`, `poster` |
| Format umum | MP3, WAV, OGG | MP4, WebM, OGG |
| Kesamaan | Sama-sama memakai `controls`, `autoplay`, `loop`, dan `<source>` | |

---

## 5. Catatan dan Saran Perbaikan

Beberapa hal yang ditemukan pada kode praktikum dan sebaiknya diperbaiki:

1. **Path media** di `halaman 2.html` memakai `/media/musik.mp3` (diawali `/`) sehingga audio/video bisa gagal dimuat saat file dibuka langsung. Gunakan path relatif: `media/musik.mp3` dan `media/video.mp4`.
2. **Konten di luar `</html>`**: pada `index.html` dan `halaman 2.html`, sebagian elemen (tabel, form, audio, video) berada setelah tag `</html>`. Sebaiknya semua dipindahkan ke dalam `<body>`.
3. **`id` ganda** di `index.html`: `nama`, `email`, dan `prodi` dipakai lebih dari sekali. `id` harus unik agar `<label for>` bekerja benar.
4. **`for` tidak cocok** pada checkbox JavaScript: `<input id="js">` tetapi `<label for="JavaScript">`. Samakan keduanya.
5. **Tag belum tertutup**: `<table>` di `halaman 3.html` belum ditutup dengan `</table>`, dan `<footer>` belum ditutup dengan `</footer>`.
6. **Nama tautan navigasi** berbeda antarhalaman (misalnya `halaman 2.html` disebut "form" di satu halaman dan "Kontak" di halaman lain). Sebaiknya diseragamkan.
7. Gunakan nama file tanpa spasi (misalnya `halaman2.html`) agar URL lebih rapi.

---

## 6. Ringkasan Konsep yang Dipelajari

- Tabel: `table`, `tr`, `th`, `td`, `caption`, `thead`, `tbody`, `tfoot`, `colspan`
- Form: `form`, `label`, `input` (text, email, password, date, number, radio, checkbox), `select`, `textarea`, `button`
- Validasi: `required`, `minlength`, `min`, `max`
- Semantic HTML: `header`, `nav`, `main`, `section`, `article`, `aside`, `footer`
- Multimedia: `audio`, `video`, `source`, `controls`
