---
title: "Remove 'System Program Problem Detected Message' From Ubuntu"
layout: post
date: 2017-05-30 21:11
tag:
- Ubuntu
comments: true
author: nurulfajar
---
Bagi para *user* Ubuntu, pastinya udah nggak asing lagi sama yang namanya message/notif "*System program problem detected*" terus ada pesan tambahan "*Do you want to report the problem now?*". Sebenarnya message ini bertujuan agar *bug* yang baru saja terjadi dapat kita laporkan ke developer Ubuntu itu sendiri. Dan awalnya sih saya rajin *report* bug sana sini, namun lama kelamaan kok ganggu juga ya, Haha. Yaudah mending kita remove aja. *maap mbah canonical*.

**Step-1:**
<br />
Buka terminal lalu ketik:
```
$ sudo rm /var/crash/*
```

**Step-2:**
<br />
Disable apport service (ini service si *problem* detektor)
```
$ sudo gedit /etc/default/apport
```
```
# set this to 0 to disable apport, or to 1 to enable it
# you can temporarily override this with
# sudo service apport start force_start=1
enabled=1
```
Ubah pada bagian *enabled=1* menjadi *enabled=0*
```
# set this to 0 to disable apport, or to 1 to enable it
# you can temporarily override this with
# sudo service apport start force_start=1
enabled=0
```
Save and close the file.

**Step-3:**
<br />
Terakhir, stop apport service:
```
$ sudo systemctl stop apport
```
*Done*
