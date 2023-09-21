# Jarkom-Modul-1-B05-2023

### Praktikum Jarkom Modul 1
Group Members:
1. Keysa Anadea (5025211028)
2. 
   
### Question 1 
User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.
a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 
b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 
c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
### Answer 1
#### 1a dan 1b
Untuk mengerjakan soal no 1 a dan b, hal yang pertama dilakukan adalah menggunakan filter FTP. setelah itu dalam soal diberikan instruksi bahwa salah satunya adalah menggunggah suatu file.

![image](https://github.com/keysanadea/Jarkom-Modul-1-B05-2023/assets/88714452/da946a8d-b568-4d54-83a9-902d3bcec7d1)

setelah itu kita akan mencari info yang requestnya menggunggah file atau STOR. yang terdapat pada no 147 setelah itu kita double tap dua kali serta drop down di transmission control dan protocol dan dapat sequence number raw dan acknowledge number raw.

![image](https://github.com/keysanadea/Jarkom-Modul-1-B05-2023/assets/88714452/7897566c-240b-4445-a238-b88dbbc89acf)

#### 1c dan 1d
pada c dan d juga memiliki konsep sama hanya saja yang dicari adalah packet yang menunjukan response dari aktivitas tersebut berarti kita ambil packet no setelah 147 yang merupakan response dari aktivitas STOR di n 147.

![image](https://github.com/keysanadea/Jarkom-Modul-1-B05-2023/assets/88714452/c421d110-d3e1-4485-ab3a-2f9ab640a89d)

### Question 2 
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!
### Answer 2
Langkah pertama adalah membuka file capture di Wireshark. Setelah itu, kita menggunakan filter berikut ini di bagian atas layar atau panel "Display Filter" untuk menyaring paket-paket sesuai perintah soal yang ingin dicari: frame contains “Jarkom” setelah itu jika di follow TCP Streamnya akan menunjukkan web server yang digunakan.
![image](https://github.com/keysanadea/Jarkom-Modul-1-B05-2023/assets/88714452/25155852-929b-47e1-9cca-01f7a4ab351c)
![image](https://github.com/keysanadea/Jarkom-Modul-1-B05-2023/assets/88714452/cfd5ae61-989c-4989-9b80-6a99f103ba33)

### Question 3
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
a. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
b. Protokol layer transport apa yang digunakan?
### Answer 3
#### 3a
Langkah pertama adalah membuka file capture di Wireshark. Setelah itu, kita menggunakan filter berikut ini di bagian atas layar atau panel "Display Filter" untuk menyaring paket-paket sesuai perintah soal yang ingin dicari: (ip.src == 239.255.255.250 && udp.srcport == 3702) || (ip.dst == 239.255.255.250 && udp.dstport == 3702). Filter ini akan menampilkan daftar paket yang memiliki alamat IP sumber atau tujuan 239.255.255.250 dan port 3702.

![image](https://github.com/keysanadea/Jarkom-Modul-1-B05-2023/assets/88714452/9d0b7a58-1ecc-4fcb-a8db-be6d27f71009)

#### 3b
Pada screenshot diatas juga dapat dilihat bahwa sudah tertera jelas untuk protocol yang digunakan adalah UDP

### Question 4
Berapa nilai checksum yang didapat dari header pada paket nomor 130?
### Answer 4
- membuka file soal di wireshark
- klik kanan pada bagian protocol dari paket no.130
- setelah itu akan terdapat checksum yaitu 0x18e5
- masukkan ncat 10.21.78.111 13591 terminal
![image](https://github.com/keysanadea/Jarkom-Modul-1-B05-2023/assets/88714452/74d80a8b-3053-429b-bdd0-26f88e73ddbd)

### Question 5
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
- Berapa banyak packet yang berhasil di capture dari file pcap tersebut?
- Port berapakah pada server yang digunakan untuk service SMTP?
- Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?
### Answer 5
Pada no 5, kita diminta menganalisis file packet capture berupa zipfile yang memerlukan password untuk membukanya dimana isi dari zipfile tersebut adalah command pada terminal kita bisa memperoleh password dari file soal yang dibuka di wireshark dengan cara membuka salah satu info dengan follow ke TCP Stream, setelah itu kita akan meperoleh password yang perlu decode ke Base64

![image](https://github.com/keysanadea/Jarkom-Modul-1-B05-2023/assets/88714452/321a527a-8707-46cb-9bc8-f5bd8025aec2)

sehingga diperoleh password untuk membuka zipfile adalah “5implePas5word”, setelah zipfile terbuka, kita bisa memasukkan instance ke terminal

![image](https://github.com/keysanadea/Jarkom-Modul-1-B05-2023/assets/88714452/1a80598f-f5af-4fdf-aa7b-3e42d5f7a1ef)

untuk soal a, banyak paket yang tercapture adalah 60

![image](https://github.com/keysanadea/Jarkom-Modul-1-B05-2023/assets/88714452/82c2ea4c-013f-477f-860c-1286d1322d8a)

untuk soal b, port yang digunakan untuk service SMTP

![image](https://github.com/keysanadea/Jarkom-Modul-1-B05-2023/assets/88714452/0a31cb33-0468-4c0f-8d23-25ec67fbc6ad)

untuk soal c, public IP, adalah ip diluar
- 10.0.0.0 — 10.255.255.255
- 172.16.0.0 — 172.31.255.255
- 192.168.0.0 — 192.168.255.255
