# Anggota Kelompok
1. Dherisma Hanindita Utami (07)
2. Dilta Febiana (08)
3. Meliusa Nora Hariyanti (14)

# Pertanyaan
1. Apa yang telah kelompok Anda lakukan pada pertemuan kali ini?
    : Kelompok kami telah melakukan installasi dan konfigurasi aplikai arduino IDE dan mencoba menjalankan atau verify potongan kode program untuk mengecek error apa tidak serta menyambungkan port USB Node MCU dengan ESP8266 ke laptop. Lalu kami juga menginstall fritzing untuk mendesain yang digunakan oleh desainer, seniman, dan para penghobi elektronika untung perancangan berbagai peralatan elektronika.
    <!-- Bisa berisi potongan kode program atau output program, jelaskan maksud dari kode tersebut. Bisa berupa gambar, jika terdapat gambar silakan membuat folder yang berbeda dengan kelompok yang lain. -->
2. Apa ada kendala pada pertemuan kali ini, jika ada sebutkan!
    : Tidak ada kendala dalam praktikum saat ini
    
    <!-- Silakan sebutkan kendala, misalkan; terjadi error pada langkah, kemudian solusinya apa.  -->
3. Apa yang bisa kelompok Anda simpulkan pada pertemuan kali ini!
    :Dalam praktikum saat ini kami dapat melakukan instalasi dan konfigurasi software dan hardware, dapat menggunakan Arduino IDE, VS Code dan fritzing, kami juga dapat merangkai MCU dengan bebera sensor, dan akulator dan LCD dan kami dapat membuat kode sederhana MCU dan Writing

    <!-- Kesimpulan kelompok Anda! -->
4. Silakan mengerjakan tugas yang terdapat di jobsheet!


## TUGAS
1. Dari aktifitas hari ini, apakah yang telah kelompok Anda lakukan. sebutkan jika terjadi kendala dari aktifitas tersebut 
    : Kelompok kami telah melakukan installasi dan konfigurasi aplikai arduino IDE dan mencoba menjalankan atau verify potongan kode program untuk mengecek error apa tidak serta menyambungkan port USB Node MCU dengan ESP8266 ke laptop. Lalu kami juga menginstall fritzing untuk mendesain yang digunakan oleh desainer, seniman, dan para penghobi elektronika untung perancangan berbagai peralatan elektronika
    Tidak ada kendala yang terjadi pada praktikum saat ini
2. Buatlah sebuah skematik sederhana dari salah satu sensor atau aktuator yang telah kelompok Anda beli, boleh menggunakan Fritzing atau Wokwi.
    : 
```void setup() {
  // put your setup code here, to run once:
  Serial.begin(115200);
  Serial.println("Hello, ESP32!");
}

void loop() {
  // put your main code here, to run repeatedly:
  delay(10); // this speeds up the simulation
}
```

<br> <image src= "1.jpeg">


3. Buatlah kode sederhana untuk menyalakan LED merah bawaan node MCU seperti pada gambar di bawah ini


```void setup() {
  pinMode(LED_BUILTIN, OUTPUT); 
}

void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   // menyalakan LED merah
  delay(1000);                       // menunggu selama 1 detik
  digitalWrite(LED_BUILTIN, LOW);    // mematikan LED merah
  delay(1000);
}
```



### This is sample
Continually harness clicks-and-mortar methodologies through premier products. Interactively seize enabled meta-services without unique growth strategies. Compellingly procrastinate backward-compatible value through principle-centered ROI. Uniquely generate focused ideas whereas backward-compatible solutions. Conveniently morph high-payoff strategic theme areas for premium initiatives.

Seamlessly reintermediate compelling markets via diverse methods of empowerment. Assertively integrate cross-unit web services before cutting-edge best practices. Assertively drive efficient outsourcing vis-a-vis distinctive technologies. Distinctively deploy interdependent process improvements after functional infomediaries. Progressively integrate progressive leadership vis-a-vis enterprise channels.

Dynamically seize user-centric infrastructures rather than low-risk high-yield e-services. Competently exploit backend manufactured products through end-to-end deliverables. Credibly formulate B2C data after value-added infrastructures. Completely promote frictionless markets via adaptive core competencies. Credibly benchmark market positioning intellectual capital after inexpensive "outside the box" thinking.

Uniquely build optimal outsourcing whereas market positioning core competencies. Conveniently predominate cutting-edge benefits rather than business "outside the box" thinking. Intrinsicly innovate ethical relationships through cutting-edge meta-services. Energistically provide access to bleeding-edge products via cutting-edge infomediaries. Competently plagiarize best-of-breed value vis-a-vis quality e-business.

Assertively leverage existing cross-media partnerships without open-source value. Enthusiastically deploy impactful catalysts for change whereas stand-alone methods of empowerment. Progressively aggregate quality catalysts for change and B2C resources. Rapidiously simplify end-to-end process improvements whereas 2.0 alignments. Collaboratively seize parallel.