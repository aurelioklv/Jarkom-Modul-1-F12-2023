# Jarkom-Modul-1-F12-2023

| Nama | NRP |
| ----------- | ----------- |
| Aurelio Killian Lexi Verrill | 5025211126 |
| Rano Noumi Sulistyo | 5025211185 | 

## 1. Lorem ipsum dolor sit amet
## 2. Lorem ipsum dolor sit amet
## 3. Lorem ipsum dolor sit amet
## 4. Lorem ipsum dolor sit amet
## 5. Lorem ipsum dolor sit amet
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

