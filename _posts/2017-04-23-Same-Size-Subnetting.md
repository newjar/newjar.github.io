---
title: "Subnetting With FLSM and VLSM (wich better?)"
layout: post
date: 2017-04-23 14:35
tag:
- Networking
- Cisco
comments: true
author: nurulfajar
---
<figcaption class="caption">Contoh kasus</figcaption>
![File.png]({{images.baseurl}}/assets/images/cisco/Subnetting.PNG)

Contoh permasalahan pada subnetting kelas C :
<br />
IP Address : 192.168.69.0

## Subnetting dengan FLSM (Fixed Length Subnet Mask)
Cara subnetting dengan metode ini adalah dengan menggunakan 1 subnetmask / prefix saja (Same size).
* table FLSM:

**Network**|**Netmask**|**Net.ID**|**BC**|**Range IP**|**Host**
:--------:|:--------:|:--------:|:--------:|:--------:|:--------:
DHCP Server|255.255.255.224|.0|.31|.1-30|30
DHCP Router|255.255.255.224|.32|.63|.33-62|14
IP Static|255.255.255.224|.64|.95|.65-94|2

Kekurangan dari FLSM ini adalah, banyaknya IP address yang terbuang. Kita bisa melihat dari contoh table diatas, pada bagian Network IP Static hanya membutuhkan 2 Host (Total 4 address) saja, berarti ada sekitar 28 Host yang terbuang.

## Subnetting dengan VLSM (Variable Length Subnet Mask)
Cara kedua adalah dengan metode VLSM. disini kita tidak terikat lagi dengan satu prefix saja, kita dapat menyesuaikan prefix yang ingin digunakan sesuai dengan jumlah host yang dibutuhkan. Cara penyelesaiannya dengan mengurutkan kebutuhan host yang paling banyak.
* table VLSM:

**Network**|**Netmask**|**Net.ID**|**BC**|**Range IP**|**Host**
:-----:|:-----:|:-----:|:-----:|:-----:|:-----:
DHCP Server|255.255.255.224|.0|.31|.1-30|30
DHCP Router|255.255.255.240|.32|.47|.33-46|14
IP Static|255.255.255.252|.48|.51|.49-50|2

<br />
Untuk table prefix lengkapnya bisa dilihat [Disini](https://www.aelius.com/njh/subnet_sheet.html){:target="_blank"}
