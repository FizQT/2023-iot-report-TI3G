# LAPORAN PRAKTIKUM  
# Anggota Kelompok
1. Gustania Nirmala Meisi (10)
2. Rosis Hudaya Putra (16)
3. Safira Istifarini (17)<br>
## <b>Implementasi Sensor Suhu dan Kelembapan<b>
<br>

# <b>Praktikum Wokwi</b>
<br>
1. Membuat rangkaian Wokwi seperti berikut ini :
 <br>
 <img src = "kelompok04\hasil2.png"><br>

2. Memasukkan kode program pada code editor wokwi
```cpp 
const int DHT_PIN = 15; //mendefinisikan pin digital yang digunakan DHT22 DHTesp dhtSensor; //objek dhtSensor untuk membaca suhu dan kelembaban dari sensor

void setup() { Serial.begin(115200); dhtSensor.setup(DHT_PIN, DHTesp::DHT22); //inisialisasi sensor DHT22 }

void loop() { TempAndHumidity data = dhtSensor.getTempAndHumidity(); Serial.println("Temp: " + String(data.temperature, 2) + "°C"); Serial.println("Kelembapan: " + String(data.humidity, 1) + "%"); Serial.println("---"); delay(1000); }
```
3. Hasil Ketika dijalankan : 

 <br>
 <img src = "kelompok04\hasil1.png"><br>
<br>

 # <b>Praktikum Membaca data suhu dan kelembaban udara di NodeMCU</b>
 <br>

1. Buat project dengan nama vs-program
2. Tentukan board yang digunakan, dengan mengetik esp8266 kemudian pilih yang Espressif ESP8266 EFSP-12E
Untuk lokasi penyimpanan project disesuaikan dengan kebutuhan Anda.
3. Tunggu beberapa saat sampai dibuat struktur project oleh Visual Studio Code. Kemudian tambahkankan beberapa konfigurasi pada file platform.ini
<br>

```cpp
lib_deps =
    adafruit/DHT sensor library@^1.4.1
    adafruit/Adafruit Unified Sensor @ ^1.1.4

monitor_speed = 115200
```
4. Tambahkan baris kode untuk inisialisasi dan menambahkan fungsi sensor seperti di bawah ini

```cpp
#include <Arduino.h>
#include <DHT.h>

#define DHTTYPE DHT11

DHT dht(D7, DHTTYPE);
```
5. Tambahkan kode baris pada fungsi setup() untuk melakukan konfigurasi agar baudrate di serial monitor menjadi 11500.

```cpp
Serial.begin(115200);
Serial.println("Menggunakan DHT11");
```
6. Yang terakhir, tambahkan kode untuk menampilkan data hasil pembacaan sensor pada fungsi loop().

```cpp
delay(2000);
float h = dht.readHumidity();
float t = dht.readTemperature();
float f = dht.readTemperature(true);

if (isnan(h) || isnan(t) || isnan(f))
{
  Serial.println("Failed to read from DHT sensor!");
  return;
}

float hif = dht.computeHeatIndex(f, h);
float hic = dht.computeHeatIndex(t, h, false);

Serial.print(F("Humidity: "));
Serial.print(h);
Serial.print(F("%  Temperature: "));
Serial.print(t);
Serial.print(F("°C "));
Serial.print(f);
Serial.print(F("°F  Heat index: "));
Serial.print(hic);
Serial.print(F("°C "));
Serial.print(hif);
Serial.println(F("°F"));
```
7. Hasil alat : 

<br>
 <img src = "kelompok04\prak.jpg"><br>
<br>

8. Hasil Simulasi :

<br>
<video width="320" autoplay loop muted>
  <source src="kelompok04\prak1.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
<br>
<br>

9. Membuat rangkaian Wokwi seperti berikut ini :

 <br>
 <img src = "kelompok04\hasil2.png"><br>
<br>

10. Menambahkan kode program pada kode editor wokwi:

```cpp 
const int DHT_PIN = 15; //mendefinisikan pin digital yang digunakan DHT22 
DHTesp dhtSensor; //objek dhtSensor untuk membaca suhu dan kelembaban dari sensor

void setup() { 
    Serial.begin(115200); dhtSensor.setup(DHT_PIN, DHTesp::DHT22); //inisialisasi sensor DHT22 
    }

void loop() { TempAndHumidity data = dhtSensor.getTempAndHumidity(); 
Serial.println("Temp: " + String(data.temperature, 2) + "°C"); 
Serial.println("Kelembapan: " + String(data.humidity, 1) + "%"); 
Serial.println("---"); 
delay(1000); 
}
```
11. Hasil Ketika dijalankan :

 <br>
 <img src = "kelompok04\hasil1.png"><br>
<br>

# <b>TUGAS</b>
<br>

1. Modifikasi baris kode pada bagian praktikum sehingga muncul data suhu dalam satuan Kelvin dan Reamur!
2. Buatlah simulasi sebuah alat pembaca suhu dan kelembaban udara di tengah kota dengan memanfaatkan lampu LED sebagai indikator dengan disertai keterangan data suhu dan kelembaban yang ditampilkan pada serial monitor!

    Contoh: Suhu pada sebuah kota dikategorikan dingin, normal, dan panas. Masing-masing kategori memiliki indikator lampu LED yang menyala, salah satunya ketika kategori dingin diwakili oleh LED hijau, normal diwakili oleh LED warna Biru, dan panas diwakili oleh LED warna Merah.

    Misalkan tidak memiliki LED RGB, silakan menggunakan LED build in NODEMCU.

3. Gambarkan skematik dari simulasi yang Anda buat.

4. Hasil dari simulasi tersebut silakan upload di youtube atau google drive dan urlnya disisipkan pada laporan Anda.

# <b> Jawaban</b>
<br>

1. Modifikasi baris kode pada bagian praktikum sehingga muncul data suhu dalam satuan Kelvin dan Reamur

  a. Rancangan Alat : 

  <br>
  <img src = "kelompok04\alat1.jpg"><br>
  <br>

  b. Kode Program : 

  <br>

  ```cpp
  #include <Arduino.h>
#include <SimpleDHT.h>

#define pinDHT 7 // SD3 pin signal sensor DHT

byte temperature = 0;
byte humidity = 0;

SimpleDHT11 dht11(D7); // instan sensor dht11

void KelembabanSuhu()
{
  int err = SimpleDHTErrSuccess;

  if ((err = dht11.read(&temperature, &humidity, NULL)) != SimpleDHTErrSuccess)
  {
    Serial.print("Pembacaan DHT11 gagal, err=");
    Serial.println(err);
    delay(1000);
    return;
  }

  Serial.print("Sample OK: ");
  Serial.print((int)temperature);

  Serial.print(" *C, ");
  Serial.print((int)humidity);
  Serial.print(" H, ");

  // Konversi ke satuan Kelvin
  float temperatureK = temperature + 273.15;
  Serial.print(temperatureK);
  Serial.print(" K, ");

  // Konversi ke satuan Reaumur
  float temperatureR = 4.0 / 5.0 * temperature;
  Serial.print(temperatureR);
  Serial.println(" Re");

  delay(1500);
}

void setup()
{
  Serial.begin(115200);
  Serial.println("Simple DHT");
  delay(1000);
}

void loop()
{
  KelembabanSuhu();
}
```

  c. hasil : 

<br>
<video width="320" autoplay loop muted>
  <source src="kelompok04\tugas1.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
<br>

<br>
2. simulasi sebuah alat pembaca suhu dan kelembaban udara di tengah kota dengan memanfaatkan lampu LED sebagai indikator dengan disertai keterangan data suhu dan kelembaban yang ditampilkan pada serial monitor

  a. Rancangan alat :

  <br>
  <img src = "kelompok04\tugas2.jpg"><br>
  <br>

  b. Kode program : 

  <br>

  ```cpp
#include <Arduino.h>
#include <SimpleDHT.h>

#define pinDHT 7 // SD3 pin signal sensor DHT

byte temperature = 0;
byte humidity = 0;
int ledDingin = D5;
int ledNormal = D6;
int ledPanas = D2;

SimpleDHT11 dht11(D7); // instan sensor dht11

void KelembabanSuhu()
{
  int err = SimpleDHTErrSuccess;

  if ((err = dht11.read(&temperature, &humidity, NULL)) != SimpleDHTErrSuccess)
  {
    Serial.print("Pembacaan DHT11 gagal, err=");
    Serial.println(err);
    delay(1000);
    return;
  }

  Serial.print("Suhu: ");
  Serial.print((int)temperature);
  Serial.print(" C, Kelembaban: ");
  Serial.print((int)humidity);
  Serial.println("%");

  if (temperature < 20)
  {
    digitalWrite(ledDingin, HIGH);
    digitalWrite(ledNormal, LOW);
    digitalWrite(ledPanas, LOW);
  }
  else if (temperature >= 20 && temperature <= 30)
  {
    digitalWrite(ledDingin, LOW);
    digitalWrite(ledNormal, HIGH);
    digitalWrite(ledPanas, LOW);
  }
  else
  {
    digitalWrite(ledDingin, LOW);
    digitalWrite(ledNormal, LOW);
    digitalWrite(ledPanas, HIGH);
  }

  delay(1000);
}

void setup()
{
  Serial.begin(115200);
  pinMode(ledDingin, OUTPUT);
  pinMode(ledNormal, OUTPUT);
  pinMode(ledPanas, OUTPUT);
  Serial.println("Alat Pembaca Suhu dan Kelembaban");
  delay(1000);
}

void loop()
{
  KelembabanSuhu();
}
```

  c. Hasil : 

 <br>
 <img src = "kelompok04\Tugas2.jpg"><br>
<br>

<br>
 <img src = "kelompok04\Tugas2.1.jpg"><br>
<br>

  d. Hasil Simulasi : 

<br>
<video width="320" autoplay loop muted>
  <source src="kelompok04\tugas2.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
<br>

<br>
3. Gambar Skematik dari Simulasi yang dibuat : 

 <br>
 <img src = "kelompok04\tugas3.jpg"><br>
<br>



