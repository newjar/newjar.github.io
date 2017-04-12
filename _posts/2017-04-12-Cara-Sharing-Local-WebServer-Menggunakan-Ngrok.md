---
title: Cara Sharing Local WebServer Menggunakan Ngrok
layout: post
date: 2017-04-12 10:31
tag:
- Networking
- Windows
- Linux
comments: true
author: nurulfajar
---

Sebelumnya kita kenalan dulu apa sih Ngrok itu?, Ngrok adalah multiplatform tunnelling, sebuah reverse proxy software yang mampu membuat sebuah local server menjadi public. Ngrok berbasis open source, kita bisa memodifikasinya sesuai kebutuhan. Source code-nya dapat diakses di [Github](https://github.com/inconshreveable/ngrok){:target="_blank"}.
Ngrok ini cukup membantu saya saat sedang ada project ataupun sekedar mengerjakan tugas.

Langsung saja kita praktekan cara kerja Ngrok.

**Requirement** :
- Internet.
- Localhost WebServer (pada case ini saya menggunakan XAMPP di Windows. Untuk di Linux/MacOS bisa menggunakan LAMP/MAMP).
- File Ngrok : [Download](https://ngrok.com/download){:target="_blank"}

**Step-1**
- Download file Ngrok (Sesuaikan dengan OS yang dipakai) lalu Extract.

![file.png]({{site.base}}/assets/images/ngrok/ngrok1.png)

**Step-2**
- Setelah di Extract, lalu masuk ke Direktorinya. Dan pastikan WebServer kalian sudah aktif.
Pada direktori Ngrok, tekan Shift + klik Kanan (untuk Windows) lalu pilih "Open command window here". untuk di Linux klik kanan lalu Open terminal here.

![file.png]({{site.baseurl}}/assets/images/ngrok/ngrok2.PNG)

**Step-3**
- Lalu ketik command, "ngrok.exe http (port)" pada case ini saya menggunakan port 8080 dari XAMPP. Kemudian kita akan mendapatkan alamat forwarding dari Ngrok, copy salah satu alamat tersebut dan paste di browser kalian.

![file.png]({{site.baseurl}}/assets/images/ngrok/ngrok3.png)
![file.png]({{site.baseurl}}/assets/images/ngrok/ngrok4.png)
Alamat yang diberikan Ngrok berhasil connect dengan Localhost XAMPP saya. Dengan begini kalian dapat mengakses alamat tsb dari devices lain. Baik dari jaringan local yang sama maupun jaringan publik.

Untuk materi lengkapnya kalian bisa langsung mengunjungi [Ngrok documents](https://ngrok.com/docs){:target="_blank"}
