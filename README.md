# Jarkom-Modul-1-F12-2023

| Nama | NRP |
| ----------- | ----------- |
| Aurelio Killian Lexi Verrill | 5025211126 |
| Rano Noumi Sulistyo | 5025211185 | 

## 1. 
User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.
a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 
b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 
c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

Sequence number adalah adalah penghitung yang digunakan untuk melacak setiap byte yang dikirim ke luar oleh host. Sementara acknowledge number berisi sequance number dari byte berikutnya yang diharapkan oleh penerima pada koneksi 
Paket yang dispesifik oleh soal adalah paket yang melakukan aksi STOR, yang merupakan aksi upload dalam ftp. Setelah mencari protokol ftp dengan tersebut ditemukan upload zip c75_GrapThePhiser.
![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/f6e19bf6-1e84-4c86-ab32-a03cc2fff10b)  
Disini kita bisa lihat raw numbernya dengan liat detail packet
![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/16896318-e130-4519-aebb-34b4c8bcb4ce)  
![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/9bca1d89-cf36-4490-9bf0-338291acc7d4)  
![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/d0579735-4f55-45ca-9947-a2d0ea05d2d1)

## 2. 
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!
Dalam sebuah paket, detail terhadap web server yang digunakan oleh HTTP terletak dalam header nya, sehingga kita perlu melihat detail isi header untuk mengetahui server yang digunakan.
Pada no 2 kita cari di pcap web server yang digunakan disini kita cari dengan http.host lalu kita follow stream httpnya
![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/ac648486-21d8-409b-a669-2244eeda00b6)  
![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/c974f07e-873f-4a3b-a082-7ea8815ffdbe)  
![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/6640fee7-fa71-4306-a2ba-ac3ffc4bc8da)
Ditemukan server yang digunakan adalah gunicorn
## 3. Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
Protokol layer transport apa yang digunakan?
Disini kita langsung saja cari ip.addr – 239.255.255.250. berikut adalah filter yang dapat digunakan untuk mencari paket yang menggunakan ip spesifik,
Untuk portnya kita cek udp atau tcp, dikaternakan dalam penggunaan port berdasarkan layer transport yang biasanya menggunakan antara udp atau tcp. tidak ditemukan tcp sehingga menggunakan UDP untuk protocolnya
udp.port == 3702
![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/9ea8e461-ef04-4311-936c-a850a02b73da)  
![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/e1cd44ed-ccb0-4a1c-b7c9-aec7e3165eed)

## 4. Berapa nilai checksum yang didapat dari header pada paket nomor 130?
Checksum adalah nilai yang mewakili jumlah bit dalam pesan transmisi dan digunakan oleh para profesional IT untuk mendeteksi kesalahan dalam transmisi data
Kita perlu melihat isi dari paket yang ditulis untuk mendapatkannya.
Untuk no 4 kita langsung buka pcap dan scroll ke paket 130. Setelah itu kita cari detailnya sehingga ditemukan checksum paket(bukan header)

![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/99659fb5-ca0d-41e7-b18a-3eb48e4295d6)  
![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/8584bd47-9c75-41b7-9f60-e2dc4a9773eb)

## 5. Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
a. Berapa banyak packet yang berhasil di capture dari file pcap tersebut?
b. Port berapakah pada server yang digunakan untuk service SMTP?
c. Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

a. Disini kita buka pcap dan scroll ke paling bawah, ditemukan banyak paketnya 60. Wireshark otomatis menghitung jumlah semua paket.
b. kita cari server dengan cek port untuk smtp, dengan mancari paket dengan protocol SMTP dan melihat detailnya, port yang digunakan adalah 25. yang merupakan standard SMTP
c.  IP address dicari yang sesuai range public ip address 1.0.0.0 ke 223.255.255.255 yaitu 74.53.140.153 yang merupakan ip public dari 3 ip yang ditemukan.

![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/adc0d4a6-466f-4049-a642-c87bdf7d8275)  
![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/2007d75f-8983-4a81-8c44-98365ba06cea)  
Untuk netcat kita follow tcp streamnya. Dan kita temukan password untuk connect.txt . Kita decode than temu password 5implePas5word. Dan netcat nc 10.21.78.111 11111
![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/1ffc90de-08e5-4f70-8ceb-a67eaf7deda1)  
![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/e93a7c7b-e89f-4b38-81e3-3c8414a512fb)

## 6. Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "**server SOURCE ADDRESS 7812 is invalid**". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.
Clue:
- Kata-kata yang memuat huruf kapital: ["Seorang", "Udin", "Berteman", "SlameT", "Ia", "valoranT", "terdUga", "Sebuah", dan "Invalid"]. Huruf-huruf tersebut membentuk kata "SUBSTITUSI".
- "server SOURCE ADDRESS 7812 is invalid". Kata "**SOURCE ADDRESS**" ditulis dengan Uppercase. Ada kemungkinan bahwa pada source address merupakan sebuah pesan.
- "hasil pencarian hanya menampilkan a1 e5 u21". ```a1 e5 u21``` merupakan pasangan huruf dengan urutan abjad huruf tersebut.


Dari clue tersebut, diperkirakan bahwa kita harus mendekode source address menggunakan ```a1z26 cipher``` dengan partisi bilangannya sebagai beriku:   
104.18.14.101 menjadi ```10 4 18 14 10 1``` sehingga hasilnya adalah ```JDRNJA```  

![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/3741e222-00bb-4120-9498-0214cebeaadb)

## 7. Berapa jumlah packet yang menuju IP 184.87.193.88?
Paket yang menuju ip tersebut dapat dicari menggunakan display filter ```ip.dst == 184.87.193.88```. Kemudian dapat dilihat bahwa ada 6 paket yang memenuhi filter tersebut.  

![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/0b8635d4-505b-4679-94b5-d4b80a456ce8)  

![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/05016028-7f5f-4586-a2b9-4235dfc9b917)

## 8. Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)
```tcp.dstport == 80 || udp.dstport == 80```  

![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/09ad2fe4-f34d-48b8-a0f6-6aa42e0f95fd)

## 9. Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!
```ip.src == 10.51.40.1 && ip.dst != 10.39.55.34```  

![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/565354e3-8a26-4804-86be-c63d2846a5ed)

## 10. Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet
Disini kita buka pcap dan sort telnet, lalu kita cari dari packet yang memiliki detail password.
Telnet memiliki sifat systematis dalam login credentialsnya, untuk mendapatkan credentials harus mencari paket yang memiliki tulisan password: or login:, setelah ditemukan bisa kita follow stream nya. Dan ditemukan credentials sebagai berikut
Login = dhafin
Pasword = kesangannyak0k0S
![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/e87cba4b-d8d7-4624-a112-d1e4e0471ea1)  
![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/4ca3fa8a-b2f4-4781-8f1b-cf2825aa7921)  
![image](https://github.com/aurelioklv/Jarkom-Modul-1-F12-2023/assets/87407047/53909635-1e4a-4b9c-b8dd-1511909e96fc)
