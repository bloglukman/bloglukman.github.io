---
layout: post
title: "Instalasi Java"
date: 2014-10-23 15:48:28 +0700
comments: true
categories: Java
---

Saya akan menjelaskan bagaimana menginstall Java pada sistem operasi Windows dan Linux. Berikut adalah langkah langkah menginstall Java.
<!--more-->

Untuk menginstall Java langkah umum yang kita lakukan adalah :

* Check sistem operasi.
* Check berapa bit pada sistem operasi.
* Download Java JDK sesuai dengan sistem operasi dan bit nya.
* Install Java JDK.
* Path Java.
* Check Java apakah sudah terinstall atau belum.

Langkah pertama adalah check sistem operasi. Langkah ini tentu sudah kita lakukan, kita sudah tahu sistem operasi apa yang kita gunakan. Jadi kita mulai dengan check berapa bit sistem operasi yang kita jalankan.
<hr />

### Windows

* Check berapa bit sistem operasi yang kita jalankan dengan cara
	* Klik kanan My Computer.
	* Klik Properties.
	* Lihat versi (x86 = 32bit dan x64 = 64bit).

* Download Java JDK berdasarkan sistem operasi dan bit yang tepat di situs resmi [Java Oracle](http://www.oracle.com/technetwork/java/javase/downloads/index.html).

* Install Java :
	* Klik 2x file installer yang telah kita download.
	* Pilih lokasi penyimpanan direktori Java. Secara default di C:\Program Files
	* Klik Install.
	* Klik Next.
	* Tunggu Proses Installasi.
	* Klik Close. 

* Path Java dapat dilakukan dengan cara sebagai berikut:
	* Buka Command Prompt.
	* Ketik perintah dibawah.

{% codeblock lang:rout %}
> set JAVA_HOME="C:\Program Files\Java\jdk1.5.0_14"
> set PATH=%JAVA_HOME%\bin;%PATH%
{% endcodeblock %}

* Check Java yang sudah kita install dengan cara :
	* Buka Command Prompt.
	* Ketik perintah dibawah.

{% codeblock lang:rout %}
> java -version
{% endcodeblock %}

** *Jika muncul versi java berarti anda telah sukses menginstall java. Jika belum coba restart Computer dan check version lagi. Jika belum juga berarti ada langkah yang terlewat* **

<hr />

###Linux

* Check berapa bit sistem operasi yang kita jalankan dengan cara :
	* Buka Terminal
	* Ketik perintah dibawah

{% codeblock lang:kconfig %}
$ file /sbin/init
{% endcodeblock %}

* Download Java JDK berdasarkan sistem operasi dan bit yang tepat di situs resmi [Java Oracle](http://www.oracle.com/technetwork/java/javase/downloads/index.html).

* Install Java pada linux kita cukup mengekstrak file yang kita download lalu letakan direktori di ```/opt/```

* Path Java dapat dilakukan dapat dilakukan dengan cara :
	* Buka Terminal
	* Ketik perintah dibawah

{% codeblock lang:kconfig %}
$ export JAVA_HOME=/usr/java/jdk1.5.0_07/bin/java
$ export PATH=$PATH:/usr/java/jdk1.5.0_07/bin
$ source /etc/profile
{% endcodeblock %}

* Check Java yang sudah kita install dengan cara :
	* Buka Terminal.
	* Ketik perintah dibawah.

{% codeblock lang:kconfig %}
$ java -version
{% endcodeblock %}

** *Jika muncul versi java berarti anda telah sukses menginstall java. Jika belum coba restart Computer dan check version lagi. Jika belum juga berarti ada langkah yang terlewat* **

<hr />