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

### Explanation
- Make reverse file in yudhistira with this syntax :
  ``` nano /etc/bind/jarkom/3.232.192.in-addr.arpa   ```
- Restart server with this syntax : ``` service bind9 restart ```
- Ping reverse domain in client Nakula and Sadewa with this syntax :
  ``` host -t PTR 192.232.3.3  ```

## Soal-6
Agar dapat tetap dihubungi ketika DNS Server Yudhistira bermasalah, buat juga Werkudara sebagai DNS Slave untuk domain utama.

### Explanation
- Open local configuration in werkudara with this syntax : ``` nano /etc/bind/named.conf.local  ```
- Make werkudara as the DNS Slave domain
- Save the file
- Restart server with this syntax : ``` service bind9 restart ```
- Stop the bind9 in yudhistira with this syntax : ``` service bind9 stop ```
- Ping abimanyu.I08.com in client Nakula and Sadewa

## Soal-7
Seperti yang kita tahu karena banyak sekali informasi yang harus diterima, buatlah subdomain khusus untuk perang yaitu baratayuda.abimanyu.yyy.com dengan alias www.baratayuda.abimanyu.yyy.com yang didelegasikan dari Yudhistira ke Werkudara dengan IP menuju ke Abimanyu dalam folder Baratayuda.

### Explanation
- Open the configuration options in Yudhistira with this syntax : ``` nano /etc/bind/named.conf.options ```
- Add allow query and comment ``` dnssec-validation auto; ```
- Restart server with this syntax : ``` service bind9 restart ```
- Open the configuration options in werkudara with this syntax : ``` nano /etc/bind/named.conf.options ```
- Add allow query and comment ``` dnssec-validation auto; ```
- Restart server with this syntax : ``` service bind9 restart ```
- Make folder baratayuda in werkudara with this syntax : ``` mkdir /etc/bind/baratayuda ```
- Make file baratayuda.abimanyu.I08.com in wekudara with this syntax :
  ``` nano /etc/bind/baratayuda/baratayuda.abimanyu.I08.com  ```
- Restart server with this syntax : ``` service bind9 restart ```
- Ping www.baratayuda.abimanyu.I08.com in client Nakula and Sadewa

## Soal-8
Untuk informasi yang lebih spesifik mengenai Ranjapan Baratayuda, buatlah subdomain melalui Werkudara dengan akses rjp.baratayuda.abimanyu.yyy.com dengan alias www.rjp.baratayuda.abimanyu.yyy.com yang mengarah ke Abimanyu.

### Explanation
- Add the following subdomain in baratayuda.abimanyu.I08.com in werkudara
- Ping www.rjp.baratayuda.abimanyu.I08.com in client Nakula and Sadewa
