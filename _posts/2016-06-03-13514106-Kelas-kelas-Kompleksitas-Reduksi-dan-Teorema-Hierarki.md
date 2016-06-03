---
layout:     post
title:      Kelas-kelas Kompleksitas, Reduksi dan Teorema Hierarki
date:       2016-06-03
summary:    Penjelasan singkat mengenai kelas kompleksitas
categories: tugas
---

## Kelas Kompleksitas

### Definisi
Kelas kompleksitas adalah himpunan permasalahan yang kompleksitasnya memiliki keterhubungan. Biasanya, suatu kelas kompleksitas dapat dituliskan dalam bentuk:

> suatu himpunan permasalahan yang dapat diselesaikan menggunakan mesin abstrak M dengan O(f(*n*)) dari sumber R, di mana *n* adalah ukuran masukan.

Untuk lebih sederhananya, permasalahan dapat dikatakan termasuk dalam kelas kompleksitas yang sama jika memiliki kesamaan pada faktor-faktor berikut ini.

- Tipe permasalahan komputasi, misalnya permasalahan keputusan (*decision problems*), permasalahan fungsi (*function problems*), permasalahan penghitungan (*counting problems*), permasalahan optimasi (*optimization problems*), dll.
- Model komputasi, misalnya mesin Turing (deterministik/non-deterministik), sirkuit Boolean, sirkuit monoton, dll.
- Sumber yang dibatasi dan pembatasnya, biasanya kedua hal ini dinyatakan bersama, misalnya waktu polinom, ruang logaritmik, kedalaman konstan, dll.

### Contoh Kelas Kompleksitas
Berikut ini adalah beberapa contoh kelas kompleksitas dalam permasalahan keputusan.

Kelas Kompleksitas | Model Komputasi | Batasan Sumber
:---:|:---:|:---:
DTIME(*f(n)*)|Mesin Turing deterministik|Waktu *f(n)*
P|Mesin Turing deterministik|Waktu poli*(n)*
EXPTIME|Mesin Turing deterministik|Waktu 2<sup>poli*(n)*</sup>
NTIME(*f(n)*)|Mesin Turing non-deterministik|Waktu *f(n)*
NP|Mesin Turing non-deterministik|Waktu poli*(n)*
NEXPTIME|Mesin Turing non-deterministik|Waktu 2<sup>poli*(n)*</sup>
DSPACE(*f(n)*)|Mesin Turing deterministik|Ruang *f(n)*
L|Mesin Turing deterministik|Ruang O(log *n*)
PSPACE|Mesin Turing deterministik|Ruang poli*(n)*
EXPSPACE|Mesin Turing deterministik|Ruang 2<sup>poli*(n)*</sup>
NSPACE(*f(n)*)|Mesin Turing non-deterministik|Ruang *f(n)*
NL|Mesin Turing non-deterministik|Ruang O(log *n*)
NPSPACE|Mesin Turing non-deterministik|Ruang poli*(n)*
NEXPSPACE|Mesin Turing non-deterministik|Ruang 2<sup>poli*(n)*</sup>


## Reduksi
Reduksi adalah algoritma untuk mengubah suatu permasalahan ke permasalahan yang lain. Reduksi ini digunakan jika terjadi salah satu dari keadaan berikut ini.

1. Kita ingin memecahkan suatu permasalahan yang serupa dengan permasalahan lain yang sudah terselesaikan.
2. Kita memiliki permasalahan yang sudah terbukti sulit untuk diselesaikan, kemudian kita memiliki permasalahan baru yang serupa dengan permasalahan tersebut.

Reduksi yang biasanya digunakan adalah reduksi waktu-polinom, yaitu reduksi yang prosesnya membutuhkan waktu polinomial. Misalnya permasalahan penguadratan suatu bilangan bulat dapat direduksi ke dalam permasalahan mengalikan dua bilangan bulat. Artinya, algoritma perkalian dua buah bilangan bulat dapat digunakan untuk menguadratkan bilangan bulat, dengan cara memberikan masukan dua buah bilangan yang sama pada algoritma perkalian. Maka dapat dilihat bahwa penguadratan tidak lebih sulit dari perkalian, karena permasalahan penguadratan dapat direduksi ke permasalahan perkalian.

## Teorema Hierarki

### Teorema Hierarki Waktu
Sebuah fungsi dikatakan *time-constructible* jika terdapat suatu mesin Turing deterministik sedemikian hingga untuk setiap *n* dalam domain, ketika mesin tersebut dimulai dengan sebuah masukan *n*, ia akan berhenti setelah tepat *f(n)* langkah.

Teorema hierarki waktu dibedakan menjadi teorema hierarki waktu deterministik dan non-deterministik, dengan bunyi berikut ini secara berurutan.

> Jika *f(n)* adalah fungsi *time-constructible* maka terdapat permasalahan keputusan yang tidak dapat dipecahkan dalam waktu deterministik *worst-case* *f(n)* tetapi dapat dipecahkan dalam waktu deterministik *worst-case* *f(n)<sup>2</sup>*.

> Jika *g(n)* adalah fungsi *time-constructible* dan *f(n+1)*=o(*g(n)*), maka terdapat permasalahan keputusan yang tidak dapat dipecahkan dalam waktu non-deterministik *f(n)* tetapi dapat dipecahkan dalam waktu non-deterministik *g(n)*.

### Teorema Hierarki Ruang
Sebuah fungsi dikatakan *space-constructible* jika *f(n)* >= log *n* dan terdapat suatu mesin Turing yang dapat mengomputasi fungsi *f(n)* dalam ruang O(*f(n)*) ketika dimulai dengan masukan 1<sup>n</sup>, di mana 1<sup>n</sup> merepresentasikan sebuah string dengan *n* buah 1.

> Untuk setiap fungsi *space-constructible*, terdapat sebuah bahasa *L* yang dapat diputuskan di ruang O(*f(n)*) tetapi tidak pada ruang o(*f(n)*).

Teorema hierarki ruang dapat dibilang lebih kuat daripada teorema hierarki waktu, dapat dilihat dari hal-hal berikut ini.

- Hanya membutuhkan s(n) setidaknya log *n*, sedangkan teorema hierarki waktu membutuhkan setidaknya *n*.
- Dapat memisahkan kelas dengan perbedaan asimtot apapun, sedangkan teorema hierarki waktu harus menggunakan faktor logaritma.
- Hanya membutuhkan fungsi yang *space-constructible*, tidak harus *time-constructible*.
