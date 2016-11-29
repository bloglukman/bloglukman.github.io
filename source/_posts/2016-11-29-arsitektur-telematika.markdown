---
layout: post
title: "Arsitektur Telematika"
date: 2016-11-29 14:34:47 +0700
comments: true
categories: Article
---

###1. Pengertian
Arsitektur Telematika adalah sebuah aplikasi yang secara logic berada diantara lapisan aplikasi (application layer dan lapisan data dari sebuah arsitektur layer – layer TCP/IP) yang dapat meningkatkan hubungan jaringan komunikasi dengan teknologi informasi.
<!-- more -->

<hr />

###2. Elemen Utama Arsitektur

1. Arsitektur sistem pemrosesan, menentukan standar teknis untuk hardware, lingkungan sistem operasi, dan software aplikasi, yang diperlukan untuk menangani persyaratan pemrosesan informasi perusahaan dalam spektrum yang lengkap. Standar merupakan format, prosedur, dan antar muka, yang menjamin bahwa perlengkapan dan software dari sekumpulan penyalur akan bekerja sama.

2. Arsitektur telekomunikasi dan jaringan, menentukan kaitan di antara fasilitas komunikasi perusahaan, yang melaluinya informasi bergerak dalam organisasi dan ke peserta dari organisasi lain, dan hal ini juga tergantung dari standar yang berlaku.

3. Arsitektur data, sejauh ini merupakan yang paling rumit diantara ketiga arsitektur di atas, dan termasuk yang relatif sulit dalam implementasinya, menentukan organisasi data untuk tujuan referensi silang dan penyesuaian ulang, serta untuk penciptaan sumber informasi yang dapat diakses oleh aplikasi bisnis dalam lingkup luas.

<hr />

###3. Arsitektur Client - Server
Karena keterbatasan sistem file sharing, dikembangkanlah Arsitektur Client-Server. Arsitektur Client-Server merupakan sebuah aplikasi yang bertugas untuk membagi pekerjaan antara server(penyedia layanan) dan client. Client dan server terkadang menggunakan jaringan komputer pada hardware yang terpisah. Sedangkan server dapat menjalankan satu atau lebih program untuk memberikan data-data pada client. Arsitektur client – server telematika terdiri dari 2 buah arsitektur yakni, arsitektur sisi client dan sisi servernya.

####**Arsitektur Client Side**
Arsitektur dari sisi klien mengarah pada  pelaksanaan data  pada browser sisi koneksi HTTP. Contohnya adalah JavaScript dari sisi eksekusi client dan cookie dari sisi penyimpanan pada client. Beberapa ciri khas dari sisi client, sebagai berikut :

- Selalu memulai permintaan ke server.
- Menunggu dan menerima balasan dari server.
- Biasanya terhubung ke sejumlah kecil dari server pada satu waktu.
- Biasanya berinteraksi langsung dengan pengguna akhir dengan menggunakan antarmuka pengguna seperti antarmuka pengguna grafis. Khusus jenis klien mencakup: web browser, e-mail klien, dan online chat klien.

####**Arsitektur Server Side**

Pada sisi server, terdapat server Web khusus yang mengeksekusi perintah dengan menggunakan metode HTTP. Contoh dari sisi server adalah penggunaan CGI script yang tertanam di halaman HTML, hal tersebut dapat memicu terjadinya perintah untuk mengeksekusi. Beberapa ciri khas dari sisi server, sebagai berikut :

- Menunggu permintaan dari salah satu client.
- Melayani permintaan klien dan menjawab sesuai data yang diminta oleh client.
- Suatu server dapat berkomunikasi dengan server lain untuk melayani permintaan client.
- Jenis-jenisnya : web server, FTP server, database server, E-mail server, file server, print server.
- Client dan server dikembangkan oleh berbagai perusahaan software besar seperti Lotus, Microsoft, Novell, Baan, Informix, Oracle, PeopleSoft, SAP, Sun, dan Sybase. Perusahaan-perusahaan tersebut telah menjadi perusahaan komputer yang stabil dan besar pada era ini.

<hr />

###4. Kolaborasi Client Side dengan Server Side

Berikut ini adalah penjelasan mengenai beberapa kolaborasi arsitektur sisi client dan sisi server :

####**One-Tier / Single-Tier / Stand Alone**

Pada Arsitektur Single-Tier, semua komponen produksi dari sistem dijalankan pada komputer yang sama. Beberapa sifat dari Single-Tier antara lain :

- Sederhana dan alternatifnya sangat mahal.
- Membutuhkan sedikit perlengkapan untuk dibeli dan dipelihara.
- Kelemahan pada keamanan dari arsitektur ini yaitu rendahnya dan kurangnya skalabilitas.

{% img center /images/one-tier.jpg Gambar One-Tier %}

####**Two-Tier**

Pada Arsitektur Two-tier, antarmuka pengguna ditempatkan di lingkungan desktop dan sistem manajemen database. Biasanya dalam sebuah server, yang lebih kuat merupakan mesin yang menyediakan layanan bagi banyak klien. Pengolahan informasi dibagi antara sistem interface lingkungan dan lingkungan server manajemen database. Arsitektur two-tier lebih aman dan terukur daripada pendekatan single-tier. Mempunyai database pada komputer yang terpisah meningkatkan kinerja keseluruhan situs. Kelemahannya adalah biaya yang mahal dan arsitektur yang kompleks.

{% img center /images/two-tier.jpg Gambar Two-Tier %}

####**Three-Tier**

Model three-tier atau multi-tier dikembangkan untuk menjawab keterbatasan pada arsitektur two-tier. Konsep model three-tier adalah model yang membagi fungsionalitas ke dalam lapisan-lapisan, aplikasi-aplikasi mendapatkan skalabilitas, keterbaharuan, dan keamanan. Three-tier client dan server arsitektur digunakan untuk meningkatkan performa untuk jumlah pengguna besar dan juga meningkatkan fleksibilitas ketika dibandingkan dengan pendekatan dua tingkat. Kekurangannya adalah pengembangan lebih sulit daripada pengembangan pada arsitektur dua lapis.

Pada tiga tingkatan arsitektur, sebuah middleware digunakan diantara sistem user interface lingkungan klien dan server manajemen database lingkungan. Middleware ini diimplementasikan dalam berbagai cara seperti pengolahan transaksi monitor, pesan server atau aplikasi server.


{% img center /images/three-tier.jpg Gambar Three-Tier %}

<br/>
<hr />
->Sumber : [Wikipedia](https://id.wikipedia.org/wiki/Telematika), [Blog 1](https://nidafe.wordpress.com/2015/10/12/arsitektur-telematika/), [Blog 2](https://bluewarrior.wordpress.com/2009/11/27/arsitektur-telematika/)<-
<hr />