# Anggota Kelompok
1. Yoby Ryaian Pratama : 19
2. Izzatun Nauly : 12
3. Dewi Lailaturrohma : 06

# IoT Gateway dan Web Dashboard

# Install di Lokal
Message broker juga dapat dilakukan installasi di local, pada kesempatan ini akan melakukan installasi message broker Mosquitto pada sistem operasi Windows.
1. Download terlebih dahulu di sini.
2. Lakukan installasi sampai selesai seperti ditunjukkan pada gambar di bawah ini

<img src = "Kelompok5\1.jpeg">

3. Agar perintah mosquitto bisa dikenali perlu didaftarkan (path) terlebih dahulu, gambar di bawah ini adalah perintah mosquitto yang belum dikenali.

<img src = "Kelompok5\2.jpeg">

4. Secara default folder installasi terdapat di C:\Program Files\mosquitto, sehingga kita perlu mendaftarkan folder tersebut pada path environment yang ditunjukkan pada gambar di bawah ini
<img src = "Kelompok5\3.jpeg">

5. Ketik kembali perintah mosquitto pada Windows PowerShell, seharusnya outputnya berbeda dari yang sebelumnya artinya message broker sudah berjalan.

# Menambahkan Password MQTT

Agar lebih aman terhadap pihak-pihak yang tidak bertanggungjawab, perlu ditambahkan keamanan ketika akan menggunakan message broker yang telah kita install, salah satunya yaitu menambahkan authentifikasi berupa user dan password ketika ingin melakukan subscribe ataupun publish message.

<img src = "Kelompok5\4.jpeg">

<img src = "Kelompok5\5.jpeg">

<img src = "Kelompok5\6.jpeg">

## Pertanyaan
1. Apakah fungsi dari baris perintah protocol websockets pada file konfig mosquitto?
2. Silakan ganti menjadi false pada per_listener_settings true, restart mosquitto. Apakah yang akan terjadi atau pengaruhnya apa?
3. Buatlah user yang lain, kemudian lakukan subscribe dan publish message!

## Jawaban
1. Dalam file konfigurasi Mosquitto, baris perintah protocol websockets digunakan untuk mengaktifkan dukungan protokol WebSocket dalam server Mosquitto. WebSocket adalah protokol komunikasi dua arah yang memungkinkan komunikasi waktu nyata antara klien dan server melalui koneksi TCP tunggal. Dengan menggunakan protokol WebSocket, klien dapat melakukan komunikasi dengan server Mosquitto menggunakan protokol MQTT melalui koneksi WebSocket.
2. Secara default, Mosquitto memungkinkan penggunaan pengaturan yang berbeda untuk setiap pendengar yang didefinisikan dalam file konfigurasi. Dengan pengaturan per_listener_settings yang diaktifkan (true), Anda dapat menentukan pengaturan khusus untuk setiap pendengar dengan memberikan blok konfigurasi yang terpisah untuk setiap pendengar yang didefinisikan.
3. subscribe dan publish message
<img src = "Kelompok5\6.jpeg">