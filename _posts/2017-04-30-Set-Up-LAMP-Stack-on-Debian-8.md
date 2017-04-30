---
title: "Install LAMP Stack di Debian 8"
layout: post
date: 2017-04-30 18:56
tag:
- Networking
- Linux
- Debian
comments: true
author: nurulfajar
---
## Pengenalan
Apa sih LAMP itu?, LAMP adalah sekumpulan perangkat lunak yang terdiri dari Linux, Apache, MySQL database dan PHP. LAMP digunakan sebagai pondasi untuk membuat sebuah aplikasi berbasis web.
<br />
Pada tutorial ini saya menggunakan Debian 8 (Jessie).

## Requirements
* Pastikan sudah menginstall "Sudo" dan membuat user di group Sudo. karena default dari debian tidak memberikan perintah sudo.
* Sudah menginstall basic security packages seperti IPTables, Fail2Ban, dll.

## Step 1 - Update the System
Buka terminal lalu ketik:
```
$ sudo apt-get Update && sudo apt-get upgrade
```
## Step 2 - Install Apache
Install Apache web server:
```
$ sudo apt-get install apache2 apache2-doc
```
Jika sudah selesai, kalian dapat menge-check nya dengan membuka browser, lalu ketik: <span class="evidence">localhost</span>. hasilnya akan seperti ini:
![file.png]({{images.baseurl}}/assets/images/linux/localhost.png)

### Step 3 - Install and Secure MySQL
Install MySQL database:
```
$ sudo apt-get install mysql-server php5-mysql
```
Ditengah proses install nanti akan muncul pop-up dialog untuk meng-input password untuk akses **root MySQL**.
![file.png]({{images.baseurl}}/assets/images/linux/mysql-pass.png)

isi sesuai keinginan lalu "Tab" > Enter.

## Step 3-2
Configure secure mysql installation:
```
$ sudo mysql_secure_installation
```
```
Change the root password? [Y/n]: n
```
```
Remove anonymouse users? [Y/n]: Y
```
```
Remove test database and access to it? [Y/n]: Y
```
```
Reload privilege tables now? [Y/n]: Y
```
proses installasi MySQL selesai.

## Step 4 - Install PHP
```
$ sudo apt-get install php5-common libapache2-mod-php5 php5-cli
```

## Step 5 - Restart Apache service
```
$ sudo systemctl restart apache2
```
Done.

Untuk direktori publik web apache, kalian dapat mengaksesnya di <span class="evidence">/var/www/html/</span>.
