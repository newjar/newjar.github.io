---
title: "How to Install Spotify Client on Fedora 25"
layout: post
date: 2017-04-13 11:39
tag:
- Linux
- Fedora
comments: true
author: nurulfajar
---

Since i moved my main linux distro from Ubuntu to Fedora, i'm felt a big different flavors. Ubuntu or Debian based distro is easy for software installation, but in fedora i feel a bit bleeding.

lets trying to install Spotify client on Fedora 25.

**Step-1**:
* Download the latest rpmfusion-nonfree-release-stable rpm from.
```
http://download1.rpmfusion.org/nonfree/fedora/
```

**Step-2**:
* Install rpmfusion-nonfree-release-stable rpm:
```
# rpm -Uvh rpmfusion-nonfree-release-stable*rpm
```

**Step-3**:
* Install lpf-spotify-client rpm package:
```
# dnf install lpf-spotify-client.
```

**Step-4**:
* Open app menu and search "lpf spotify-client", then add your user to lpf group (just click "OK"). And wait for Downloading Spotify client.

**Step-5**:
* Open terminal and follow command.
```
lpf install spotify-client
```
* Then click "OK" in pop up lpf dialog.

![File.png]({{images.baseurl}}/assets/images/spotify-fedora.png)