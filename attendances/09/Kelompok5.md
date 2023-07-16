# Anggota Kelompok
1. Yoby Ryaian Pratama : 19
2. Izzatun Nauly : 12
3. Dewi Lailaturrohma : 06

# Installasi IoT Platform

## 1.	Install node red melalui windows

<img src = "Kelompok5\Gambar1.png">

<img src = "Kelompok5\Gambar2.png">

Merubah password node red dengan masuk ke file "setting"

<img src = "Kelompok5\Gambar3.png">

Melakukan uncomment pada kode di bawah

<img src = "Kelompok5\Gambar4.png">

Kemudain pada cmd ketikkan perintah "node-red admin hash-pw" dan ketikkan password anda

<img src = "Kelompok5\Gambar5.png">

Jalankan dengan mengetikkan "node-red"

<img src = "Kelompok5\Gambar6.png">

Copas link pada seperti gambar dibawah kemudian tempelkan pada browsher

<img src = "Kelompok5\Gambar7.png">

Silahkan login terlebih dahulu

<img src = "Kelompok5\Gambar8.png">

Tampilan pada halaman utama node red

<img src = "Kelompok5\Gambar9.png">

## Hasil pertanyaan

1. Tambahkan kembali node function dan node debug, yang masing-masing fungsinya adalah untuk memfilter dimana movie yang akan tampil hanya movie dengan tahun > 2000 dan untuk menampilkan data filter tersebut.

2. Flow dan output pada debug dapat dilihat seperti berikut ini

<img src = "Kelompok5\Gambar10.png">

## Tugas

Buatlah sebuah flow yang digunakan untuk menentukan sebuah kondisi temperatur dingin, normal, dan panas. Terdapat 3 node inject masing-masing sebagai berikut;

- Ketika inject pertama diklik akan muncul di panel debug menampilkan dingin, lewatkan nilai 5 pada node inject pertama.
- Ketika inject kedua diklik akan muncul di panel debug menampilkan normal, lewatkan nilai 25 pada node inject kedua.
- Ketika inject ketiga diklik akan muncul di panel debug menampilkan panas, lewatkan nilai 50 pada node inject ketiga.

Perhatian keluaran pada panel debug di bawah ini, itu output yang diharapkan.

<img src = "Kelompok5\Gambar11.png">