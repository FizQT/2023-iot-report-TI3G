# LAPORAN PRAKTIKUM  
# Anggota Kelompok
1. Gustania Nirmala Meisi (10)
2. Rosis Hudaya Putra (16)
3. Safira Istifarini (17)<br>

# <b>LDR dan HC-SR04<b>
Implementasi program sensor cahaya LDR dan sensor Ultrasonic

## <b>Teori Singkat<b>
### <b>Sensor Cahaya<b><br>
Sensor cahaya digunakan untuk menangkap intensitas cahaya di sekitar. Sensor yang digunakan adalah sensor LDR (Light Dependent Resistor).

### <b>Ultrasonic Sensor HC-SR04<b><br>
Sensor ultrasonik merupakan sensor yang berfungsi untuk mendeteksi suatu benda dengan jarak tertentu sesuai dengan jenis sensornya. Pada praktikum kali ini dibahas mengenai cara menggunakan serta implemetasi sensor ultrasonik pada NodeMCU. Sensor ultrasonik yang digunakan adalah tipe HC-SR04 dengan jarak yang dapat untuk mendeteksi benda dengan akurasi 3 mm. Sensor ini memiliki pin Trigger, dimana pin ini berfungsi sebagai pengirim sinyal dan pin Echo yang berfungsi sebagai penerima sinyal yang didapat dari pantulan benda.

## <b>Praktikum 1 - Membaca data intensitas cahaya<b><br>
1. Buatlah projek pada PlatformIO, namanya sesuai dengan keinginan Anda.
2. Deklarasikan variabel untuk menampung nilai sensor dan untuk variabel sensor seperti di bawah ini
```cpp
 #define sensorLDR A0
 int nilaiSensor;
 ```
 3. Tambahkan beberapa kode untuk melakukan konfigurasi serial monitor pada fungsi `setup()`.
 ```cpp
 Serial.begin(115200);
 Serial.println("Contoh Penggunaan Sensor LDR");
 delay(3000);
 ```
 4. Dan yang terakhir, membuat kode untuk membaca nilai dari sensor dan menampilkannya seperti berikut ini pada fungsi `loop()`.
 ```cpp
  nilaiSensor = analogRead(sensorLDR);
 Serial.print(“Nilai Sensor : “);
 Serial.println(nilaiSensor);
 delay(1000);
 ```
 Normalnya ketika program Anda dijalankan maka akan menampilkan nilai 0-1024, Semakin banyak cahaya yang mengenai LDR maka nilai resistansinya akan menurun, dan sebaliknya semakin sedikit cahaya yang mengenai LDR maka nilai hambatannya akan semakin membesar. Ketika hasil pembacaan sensor nilainya tidak seperti yang disebutkan, silakan kalibrasi sensor tersebut dengan cara memutar baut kecil yang terdapat di sensor menggunakan obeng kecil sambil mengamati keluaran yang ada di serial monitor.

Rangkaian Wokwi LDR
<img src = "kelompok04\LDR.png" width="500px">
<img src = "kelompok04\LDR1.png" width="500px"><br>
Kode Program

```cpp
 #define sensorLDR 34
 int nilaiSensor;

void setup() {
   Serial.begin(115200);
 Serial.println("Contoh Penggunaan Sensor LDR");
 delay(3000);
}

void loop() {
 nilaiSensor = analogRead(sensorLDR);
 Serial.print("Nilai Sensor : ");
 Serial.println(nilaiSensor);
 delay(1000);
}
```
Hasil
<img src = "kelompok04\LDRHasil.png" width="500px">

## <b>Praktikum 2 - Membaca data jarak benda<b><br>
Pada project awal ini akan dilakukan percobaan untuk bagaimana menerapakan atau mengimplementasikan pembacaan sensor ultrasonic untuk kemudian ditampilkan pada serial monitor yang ada pada Wokwi.

<br>Rangkaian Wokwi Ultrasonik
<img src = "kelompok04\ultra.png" width="500px">
<img src = "kelompok04\ultra1.png" width="500px"><br>
Kode Program

```cpp
#define triggerPin 32
#define echoPin 33


void setup() {
   Serial.begin (115200);
   pinMode(triggerPin, OUTPUT);
   pinMode(echoPin, INPUT);
   pinMode(BUILTIN_LED, OUTPUT);
}

void loop() {
   long duration, jarak;
   digitalWrite(triggerPin, LOW);
   delayMicroseconds(2);
   digitalWrite(triggerPin, HIGH);
   delayMicroseconds(10);
   digitalWrite(triggerPin, LOW);
   duration = pulseIn(echoPin, HIGH);
   jarak = duration * 0.034 / 2;
   Serial.print(jarak);
   Serial.println(" cm");
   delay(2000);
}
```
Hasil
<img src = "kelompok04\ultrasonic.png" width="500px">

## <b>Tugas<b><br>
1. Buatlah sebuah rangkaian untuk LED, sensor cahaya dan sensor suhu menggunakan Wokwi, kemudian buatlah program dengan skenario sebagai berikut
<img src = "kelompok04\TUGAS-BAG1-RANGKAIAN.jpg" width="500px"><br>
* Ketika cahaya redup dan suhu kategori dingin maka LED warna biru akan berkedip-kedip (Kuning).
<img src = "kelompok04\TUGAS-BAG1-KONDISI1.jpg" width="500px"><br>
* Ketika cahaya terang dan suhu tergolong tinggi, LED merah akan menyala (Tosca). 
<img src = "kelompok04\TUGAS-BAG1-KONDISI2.jpg" width="500px"><br>
* Ketika tidak memiliki LED RGB, silakan memanfaatkan LED build in adalah LED bawaan esp8266, biasanya berwarna biru atau merah 2.<br>
Hasil Simulasi : Video dokumentasi hasil tugas [klik disini](https://drive.google.com/file/d/17nSOrnTJvoKsUHrawi_80jdU-NetbH5G/view?usp=sharing)

2. Buatlah rangkaian dan kode programnya dimana:<br>
Terdapat tambahan 1 LED RGB,
<img src = "kelompok04\TUGAS-BAG2-RANGKAIAN.jpg" width="500px"><br>
* LED Blue menyala jika jarak yang terbaca 1 cm (Kuning)
<img src = "kelompok04\TUGAS-BAG2-KONDISI1.jpg" width="500px"><br>
* LED Green menyala jika jarak yang terbaca 2 cm (Magenta)
<img src = "kelompok04\TUGAS-BAG2-KONDISI2.jpg" width="500px"><br>
* LED Red menyala jika jarak yang terbaca 3 cm (Tosca)
<img src = "kelompok04\TUGAS-BAG2-KONDISI3.jpg" width="500px"><br>
* LED menyala semua dan berkedip kedip selama 1 detik jika jarak melebihi dari 3 cm (Warna Putih)<br>
<img src = "kelompok04\TUGAS-BAG2-KONDISI4.jpg" width="500px"><br>
Hasil Simulasi : Video dokumentasi hasil tugas [klik disini](https://drive.google.com/file/d/17mXgQfOZKFlxSEZRTS3sIKIfm2ZeYb-n/view?usp=sharing)