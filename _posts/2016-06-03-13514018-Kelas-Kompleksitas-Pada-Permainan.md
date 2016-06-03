---
layout:     post
title:      Kelas Kompleksitas Pada Permainan
date:       2016-06-03
summary:    Membandingkan kelas kompleksitas.
categories: tugas
---
<br>
## Pendahuluan
Artikel ini akan membahas kompleksitas dari beberapa permainan, yang umumnya merupakan permainan papan (board game) seperti tic-tac-toe, checkers, dan catur. Selain itu juga membahas kompleksitas komputasinya jika permainan tersebut digeneralisasi.
<br>

## Dasar Teori

### Kompleksitas
Teori kompleksitas komputasi adalah teori yang mengklasifikasikan permasalahan komputasi berdasarkan tingkat kesulitannya dan hubungan dari kelas-kelas tersebut. Permasalahan komputasi dipahami sebagai sebuah masalah yang dapat diselesaikan dengan computer. Permasalahan dapat diselesaikan dengan aplikasi mekanik dari tahap-tahap matematika seperti algoritma. 
<br>
<br>
Beberapa masalah yang mempunyai tingkat kompleksitas serupa dikelompokan dalam suatu kelas kompleksitas.
#### Kompleksitas Waktu
Kompleksitas waktu menunjukan jumlah waktu atau jumlah tahapan yang dibutuhkan suatu komputer untuk menyelesaikan masalah komputasi dengan menggunakan algoritma tertentu.

Deterministik Turing machine :

| Kelas         | Batasan             | Keterangan    |
| ------------- | ------------------- | ------------- |
| DTIME         | Time f(n)           |               |
| P             | Time poly(n)        | Polinomial    |
| EXPTIME       | Time 2^(poly(n))    | Eksponensial  |

Non-deterministik Turing machine :

| Kelas         | Batasan             | Keterangan    |
| ------------- | ------------------- | ------------- |
| NTIME         | Time f(n)           |               |
| NP            | Time poly(n)        | Polinomial    |
| NEXPTIME      | Time 2^(poly(n))    | Eksponensial  |

#### Kompleksitas Ruang
Kompleksitas ruang menunjukan jumlah total memori yang dibutuhkan suatu komputer untuk menyelesaikan masalah komputasi dengan menggunakan algoritma tertentu.

Deterministik Turing machine :

| Kelas         | Batasan             | Keterangan    |
| ------------- | ------------------- | ------------- |
| DSPACE        | Space f(n)          |               |
| L             | Space O(log n)      | Logaritmik    |
| PSPACE        | Space poly(n)       | Polinomial    |
| EXPTIME       | Space 2^(poly(n))   | Eksponensial  |

Non-deterministik Turing machine :

| Kelas         | Batasan             | Keterangan    |
| ------------- | ------------------- | ------------- |
| NSPACE        | Space f(n)          |               |
| NL            | Space O(log n)      | Logaritmik    |
| NPSPACE       | Space poly(n)       | Polinomial    |
| NEXPSPACE     | Space 2^(poly(n))   | Eksponensial  |

### Kompleksitas Permainan
Kompleksitas dari sebuah permainan dapat diukur dengan beberapa cara :

1. State-space complexity
<br>
State-space complexity adalah jumlah posisi legal yang mungkin dicapai dari posisi awal permainan. Meskipun sulit untuk dihitung secara akurat, upper bound masih dapat dihitung dengan mengikutsertakan posisi ilegal. Kompleksitas ini menggambarkan jumlah kombinasi kondisi papan permainan yang mungkin terjadi.

2. Game-tree complexity
<br>
Game-tree complexity adalah jumlah total permainan yang mungkin dimainkan, yaitu jumlah daun dari pohon permainan yang berakar pada posisi awal. Game-tree biasanya lebih besar dari state-space karena sebuah state dari permainan mungkin dicapai dari pergerakan (move) dengan urutan yang berbeda.

## Kompeleksitas pada beberapa permainan

1. Tic-tac-toe
<br>
Setiap sel pada papan mempunyai tiga kemungkinan, sehingga upper bound state-space pada tic-tac-toe dapat dihitung 3^9 = 19683. Namun jumlah ini masih mengikutsertakan posisi ilegal, seperti 5 buah cross tanpa nought. Dengan [perhitungan yang lebih teliti](http://imagine.kicbak.com/blog/?p=249), mengeliminasi posisi ilegal, maka didapat state-space sebanyak 5478.
Ukuran pohon permainan (game-tree) yaitu 9! = 362880 (ada 9 tempat yang mungkin dipilih pemain urutan pertama, 8 tempat untuk pemain urutan kedua, dan seterusnya). Pohon ini mengikutsertakan permainan yang ilegal dimana permainan tetap berlanjut meskipun sudah ada yang menang. Perhitungan yang lebih baik menghasilkan 255168 jumlah permainan yang mungkin.
<br>
<br>
2. Checkers 8x8 (English draughts)
<br>
Checkers diperkirakan mempunyai state-space dengan jumlah 10^20 dan game-tree dengan jumlah 10^40.
<br>
<br>
3. Catur
<br>
Claude Shannon memperkirakan ada 10^43 posisi yang mungkin dalam catur (Shannon number). Perhitungan yang lebih baik menunjukan hasil yang lebih akurat sejumlah 10^46.7.
Berdasarkan asumsi rata-rata branching factor sebesar 35 dan lama permainan sebesar 80 turn, didapatkan 35^80 = 3 x 10^123 (Victor Allis).
<br>

## Permainan yang digeneralisasi
Permainan yang digeneralisasi adalah permainan yang ukuran papan permainannya digeneralisasi sehingga mungkin berukuran berapapun.

1. Untuk permainan yang jumlah move nya sejumlah polinomial berdasarkan ukuran papan permainannya, menentukan kemungkinan menang untuk pemain pertama pada suatu posisi membutuhkan kompleksitas PSPACE-complete. Permainan yang termasuk PSPACE-complete misalnya tic-tac-toe.
<br>
<br>
2. Untuk permainan yang jumlah move nya sejumlah eksponensial berdasarkan ukuran papan permainannya, menentukan kemungkinan menang untuk pemain pertama pada suatu posisi membutuhkan kompleksitas EXPTIME-complete. Permainan yang termasuk EXPTIME-complete misalnya checkers dan catur.
<br>

## Kesimpulan
Besarnya kompleksitas permainan yang diukur dari jumlah posisi legal dan ukuran pohonnya menggambarkan variasi dari sebuah permainan. Semakin besar kompleksitasnya, maka semakin banyak alur permainan yang mungkin terjadi dari suatu permainan.
<br>
## Sumber
- http://imagine.kicbak.com/blog/?p=249
- http://www.sciencedirect.com/science/article/pii/0166218X7990012X
