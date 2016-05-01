---
layout: post
title: "Hello Java"
date: 2014-10-30 11:42:27 +0700
comments: true
categories: Java
---

Hal pertama yang kita pelajari dalam membuat program komputer adalah menampilkan "Hello World!". Pada kesempatan kali ini saya akan menjelaskan bagaimana membuat program tersebut pada Java. Sebelum memulai anda harus mengenal dulu :

<!-- more -->

- Package
- Class
- Method
- Main Method


### 1. Package
Package adalah sarana/cara pengelompokkan dan pengorganisasian kelas-kelas dan interface yang sekelompok menjadi suatu unit tunggal dalam library.

### 2. Class
Class mendefinisikan sekumpulan objek yang memiliki kesamaan keadaan dan perilaku. Class digunakan untuk membuat objek, dan berperan sebagai tipe data dari objek. Class merupakan sarana pengkapsulan kumpulan data dan kumpulan method yang mengoperasikan kumpulan data tersebut.

### 3. Method
Sebuah method adalah bagian-bagian kode yang dapat dipanggil oleh program utama atau dari method lainnya untuk menjalankan fungsi yang spesifik.

### 4. Main Method
Method main()adalah method utama yang pasti dimiliki oleh semua program java (selain applet) dan akan dieksekusi pertama kali pada saat program dijalankan.

<hr />

Sekarang kita akan membuat "Hello World!" pada Java.

**1. Buat File Java**

Buat file berekstensi ```.java```. Jangan ada karakter ```spasi``` karena File yang kita buat akan menjadi nama class. Saya beri nama File saya ```Hello.java```.

<br />
**2. Mendeklarasi class**

Buka file yang telah anda buat dengan text editor seperti notepad atau bila perlu notepad++ agar code program lebih mudah dibaca. dibawah ini adalah Contoh class pada java.
{% codeblock lang:java %}
class Hello{

}
{% endcodeblock %}
Mengapa class nya ditulis ```Hello``` ? tentu karena tadi saya memberi nama filenya ```Hello.java```

<br />
**3. Membuat Method Main**

Buat main metode didalam class Hello. code program menjadi seperti dibawah.
{% codeblock lang:java %}
class Hello{
	public static void main(String args[]){

	}
}
{% endcodeblock %}

<br />
**4. Menampilkan "Hello World!"**

Untuk menampilkan output dilayar shell pada java kita dapat gunakan ```System.out.print```. Sehingga kode program menjadi seperti gambar dibawah.
{% include_code java/Hello.java %}

** 5. Compile dan Run**

Agar program dapat dijalankan tentu kita harus mengkompilasi kode program yang telah kita buat, untuk meng-compile ikuti langkah langkah dibawah :

+ Buka cmd / terminal
+ pindah ke direktori tempat kita membuat file dangan perintah cd. contoh jika kita membuat di 
desktop
{% codeblock lang:kconfig Linux %}
$ cd ~/Desktop
{% endcodeblock %}
{% codeblock lang:rout Windows %}
> cd C:\Users\username\Desktop\
{% endcodeblock %}
+ Compile kode program seperti contoh dibawah
{% codeblock %}
javac Hello.java
{% endcodeblock %}
+ jalankan hasil compile seperti contoh dibawah
{% codeblock %}
java Hello
{% endcodeblock %}
