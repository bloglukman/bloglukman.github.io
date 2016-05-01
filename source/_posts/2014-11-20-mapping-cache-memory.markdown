---
layout: post
title: "Mapping Cache Memory"
date: 2014-11-20 21:47:18 +0700
comments: true
categories: Article 
---

Karena saluran cache memory lebih sedikit dibandingkan dengan blok memori utama, maka diperlukan algoritma untuk pemetaan blok memori utama ke dalam saluran cache memory. Pemilihan terhadap fungsi pemetaan akan sangat menentukan bentuk organisasi cache memory.

<!-- more -->

Telah kita ketahui bahwa cache memory mempunyai kapasitas yang kecil dibandingkan memori utama. Sehingga diperlukan aturan blok-blok mana yang diletakkan dalam cache memory. Terdapat tiga metode, yaitu pemetaan langsung (direct mapping), pemetaan asosiatif, dan pemetaan asosiatif set.

###Direct Mapping


* Setiap blok pada main memory dipetakan dengan line tertentu pada cache.di mana i adalah nomor line pada cache yang digunakan untuk meletakkan blok main memory ke-j.
	<hr />
	{% blockquote %}
	<b>i = j modulo C</b>
	{% endblockquote %}
	<hr />
* Jika M = 64 dan C = 4, maka pemetaan antara line dengan blok menjadi seperti berikut :
	* Line 0 can hold blocks 0, 4, 8, 12, ... 
	* Line 1 can hold blocks 1, 5, 9, 13, ... 
	* Line 2 can hold blocks 2, 6, 10, 14, ... 
	* Line 3 can hold blocks 3, 7, 11, 15, ... 

<br />

* Pada cara ini, address pada main memory dibagi 3 field atau bagian, yaitu:
	* Tag identifier.
	* Line number identifier
	* Word identifier (offset)

<br />

* Word identifier berisi informasi tentang lokasi word atau unit addressable lainnya dalam line tertentu pada cache.

* Line identifier berisi informasi tentang nomor fisik (bukan logika) line pada cache.
	
* Tag identifier disimpan pada cache bersama dengan blok pada line.
	* Untuk setiap alamat memory yang dibuat oleh CPU, line tertentu yang menyimpan copy alamat tersebut ditentukan, jika blok tempat lokasi data tersebut sudah dikopi dari main memory ke cache.
	* Tag yang ada pada line akan dicek untuk melihat apakah benar blok yang dimaksud ada pada line tsb.

<hr />

{% img center /images/4.png Gambar 1 %}

->** Gambar Organisasi Direct Mapping. **<-

<hr />

** Keuntungan ** menggunakan Direct Mapping antara lain:

* Mudah dan murah diimplementasikan.

* Mudah untuk menentukan letak salinan data main memory pada cache.

<br />

** Kerugian ** menggunakan Direct Mapping antara lain:

* Setiap blok main memory hanya dipetakan pada 1 line saja. Terkait dengan sifat lokal pada main memory, sangat mungkin mengakses blok yang dipetakan pada line yang sama pada cache. Blok seperti ini akan menyebabkan seringnya sapu masuk dan keluar data ke/dari cache, sehingga hit ratio mengecil.

* Hit ratio adalah perbandingan antara jumlah ditemukan- nya data pada cache dengan jumlah usaha mengakses cache.

<hr />

{% img center /images/5.png Gambar 2 %}

->** Gambar Contoh Pengalamatan Direct Mapping. **<-

<hr />

<div class="row">
	<div class="col-md-8 col-md-offset-2">
		<center><b><i><u>Tabel Direct Mapping</u></i></b></center>
		<br />
		<table class="table table-striped">
			<tr>
				<th>Item</th>
				<th>Keterangan</th>
			</tr>
			<tr>
				<td>Panjang alamat</td>
				<td>(s + w) bits</td>
			</tr>
			<tr>
				<td>Jumlah unit yang dapat dialamati</td>
				<td>2s+w words or bytes</td>
			</tr>
			<tr>
				<td>Ukuran Blok sama dengan ukuran Line</td>
				<td>2w words or bytes</td>
			</tr>
			<tr>
				<td>Jumlah blok di memori utama</td>
				<td>2s+ w/2w = 2s</td>
			</tr>
			<tr>
				<td>Jumlah line di cache</td>
				<td>m = 2r</td>
			</tr>
			<tr>
				<td>Besarnya tag</td>
				<td>(s – r) bits</td>
			</tr>
		</table>
	</div>
</div>

<hr />

###Associative Mapping

* Memungkinkan blok diletakkan di sebarang line yang sedang tidak terpakai.

* Diharapkan akan mengatasi kelemahan utama Direct Mapping.

* Harus menguji setiap cache untuk menemukan blok yang diinginkan.
	* Mengecek setiap tag pada line
	* Sangat lambat untuk cache berukuran besar.

* Nomor line menjadi tidak berarti. Address main memory dibagi menjadi 2 field saja,
yaitu tag dan word offset.

<hr />

{% img center /images/6.png Gambar 3 %}

->** Gambar Organisasi Associative Mapping. **<-

<hr />

* Melakukan pencarian ke semua tag untuk menemukan blok.

* Cache dibagi menjadi 2 bagian :
	* lines dalam SRAM
	* tag dalam associative memory

<hr />

{% img center /images/7.png Gambar 4 %}

->** Gambar Contoh Pengalamatan Associative Mapping. **<-

<hr />

** Keuntungan ** Associative Mapping:

* cepat dan fleksibel.

** Kerugian ** Associative Mapping:

* biaya implementasi. Misalnya : 
	
	* untuk cache ukuran 8 kbyte dibutuhkan 1024 x 17 bit associative memory untuk menyimpan tag identifier.

<div class="row">
	<div class="col-md-8 col-md-offset-2">
		<center><b><i><u>Tabel Associative Mapping</u></i></b></center>
		<br />
		<table class="table table-striped">
			<tr>
				<th>Item</th>
				<th>Keterangan</th>
			</tr>
			<tr>
				<td>Panjang alamat</td>
				<td>(s + w) bits</td>
			</tr>
			<tr>
				<td>Jumlah unit yang dapat dialamati</td>
				<td>2s+w words or bytes</td>
			</tr>
			<tr>
				<td>Ukuran Blok sama dengan ukuran Line</td>
				<td>2w words or bytes</td>
			</tr>
			<tr>
				<td>Jumlah blok di memori utama</td>
				<td>2s+ w/2w = 2s</td>
			</tr>
			<tr>
				<td>Jumlah line di cache</td>
				<td>undetermined</td>
			</tr>
			<tr>
				<td>Besarnya tag</td>
				<td>s bits</td>
			</tr>
		</table>
	</div>
</div>

<hr />

###Set Associative Mapping

* Merupakan kompromi antara Direct dengan Full Associative Mapping.

* Membagi cache menjadi sejumlah set (v) yang masing-masing memiliki sejumlah line (k)

* Setiap blok dapat diletakkan di sebarang line dengan nomor set:
	<hr />
	{% blockquote %}
	<b>nomor set = j modulo v</b>
	{% endblockquote %}
	<hr />

{% img center /images/8.png Gambar 5 %}

->** Gambar Organisasi K-Way Set Associative Mapping. **<-

<hr />

* Jika sebuah set dapat menampung X line, maka cache disebut memiliki X-way set associative cache.

* Hampir semua cache yang digunakan saat ini menggunakan organisasi 2 atau 4-way set associative mapping.

<hr />

{% img center /images/9.png Gambar 6 %}

->** Gambar Contoh Pengalamatan 2-Way Associative Mapping. **<-

<hr />

* Setiap blok memori dapat menempati lebih dari satu kemungkinan nomor line (dapat menggunakan line yang kosong), sehingga thrashing dapat diperkecil.

* Jumlah tag lebih sedikit (dibanding model associative), sehingga jalur untuk melakukan perbandingan tag lebih sederhana.

<div class="row">
	<div class="col-md-8 col-md-offset-2">
		<center><b><i><u>Tabel Set Associative Mapping</u></i></b></center>
		<br />
		<table class="table table-striped">
			<tr>
				<th>Item</th>
				<th>Keterangan</th>
			</tr>
			<tr>
				<td>Panjang alamat</td>
				<td>(s + w) bits</td>
			</tr>
			<tr>
				<td>Jumlah unit yang dapat dialamati</td>
				<td>2s+w words or bytes</td>
			</tr>
			<tr>
				<td>Ukuran Blok sama dengan ukuran Line</td>
				<td>2w words or bytes</td>
			</tr>
			<tr>
				<td>Jumlah blok di memory utama</td>
				<td>2d</td>
			</tr>
			<tr>
				<td>Jumlah line dalam set</td>
				<td>k</td>
			</tr>
			<tr>
				<td>Jumlah set</td>
				<td>V=2d</td>
			</tr>
			<tr>
				<td>Jumlah line di cache</td>
				<td>Kv = k*2d</td>
			</tr>
			<tr>
				<td>Besarnya tag</td>
				<td>(s-d) bits</td>
			</tr>>
		</table>
	</div>
</div>

<hr />

###Algoritma Penggantian

Yang dimaksud algoritma penggantian adalah suatu mekanisme pergantian blok-blok dalam cache memory yang lama dengan data baru. Dalam pemetaan langsung tidak diperlukan algoritma ini, namun dalam pemetaan asosiatif dan asosiatif set, algoritma ini mempunyai peranan penting untuk meningkatkan kinerja cache memory.

Banyak algoritma penggantian yang telah dikembangkan. Algoritma yang paling efektif adalah Least Recently Used (LRU), yaitu mengganti blok data yang terlama berada dalam cache memory dan tidak memiliki referensi. Algoritma lainnya adalah First In First Out (FIFO), yaitu mengganti blok data yang awal masuk. Kemudian Least Frequently Used (LFU) adalah mengganti blok data yang mempunyai
referensi paling sedikit. Teknik lain adalah algoritma Random, yaitu penggantian tidak berdasakan pemakaian datanya, melainkan berdasarkan slot dari beberapa slot kandidat secara acak.

<hr />

###Write Policy

Apabila suatu data telah diletakkan pada cache memory maka sebelum ada penggantian harus dicek apakah data tersebut telah mengalami perubahan. Apabila telah berubah maka data pada memori utama harus di-update. Masalah penulisan ini sangat komplek, apalagi memori utama dapat diakses langsung oleh modul I/O, yang memungkinkan data pada memori utama berubah, lalu bagaimana dengan data yang
telah dikirim pada cache? Tentunya perbedaan ini menjadikan data tidak valid.

Teknik yang dikenalkan diantaranya, write through, yaitu operasi penulisan melibatkan data pada memori utama dan sekaligus pada cache memory sehingga data selalu valid. Kekurangan teknik ini adalah menjadikan lalu lintas data ke memori utama dan cache memory sangat tinggi sehingga mengurangi kinerja sistem, bahkan bisa terjadi hang. Teknik lainnya adalah write back, yaitu teknik meminimasi penulisan dengan cara penulisan pada cache memory saja. Pada saat akan terjadi
penggantian blok data cache memory maka baru diadakan penulisan pada memori utama. Masalah yang timbul adalah manakala data di memori utama belum diupdate telah diakses modul I/O sehingga data di memori utama tidak valid.

Penggunaan multi cache terutama untuk multiprocessor adan menjumpai masalah yang lebih komplek. Masalah validasi data tidak hanya antara cache memory dan memori utama saja, namun antar cache memory juga harus diperhatikan. Pendekatan penyelesaian masalah yang dapat dilakukan adalah dengan :

* Bus Watching with Write Through, yaitu setiap cache controller akan memonitoring bus alamat untuk mendeteksi adanya operasi tulis. Apabila ada operasi tulis di alamat yang datanya digunakan bersama maka cache controller akan menginvalidasi data cache-nya.

* Hardware Transparency, yaitu adanya perangkat keras tambahan yang menjamin semua updating data memori utama melalui cache direfleksikan pada seluruh cache yang ada.

* Non Cacheable Memory, yaitu hanya bagian memori utama tertentu yang digunakan secara bersama. Apabila ada mengaksesan data yang tidak di share merupakan kegagalan cache.

<hr />

###Miss Cache

Saat miss menulis, anda bisa punya pilihan antara membawa blok ke cache (write-allocate) atau tidak (write-no-allocate). Saat miss membaca, anda selalu membawa blok ke cache (lokalitas spasial atau temporal) - blok mana yang diganti:

* tidak ada pilihan untuk direct-mapped cache
* memilih secara acak way yang akan diganti
* mengganti way yang paling jarang dipakai (LRU)
* penggantian FIFO (round-robin)

Tipe miss cache adalah sebagai berikut:

* Miss wajib : terjadi saat pertama kali word memori diakses. Merupakan miss untuk cache yang infinit.

* Miss kapasitas : terjadi karena program menyentuh banyak word yang lain sebelum menyentuh ulang word yang sama. Merupakan miss untuk cache fully- associative.

* Miss konflik : terjadi karena dua work dipetakan ke lokasi yg sama di cache. Merupakan miss yang terjadi ketika berganti dari cache fully-associative kedirect-mapped.