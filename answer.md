# Jawaban Praktikum: Lutfi Ismail Aliansah Putra (10224004)

## Bagian 1: Pemanasan

1. Selector-nya adalah `nav a`,
deklarasinya adalah `nav a.active:hover { color: red; }`, property-nya adalah `color`, value-nya adalah `red`, dan pseudo-class-nya adalah `active:hover`.
2. Elemen yang bersifat block: `p`, `li`, dan `h2`. Elemen yang bersifat inline: `a`, `span` dan `strong`.
3. Yang menjadi hijau adalah paragraf A dan B.
4. Warnanya akan biru, karena `h1 { color: blue; }` (elemen selector) memiliki bobot hierarki prioritas lebih tinggi.
5. Urutan penulisan tag HTML-nya salah. Yang benar adalah seperti berikut: `<p>Hello <strong>world</strong></p>`

---

## Bagian 3: Prediksi Selector Golf

P1. Semua paragraf yang disebutkan akan berwarna biru. Karena element selector `p { color: blue; }` memiliki tingkat prioritas lebih tinggi daripada yang lain.

P2. `main section p` 🡪 `p` 🡪 `#tech p` 🡪 `.club p`.

Setelah diuji (hasil sebenarnya):
Semua paragraf yang disebutkan akan berwarna biru. Karena element selector `p { color: blue; }` memiliki tingkat prioritas lebih tinggi daripada yang lain. Hasil sebenarnya paragraf "Weekly hack nights." berwarna hijau (prediksi saya salah karena lupa tidak melihat sebelum tag `<p>` ada tag `section` sebagai container-nya), "Bring your own laptop." berwarna kuning (prediksi saya salah karena saya pikir element selector akan lebih diprioritaskan daripada class selector), dan "© 2026 Student Affairs" berwarna biru. Jawaban yang bagian ini sudah benar yaitu berwarna biru. Karena paragraf "© 2026 Student Affairs" tidak memiliki class dan tidak berada di dalam elemen `<section>` jadi style yang diterapkan adalah dari kode `p { color: blue; }`.

---

## Bagian 4: Box model

Q1 (content-box):

Dengan CSS:

```css
.card {
  width: 300px;
  padding: 16px;
  border: 1px solid;
  margin: 24px;
  box-sizing: content-box;
}
```

Pada content-box, properti width hanya menghitung lebar area konten, belum termasuk padding dan border.

Perhitungannya:

| Komponen | Perhitungan | Lebar |
|:--------:|:-----------:|:-----:|
| Content |	width |	300 px |
| Padding | kiri + kanan	16 × 2 |	32 px |
| Border | kiri + kanan	1 × 2	| 2 px |
| Total | lebar kartu	300 + 32 + 2 |	334 px |

Jadi, lebar yang terlihat dari tepi border kiri ke tepi border kanan adalah:

300 + (2 * 16) + (2 * 1) = 334 px

Margin 24px tidak dihitung karena margin berada di luar border.

Jika menghitung keseluruhan ruang horizontal termasuk margin kiri dan kanan, hasilnya adalah 334 + 48 = 382px.

Q2 (border-box):

Jika ditambahkan box-sizing: border-box

```css
.card {
  width: 300px;
  padding: 16px;
  border: 1px solid;
  margin: 24px;
  box-sizing: border-box;
}
```

Pada border-box, properti width sudah mencakup content + padding + border.

Perhitungannya:

| Komponen | Perhitungan | Lebar |
|:--------:|:-----------:|:-----:|
| Lebar total kartu |	width |	300 px |
| Padding kiri + kanan |	16 × 2 |	32 px |
| Border kiri + kanan |	1 × 2	| 2 px |
| Lebar content	| 300 − 32 − 2 | 266 px |

Jadi, lebar yang terlihat dari tepi border ke tepi border menjadi 300 px, bukan 334 px.

Pengecekan DevTools:
content: 300px
padding: 16px
border: 1px
margin: 24px

---

## Bagian 5: Tabel debug

| # | Baris | Bug | Perbaikan | Cara menemukannya |
|---|-------|-----|-----------|-------------------|
| 1 | 12    | Tidak ada tanda titik koma (`;`) | Tambahkan titik koma (`;`) | Terlihat warning dari kode setelah baris 12 |
| 2 | 9 | Typo penulisan properti `colour` seharusnya `color` | Tulis jadi `color` | Warning dari vscode-nya |
| 3 | 32 | Tidak menutup tanda petik | Tambahkan tanda petik petup (`"`) | Membaca kode |
| 4 | 19 | Salah penulisan ID selector | Ubah dari `#news-list` menjadi `#newsList` sesuai yang ditulis di HTML-nya | Membaca kode |
| 5 | 20 | Salah penulisan | Hapus spasi di antara teks `18` dan `px`, cara penulisannya harusnya disatukan, jangan ada spasinya | Membaca kode |
| 6 | 23 | Typo penulisan value properti | Ubah dari `centre` jadi `center` | Membaca kode |
| 7 | 29 | Salah menulis tag penutup `<h1>` | Ganti dari `</h2>` jadi `</h1>` | Membaca kode |
| 8 | 15 | Salah penulisan nama class CSS | Ganti nama class-nya dari `.Card` jadi `.card` | Membaca kode |
| 9 | 37 | Sebenarnya ini bukan bug, tapi best practice yang sebaiknya diikuti—yaitu menambahkan atribut `alt` pada elemen `<img>` | Tambahkan atribut `alt` dan isi deskripsinya sesuai dengan gambar yang ditampilkan | Membaca kode |

---

## Bagian 6: Tabel Code Review

| # | Baris | Masalah | Mengapa penting | Perbaikan saya |
|:-:|:-----:|:-------:|:---------------:|:--------------:|
| 1 | 29 | Menggunakan tag `<div>` untuk membungkus konten header | Menggunakan tag `<div>` tidak memberi makna pada browser (semantik) | Gunakan tag yang semestinya, yaitu `<header>` |
| 2 | 30 | Menggunakan tag `div` untuk membungkus judul seharusnya gunakan tag heading (`<h1>`-`h6`) | Karena untuk menunjukkan bahwa teks tersebut adalah heading/judul | Ganti dengan tag `h1` |
| 3 | 31 | Menggunakan tag `<div>` untuk membungkus navigasi | Ada tag yang diperuntukkan untuk hal tersebut yang semantik, kenapa tidak menggunakannya | Ganti `<div>` dengan `<nav>` |
| 4 | 36 | Menggunakan tag `<div>` untuk membungkus content atau bagian-bagian di bawah header | lebih tepat jika menggunakan tag `<section>` | Ubah tag `<div>` jadi `<section>` dengan atribut `id="content"` |
| 5 | 37 | Menggunakan tag `<div>` untuk membungkus subjudul | Ada tag yang lebih tepat, yaitu `<h1>`-`<h6>` | Ubah dari tag `<div>` menjadi `<h2>` |
| 6 | 39 | Menggunakan tag `<div>` untuk membungkus paragraf | Ada tag yang lebih tepat dan semantik, yaitu tag `<p>` | Ubah dari tag `<div>` menjadi `<p>` |
| 7 | 43 | Menggunakan tag `<div>` untuk membungkus subjudul | Ada tag yang lebih tepat, yaitu `<h1>`-`<h6>` | Ubah dari tag `<div>` menjadi `<h2>` |
| 8 | 45 | Elemen input salah value pada atribut type, seharusnya bukan `text` tapi `email`, karena input tersebut berupa email | Value atribut tidak sesuai dengan tujuan/fungsinya | Ganti dari `type="text"` menjadi `type=email` |
| 9 | 48 | Menggunakan tag `<div>` untuk membungkus footer | Ada tag semantik yang lebih tepat untuk digunakan, yaitu tag `footer` | Ubah dari tag `<div>` menjadi `<footer>` |
| 10 | 19-22 | Mendeklarasikan styling, tapi tidak ada elemen yang ingin diberi gaya | Menulis kode yang tidak diperlukan/digunakan | Hapus kode tersebut |

Refleksi:

1. Mungkin masalah yang paling sulit disadari jika hanya melihat halamannya di browser adalah penggunaan tag untuk membagi halaman website—seperti tag `<section>`, `article`, `div`, dan lain-lain. Karena kadang bingung mana tag yang lebih tepat untuk saya gunakan.
2. Walaupun halaman aslinya tetap berfungsi, penting untuk kita ketahui bahwa browser tidak hanya menampilkan konten website-nya saja. Tapi, browser juga membaca apakah tag HTML yang digunakan memiliki makna yang tepat atau tidak untuk membungkus konten yang ditampilkan ke user. Semakin tepat penggunaan tag HTML-nya, maka website kita akan lebih baik karena kita menggunakan tag yang semantik dan mempermudah pembacaan website kita.
3. Memastikan apakah tag yang digunakan sudah tepat dan (semantik) dan memberi nama class atau id yang deskriptif

---

## Bagian 7: Exit ticket

1. 
2. 
3. 