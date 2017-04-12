---
title: "Configure DHCP Server on Cisco Packet Tracer"
layout: post
comments: true
tag:
- Cisco
- Networking
author: nurulfajar
---
Konfigurasi DHCP Server menggunakan 1 buah router, switch dan hub.


* ### Buat topologi jaringan seperti gambar dibawah.

![file.png]({{site.baseurl}}/assets/images/cisco/topology-2.png)

* ### Konfigurasi IP server.

![file.png]({{site.baseurl}}/assets/images/cisco/setting-ip-server.png)

* Sesuaikan dengan konfigurasi yang ingin kita buat di router.


* ### Konfigurasi DHCP service pada server.

![file.png]({{site.baseurl}}/assets/images/cisco/setting-dhcp-server.png)

* Pada bagian `service`, ubah menjadi `on`.
* Pada bagian `Default Gateway`, isi sesuai default gateway.
* Lalu ubah `Start Ip Adress`, guna untuk menentukan dimulainya berapa ip address untuk client.
* Ubah juga `Maximum Ip Adress`, ini untuk menentukan berapa jumlah maximum ip address yang akan dibuat.
* Lalu klik `Save` and exit.

* ### Konfigurasi Ip & Subnetmask `fa` pada router.

![file.png]({{site.baseurl}}/assets/images/cisco/setting-router.png)

* Jika ingin membuat password untuk akses previledge, gunakan perintah `enable secret "password"`.

* ### Kemudian set ip masing2 client. Pada contoh ini PC0 & PC1 akan menggunakan Ip DHCP dari server, sedangkan PC2 & PC3 menggunakan Ip static dari router.

* Contoh PC0

![file.png]({{site.baseurl}}/assets/images/cisco/dhcp-PC0.png)

* Contoh CP2

![file.png]({{site.baseurl}}/assets/images/cisco/dhcp-PC2.png)

* ### Test ping ke server

![file.png]({{site.baseurl}}/assets/images/cisco/dhcp-PC2-ping.png)

Done.
