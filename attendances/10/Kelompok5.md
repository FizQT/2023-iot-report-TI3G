# Anggota Kelompok
1. Yoby Ryaian Pratama : 19
2. Izzatun Nauly : 12
3. Dewi Lailaturrohma : 06

# Manajemen IoT Dashboard System
Layaknya sebuah IoT platform yang mempermudah pengguna dalam memvisualisaikan atau menyajikan data kepada pengguna, Node-RED juga menyediakan sebuah dashboard agar kita dapat dengan mudah untuk menyajikan data secara live atau real time.

Untuk menggunakan atau membuat tampilan dashhboard menggunakan Node-RED juga sangat mudah, yaitu tinggal melakukan drag and drop pada worksheet untuk setiap komponen.

## Praktikum
1. Install Dashboard Node-RED
- Menggunakan perintah npm.
- Menggunakan menu Manage pallete pada Node-RED, mengakses Node-RED via browser.

<img src = "Kelompok5\instalasi.jpeg">

2. Membuat Dashboard Node-RED
- Terlebih dahulu pilih menu dashboard, yang terdapat di pojok kanan bawah. dashbaord ini adalah untuk mengkonfigurasi website yang akan kita buat misalkan dari sistem menu/hirarki menu ataupun title website. Perhatikan gambar di bawah ini

<img src = "Kelompok5\1.jpeg">

<img src = "Kelompok5\21.jpeg">

- Pada bagian Tabs & Links klik tombol tab sehingga akan ditambahkan tab baru di bawahnya, pada tab baru yang terbentuk yaitu Tab 1 klik tombol edit sehingga akan muncul jendela Edit dashboard tab node seperti berikut

<img src = "Kelompok5\3.jpeg">

- Selanjutnya tambahkan Group pada Tab Home tersebut dengan klik tombol group. Selanjutnya klik edit pada group yang baru ditambahkan sehingga akan muncul jendela Edit dashboard tab node kembali. Sesuaikan nilai-nilai seperti pada gambar berikut

<img src = "Kelompok5\4.jpeg">

- Ulangi langkah sebelumnya sehingga tampilannya menjadi seperti berikut

<img src = "Kelompok5\5.jpeg">

- Drag ke worksheet/flow node switch kemudian double klik sehingga akan menampilkan jendela seperti di bawah, sesuaikan bagian seperti Group, Label, dan Name seperti pada gambar di bawah ini.

<img src = "Kelompok5\6.jpeg">

- Ulangi langkah sebelumnya, tetapi yang ditambahkan adalah node text, sesuaikan property seperti pada gambar berikut

<img src = "Kelompok5\7.jpeg">

- Hubungkan node switch dan node text, hasil akhirnya adalah sebagai berikut. Kemudian silakan lakukan deploy dengan klik tombol Deploy. Untuk melihat tampilannya silakan akses Node-RED, misalnya http://ec2-52-91-160-126.compute-1.amazonaws.com:1880/ui.

<img src = "Kelompok5\8.jpeg">

- Hasil akhirnya adalah sebagai berikut

<img src = "Kelompok5\9.jpeg">

## Pertanyaan

Silakan modifikasi flow di atas sehingga ketika node switch digeser tidak menghasilkan nilai true atau false, tetapi ketika digeser nilainya adalah nyala atau mati. Perhatikan gambar berikut ini

<img src = "Kelompok5\Hidup.jpeg">

<img src = "Kelompok5\Mati.jpeg">

## Tugas
Buatlah sebuah dashboard website untuk memonitoring dan control pada sebuah ruang lobby, ruang kajur, dan ruang dosen. Masing-masing ruang dengan detail node yang dibutuhkan pada node dashboard sebagai berikut;
1. Tab Home memiliki group Lobby, Ruang Kajur, dan Ruang Dosen.
Group Lobby terdapat 2 node inject, 2 function, gauge, dan chart.
Group Ruang Kajur terdapat 2 node inject, 2 function, gauge, dan chart.
Group Ruang Dosen terdapat 2 node inject, 2 function, gauge, dan chart.
Jika diperhatikan node gauge dan chart bisa otomatis berjalan, hal tersebut diaktifkan saja pada bagian otomatis pada node inject.

    Sedangkan nilai yang selalu muncul acak itu menggunakan node funcion, Math.floor(Math.random()*101)

    Jumlah line antara node chart pada Lobby, Ruang Kajur, dan Ruang Dosen berbeda bisa dilakukan dengan cara mengubah Setup Outputs pada function.

2. Tab Room Control terdiri dari group Lampu dan AC.
Group Lampu memiliki 3 switch, 3 function, dan 3 text.
Group AC memiliki 3 slider dan 3 text.
function digunakan untuk parsing boolean ke string, "nyala atau mati".

3. Tab About hanya terdiri dari text biasa.


Hasilnya adalah sebagai berikut
<img src = "Kelompok5\Hasil.jpeg">

<img src = "Kelompok5\Home.jpeg">

<img src = "Kelompok5\Room.jpeg">

<img src = "Kelompok5\About.jpeg">