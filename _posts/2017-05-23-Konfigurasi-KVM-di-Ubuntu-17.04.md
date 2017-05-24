---
title: "Konfigurasi KVM di Ubuntu 16.04/17.04/17.10 64-bit"
layout: post
date: 2017-05-23 21:08
tag:
- Linux
- Ubuntu
- Android
comments: true
author: nurulfajar
---
KVM adalah sebuah virtualisasi berbasis hardware intel-v maupun AMD-v untuk sistem operasi Linux. KVM berguna saat kita menjalankan sebuah emulator, dimana performa dari emulator tsb akan dipondasikan oleh hardware yang ada. Terutama untuk pengguna IDE Android Studio di OS Linux, karena fitur *Intel Hardware Accelerated Execution Manager (Intel® HAXM)* tidak dapat dijalankan di OS Linux, maka penggantinya kita dapat menggunakan KVM ini.

**Requirements**:
+ Pastikan sudah meng-install JDK

**Step-1**
Cek processor kalian apakah support KVM atau tidak:
```
$ egrep -c '(vmx|svm)' /proc/cpuinfo
```
jika hasil outputnya *0* = tidak support.
jika hasil outputnya *1* atau lebih = support.

**Step-2**
Installasi KVM:
```
$ sudo apt-get install qemu-kvm libvirt-bin ubuntu-vm-builder bridge-utils
```

**Step-3**
Tambahkan username kalian ke grup libvirtd :
```
$ sudo adduser username libvirtd
```
lalu logout dan login kembali

**Step-4**
Install *mksdcard utility* untuk membuat AVD (Android Virtual Device) di Android Studio :
```
$ sudo apt-get install libstdc++6:i386 libgcc1:i386 zlib1g:i386 libncurses5:i386
```

**Step-5**
Verifikasi installasi:
```
$ virsh list --all

```
```
Id Name                 State
----------------------------------
$
```
jika hasilnya seperti diatas berarti installasi sukses.


**Optional**
<br />
install virt-manager
```
$ sudo apt-get install virt-manager
```

**Start the AVD from Android SDK Directly from Terminal**
<br />
Pastikan sudah membuat sebuah AVD, yang berbasis x86 Intel processor. Saya sarankan menggunakan *minimum* API 22.
<br />
Lalu masuk ke direktori SDK kalian. contoh disini direktori saya berada di /home/newjar/Android/Sdk/tools/. Lalu ketik perintah:

```
$ ./emulator -use-system-libs @nama-emulator -qemu -enable-kvm
```

*Done*
