# Jawaban Praktikum: Lutfi Ismail Aliansah Putra (10224004)

## Bagian 1: Pemanasan
1. Selector-nya adalah `nav a`,
deklarasinya adalah `nav a.active:hover { color: red; }`, property-nya adalah `color`, value-nya adalah `red`, dan pseudo-class-nya adalah `active:hover`.
2. Elemen yang bersifat block: `p`, `li`, dan `h2`. Elemen yang bersifat inline: `a`, `span` dan `strong`.
3. Yang menjadi hijau adalah paragraf A dan B.
4. Warnanya akan biru, karena `h1 { color: blue; }` (elemen selector) memiliki bobot hierarki prioritas lebih tinggi.
5. Urutan penulisan tag HTML-nya salah. Yang benar adalah seperti berikut: `<p>Hello <strong>world</strong></p>`

## Bagian 3: Prediksi Selector Golf
P1. Semua paragraf yang disebutkan akan berwarna biru. Karena element selector `p { color: blue; }` memiliki tingkat prioritas lebih tinggi daripada yang lain.

P2. `main section p` 🡪 `p` 🡪 `#tech p` 🡪 `.club p`.

Setelah diuji (hasil sebenarnya):
Semua paragraf yang disebutkan akan berwarna biru. Karena element selector `p { color: blue; }` memiliki tingkat prioritas lebih tinggi daripada yang lain. Hasil sebenarnya paragraf "Weekly hack nights." berwarna hijau (prediksi saya salah karena lupa tidak melihat sebelum tag `<p>` ada tag `section` sebagai container-nya), "Bring your own laptop." berwarna kuning (prediksi saya salah karena saya pikir element selector akan lebih diprioritaskan daripada class selector), dan "© 2026 Student Affairs" berwarna biru. Jawaban yang bagian ini sudah benar yaitu berwarna biru. Karena paragraf "© 2026 Student Affairs" tidak memiliki class dan tidak berada di dalam elemen `<section>` jadi style yang diterapkan adalah dari kode `p { color: blue; }`.

## Bagian 4: Box model
Q1 (content-box):
Q2 (border-box):
Pengecekan DevTools:

## Bagian 5: Tabel debug
| # | Baris | Bug | Perbaikan | Cara menemukannya |
|---|-------|-----|-----------|-------------------|

## Bagian 6: Tabel Code Review
| # | Baris | Masalah | Mengapa penting | Perbaikan saya |
|---|-------|---------|-----------------|----------------|

Refleksi:
1.
2.
3.

## Bagian 7: Exit ticket
1.
2.
3.
