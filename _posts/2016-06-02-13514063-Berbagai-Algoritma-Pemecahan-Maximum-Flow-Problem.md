---
layout:     post
title:      Berbagai Algoritma Pemecahan Maximum-Flow Problem
date:       2016-06-01 
summary:    Artikel yang diajukan untuk memenuhi tugas 2 calon IRK 2016
categories: tugas
---

<br>

# Berbagai Algoritma Pemecahan *Maximum-Flow Problem*

*Maximum-flow problem* (Permasalahan Aliran Maksimum) merupakan salah satu model yang seringkali digunakan dalam optimasi suatu sistem di dunia nyata sehingga sistem tersebut menghasilkan produksi semaksimal mungkin. *Maximum-flow* (aliran maksimum) suatu sistem ditinjau untuk mengetahui jumlah maksimum yang dapat dilalui oleh suatu aliran tertentu dari satu sumber ke suatu tampungan. Jumlah yang dialirkan dari sumber sama dengan jumlah yang berada pada tampungan. *Maximum-flow problem* digambarkan dalam suatu graf berarah dengan masing-masing sisi berperan sebagai arah aliran dan masing-masing sisi memiliki bobot. Ilustrasi singkat mengenai konsep *maximum-flow problem* akan dijelaskan di bawah ini.

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/94/Max_flow.svg/330px-Max_flow.svg.png">

Gambar 1. Graf Berarah dan Berbobot

Graf di atas menunjukan aliran yang berasal dari suatu sumber (*source*) **s** ke penampungan (*sink*) **t** dengan melewati keempat simpul, yaitu **o**, **p**, **q**, dan **r**. Anggap sisi-sisi pada graf sebagai pipa. Setiap pipa memiliki bobot. Bobot tersebut menunjukan jumlah aliran (*flow*) yang telah melewati pipa dari sumber menuju penampungan, serta kapasitas maksimum aliran (*capacity*) yang dilewati oleh sebuah pipa. Kedua bobot tersebut dituliskan dengan cara jumlah aliran di sebelah kiri dan kapasitas dituliskan sebelah kanan, keduanya dibatasi dengan garis miring ‘/’ atau garis lurus ‘|’.

Dari graf tersebut di atas, akan dicari aliram maksimum yang mungkin dari sumber S ke penampungan T dengan syarat sebagai berikut:
```sh
1. Jumlah aliran pada pipa tidak melebih jumlah kapasitas pipa
```
```sh
2. Jumlah aliran yang masuk dari dari satu simpul ke simpul lain sama.
```

Untuk mencari aliran maksimum pada graf tersebut bukanlah hal mudah. Harus diperhatikan bahwa setiap sisi memiliki kapasitas yang berbeda-beda, sedangkan jumlah aliran yang melewati pipa dari sumber ke penampungan haruslah sama sehingga aliran maksimum bukan hanya mengenai kapasitas satu sisi, melainkan memperhitungkan kapasitas banyak sisi. Selain itu, sebagian besar simpul berderajat lebih dari satu, artinya aliran mengalami percabangan sehingga perhitungannya menjadi lebih rumit.

Oleh karena itu, dibuatlah algoritma-algoritma yang dapat memecahkan permasalahan *maximum-flow* ini. Pada tulisan ini, akan dijelaskan lebih lanjut mengenai algoritma pemecahan *maximum-flow problem*. Algoritma yang akan dijabarkan pada tulisan kali ini adalah:

---

####1. [Algoritma Ford-Fulkerson] (#algoritma-ford-fulkerson)
####2. [Algoritmma Edmonds-Karp] (#algoritma-edmonds-karp)
####3. [Algoritma Dinic] (#algoritma-dinic)
####4. [Algoritma *Push-Relabel*] (#algoritma-push-relabel)

---

<br>
<br>

## Algoritma Ford-Fulkerson

Salah satu algoritma paling terkenal adalah Algoritma Ford-Fulkerson. Algoritma ini memecahkan masalah dengan cara mencari lintasan dari sumber ke penampungan yang masih memiliki kapasitas untuk dilewati sehingga aliran bisa melewati lintasan tersebut dengan jumlah semaksimal mungkin.

Langkah-langkah dalam mengimplementasikan algoritma Ford-Fulkerson untuk mencari aliran maksimum adalah sebagai berikut:

1. Menginisialisasi jumlah aliran dari sumber S ke penampungan T pada setiap sisi dengan 0.
2. Mencari lintasan *augmenting*. Lintasan *augmenting* merupakan lintasan yang berasal dari simpul sumber menuju simpul penampungan. Lintasan *augmenting* terbagi menjadi dua, yakni lintasan dengan sisi selanjutnya belum penuh (*non-full forward-edges*), atau lintasan dengan sisi sebaliknya tidak kosong (*non-empty backward-edge*). Sisi belum penuh berarti jumlah aliran lebih kecil sama dengan kapasitas. Sisi tidak kosong berarti jumlah aliran lebih besar nol. Misalkan pada Gambar 1, lintasan **s**, **o**, **q**, **t** merupakan lintasan *augmenting*. Begitu juga dengan lintasan **s**, **p**, **r**, **t**. Perlu diperhatikan bahwa dalam pemilihan lintasan augmenting, penghitung yang satu dengan yang lain dapat menghasilkan lintasan *augmenting* yang berbeda-beda, namun aliran maksimum total yang didapat hasilnya akan sama.
3. Selama masih ada lintasan *augmenting*, proses perhitungan terus berjalan. Perhitungan dilakukan berdasarkan kapasitas terkecil pada sisi dalam lintasan *augmenting* (*bottleneck capacity*). Jumlah aliran maksimum yang dapat dilalui suatu lintasan adalah kapasitas tersisa yang terkecil pada sisi dari lintasan tersebut. Kapasitas tersisa suatu sisi merupakan pengurangan dari kapasitas awal dengan jumlah aliran yang telah melewati sisi. Jumlah aliran maksimum suatu lintasan kemudian ditambahkan pada masing-masing jumlah aliran sisi yang terlibat pada lintasan tersebut.
4. Langkah 1 dan 2 dilakukan sampai lintasan *augmenting* sudah tidak ada.
5. Menjumlahkan semua jumlah aliran maksimum pada setiap lintasan *augmenting*. *Maximum-flow* suatu sistem merupakan total dari semua jumlah aliran maksimum pada setiap lintasan *augmenting*

Langkah algoritma tesebut pada pseucode dituliskan sebagai berikut:

<img src="http://courses.ics.hawaii.edu/ReviewICS311/morea/200.maximum-flow/fig/code-Ford-Fulkerson.jpg">

Gambar 2. *Pseudocode* Algoritma Ford-Fulkerson

Contoh pengimplementasian Algoritma Ford-Fulkerson pada pemecahan *maximum-flow problem* digambarkan pada ilustrasi di bawah ini.

<img src="http://staff.ustc.edu.cn/~csli/graduate/algorithms/book6/595_a.gif">

Gambar 3. Contoh pengimplementasian Algoritma Ford-Fulkerson pada pemecahan *maximum-flow problem*

<br>

## Algoritma Edmonds-Karp

Algoritma Edmonds-Karp merupakan penyempurnaan dari algoritma Ford-Fulkerson. Perbedaan mendasar dari kedua algoritma tersebut adalah pemilihan lintasan *augmenting*. Lintasan *augmenting* pada algoritma Ford-Fulkerson biasanya tidak ditentukan berdasarkan apapun asalkan terdapat *non-full forward-edges* dan *non-empty backward-edge*. Hal ini memungkinkan terjadi pemilihan lintasan *augmenting* yang kurang baik dan pemilihan-pemilihan selanjutnya akan terkena imbasnya sehingga menjadi kurang efisien. 

Pada algoritma Edmonds-Karp, pemilihan lintasan *augmenting* berdasarkan jumlah sisi paling sedikit pada beberapa pilihan lintasan. Lintasan dengan jumlah sisi paling sedikit akan didahulukan. Jika terdapat beberapa lintasan dengan jumlah sisi yang sama, maka yang didahulukan adalah lintasan dengan simpul memiliki abjad atau urutan terkecil. Pemilihan lintasan *augmenting* algoritma Edmonds-Karp ini menggunakan algoritma *Breadth-First Search* (BFS). Setiap pilihan lintasan dimasukkan ke dalam antrian. Lintasan dengn jumlah sisi paling sedikit didahulukan dalam antrian.

Langkah yang digunakan pada algoritma Edmonds-Karp sama dengan langkah yang digunakan pada algoritma Edmonds-Karp. Perbedaannya hanyalah pada langkah pemilihan lintasan *augmenting*. 

Langkah algoritma tesebut pada pseucode dituliskan sebagai berikut:

```sh
Edmonds-Karp(G,s,t)
1 for each edge (u, v) element of G.E
2      (u, v).f = 0
3 flow <- 0; Gf <- G 
4 while there exists a path p from s to t in the residual graph Gf
5      Let p be an s - t path in Gf with the minimum number of edges
6      Augment flow using P
7      Update Gf
8 return flow
```

<br>

## Algoritma Dinic

Algoritma Dinic merupakan algoritma pemecahan *maximum-flow problem*. Algoritma ini memanfaatkan konsep *blocking flow* dalam penentuan lintasan *augmenting*. *Blocking flow* pada suatu graf menyebabkan setidaknya memiliki satu sisi pada semua lintasan dari sumber ke penampungan yang jumlah alirannya sama dengan jumlah kapasitas maksimumnya (sisi tidak bisa dialiri lagi). Penjelasan mengenai penggunaan *blocking flow* akan dijelaskan lebih lanjut pada bagian langkah pengimplementasian algoritma Dinic di bawah ini.

Langkah-langkah dalam mengimplementasikan algoritma Dinic untuk mencari aliran maksimum adalah sebagai berikut:

1. Menginisialisasi jumlah aliran dari sumber S ke penampungan T pada setiap sisi dengan 0.
2. Mengonstruksi suatu graf residu relatif terhadap aliran yang ada. Graf residu merupakan graf yang menunjukan kapasitas ketika sudah ada suatu aliran yang mengalir di graf tersebut. Jika belum ada aliran yang mengalir, maka graf residu sama dengan graf awal (*flow* = 0). 
3. Membentuk lintasan *augmenting* dari graf residu. Jika tidak ada lintasan *augmenting* yang memenuhi (aturan penentuan lintasan *augmenting* sama dengan aturan pada algoritma Edmonds-Karp, yakni memilih lintasan dengan sisi tersedikit), maka keluarkan nilai *flow* yang telah didefinisikan sebelumnya. Jika terdapat lintasan *augmenting* yang memenuhi, maka *blocking flow* dibentuk. Dengan *blocking flow*, dapat dipastikan bahwa suatu lintasan *augmenting* memiliki sisi yang sudah penuh (jumlah aliran sisi sama dengan jumlah kapasitas maksimum sisi).  
4. Melakukan tahap 2 dan 3 sampai tidak terdapat lintasan *augmenting* yang memenuhi.
5. Menjumlahkan semua jumlah aliran maksimum pada setiap lintasan *augmenting*. *Maximum-flow* suatu sistem merupakan total dari semua jumlah aliran maksimum pada setiap lintasan *augmenting*

Langkah algoritma tesebut pada pseucode dituliskan sebagai berikut:

```sh
Dinic(G,s,t)
1  for each edge (u, v) element of G.E
2       (u, v).f = 0
3  flow <- 0; Gf <- G
4  while there exists a path p from s to t in the residual graph Gf
5       find blocking flow of path p in Gf
6       cf(p) <- blocking flow of path p in Gf
7       for each edge (u, v) in p
8            if (u, v) element of E
9                 (u, v).f <- (u, v).f + cf(p)
10           else (v, u).f <- (v, u).f - cf(p)
11      flow <- flow + cf(p)
12      Update Gf
13  return flow
```

<br>

## Algoritma *Push-Relabel*

Algoritma "push-relabel*, berbeda dengan tiga algoritma di atas, tidak menggunakan konsep lintasan *augmenting* sama sekali. 

<br>

#### Referensi
* http://www.geeksforgeeks.org/ford-fulkerson-algorithm-for-maximum-flow-problem/
* https://web.stanford.edu/class/cs97si/08-network-flow-problems.pdf
* http://www.cs.cornell.edu/courses/cs4820/2012sp/handouts/edmondskarp.pdf
* http://repository.ipb.ac.id/bitstream/handle/123456789/33525/G03ayu2.pdf?sequence=1&isAllowed=y
