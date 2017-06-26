---
title: "Skip All Yaourt Prompts on Arch Linux"
layout: post
date: 2017-06-26 12:47
tag:
- Linux
- Arch
comments: true
author: nurulfajar
---
Yaourt (mungkin) adalah tools terbaik untuk mendownload dan juga menginstall paket dari Arch User Repository, yang juga dikenal sebagai AUR. Selain *powerful*, paket yang ada di AUR juga sangat luas dan lengkap. Namun secara *default*, menginstall paket menggunakan Yaourt, meminta BANYAK konfirmasi untuk hal yang berbeda, misal seperti apakah kamu ingin mengedit PKGBUILD, dll. Akibatnya, Yaourt cukup mengganggu jika kamu terbiasa dengan sifat *hands-free*.
Berikut cara mengnon-aktifkan semua konfirmasi pada Yaourt:

**STEP-1:**
<br />
Buat file bernama <span class="evidence">.yaourtrc</span> didalam direktori /home/user/, lalu masukkan kode berikut:
<br />
{% gist newjar/f279dbc6b4e986c6b79d40d2e5e0d6bf %}

Pada kode baris pertama, berfungsi akan meng-*skip* atau melewati pesan yang mengkonfirmasikan paket yang ingin di install.

Kode baris kedua, akan melewatkan pesan yang menanyakan apakah kamu ingin melanjutkan *build* atau pembuatan paket tsb.

Kode baris ketiga dan terakhir akan melewatkan pesan yang menanyakan apakah kamu ingin mengedit file PKGBUILD.


*Done*
