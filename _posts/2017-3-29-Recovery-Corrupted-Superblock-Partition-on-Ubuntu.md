---
title: "Recovery Corrupted Superblock Partition on Ubuntu"
layout: post
tag:
- linux
- partition
comments: true
author: nurulfajar
---

Hari ini ketika saya menyalakan Komputer tiba-tiba saja Ubuntu saya gagal booting.   
Terdapat pesan `Input/output` error disusul dengan pesan error `Corrupted Superblock Partition Ext4` dan beberapa pesan error lainnya.   
Langsung saja ke cara memperbaikinya :

* ### Requirement :
* USB Bootable / Live CD Ubuntu (Sesuaikan dengan versi yang dipakai).

* ### How -to :
1. Booting kedalam Live USB / Live CD Ubuntu.
2. Buka Terminal.
3. lalu ketik
```
sudo fdisk -l /dev/sda
```
4. cek letak partisi Ext4 atau files system. contoh disini partisi saya ada di table **sda5**.
5. ```
sudo mke2fs -n /dev/sda5
```
Akan muncul status seperti ini:   
Superblock backups stored on blocks:
32768, 98304, 163840, 229376, 294912 ...
6. Pilih salah satu block yang ada, Lalu restore kembali. Disini saya menggunakan block pertama yaitu “32768”.
```
sudo e2fsck -b 32768 /dev/sda5 -y
```

Tunggu proses sampai selesai, lalu Reboot.  
