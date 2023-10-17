# Jarkom-Modul-2-I08-2023

Nama Anggota | NRP
------------------- | --------------		
Mardhatillah Shevy Ananti | 5025211070
Kirana Alivia Enrico | 5025211190

## Soal-1
Yudhistira akan digunakan sebagai DNS Master, Werkudara sebagai DNS Slave, Arjuna merupakan Load Balancer yang terdiri dari beberapa Web Server yaitu Prabakusuma, Abimanyu, dan Wisanggeni. Buatlah topologi.

### Explanation 
- Make the topology based on the 4th picture in the Google Drive.
- Make Yudhistira node as the DNS Master.
- Make Werkudara as the DNS Slave.
- Make Arjuna node as the Load Balancer that consist of several web servers which are Abimanyu, Prabakusuma, and Wisanggeni.
- Ping google on each node to check wether it is already connected to Pandudewanata.

## Soal-2
Buatlah website utama pada node arjuna dengan akses ke arjuna.yyy.com dengan alias www.arjuna.yyy.com dengan yyy merupakan kode kelompok.

### Explanation 
- Open the arjuna file in yudhistira with syntax :
  ``` nano /etc/bind/jarkom/arjuna.I08.com  ```
- Fill it like below
- Save the file
- Ping www.arjuna.I08.com in client Nakula and Sadewa

## Soal-3
Dengan cara yang sama seperti soal nomor 2, buatlah website utama dengan akses ke abimanyu.yyy.com dan alias www.abimanyu.yyy.com.

### Explanation
- Open the abimanyu file in yudhistira with syntax :
  ``` nano /etc/bind/jarkom/abimanyu.I08.com ```
- Fill it like below
- Save the file
- Ping www.abimanyu.I08.com in client Nakula and Sadewa

## Soal-4
Kemudian, karena terdapat beberapa web yang harus di-deploy, buatlah subdomain parikesit.abimanyu.yyy.com yang diatur DNS-nya di Yudhistira dan mengarah ke Abimanyu.

### Explanation
- Open the abimanyu file in yudhistira with syntax :
  ``` nano /etc/bind/jarkom/abimanyu.I08.com ```
- Fill it like below, insert parikesit subdomain in that file
- Ping the parikesit subdomain in client Nakula and Sadewa with this syntax :
  ``` ping parikesit.abimanyu.I08.com -c 5 ```

## Soal-5
Buat juga reverse domain untuk domain utama. (Abimanyu saja yang direverse)

## Soal-6
Agar dapat tetap dihubungi ketika DNS Server Yudhistira bermasalah, buat juga Werkudara sebagai DNS Slave untuk domain utama.

## Soal-7
Seperti yang kita tahu karena banyak sekali informasi yang harus diterima, buatlah subdomain khusus untuk perang yaitu baratayuda.abimanyu.yyy.com dengan alias www.baratayuda.abimanyu.yyy.com yang didelegasikan dari Yudhistira ke Werkudara dengan IP menuju ke Abimanyu dalam folder Baratayuda.

## Soal-8
Untuk informasi yang lebih spesifik mengenai Ranjapan Baratayuda, buatlah subdomain melalui Werkudara dengan akses rjp.baratayuda.abimanyu.yyy.com dengan alias www.rjp.baratayuda.abimanyu.yyy.com yang mengarah ke Abimanyu.
