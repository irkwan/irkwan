---
layout:     post
title:      Kelas Kompleksitas Pada Permainan
date:       2016-06-03
summary:    Membandingkan kelas kompleksitas.
categories: tugas
---
<br>
##Pendahuluan
Artikel ini akan membahas kompleksitas dari beberapa permainan, yang umumnya merupakan permainan papan (board game) seperti tic-tac-toe, checkers, dan catur. Selain itu juga membahas kompleksitas komputasinya jika permainan tersebut digeneralisasi.
<br>

##Dasar Teori

### Kompleksitas
Teori kompleksitas komputasi adalah teori yang mengklasifikasikan permasalahan komputasi berdasarkan tingkat kesulitannya dan hubungan dari kelas-kelas tersebut. Permasalahan komputasi dipahami sebagai sebuah masalah yang dapat diselesaikan dengan computer. Permasalahan dapat diselesaikan dengan aplikasi mekanik dari tahap-tahap matematika seperti algoritma.

#### Kelas-Kelas Kompleksitas

#### Kompleksitas Waktu
Kompleksitas waktu menunjukan jumlah waktu atau jumlah tahapan yang dibutuhkan suatu komputer untuk menyelesaikan masalah komputasi dengan menggunakan algoritma tertentu.

Deterministik :

| Kelas         | Batasan             |
| ------------- | ------------------- |
| DTIME         | Waktu f(n)          |
| P             | Waktu poly(n)       |
| EXPTIME       | Waktu 2^(poly(n))   |

Non-deterministik :

| Kelas         | Batasan             |
| ------------- | ------------------- |
| NTIME         | Waktu f(n)          |
| NP            | Waktu poly(n)       |
| NEXPTIME      | Waktu 2^(poly(n))   |

<br>

#### Kompleksitas Ruang
Kompleksitas ruang menunjukan jumlah total memori yang dibutuhkan suatu komputer untuk menyelesaikan masalah komputasi dengan menggunakan algoritma tertentu.

Deterministik :

| Kelas         | Batasan             |
| ------------- | ------------------- |
| DSPACE        | Ruang f(n)          |
| L             | Ruang O(log n)      |
| PSPACE        | Ruang poly(n)       |
| EXPTIME       | Ruang 2^(poly(n))   |

Non-deterministik :

| Kelas         | Batasan             |
| ------------- | ------------------- |
| NSPACE        | Ruang f(n)          |
| NL            | Ruang O(log n)      |
| NPSPACE       | Ruang poly(n)       |
| NEXPSPACE     | Ruang 2^(poly(n))   |

### Kompleksitas Permainan
Kompleksitas dari sebuah permainan dapat diukur dengan beberapa cara :

1. State-space complexity
<br>
State-space complexity adalah jumlah posisi legal yang mungkin dicapai dari posisi awal permainan. Meskipun sulit untuk dihitung secara akurat, upper bound masih dapat dihitung dengan mengikutsertakan posisi ilegal.

2. Game-tree complexity
<br>
Game-tree complexity adalah jumlah total permainan yang mungkin dimainkan, yaitu jumlah daun dari pohon permainan yang berakar pada posisi awal. Game-tree biasanya lebih besar dari state-space karena sebuah state dari permainan mungkin dicapai dari pergerakan (move) dengan urutan yang berbeda.

## Kompeleksitas pada beberapa permainan

1. Tic-tac-toe
<br>
Setiap sel pada papan mempunyai tiga kemungkinan, sehingga upper bound state-space pada tic-tac-toe dapat dihitung 3^9 = 19683. Namun jumlah ini masih mengikutsertakan posisi ilegal, seperti 5 buah cross tanpa nought. Dengan [perhitungan yang lebih teliti](http://imagine.kicbak.com/blog/?p=249), mengeliminasi posisi ilegal, maka didapat state-space sebanyak 5478.
<br>
Ukuran pohon permainan (game-tree) yaitu 9! = 362880 (ada 9 tempat yang mungkin dipilih pemain urutan pertama, 8 tempat untuk pemain urutan kedua, dan seterusnya). Pohon ini mengikutsertakan permainan yang ilegal dimana permainan tetap berlanjut meskipun sudah ada yang menang. Perhitungan yang lebih baik menghasilkan 255168 jumlah permainan yang mungkin.
<br>
2. Checkers 8x8 (English draughts)
<br>
Checkers diperkirakan mempunyai state-space dengan jumlah 10^20 dan game-tree dengan jumlah 10^40.
<br>
3. Catur.
Claude Shannon memperkirakan ada 10^43 posisi yang mungkin dalam catur (Shannon number). Perhitungan yang lebih baik menunjukan hasil yang lebih akurat sejumlah 10^46.7.
<br>
Berdasarkan asumsi rata-rata branching factor sebesar 35 dan lama permainan sebesar 80 turn, didapatkan 35^80 = 3 x 10^123 (Victor Allis).
<br>
## Permainan yang digeneralisasi
Permainan yang digeneralisasi adalah permainan yang ukuran papan permainannya digeneralisasi sehingga mungkin berukuran berapapun.
1. PSPACE-complete
<br>

2. EXPTIME-complete
## Summary
