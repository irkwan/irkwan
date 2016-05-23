---
layout:     post
title:      Mencari Akar Persamaan Nirlanjar dengan Metode Bagi Dua
date:       2016-05-20
summary:    Silakan klik pada judul untuk detailnya
categories: tugas
---

---
#Daftar Isi

1. [Metode Bagi Dua](#metode-bagi-dua)
  1. [Pendahuluan](#pendahuluan)
    1. [Metode Terbuka](#metode-terbuka)
    2. [Metode Tertutup](#metode-tertutup)
  2. [Syarat dalam Metode Tertutup](#syarat-dalam-metode-tertutup)
  3. [Kondisi yang Mungkin Terjadi](#kondisi-yang-mungkin-terjadi)
    1. [Hasil Kali Batas Negatif](#hasil-kali-batas-negatif)
    2. [Hasil Kali Batas Positif](#hasil-kali-batas-positif)
  4. [Menentukan Selang](#menentukan-selang)
  5. [Proses Membagi Dua dan Kondisi Berhenti Iterasi](#proses-membagi-dua-dan-kondisi-berhenti-iterasi)
    1. [Proses Membagi Dua](#proses-membagi-dua)
    2. [Kondisi Berhenti Iterasi](#kondisi-berhenti-iterasi)
2. [Contoh Penerapan](#contoh-penerapan)
3. [Referensi](#referensi)

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
#### Hasil Kali Batas Negatif
Pada kondisi ini akan terdapat akar sebanyak bilangan ganjil. Dalam matematis dapat ditulis sebagai berikut : f(a)f(b) < 0.
![Alt text](https://github.com/berviantoleo/mycapturepicrepo/raw/master/Numerical-Analysis/kurang0.PNG "f(a)f(b) < 0")

###### Gambar 2 - Grafik yang menghasilkan f(a)f(b) < 0
###### Sumber : [1][1]

#### Hasil Kali Batas Positif
Pada kondisi ini akan terdapat akar sebanyak bilangan genap, termasuk saat tidak ada akar. Dalam matematis dapat ditulis sebagai berikut : f(a)f(b) > 0.
![Alt text](https://github.com/berviantoleo/mycapturepicrepo/raw/master/Numerical-Analysis/lebih0.PNG "f(a)f(b) > 0")

###### Gambar 3 - Grafik yang menghasilkan f(a)f(b) > 0
###### Sumber : [1][1]

### Menentukan Selang
Ada beberapa cara untuk menentukan selang [a,b] yang cukup kecil dan mengandung akar. Adapun cara tersebut sebagai berikut :

1. Membuat grafik fungsi di bidang X-Y, lalu melihat di mana perpotongan dengan sumbu-X.
2. Membuat tabel yang memuat nilai-nilai fungsi pada titik-titik absis yang berjarak tetap (h). Nilai h dibuat cukup kecil. Contoh pembuatan tabel dan pemilihannya akan diperlihatkan dalam contoh penerapan. Cara yang digunakan yaitu menggunakan cara 2.

### Proses Membagi Dua dan Kondisi Berhenti Iterasi

#### Proses Membagi Dua
Metode bagi dua atau bisection, metode ini dimulai dari dua titik a<sub>0</sub> dan b<sub>0</sub> yang memiliki

> f(a<sub>0</sub>) > 0, dan f(b<sub>0</sub>) < 0

Karena fungsi f adalah kontinu, harus ada akar antara [a<sub>0</sub>,b<sub>0</sub>]. Dalam iterasi ke k, asumsikan kita telah mendapat interval [a<sub>k</sub>,b<sub>k</sub>] sehingga memenuhi: f(a<sub>0</sub>) > 0, dan f(b<sub>0</sub>) < 0. Metode bisection atau metode bagi dua ini mengelompokan interval [a<sub>k</sub>,b<sub>k</sub>] menjadi dua dan membuang setengahnya yang tidak mungkin ada akar-akarnya. Misalkan m<sub>k</sub> - (a<sub>k</sub> + b<sub>k</sub>) / 2.

* Jika f(m<sub>k</sub>) < 0, maka interval [a<sub>k</sub>,m<sub>k</sub>] yang akan diambil. Sehingga a<sub>k+1</sub> = a<sub>k</sub> dan b<sub>k+1</sub> = m<sub>k</sub>.
* Jika f(m<sub>k</sub>) > 0, maka interval [m<sub>k</sub>,b<sub>k</sub>] yang akan diambil. Sehingga a<sub>k+1</sub> = m<sub>k</sub> dan b<sub>k+1</sub> = b<sub>k</sub>.
* Jika f(m<sub>k</sub>) = 0, maka m<sub>k</sub> adalah akarnya dan hentikan algoritma.

Dalam prakteknya, iterasi ini akan berhenti ketika f(m<sub>k</sub>) sekecil mungkin. Misalkan x<sup>*</sup> sebagai akar yang tidak diketahui. Error yang akan didapat

> |x<sup>*</sup> - m<sub>k</sub>| < |b<sub>k</sub> - a<sub>k</sub>| = 2<sup>-k</sup>|b<sub>0</sub> - a<sub>0</sub>|.

Keuntungan dari metode bagi dua ini adalah bahwa hal itu dijamin untuk terpusat ke akar, dari pembentukan. Jika ada beberapa akar, metode bisection akan memusat ke salah satu dari beberapa akar tersebut (sehingga tidak dapat mengontrol akar yang akan dipilih oleh metode tersebut).

Adapun ringkasan dari proses membagi dua tersebut sebagai berikut.
![Alt text](https://github.com/berviantoleo/mycapturepicrepo/raw/master/Numerical-Analysis/langkah.PNG "Proses Membagi Dua")
###### Gambar 4 - Proses pada Metode Bagi Dua
###### Sumber : [1][1]

#### Kondisi Berhenti Iterasi
Kondisi berhenti iterasi dapat dipilih salah satu dari kriteria berikut :

1. Lebar selang baru : |a-b| < &epsilon;, yang dalam hal ini &epsilon; adalah nilai toleransi lebar selang yang mengurung akar.
2. Nilai fungsi di hampiran akar: f(c) < &mu;, yang dalam hal ini &mu; adalah nilai yang sangat kecil mendekati 0.
3. Galat relatif hampiran akar: |(c<sub>baru</sub> - c<sub>lama</sub>) / c<sub>baru</sub>| < &delta;, yang dalam hal ini &delta; adalah galat relatif hampiran yang diinginkan.

## Contoh Penerapan
Sebagai contoh dapat digunakan fungsi berikut ini untuk dicari akar-akarnya.

1. f(x) = e<sup>x</sup> - 5x<sup>2</sup>
  1. Grafik
     
     Agar memudahkan, saya akan memberikan gambar grafik dengan perbesaran yang berbeda untuk menunjukan daerah akar-akarnya.
     
     ![Alt text](https://raw.githubusercontent.com/berviantoleo/mycapturepicrepo/master/Numerical-Analysis/example1%2C1.PNG "Perbesaran -4 sampai 5")
     ###### Gambar 5 - Grafik pada interval -4 sampai 5
     ###### Sumber : Dokumen Pribadi

     ![Alt text](https://raw.githubusercontent.com/berviantoleo/mycapturepicrepo/master/Numerical-Analysis/example1%2C2.PNG "Perbesaran -40 sampai 40")
     ###### Gambar 6 - Grafik pada interval -40 sampai 40
     ###### Sumber : Dokumen Pribadi

  2. Tabel Nilai
     
     Tabel nilai ini dimulai dari a = -0.5 sampai v = 1.4 dengan kenaikan absis sebesar h = 0.1.

     | x      | f(x)      |
     |:------:|:---------:|
     | -0.50  | -0.643469 |
     | -0.40  | -0.129680 |
     | -0.30  |  0.290818 |
     | -0.20  |  0.618731 |
     | -0.10  |  0.854837 |
     |  0.00  |  1.000000 |
     |  0.10  |  1.055171 |
     |  0.20  |  1.021403 |
     |  0.30  |  0.899859 |
     |  0.40  |  0.691825 |
     |  0.50  |  0.398721 |
     |  0.60  |  0.022119 |
     |  0.70  | -0.436247 |
     |  0.80  | -0.974459 |
     |  0.90  | -1.590397 |
     |  1.00  | -2.281718 |
     |  1.10  | -3.045834 |
     |  1.20  | -3.879883 |
     |  1.30  | -4.780703 |
     |  1.40  | -5.744800 |
     
    Dari tabel tersebut selang-selang yang dapat dipilih dan mengandung akar:
    
    [-0.40,-0.30]
    
    [0.60,0.70]
    
  3. Iterasinya

## Referensi

1. Slide "Solusi Persamaan Nirlanjar" oleh Rinaldi Munir. [Go To Source][1]
2. Catatan Dosen dalam MIT Open Courseware pada kuliah [Introduction to Numerical Analysis](http://ocw.mit.edu/courses/mathematics/18-330-introduction-to-numerical-analysis-spring-2012/index.htm). Menerjemahkan dan mengambil sebagian konten [ini](http://ocw.mit.edu/courses/mathematics/18-330-introduction-to-numerical-analysis-spring-2012/lecture-notes/MIT18_330S12_Chapter4.pdf). [License link](http://ocw.mit.edu/terms/)

[1]: http://informatika.stei.itb.ac.id/~rinaldi.munir/MetNum/2010-2011/Solusi%20Persamaan%20Nirlanjar%20%28Bag%201%29.pdf
