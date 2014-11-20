---
layout: post
title: "Cache Memory"
date: 2014-11-20 14:20:24 +0700
comments: true
categories: Article
---

Cache memory merupakan lokasi data sementara antara prosesor dengan main memory. Penempatan cache memory ditujukan untuk mengurangi gap antara kecepatan prosesor dengan kecepatan main memory. Gambar 1 di bawah ini menunjukkan posisi cache memory yang diletakkan antara prosesor (CPU) dengan main memory. Sedangkan Gambar 2 memperlihatkan sistem interkoneksi untuk cache memory.

<!-- more -->

{% img /images/1.png Gambar 1 %}

->** Gambar 1 **<-

<hr />
{% img center /images/2.png Gambar 2 %}

->** Gambar 2 **<-

Cache berasal dari kata cash. Dari istilah tersebut cache adalah tempat menyembunyikan atau tempat menyimpan sementara. Sesuai definisi tersebut cache memory adalah tempat menympan data sementara. Cara ini dimaksudkan untuk meningkatkan transfer data dengan menyimpan data yang pernah diakses pada cache memory tersebut, sehingga apabila ada data yang ingin diakses adalah data yang sama maka maka akses akan dapat dilakukan lebih cepat. Cache memory ini adalah memori tipe SDRAM yang memiliki kapasitas terbatas namun memiliki kecepatan yang sangat tinggi dan harga yang lebih mahal dari memori utama. Cache memory ini terletak antara register dan RAM (memori utama) sehingga pemrosesan data tidak langsung mengacu pada memori utama.

Karakteristik cache memory adalah sebagai berikut:

* Kapasitas relatif lebih kecil dari main memory, tetapi memiliki kecepatan
yang relativ lebih tinggi dibanding main memory;

* Cache memory merupakan suatu memori buffer (salinan data) bagi
memori utama;

* Meskipun cache menggunakan informasi yang tersimpan dalam memori
utama, tetapi ia tidak berhadapan secara langsung dengan memori utama;

* Word yang disimpan didalam cache memory adalah word yang diambil dari
main memory, yang dikerjakan sesuai perintah CPU.
<hr />
### Level Cache Memory
Hingga saat ini, cache memory terbagi atas tiga level yaitu L1, L2 dan L3. Cache memory memori level 1 (L1) adalah cache memory yang terletak dalam prosesor (internal cache). Cache memory ini memiliki kecepatan akses paling tinggi dan harganya paling mahal. Ukuran memori berkembang mulai dari 8KB, 64KB dan 128KB. Cache memory level 2 (L2) memiliki kapasitas yang lebih besar yaitu berkisar antara 256KB sampai dengan 2MB. Namun, cache memory L2 ini memiliki kecepatan yang lebih rendah dari cache memory L1. Cache memory L2 terletak terpisah dengan prosesor atau disebut dengan external cache.Sedangkan cache memory level 3 hanya dimiliki oleh prosesor yang memiliki unit lebih dari satu misalnya dualcore dan quadcore. Fungsinya adalah untuk mengontrol data yang masuk dari tembolok L2 dari masing-masing inti prosesor.

Level 2 atau L2 cache merupakan bagian dari strategi penyimpanan multi level untuk meningkatkan performa komputer. Terdapat tiga level cache yang digunakan pada komputer, yaitu L1, L2 dan L3 cache. Tiap-tiap cache tersebut menjembatani jarak (gap) diantara processor yang sangat cepat, dengan memori RAM (Random Access Memory) yang jauh lebih lambat.

Sementara desainnya terus mengalami perubahan, L1 cache biasanya telah terintegrasi (built in) ke dalam processor, sementara L2 cache biasanya terintegrasi pada motherboard (bersamaan dengan L2 cache). Namun, beberapa processor kini menggabungkan L2 cache serta L1 cache, dan bahkan beberapa diantaranya juga menggungkan L3 cache. Kecepatan yang paling tinggi terdapat pada L1 cache, kemudian menurun pada L2 dan L3 cache. Namun kebalikannya, semakin besar angka cache, maka semakin besar pula kapasitas penyimpanan datanya.

{% img center /images/3.png Gambar 3 %}

->** Gambar 3 **<-

Tugas dari cache processor adalah untuk mengantisipasi data request, sehingga ketika pengguna mengakses sebuah program yang sering digunakan, sebagai contohnya, instruksi-instruksi yang dibutuhkan untuk menjalankan program tersebut telah siap digunakan, disimpan pada cache. Ketika hal ini terjadi, CPU dapat memproses request tanpa adanya jeda (delay), sehingga dapat meningkatkan performa komputer secara drastis.

CPU pertama-tama akan memeriksa L1 cache, diikuti dengan L2 dan L3 cache. Jika processor telah menemukan bit data yang dibutuhkan, maka disebut dengan cache hit. Namun jika cache tidak menyediakan bit data yang dibutuhkan, processor mendapatkan sebuah cache miss, dan data perlu ditarik dari RAM yang lebih lambat atau hard disk yang juga lebih lambat.
<hr />
### Kapasitas Cache

Menentukan ukuran cache memory sangatlah penting untuk mendongkrak kinerja komputer. Dari segi harga cache memory sangatlah mahal tidak seperti memori utama. Semakin besar kapasitas cache tidak berarti semakin cepat prosesnya, dengan ukuran besar akan terlalu banyak gate pengalamatannya sehingga akan
memperlambat proses.

Kita bisa melihat beberapa merek prosesor di pasaran beberapa waktu lalu. AMD mengeluarkan prosesor K5 dan K6 dengan cache memory yang besar (1MB) tetapi kinerjanya tidak bagus. Kemudian Intel pernah mengeluarkan prosesor tanpa cache memory untuk alasan harga yang murah, yaitu seri Intel Celeron pada tahun 1998-an hasil kinerjanya sangat buruk terutama untuk operasi data besar, floating point, 3D.

Intel Celeron versi berikutnya sudah ditambah cache memory sekitar 128KB.
Lalu berapa idealnya kapasitas cache memory? Sejumlah penelitian telah
menganjurkan bahwa ukuran cache antara 1KB dan 512KB akan lebih optimum.

<hr />

### Ukuran Blok
Elemen rancangan yang harus diperhatikan lagi adalah ukuran blok. Telah dijelaskan adanya sifat lokalitas referensi maka nilai ukuran blok sangatlah penting. Apabila blok berukuran besar ditransfer ke cache akan menyebabkan hit ratio mengalami penurunan karena banyaknya data yang dikirim disekitar referensi. Tetapi apabila terlalu kecil, dimungkinkan memori yang akan dibutuhkan CPU tidak tercakup.

Apabila blok berukuran besar ditransfer ke cache, maka akan terjadi :

1. Blok-blok yang berukuran lebih besar mengurangi jumlah blok yang menempati cache. Karena isi cache sebelumnya akan ditindih.

2. Dengan meningkatnya ukuran blok maka jarak setiap word tambahan menjadi lebih jauh dari word yang diminta, sehingga menjadi lebih kecil kemungkinannya digunakan cepat.

Hubungan antara ukuran blok dan hit ratio sangat rumit untuk dirumuskan,
tergantung pada karakteristik lokalitas programnya dan tidak terdapat nilai optimum
yang pasti telah ditemukan. Ukuran antara 4 hingga 8 satuan yang dapat dialamati
(word atau byte) cukup beralasan untuk mendekati nilai optimum.
<hr />
->[Sumber](http://files.yogaprihastomo.com/Kuliah/Strata%20Dua/Semester%201/Tugas%20Arsitektur%20dan%20Organisasi%20Komputer%20-%20Cache%20Memory.pdf)<-

<hr />