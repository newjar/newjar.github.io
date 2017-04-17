---
title: "Best Atom Themes & Fonts For Programming"
layout: post
date: 2017-04-17 17:50
tag:
- Linux
- Windows
- Fedora
- Installation
comments: true
author: nurulfajar
---
[Atom](https://atom.io/){:target="_blank"} adalah sebuah text editor yang berbasis *open source*. Atom ini menjadi salah satu *default* text editor untuk saya, selain karena *absolutely free* dan tentunya juga *open source*, Atom memiliki repository packages dan themes yang sangat luas.

Berikut saya akan berbagi *starter pack* untuk Atom, yang menurut saya sangat *solid* khususnya untuk programming.

**Sample picture:**
![file.png]({{images.baseurl}}/assets/images/atom/contoh.png)

**Step-1:**
- Download dan install kedua font [Fira Code](https://github.com/tonsky/FiraCode){:target="_blank"} dan [FlottFlott](http://www.dafont.com/flottflott.font){:target="_blank"}.

**Step-2:**
- Setelah menginstall kedua font tersebut, selanjutnya copy dan paste code dibawah ini ke **style.less** di dalam atom. atau klik **Edit > Stylesheet**.
```scss
atom-text-editor {
  font-family: 'Fira Code';
  font-style: normal;  
  text-rendering: optimizeLegibility;
}
atom-text-editor::shadow {
  .string.quoted,
  .string.regexp {
    -webkit-font-feature-settings: "liga" off, "calt" off;
  }
  .source.js.jsx > .keyword.control.flow.js,
  .storage, .type .function {
    vertical-align: baseline;
    font-family: 'flottflott';
    height: inherit;
    font-size: 1.5em;
    line-height: 1rem;
  }
  .source.js.jsx,
  .storage.type.function.arrow.js,
  .variable {
    font-family: 'Fira Code';
    font-style: normal;
  }
  .string.unquoted.js {
    color: #CDD3DE;
  }
  .entity.name {
    font-weight: bold;
  }
}
```
- Lalu klik **File > Save** atau **CTRL + S**.

**Step-3**:
- Download [Gloom](https://atom.io/packages/gloom){:target="_blank"} *syntax theme*. Kalian bisa mendownload-nya melalui **Edit > Preferences > Install**, atau bisa juga melalui cmd atau terminal, dengan perintah **apm install gloom**.

Done.
