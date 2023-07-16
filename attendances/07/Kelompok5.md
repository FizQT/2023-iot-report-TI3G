# Anggota Kelompok
1. Yoby Ryaian Pratama : 19
2. Izzatun Nauly : 12
3. Dewi Lailaturrohma : 06

# Implementasi 12C

## Praktikum 1 Mencari alamat I2C
Untuk dapat menggunakan LCD yang menggunakan I2C, sebelumnya harus mencari terlebih dahulu lokasi dari I2C tersebut. I2C defaultnya terdapat di 0x27, akan tetapi hal tersebut bisa berbeda bergantung dari manufacture atau vendor. Buatlah kode di bawah ini untuk mendapatkan alamat I2C pada LCD.

- Hasil praktikum 1 pada PlatformIo

<img src = "Kelompok5\Praktikum1_PlatformIo.jpeg">

- Hasil praktikum 1 pada Wokwi
<img src = "Kelompok5\Praktikum1_Wokwi.png">

## Praktikum 2 Menampilkan data pada LCD
Pada praktikum ini kita akan mencoba menggunakan LCD untuk menampilkan sebuah text, hasil praktikum pertama akan kita gunakan pada praktikum ini.

- Hasil praktikum 2 pada PlatformIo

https://drive.google.com/file/d/1JYJNgpcRJkFMK30tO0RdH2eBSEtMUkXD/view?usp=share_link

<img src = "Kelompok5\Praktikum2_PlatformIo.jpeg">

- Hasil praktikum 2 pada Wokwi
<img src = "Kelompok5\Praktikum2_Wokwi.png">

## Pertanyaan

1. Jelaskan fungsi dari pemanggilan method lcd.backlight()?

Fungsi lcd.backlight() digunakan untuk menyalakan backlight pada LCD. Backlight diperlukan agar tampilan pada LCD dapat terlihat dengan jelas di lingkungan yang kurang cahaya atau gelap. Tanpa backlight, tampilan pada LCD akan sangat sulit untuk dibaca atau bahkan tidak terlihat sama sekali.

Jadi, alasan kenapa kita perlu menggunakan lcd.backlight() adalah untuk memastikan tampilan pada LCD dapat terlihat dengan jelas di berbagai kondisi pencahayaan. Hal ini sangat penting, terutama jika LCD digunakan untuk menampilkan informasi penting atau untuk mengontrol suatu sistem.

2. Bagimana caranya mengganti tingkat intensitas kecerahan dari LCD Anda?

Dengan cara memutas pada bagian belakang LCD dengan searah jarum jam sehingga ketajaman atau intensitas cahaya pada LCD akan lebih cerah

3. Silakan modifikasi data yang ditampilkan pada LCD Anda?

<img src = "Kelompok5\Hasil_Pertanyaan.png">

## Tugas
Buatlah sebuah aplikasi yang sederhana menggunakan DHT11, LED RGB, dan LCD. Skenarionya adalah sebagai berikut

1. Buatlah ketiga komponen tersebut di dalam satu rangkaian menggunakan fritzing.
2. Tampilkan suhu dalam bentuk Fahrenheit dan Celcius, suhu yang ditampilkan adalah suhu di ruangan sekitar Anda.
3. Ketika suhu normal LED berwarna biru akan berkedip-kedip, ketika suhu dingin LED berwarna hijau akan berkedip, dan LED berwarna merah akan berkedip ketika suhu tergolong tinggi.
4. Tampilkan waktu saat ini juga pada LCD.
5. Silakan hasilnya diupload ke google drive ataupun youtube, linknya sertakan dalam laporan Anda.

- Hasil Tugas pada Platform Io

<img src = "Kelompok5\Hasil_Tugas_PlatformIo.jpeg">

https://drive.google.com/file/d/1JYJNgpcRJkFMK30tO0RdH2eBSEtMUkXD/view?usp=share_link

- Hasil Tugas pada Wokwi

<img src = "Kelompok5\Hasil_Tugas_Wokwi.png">

https://github.com/yobipratama/vs-i2c-address.git