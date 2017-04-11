---
layout: post
comments: true
title: Example Handling Multiple Request on Node Js
description: "Example code handling multiple data request"
published: true
tags: [javascript, nodejs]
---

Example code :

```js
function DaftarBelanja(DaftarNomer, DaftarNama) {

    console.log("Daftar Nomer Anda:", DaftarNomer, DaftarNama);

    DaftarDelivered(function () {
        console.log("Pesanan" ,DaftarNomer, "Atas Nama" ,DaftarNama, "Telah Delivered");
    });

}

function DaftarDelivered(callback) {
    setTimeout(callback, 5000);
}

module.exports.DaftarBelanja = DaftarBelanja;
module.exports.DaftarDelivered = DaftarDelivered;

DaftarBelanja(1, "Nama1");
DaftarBelanja(2, "Nama2");
DaftarBelanja(3, "Nama3");
DaftarBelanja(4, "Nama4");
DaftarBelanja(5, "Nama5");

```
