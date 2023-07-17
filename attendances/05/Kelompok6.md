<<<<<<< HEAD
**PERTEMUAN 6**
=======
**PERTEMUAN 5**
>>>>>>> 84ad84f70ba8d6bc0f4ab9424ec0ae52e676d7a3

Nama Kelompok : 
1. Ah Maulidi Rifki MD (01)
2. Dawam Ilhami Assidiqi (05)
3. Hafizh Izhar Darmansyah (11)
4. M. Fairuz Zakaria Firdaus (14)

<<<<<<< HEAD
**Praktikum**<br>
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
```
#include <Arduino.h>
#include <SimpleDHT.h>

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
=======
**Praktikum**

1. Project 1: Running LED RGB
Kode Program :
```#include <Arduino.h>

    #define RED_LED D5 //led warna merah
    #define GREEN_LED D6 //led warna hijau
    #define BLUE_LED D7 //led warnah biru

    void setup() {
    Serial.begin(115200);
    pinMode(RED_LED,OUTPUT);//atur pin-pin digital sebagai output
    pinMode(GREEN_LED,OUTPUT);
    pinMode(BLUE_LED,OUTPUT);
    Serial.println("Contoh Program LED RGB");
    }

    void rgbLED(){
    digitalWrite(RED_LED, HIGH); 
    digitalWrite(GREEN_LED, LOW); 
    digitalWrite(BLUE_LED, LOW); 
    Serial.println("LED Merah nyala"); 
    delay(1000); 

    digitalWrite(RED_LED, LOW); 
    digitalWrite(GREEN_LED, HIGH); 
    digitalWrite(BLUE_LED, LOW); 
    Serial.println("LED Hijau nyala"); 
    delay(1000); 

    digitalWrite(RED_LED, LOW); 
    digitalWrite(GREEN_LED, LOW); 
    digitalWrite(BLUE_LED, HIGH); 
    Serial.println("LED Biru nyala"); 
    delay(1000);
    }

    void loop() {
    rgbLED();
    }
```

## Dokumentasi Hasil
https://github.com/FizQT/testestes/assets/93257683/b3e082a7-c954-4dc0-9a50-85d22918a3bc


2. Project 2: SOS LED
Kode Program :
```
#include <Arduino.h>

#define RED_LED D5   //led warna merah
#define GREEN_LED D6 //led warna hijau
#define BLUE_LED D7  //led warnah biru

void setup()
{
  Serial.begin(115200);
  pinMode(RED_LED, OUTPUT); //atur pin-pin digital sebagai output

  Serial.println("Contoh Program LED SOS");
>>>>>>> 84ad84f70ba8d6bc0f4ab9424ec0ae52e676d7a3
}

void loop()
{
<<<<<<< HEAD
    KelembabanSuhu();
}
```
2. Skema <br>
<img src="Kelompok6/Skema Tugas.jpg" width="400px">

3. Hasil<br>
Link video :
https://drive.google.com/file/d/1h03_YnQT-We-b8mYA2plPnZ0U-gtxVMA/view?usp=sharing
=======
  // 3 dits (3 titik atau huruf S)
  for (int x = 0; x < 3; x++)
  {
    digitalWrite(RED_LED, HIGH); // LED nyala
    delay(150);                  // delay selama 150ms
    digitalWrite(RED_LED, LOW); // LED mati
    delay(100);                  // delay selama 100ms
  }
  delay(100);

  // 3 dahs (3 garis atau huruf O)
  for (int x = 0; x < 3; x++)
  {
    digitalWrite(RED_LED, HIGH); // LED nyala
    delay(400);                  // delay selama 400ms
    digitalWrite(RED_LED, LOW); // LED mati
    delay(100);                  // delay selama 100ms
  }

  // 100ms delay to cause slight gap between letters
  delay(100);
  // 3 dits again (3 titik atau huruf S)
  for (int x = 0; x < 3; x++)
  {
    digitalWrite(RED_LED, HIGH); // LED nyala
    delay(150);                  // delay selama 150ms
    digitalWrite(RED_LED, LOW); // LED mati
    delay(100);                  // delay selama 100ms
  }

  // wait 5 seconds before repeating the SOS signal
  delay(5000);
}
```

## Dokumentasi Hasil
https://github.com/FizQT/testestes/assets/93257683/dd801330-3f70-4c1d-8c93-328cfad56da3


**TUGAS**
Kode Program
```
#include <Arduino.h>

#define RED_LED D0   // LED merah
#define GREEN_LED_R D5  // LED hijau - merah
#define GREEN_LED_G D6  // LED hijau - hijau
#define GREEN_LED_B D7  // LED hijau - biru
#define BLUE_LED D4  // LED biru

void setup() {
  Serial.begin(115200);
  pinMode(RED_LED, OUTPUT);
  pinMode(GREEN_LED_R, OUTPUT);
  pinMode(GREEN_LED_G, OUTPUT);
  pinMode(GREEN_LED_B, OUTPUT);
  pinMode(BLUE_LED, OUTPUT);
  Serial.println("Contoh Program LED SOS");
}

void loop() {
  // 3 dits (3 titik atau huruf S)
  for (int x = 0; x < 3; x++) {
    digitalWrite(RED_LED, HIGH);
    delay(150);
    digitalWrite(RED_LED, LOW);
    delay(100);
  }
  delay(100);

  for (int x = 0; x < 3; x++) {
    // blink green LED in RGB format
    analogWrite(GREEN_LED_R, 0); // set red color to maximum
    analogWrite(GREEN_LED_G, 255);   // set green color to minimum
    analogWrite(GREEN_LED_B, 0);   // set blue color to minimum
    delay(400);
    analogWrite(GREEN_LED_R, 0);   // set red color to minimum
    analogWrite(GREEN_LED_G, 0);   // set green color to minimum
    analogWrite(GREEN_LED_B, 0);   // set blue color to minimum
    delay(100);
  }

  // 100ms delay to cause slight gap between letters
  delay(100);

  for (int x = 0; x < 3; x++) {
    digitalWrite(BLUE_LED, HIGH);
    delay(150);
    digitalWrite(BLUE_LED, LOW);
    delay(100);
  }

  delay(100);

  for (int x = 0; x < 3; x++) {
    digitalWrite(RED_LED, HIGH);
    delay(150);
    digitalWrite(RED_LED, LOW);
    delay(100);
  }

  // wait 5 seconds before repeating the SOS signal
delay(5000);
}
```

## Dokumentasi Hasil
https://github.com/FizQT/testestes/assets/93257683/dd801330-3f70-4c1d-8c93-328cfad56da3
>>>>>>> 84ad84f70ba8d6bc0f4ab9424ec0ae52e676d7a3
