---
title: "Set Up Virtual Host on Debian 8"
layout: post
date: 2017-04-30 20:00
tag:
- Networking
- Linux
- Debian
comments: true
author: nurulfajar
---

## Requirements
* Pastikan sudah menginstall LAMP Stack. Jika belum silahkan lihat di [Install LAMP Stack on Debian 8](https://newjar.github.io/Set-Up-LAMP-Stack-on-Debian-8/)

## Step 1 - Creating the Directory Structure
Direktori ini akan kita gunakan sebagai direktori utama di Virtual Host yang akan kita buat:
```
$ sudo mkdir -p /var/www/contohvirtual.com/public_html
```
```
$ sudo chown -R $USER:$USER /var/www/contohvirtual.com/public_html
```
```
$ sudo chmod -R 755 /var/www
```

## Step -2 Create Default pages
buat *index.html* untuk halaman *contohvirtual* yang kita buat:
```
$ nano /var/www/html/contohvirtual.com/public_html/index.html
```
Lalu buat seperti ini:
```
<html>
  <head>
    <title>contohvirtual.com!</title>
  </head>
  <body>
    <h1>Virtual Host contohvirtual.com berhasil dibuat!.</h1>
  </body>
</html>
```
Save and Exit atau **CTRL +x -> y -> Enter**.

## Step 3 - Create New Virtual Host Files
```
$ sudo cp /etc/apache2/sites-available/000-default.conf sudo cp /etc/apache2/sites-available/contohvirtual.com.conf
```
Edit *contohvirtual.com.conf*:
```
$ nano /etc/apache2/sites-available/contohvirtual.com.conf
```
Ubah pada bagian <span class="evidence">ServerAdmin dan DocumentRoot, serta tambahkan ServerName dan ServerAlias</span>
<br />
Hasilnya akan seperti ini:
```
<VirtualHost *:80>
        ServerAdmin admin@contohvirtual.com
        ServerName contohvirtual.com
        ServerAlias www.contohvirtual.com
        DocumentRoot /var/www/contohvirtual.com/public_html
        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```
Save and Exit atau **CTRL +x -> y -> Enter**.

## Step 4 - Enabling Virtual Host Files
Aktifkan Virtual Host yang baru kita buat:
```
$ sudo a2ensite contohvirtual.com.conf
```
Lalu disable *000-default.conf*
```
$ sudo a2dissite 000-default.conf
```
Restart Apache:
```
$ sudo systemctl restart apache2
```

## Step 5 - Setting Up Local Hosts File
Tambahkan IP local kalian pada files *Hosts* untuk Virtual Host yang kita buat:
```
$ sudo nano /etc/hosts
```
Lalu tambahkan (contoh):
```
192.168.85.134 contohvirtual.com
```
Save and Exit atau **CTRL +x -> y -> Enter**.

## Step 6 - Testing
Buka browser laku ketik: <span class="evidence">contohvirtual.com</span> pada tab url.
<br />
maka hasilnya akan seperti ini:
![file.png]({{images.baseurl}}/assets/images/linux/contohvirtual.com.png)

Untuk membuka Virtual Host pada Devices/Komputer lain yang berada di 1 jaringan local, kalian dapat mengaksesnya melalui browser dan ketik IP Virtual Host pada tab url.
Contoh:
![file.png]({{images.baseurl}}/assets/images/linux/contohvirtual.com-2.png)
