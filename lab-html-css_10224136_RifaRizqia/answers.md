# Jawaban Praktikum: Rifa Rizqia (10224136)

## Bagian 1: Pemanasan
1. Pada aturan nav a.active:hover { color: red; }
nav a.active:hover adalah selector nya, { color: red; } adalah deklarasi nya, color adalah property nya, red adalah value nya, dan .active serta :hover adalah pseudo-class.
2. <p>, <li>, <h2> memiliki sifat block sedangkan <span>, <a>, <strong> memiliki sifa Inline
3. Paragraf yang akan menjadi hijau adalah A dan B. karena Selector .box p (descendant selector) memilih semua elemen <p> yang berada di dalam elemen ber-class box. Maka paragraf A dan B berada di dalam <div class="box">. C bukan di dalam elemen ber-class box, dan D berada di luar.
4. Warnanya akan red, karena tingkat spesifisitas selector #title  , yaitu ID selector = 100 lebih tinggi daripada .heading yang class selector = 10 dan h1 yang type/Tag selector = 1.
5. Adanya penutupan tag (improper nesting), karena tag <strong> dibuka di dalam <p>, tetapi ditutup di luar </p>.

## Bagian 3: Prediksi Selector Golf
P1. (a) "Weekly hack nights." akan berwarna green, karena teks nya berada di <p> dimana <p> tersebut berada di dalam <section id="tech">. Selector section p lebih spesifik daripada p saja. (b) "Bring your own laptop." akan berwarna orange, karena teks nya berada di dalam <p class="note">. Class selector .note memiliki specificity paling tinggi dibanding dengan section p dan p. (c) "© 2026 Student Affairs" akan berwarna blue, karena teks nya berada di <p> di dalam <footer>. Hanya terkena aturan p { color: blue; }.
P2. 
1. #tech p : ID = 1, class = 0, element = 1 dengan score 101.
2. .club p : ID = 0, class = 1, element = 1 dengan score 011.
3. main section p : ID = 0, class = 0, element = 3 dengan score 003.
4. p : ID = 0, class = 0, element = 1 dengan score 001.

Setelah diuji (hasil sebenarnya):

## Bagian 4: Box model
Q1 (content-box): lebar total visual width adalah 334px. perhitungannya yaitu: lebar total= width + padding-left + padding-right + border-left + border-right maka lebar total= 300px + 16px + 16px + 1px + 1px= 334px.
Q2 (border-box): yang akan berubah yaitu padding dan border karena dihitung kedalam nilai width, sehingga lebar area konten secara keseluruhan mengecil menjadi 266px.

Pengecekan DevTools:

## Bagian 5: Tabel debug
## Bagian 5: Tabel debug
| # | Baris | Bug | Perbaikan | Cara menemukannya |
|---|-------|-----|-----------|-------------------|
| 1 | 8 | Properti CSS salah tulis `colour: #333;` | Ubah menjadi `color: #333;` | DevTools menunjukkan properti yang tidak valid |
| 2 | 11 | Titik koma `;` hilang setelah `#dbe7f3` | Tambahkan titik koma: `background: #dbe7f3;` | Membaca kode / Validator CSS |
| 3 | 14 | Class CSS `.Card` menggunakan huruf kapital | Ubah selector menjadi `.card` | Membaca kode (style tidak terapan ke elemen `.card`) |
| 4 | 18 | Mismatch ID antara `#news-list` di CSS dan `id="newsList"` di HTML | Ubah CSS menjadi `#newsList` | Membaca kode / DevTools tidak menerapkan font-size |
| 5 | 19 | Nilai ukuran font memiliki spasi `18 px` | Hapus spasi menjadi `18px` | DevTools menunjukkan nilai properti yang dicoret |
| 6 | 22 | Nilai `text-align: centre;` menggunakan ejaan Britania | Ubah menjadi `text-align: center;` | DevTools menunjukkan nilai tidak valid |
| 7 | 27 | Tag `<h1>` ditutup salah dengan `</h2>` | Ubah tag penutup menjadi `</h1>` | W3C HTML Validator / Membaca kode |
| 8 | 30 | Tanda kutip penutup hilang pada `href="about.html>` | Tambahkan tanda kutip: `href="about.html"` | W3C HTML Validator / Membaca kode |
| 9 | 31 | Tag `<img>` tidak memiliki atribut `alt` | Tambahkan atribut `alt="Gambar Berita"` | W3C HTML Validator |

## Bagian 6: Tabel Code Review
## Bagian 6: Tabel Code Review
| # | Baris | Masalah | Mengapa penting | Perbaikan saya |
|---|-------|---------|-----------------|----------------|
| 1 | 1-2 | Dokumen HTML tidak memiliki `<!DOCTYPE html>` dan atribut `lang` pada tag `<html>` | Browser masuk ke Quirks Mode dan mesin pencari/pembaca layar (screen reader) tidak mengenali bahasa dokumen. | Tambahkan `<!DOCTYPE html>` di baris pertama dan `<html lang="id">`. |
| 2 | 3 | Tag `<head>` kekurangan elemen `<meta charset="UTF-8">` dan `<meta name="viewport">` | Karakter khusus berpotensi rusak/corrupt dan tampilan halaman tidak responsif di layar ponsel. | Tambahkan `<meta charset="UTF-8">` dan `<meta name="viewport" content="width=device-width, initial-scale=1.0">`. |
| 3 | 5, 12, 17, 27 | Penggunaan `<div>` berlebihan tanpa tag HTML semantik (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`) | Menurunkan tingkat aksesibilitas bagi penyandang disabilitas dan merusak struktur hierarki SEO. | Ganti tag `<div>` dengan elemen semantik yang sesuai dengan fungsinya. |
| 4 | 5, 13, 20, 24 | Menggunakan `<div>` bergaya khusus sebagai pengganti elemen heading (`<h1>`, `<h2>`) | Penilaian struktur konten oleh pembaca layar dan mesin pencari menjadi tidak teratur. | Gunakan tag `<h1>` untuk judul utama dan `<h2>` untuk subjudul. |
| 5 | 6 | Menggunakan `!important` pada aturan CSS `.nav a` | Menyulitkan pemeliharaan kode (maintenance) dan menimpa spesifisitas CSS secara paksa. | Hapus `!important` dan gunakan selector CSS yang presisi. |
| 6 | 8 | Kelas CSS `.sidebar` tidak pernah digunakan di dalam dokumen HTML | Merupakan kode tidak terpakai (dead code) yang mengotori file CSS dan memperbesar ukuran file. | Hapus aturan `.sidebar` dari CSS. |
| 7 | 5 | Penentuan `width: 1200px;` secara tetap (fixed width) pada header | Menyebabkan munculnya horizontal scrollbar pada layar perangkat seluler/kecil. | Ganti dengan `max-width: 1200px;` dan `margin: 0 auto;`. |
| 8 | 6 | Kontras warna teks `.content` (`#bbbbbb`) dan tautan `.nav a` sangat rendah | Sangat sulit dibaca oleh pengguna biasa maupun yang memiliki gangguan penglihatan (low vision). | Ubah warna teks menjadi lebih kontras (misalnya `#333333` dan `#ffffff`). |
| 9 | 20, 22, 23, 25 | Menggunakan inline style (`style="..."`) dan tag pemisah `<br>` secara berlebihan | Menggabungkan struktur dan tampilan serta merusak kerapian tata letak layout. | Pindahkan semua gaya ke file CSS dan gunakan `margin`/`padding` untuk jarak. |
| 10 | 23 | Elemen gambar `<img>` tidak memiliki atribut `alt` | Pembaca layar tidak dapat menjelaskan deskripsi gambar kepada pengguna tunanetra. | Tambahkan atribut `alt="Gambar Gedung Kampus STT Cipasung"`. |
| 11 | 25, 26 | Input formulir tidak memiliki `<label>` dan tipe `email` untuk kolom email | Pengguna screen reader tidak mengetahui fungsi input, serta tidak ada validasi bawaan format email. | Hubungkan input dengan `<label>` dan ubah tipe input email menjadi `type="email"`. |

Refleksi:
1. Masalah yang paling sulit disadari hanya dengan melihat tampilan browser adalah ketiadaan tag semantik HTML dan atribut aksesibilitas (seperti `alt` pada `<img>` dan `<label>` pada form). Hal ini karena browser tetap dapat menampilkan gambar dan kotak input secara visual tanpa kendala, meskipun di balik layar kodenya tidak ramah bagi pembaca layar (screen reader).
2. Meskipun halamannya "berfungsi", masalah-masalah ini tetap penting karena memengaruhi aspek SEO, aksesibilitas bagi pengguna penyandang disabilitas, serta keterbacaan kode (maintainability). Kode yang rapi dan standar memudahkan pengembangan bersama tim di masa depan.
3. Kebiasaan yang akan saya lakukan adalah selalu memvalidasi kode HTML dan CSS melalui W3C Validator untuk memastikan 0 error, serta memeriksa kembali struktur elemen menggunakan panel DevTools browser sebelum dikumpulkan.

## Bagian 7: Exit ticket
1. Secara sederhana, aturan CSS merupakan instruksi untuk mengatur tampilan elemen HTML. Anatominya diawali oleh selector yang menentukan elemen target, diikuti oleh blok deklarasi di dalam tanda kurung kurawal yang memuat property sebagai aspek yang ingin diubah dan value sebagai nilai dari perubahan tersebut. Konsep yang menurut saya masih cukup membingungkan dan perlu pendalaman lagi adalah perhitungan bobot specificity pada CSS selector yang kompleks, serta penyesuaian perhitungan lebar elemen pada box model saat menggunakan content-box versus border-box.Meskipun begitu, hal yang sekarang sudah bisa saya lakukan secara mandiri tanpa perlu mencari di internet lagi adalah menyusun struktur dasar dokumen HTML5 yang valid menggunakan tag-tag semantik serta menghubungkan file HTML tersebut ke stylesheet CSS eksternal.
2. Saya masih agak bingung menghitung mana selector CSS yang menang kalau gayanya bentrok, sama masih suka tertukar memprediksi ukuran kotak elemen saat pakai content-box dan border-box.
3. Sekarang saya sudah lumayan paham membuat kodingan dasar HTML yang rapi serta cara menyambungkannya ke file CSS eksternal.