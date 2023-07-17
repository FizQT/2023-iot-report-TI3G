<<<<<<< HEAD
**PERTEMUAN 7**
=======
**PERTEMUAN 6**
>>>>>>> 84ad84f70ba8d6bc0f4ab9424ec0ae52e676d7a3

Nama Kelompok : 
1. Ah Maulidi Rifki MD (01)
2. Dawam Ilhami Assidiqi (05)
3. Hafizh Izhar Darmansyah (11)
4. M. Fairuz Zakaria Firdaus (14)

**Praktikum**<br>
<<<<<<< HEAD

1. Praktikum 1 - Membaca data intensitas cahaya - WOKWI WEB<br>
Kode Program :
```
#define sensorLDR 34
int nilaiSensor;


void setup() {
  // put your setup code here, to run once:
  Serial.begin(115200);
  Serial.println("Contoh Penggunaan Sensor LDR");
  delay(3000);
}


void loop() {
  // put your main code here, to run repeatedly:
  nilaiSensor = analogRead(sensorLDR);
  Serial.print("Nilai Sensor : ");
  Serial.println(nilaiSensor);
  delay(1000);
}
```
Skema dan Hasil:<br>
<img src="Kelompok6/Skema Hasil.jpg" width="400px">
<br>

2. Praktikum 2 - Membaca data jarak benda - WOKWI WEB<br>
Kode Program :
```
#define triggerPin 32
#define echoPin 33

void setup() {
  // put your setup code here, to run once:
   Serial.begin (115200);
   pinMode(triggerPin, OUTPUT);
   pinMode(echoPin, INPUT);
   pinMode(BUILTIN_LED, OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
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
<br>
Skema dan Hasil:<br>
<img src="Kelompok6/Skema Hasil 2.jpg" width="400px">
<br>

**TUGAS**<br>

Kode Program :<br>
=======
Kode Program :
```
#include <Arduino.h>
    #include <SimpleDHT.h>

    #define pinDHT 7 // SD3 pin signal sensor DHT

    byte temperature = 0;
    byte humidity = 0;

    SimpleDHT11 dht11(D7); //instan sensor dht11

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
        Serial.println(" H");

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

<img src="Kelompok6/DHT11.jpeg" width="400px">

**KESIMPULAN**<br>

-	Kesimpulan yang didapat setelah melakukan praktikum kelompok kami telah mengetahui cara kerja sensor DHT11. 
-	Cara kerja DHT11, DHT11 adalah sebuah sensor yang mana memiliki sebuah sensor suhu resistansi. Ketika suhu berubah, resistansi sensor suhu juga berubah, sehingga arus listrik yang mengalir melalui sensor juga berubah. Nilai suhu kemudian dapat dihitung berdasarkan perubahan resistansi yang terjadi.
-	Dan DHT11 juga memiliki sebuah sensor kelembapan kapastitif, yang mengukur perubahan kapasitansi pada elemen kapasitor di dalam sensor. Kapasitansi ini dipengaruhi oleh jumlah uap air dalam lingkungan sekitar sensor. Semakin banyak uap air, semakin tinggi kapasitansi dan semakin rendah resistansi yang terukur. Nilai kelembaban kemudian dapat dihitung berdasarkan perubahan kapasitansi yang terjadi.
-	Sensor DHT11 mengirimkan sinyal digital ke mikrokontroler, berupa data suhu dan kelembaban dalam bentuk sinyal pulsa dengan lebar pulsa yang bervariasi sesuai dengan nilai suhu dan kelembaban yang terukur. Sinyal pulsa ini kemudian diterjemahkan oleh mikrokontroler untuk mendapatkan nilai suhu dan kelembaban yang akurat.
-	Kelompok kami juga telah mengetahui cara kerja analogRead. analogRead() adalah fungsi pada platform mikrokontroler Arduino yang digunakan untuk membaca nilai tegangan analog dari suatu pin input pada mikrokontroler.
-	Cara kerja analogRead menggunakan converter analog ke digital (ADC) untuk mengubah nilai tegangan analog menjadi nilai digital yang dapat diolah oleh mikrokontroler. Jadi Ketika fungsi analogRead() dipanggil pada program Arduino, mikrokontroler memilih pin input yang akan dibaca dan mengukur tegangan analog pada pin tersebut.
-	Dalam penggunaan analogRead(), juga perlu diperhatikan bahwa tegangan input harus sesuai dengan rentang tegangan yang dapat diukur oleh ADC pada Arduino, yaitu 0 hingga 5 volt. Juga, nilai yang diter

**TUGAS**<br>

1.	Modifikasi baris kode pada bagian praktikum sehingga muncul data suhu dalam satuan Kelvin dan Reaumur!
>>>>>>> 84ad84f70ba8d6bc0f4ab9424ec0ae52e676d7a3
```
#include <Arduino.h>
#include <SimpleDHT.h>

<<<<<<< HEAD
// esp LED
#define RED D1
#define BLUE D2

// LDR
#define sensorLDR A0
int nilaiSensor;

// DHT11
#define pinDHT 7
SimpleDHT11 dht11(D7);

byte temperature = 0;

void setup()
{
  Serial.begin(115200);
  pinMode(BLUE, OUTPUT);
  pinMode(RED, OUTPUT);
}

void cekDHT()
{
  // cek DHT11
  int err = SimpleDHTErrSuccess;

  if ((err = dht11.read(&temperature, &humidity, NULL)) != SimpleDHTErrSuccess)
  {
    Serial.print("Pembacaan DHT11 gagal, err=");
    Serial.println(err);
    delay(1000);
    return;
  }
=======
#define pinDHT 5 // SD3 pin signal sensor DHT

byte temperature = 0;
byte humidity = 0;

SimpleDHT11 dht11(D5); //instan sensor dht11

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

    // Convert temperature to Kelvin
    float temperatureK = (float)temperature + 273.15;
    Serial.print(" Kelvin, ");

    // …
    delay(1500);
}

void setup()
{
    pinMode(RED_PIN, OUTPUT);
    pinMode(GREEN_PIN, OUTPUT);
    pinMode(BLUE_PIN, OUTPUT);

    
    Serial.begin(115200);
    Serial.println("Simple DHT");
    delay(1000);
>>>>>>> 84ad84f70ba8d6bc0f4ab9424ec0ae52e676d7a3
}

void loop()
{
<<<<<<< HEAD

  cekDHT();
  float celsius = (float)temperature;

  // mengambil data cahaya
  nilaiSensor = analogRead(sensorLDR);

  // print informasi sensor cahaya dan suhu
  Serial.print("Temp: ");
  Serial.print(celsius);
  Serial.println("°C");

  Serial.print("Nilai Sensor Cahaya : ");
  Serial.println(nilaiSensor);
  Serial.println("-------------------------");

  // - Ketika cahaya redup dan suhu kategori dingin maka LED warna biru akan berkedip-kedip.
  if (nilaiSensor >= 1000 && celsius <= 30)
  {
    for (int x = 0; x < 3; x++)
    {
      digitalWrite(BLUE, HIGH); // LED kondisi 1 nyala
      delay(1500);              // delay selama 150ms
      digitalWrite(BLUE, LOW);  // LED mati
      delay(1000);              // delay selama 100ms
    }
  }
  // - Ketika cahaya terang dan suhu tergolong tinggi, LED merah akan menyala.
  else if (nilaiSensor <= 1000 && celsius >= 30)
  {
    digitalWrite(RED, HIGH); // LED kondisi 2 dinyalakan
  }
  else
  {
    digitalWrite(RED, LOW);
    digitalWrite(BLUE, LOW);
  }
  delay(1000);
}
```

Hasil :<br>
<img src="Kelompok6/Skema Tugas.jpg" width="400px">
=======
    KelembabanSuhu();
}
```
2. Skema <br>
<img src="Kelompok6/Skema Tugas.jpg" width="400px">

3. Hasil<br>
Link video :
https://drive.google.com/file/d/1h03_YnQT-We-b8mYA2plPnZ0U-gtxVMA/view?usp=sharing
>>>>>>> 84ad84f70ba8d6bc0f4ab9424ec0ae52e676d7a3
