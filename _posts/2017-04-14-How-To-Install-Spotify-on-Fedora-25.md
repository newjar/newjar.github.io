---
title: "How to Install Spotify Client on Fedora 25"
layout: post
date: 2017-04-13 11:39
tag:
- Linux
- Fedora
- Installation
comments: true
author: nurulfajar
---

Since i moved my main linux distro from Ubuntu to Fedora, i'm felt a big different flavors. Ubuntu or Debian based distro is easy for software installation, but on fedora i feel a bit bleeding.

lets trying to install Spotify desktop client on Fedora 25.

## With lpf installation
**Step-1**:
* Download the latest rpmfusion-nonfree-release-stable rpm from:
```
http://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-25.noarch.rpm
```

**Step-2**:
* Install rpmfusion-nonfree-release-stable rpm:
```
# rpm -Uvh rpmfusion-nonfree-release-stable*rpm
```

**Step-3**:
* Install lpf-spotify-client rpm package:
```
# dnf install lpf-spotify-client
```

**Step-4**:
* Open app menu and search "lpf spotify-client", then add your user to lpf group (just click "OK"). And wait for Downloading Spotify client.

**Step-5**:
* Open terminal and follow command.
```
lpf install spotify-client
```
* Then click "OK" in pop up lpf dialog.

## Update
i found simple installation with [Flatpak](http://flatpak.org){:target="_blank"}

## With Flatpak Installation (Preffered way)
**Step-1**:
* Install Flatpak framework:
```
$ sudo dnf install flatpak
```

* Then build and install Spotify desktop client:
```
$ flatpak install --from https://s3.amazonaws.com/alexlarsson/spotify-repo/spotify.flatpakref
$ flatpak run com.spotify.Client
```

![File.png]({{images.baseurl}}/assets/images/spotify-fedora.png)
