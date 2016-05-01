---
layout: post
title: "Langkah - langkah meng-crimping kabel utp dan membuat jaringan peer to peer"
date: 2016-03-11 23:10:57 +0700
comments: true
categories: Networking
---

Saya akan menjelaskan cara mengcrinping kabel UTP ke RJ45 (straight dan cross) dan membuat jaringan peer to peer. Sebelum kita memasang kita terlebih dahulu harus mengetahui standart pemasangannya. Standart pemasangannya ada dua, yaitu 568A dan 568B .

<!-- more -->

568A = PH, H, PO, B, PB, O, PC, C   
568B = PO, O, PH, B, PB, H, PC, C

Keterangan :

* PO = Putih Oren
* O   = Oren
* PH = Putih Hijau
* H   = Hijau
* PB = Putih Biru
* B   = Biru
* PC = Putih Coklat
* C   = Coklat

Sebelum mulai mengcrimping , kalian harus menyiapkan beberapa peralatan. 

- Tang crimping
- Kabel UTP
- RJ45
- Tester

Lalu kita bisa mulai mengcrimpig . langkah-langkah :

* Pertama siapkan kabel UTP-nya, potong sesuai yang kita inginkan . Setelah kita potong , kita kupas kulitnya dengan menggunakan tang crimping sampai terlihat kabel bagian dalamnya, seperti pada gambar.

<br />

{% img center /images/crimp-1.jpeg Gambar 1 %}

<hr />

* Susun warna kabel sesuai urutan, pada gambar dibawah adalah susunan Straight

<br />

{% img center /images/crimp-2.jpg Gambar 2 %}

<hr />

* Setelah rata lalu kita masukan ke RJ45 nya . masukan dengan perlhan-lahan dan jangan samapi ada kabel yang menyilang atau terselip. Pastikan lurus dan terpasang dengan pas.

<br />

{% img center /images/crimp-3.jpeg Gambar 3 %}

<hr />

* Masukkan dan jepitkan kabel UTP dan RJ45yang telah disatukan pada lubang yang terdapat pada tang crimping.

<br />

{% img center /images/crimp-4.jpg Gambar 4 %}

<hr />

* Jika satu ujung tersusun cross maka ujung yang lain harus straight, jika straight ujung yang lain dapat berupa cross ataupun straight.

* Colokan kedua kabel ke pc atau laptop

* Konfigurasi IP secara static, misal PC 1 diberi IP : 192.168.1.1 dan PC 2 diberi IP : 192.168.1.2.

* Lakukan test ping dengan CMD, dengan perintah ping 192.168.1.1 	