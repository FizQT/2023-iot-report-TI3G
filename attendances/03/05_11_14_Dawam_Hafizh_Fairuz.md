# Anggota Kelompok
1. Dawam Ilhami Assidiqi (05)
2. Hafizh Izhar Darmansyah (11)
3. Muhammad Fairuz Zakaria Firdaus (14)

# Pertanyaan
1. Apa yang telah kelompok Anda lakukan pada pertemuan kali ini?
    Jawab : 
    - Instalasi Arduino IDE
    - Instalasi Fritzing Designer
    - Instalasi PlatformIO IDE di Visual Studio Code
    - Instalasi Wokwi Simulator di Visual Studio Code
    - Implementasi Wokwi secara online melalui website
    - Membuat kode program sederhana untuk menyalakan LED bawaan node MCU
      Kode Program : 
        void setup() {
        pinMode(LED_BUILTIN, OUTPUT); // mengatur pin LED_BUILTIN sebagai output
        }

        void loop() {
        digitalWrite(LED_BUILTIN, HIGH); // menyalakan LED merah
        delay(1000); // menunggu selama 1 detik
        digitalWrite(LED_BUILTIN, LOW); // mematikan LED merah
        delay(1000); // menunggu selama 1 detik
        }

2. Apa ada kendala pada pertemuan kali ini, jika ada sebutkan!
    Jawab :
    Terjadi error pada langkah instalasi Arduino IDE bagian portnya tidak muncul pada Device Manager dan pada aplikasi Arduino IDE. Solusinya kita harus install terlebih dahulu drivernya yang dapat diunduh di https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers

3. Apa yang bisa kelompok Anda simpulkan pada pertemuan kali ini!
    Jawab : 
    - Kita dapat mengetahui tentang :
        - Arduino IDE (Integrate Development Enviroment) ialah software yang dipakai untuk membuat, mengedit suatu kode program, memverifikasi, dan mengunggah kode program ke arduino.
        - Fritzing designer adalah aplikasi untuk membuat skema pengabelan untuk komponen-komponen yang dibutuhkan, misalnya Micrcontroller Unit (NodeMCU, Arduino dll), berbagai jenis module sensor dan aktuator serta komponen-komponen pendukung lainnya.
        - Wokwi adalah sebuah simulator elektronik online, kita dapat mengunakan untuk mensimulasikan Arduino, ESP32, dan banyak board-board terkenal yang lain, komponen-komponen dan sensor.
        - Kita dapat membuat Kode Program Sederhana untuk menyalakan LED merah bawaan node MCU

3. Silahkan mengerjakan tugas yang terdapat di jobsheet!
    Jawab : 
    Membuat Kode Program Sederhana untuk menyalakan LED merah bawaan node MCU : 
        void setup() {
        pinMode(LED_BUILTIN, OUTPUT); // mengatur pin LED_BUILTIN sebagai output
        }

        void loop() {
        digitalWrite(LED_BUILTIN, HIGH); // menyalakan LED merah
        delay(1000); // menunggu selama 1 detik
        digitalWrite(LED_BUILTIN, LOW); // mematikan LED merah
        delay(1000); // menunggu selama 1 detik
        }