---
layout:     post
title:      Mencari Akar Persamaan Nirlanjar dengan Metode Bagi Dua
date:       2016-05-20
summary:    Silakan klik pada judul untuk detailnya
categories: tugas
---

## Hai, IRKWAN.
Saat ini saya ingin membagikan sesuatu yang spesial untuk Anda. Apakah itu?
Apakah Anda ingat dengan persamaan seperti berikut ini ?

> x<sup>2</sup> + 2x + 2 = 0

Saya rasa itu mudah bagi Anda untuk menemukan akar persamaannya. Bagaimana dengan sin(x<sup>2</sup>) = 0? Saya rasa semakin sulit.
Pada kesempatan saat ini saya ingin mengenalkan metode bagi dua untuk mencari akar persamaan nirlanjar. Mari kita simak.

## Metode Bagi Dua

### Pendahuluan
Sebelum mengetahui metode bagi dua, perlu diketahui bahwa untuk mencari akar persamaan memiliki dua metode secara umum, yaitu metode terbuka dan metode tertutup. Metode bagi dua termasuk pada metode tertutup. Adapun penjelesan singkat mengenai metode tersebut sebagai berikut.

#### Metode Terbuka
Berikut beberapa poin singkat mengenai metode terbuka :
* tidak memerlukan selang [a,b] yang mengandung akar
* mencari akar melalui suatu lelaran (iterasi) yang dimulai dari sebuah tebakan (guest) awal,
* pada setiap lelaran kita menghitung hampiran akar yang baru. 
* Mungkin saja hampiran akar yang baru mendekati akar sejati (konvergen), atau mungkin juga menjauhinya (divergen). 
* Karena itu, metode terbuka tidak selalu berhasil menemukan akar, kadang-kadang konvergen, kadangkala ia divergen.

#### Metode Tertutup
Sedangkan metode tertutup dapat diringkas sebagai berikut :
* mencari akar di dalam selang [a,b];
* Selang [a,b] sudah dipastikan berisi minimal satu buah akar,
* karena itu metode jenis ini selalu berhasil menemukan akar.
* Dengan kata lain, lelarannya selalu konvergen (menuju) ke akar,
* karena itu metode tertutup kadang-kadang dinamakan juga **metode konvergen**.

### Syarat dalam Metode Tertutup
Sudah diketahui bahwa metode bagi dua merupakan metode tertutup, oleh karena itu perlu diketahui juga mengenai metode tertutup lebih dalam dan mengenai syarat-syaratnya. Pada metode tertutup memerlukan selang [a,b] yang mengandung minimal satu buah akar. Adapun **syarat cukup** keberadaan akar sebagai berikut :
> Jika f(a)f(b) < 0 dan f(x) menerus di dalam selang [a,b], maka *paling sedikit* terdapat satu buah akar persamaan f(x) = 0 di dalam selang [a,b].

Dari pernyataan tersebut dapat disimpulkan bahwa selang [a,b] harus berbeda tanda pada nilai-nilai fungsinya supaya terdapat minimal 1 buah akar.

![Alt text](https://perguruanfarhan.files.wordpress.com/2012/03/pers19.jpg "Ilustrasi Metode Bagi Dua")

###### Gambar 1 - Ilustrasi grafis untuk akar hampiran dalam metode bagi dua.
###### Sumber : https://perguruanfarhan.files.wordpress.com/2012/03/pers19.jpg diakses pada tanggal 23 Juni 2016 pukul 11.44

### Kondisi yang Mungkin Terjadi
#### 1. f(a)f(b) < 0
Pada kondisi ini akan terdapat akar sebanyak bilangan ganjil.

#### 2. f(a)f(b) > 0
Pada kondisi ini akan terdapat akar sebanyak bilangan genap, termasuk saat tidak ada akar.

### Menentukan Selang [a,b]
Ada beberapa cara untuk menentukan selang [a,b] yang cukup kecil dan mengandung akar. Adapun cara tersebut sebagai berikut :
1. Membuat grafik fungsi di bidang X-Y, lalu melihat di mana perpotongan dengan sumbu-X.
2. Membuat tabel yang memuat nilai-nilai fungsi pada titik-titik absis yang berjarak tetap (h). Nilai h dibuat cukup kecil. Contoh pembuatan tabel dan pemilihannya akan diperlihatkan dalam contoh penerapan. Cara yang digunakan yaitu menggunakan cara 2.

### Proses Membagi Dua dan Kondisi Berhenti Iterasi

## Contoh Penerapan


###### Referensi :
[1] Slide Solusi Persamaan Nirlanjar oleh Rinaldi Munir. [Go To Source](http://informatika.stei.itb.ac.id/~rinaldi.munir/MetNum/2010-2011/Solusi%20Persamaan%20Nirlanjar%20%28Bag%201%29.pdf)

[2] Catatan Dosen dalam MIT Open Courseware pada kuliah [Introduction to Numerical Analysis](http://ocw.mit.edu/courses/mathematics/18-330-introduction-to-numerical-analysis-spring-2012/index.htm). Menerjemahkan dan mengambil sebagian konten [ini](http://ocw.mit.edu/courses/mathematics/18-330-introduction-to-numerical-analysis-spring-2012/lecture-notes/MIT18_330S12_Chapter4.pdf). [License link](http://ocw.mit.edu/terms/)
