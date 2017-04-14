---
title: "'thefuck' an Assistant Console Command For Linux"
layout: post
date: 2017-04-14 20:23
tag:
- Linux
comments: true
author: nurulfajar
---
*thefuck* adalah sebuah tools yang mampu mengoreksi perintah konsol sebelumnya jika terjadi kesalahan.
Menurut saya tools ini cukup *cool*, namun belum cukup *fungsional* untuk saya. Mungkin kedepannya akan lebih berguna.
Langsung saja ke-installation *thefuck*.

**Requirements:**
- Python (2.7+ or 3.3+)
- Pip
- Python-dev

**Step-1**:
- Install *thefuck*.
```
# dnf -y install python-pip python-devel
# dnf -y install thefuck
```
Pada case ini saya menggunakan distro fedora.
untuk distro lain silahkan lihat: [Disini](https://github.com/nvbn/thefuck/wiki/Installation){:target="_blank"}

**Step-2**:
- Tambahkan perintah berikut dibaris paling bawah pada file <span class="evidence">.bashrc, .zshrc</span> atau pada startup script lainnya yang kalian gunakan.
```
eval "$(thefuck --alias fuck)"
```
- Kalian bisa mengganti kata setelah *alias* dengan apa saja. contoh diatas: *fuck* *:trollface*.

- Close terminal dan buka kembali.

Contoh pengoreksian perintah:
![File.png]({{images.baseurl}}/assets/images/thefuck.png)

Kalian juga bisa menambahkan perintah pengoreksian tersendiri.
materi lengkapnya silahkan lihat: [Disini](https://github.com/nvbn/thefuck){:target="_blank"}
