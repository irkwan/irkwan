---
layout:     post
title:      Tugas 2 Ca-IRK 2016
date:       2016-06-01 
summary:    Berbagai Algoritma Pemecahan Maximum-Flow Problem
categories: tugas
---

# Berbagai Algoritma Pemecahan *Maximum-Flow Problem*

*Maximum-flow problem* (Permasalahan Aliran Maksimum) merupakan salah satu model yang seringkali digunakan dalam optimasi suatu sistem di dunia nyata sehingga sistem tersebut menghasilkan produksi semaksimal mungkin. *Maximum-flow* (aliran maksimum) suatu sistem ditinjau untuk mengetahui jumlah maksimum yang dapat dilalui oleh suatu aliran tertentu dari satu sumber ke suatu tampungan. Jumlah yang dialirkan dari sumber sama dengan jumlah yang berada pada tampungan. *Maximum-flow problem* digambarkan dalam suatu graf berarah dengan masing-masing sisi berperan sebagai arah aliran dan masing-masing sisi memiliki bobot. Ilustrasi singkat mengenai konsep *maximum-flow problem* akan dijelaskan di bawah ini.

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/94/Max_flow.svg/330px-Max_flow.svg.png">

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

1. [*Linear Programming*] (#linear-programming)
2. [Algoritma Ford-Fulkerson] (#algoritma-ford-fulkerson)
3. [Algoritma Augmenting Path] (#algoritma-augmenting-path)


## *Linear Programming*

## Algoritma Ford-Fulkerson

## Algoritma *Augmenting Path*
