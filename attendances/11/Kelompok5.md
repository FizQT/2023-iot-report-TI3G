# Anggota Kelompok
1. Yoby Ryaian Pratama : 19
2. Izzatun Nauly : 12
3. Dewi Lailaturrohma : 06

# Konfigurasi Smart Device
## Praktikum

1. MQTT Node-RED
- Silakan seret node inject ke worksheet, kemudian ubahlah nilai properties seperti pada gambar berikut

<img src = "Kelompok5\1.jpeg">

- Seret juga node function ke worksheet, sesuaikan propertiesnya seperti pada gambar berikut

<img src = "Kelompok5\2.jpeg">

- Jangan lupa seret juga node mqtt out pada kategori network, tambahkan server broker agar bisa publish data dengan cara klik icon pensil. Konfigurasinya adalah sebagai berikut adalah sebagai berikut

<img src = "Kelompok5\3.jpeg">

Pada bagian Name isikan Mqtt Server AWS, Server diisikan broker.hivemq.com dan port isikan 1883.

Untuk node mqtt out kira-kira seperti berikut

<img src = "Kelompok5\4.jpeg">

Perhatian gambar berikut untuk flow lengkapnya, setelah semua node dihubungkan.

<img src = "Kelompok5\5.jpg">

- Tambahkan node mqtt in ke worksheet, sesuaikan konfigurasi sebagai berikut

<img src = "Kelompok5\6.jpeg">

Pada bagian Server, Topic dan Qos disamakan dengan node mqtt out sedangkan Name silakan isikan dengan sample subscriber.

- Tambahkan node terakhir yaitu node debug, sementara untuk kongifigurasinya tidak perlu disesuaikan. Hubungkan kedua node tersebut sehingga menjadi sebagai berikut

<img src = "Kelompok5\7.jpg">

Sehingga flow lengkap dari langkah awal sampai akhir adalah sebagai berikut

<img src = "Kelompok5\8.jpg">

## Verifikasi Hasil Percobaan 

Setelah dilakukan deploy, kemudian klik tab debug atau icon kutu seharusnya adalah sebagai berikut. Adapun untuk nilainya pasti berbeda

<img src = "Kelompok5\9.jpeg">

## Pertanyaan

1. Pada node inject, pada properties Repeat dengan nilai interval. Apakah fungsinya?
2. Apakah yang dimaksud dengan baris kode msg.payload=Math floor(Math.random()*100);?
3. Bagian node mqtt out, apakah fungsi Qos dengan nilai 2?

## Jawaban

1. Dalam konteks yang umum, Node "inject" pada aliran kerja Node-RED memungkinkan memasukkan sinyal atau peristiwa ke dalam aliran secara terjadwal. Properti "Repeat" dengan nilai "interval" digunakan untuk mengatur interval waktu antara dua pemancaran sinyal yang berulang. Dengan menggunakan properti ini dapat mengatur interval waktu berulang untuk mengirimkan sinyal ke aliran kerja.
2. Baris kode "msg.payload=Math.floor(Math.random()*100);" digunakan untuk menghasilkan sebuah bilangan acak antara 0 hingga 99 (inklusif) dan menyimpannya ke dalam properti "payload" dari objek pesan (msg). 
3. Pada Node MQTT Out di Node-RED, opsi QoS (Quality of Service) dengan nilai 2 mengacu pada tingkat kualitas layanan yang digunakan saat mengirim pesan melalui protokol MQTT (Message Queuing Telemetry Transport). QoS mengontrol bagaimana pesan dikirim dan diterima antara publisher (pengirim) dan subscriber (penerima) melalui broker MQTT.

## Menghubungkan Smart Device Node-RED
1. Silakan buat flow baru dengan cara klik tombol plus(+), tambahkan terlebih dahulu node mqtt in ke worksheet dengan konfigurasi sebagai berikut

<img src = "Kelompok5\10.jpg">

2. Buatlah dashboard dengan tab Site dengan title Node-RED Dashboard dengan layout adalah sebagai berikut

<img src = "Kelompok5\11.jpg">

3. Tambahkan node chart dan sesuaikan konfigurasinya menjadi sebagai berikut

<img src = "Kelompok5\12.jpg">

Jangan lupa pada bagian Name diisikan dengan room-temp.

4. Hubungkan kedua node tersebut dan Deploy, tampilan dashboard secara utuh menjadi demikian

<img src = "Kelompok5\13.jpg">

Langkah terakhir yang perlu dilakukan yaitu membuat kode smart device, ESP8266. Tambahkan atau pasang sensor DHT11 yang rencananya akan kita tampilkan pada dashboard yang sebelumnya telah kita buat. Kode lengkapnya adalah sebagai berkut

<img src = "Kelompok5\14.jpeg">

## Verifikasi Hasil Percobaan

<img src = "Kelompok5\14.jpeg">

Tampilan serial monitor

<img src = "Kelompok5\15.jpeg">

Tampilan Node-RED pada browser

## Pertanyaan
1. Modifikasi program di ESP8266 di atas agar bisa melakukan subscribe dengan topik room/lamp?
2. Tambahkan kode di atas agar bisa publish nilai kelembaban dengan topik room/humadity?
3. Tambah node chart agar dapat menampilkan nilai kelembaban, node chart masih dalam satu group yaitu Room pada dashboard Node-RED.

## Jawaban

1. Hasil Modifikasi program di ESP8266 di atas agar bisa melakukan subscribe dengan topik room/lamp
<img src = "Kelompok5\16.jpg">

2. Hasil menambahkan nilai kelembaban dengan topik room/humadity
<img src = "Kelompok5\16.jpg">

3. Hasil node chart agar dapat menampilkan nilai kelembaban, node chart masih dalam satu group yaitu Room pada dashboard Node-RED
<img src = "Kelompok5\17.jpg">
<img src = "Kelompok5\18.jpeg">

## Tugas
Masih lanjutan dengan tugas, tambahkan sensor LDR dan LED RGB pada ESP8266. Ketentuannya adalah sebagai berikut

1. Tab Home terdiri dari group Control, Monitoring, dan Cahaya.
Group Control memiliki 3 node switch dan 3 text statis, fungsi dari group ini adalah untuk menghidupkan dan mematikan led RGB.
Group Monitoring 2 node chart untuk menampilkan suhu dan kelembaban.
Group Cahaya terdiri dari text dan gauge, text untuk menampilkan kategori terang, redup, dan gelap. Sedangkan node gauge untuk menampilkan nilai sensor LDR.
2. Tab Contact Pada tab ini digunakan untuk menampilkan data kelas, NIM, dan Nama. Silakan diisi dengan nama Anda masing-masing.

Hasil yang diharapkan adalah sebagai berikut
<img src = "Kelompok5\tugas.jpg">

<img src = "Kelompok5\tugas1.jpeg">