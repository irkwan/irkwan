---
layout:     post
title:      Kelas Kompleksitas Pada Permainan
date:       2016-06-03
summary:    Membandingkan kelas kompleksitas.
categories: tugas
---
<br>
#Pendahuluan
Artikel ini akan membahas kompleksitas dari beberapa permainan, yang umumnya merupakan permainan papan (board game) seperti tic-tac-toe, checkers, dan catur. Selain itu juga membahas kompleksitas komputasinya jika permainan tersebut digeneralisasi.

#Dasar Teori

## Kompleksitas
Teori kompleksitas komputasi adalah teori yang mengklasifikasikan permasalahan komputasi berdasarkan tingkat kesulitannya dan hubungan dari kelas-kelas tersebut. Permasalahan komputasi dipahami sebagai sebuah masalah yang dapat diselesaikan dengan computer. Permasalahan dapat diselesaikan dengan aplikasi mekanik dari tahap-tahap matematika seperti algoritma.

### Kelas-Kelas Kompleksitas

### Kompleksitas Waktu
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

### Kompleksitas Ruang
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

## Kompleksitas Permainan
Kompleksitas dari sebuah permainan dapat diukur dengan beberapa cara :

1. State-space complexity
<br>
State-space complexity adalah jumlah posisi legal yang mungkin dicapai dari posisi awal permainan. Meskipun sulit untuk dihitung secara akurat, upper bound masih dapat dihitung dengan mengikutsertakan posisi ilegal.

2. Game-tree complexity
<br>
Game-tree complexity adalah jumlah total permainan yang mungkin dimainkan, yaitu jumlah daun dari pohon permainan yang berakar pada posisi awal. Game-tree biasanya lebih besar dari state-space karena sebuah state dari permainan mungkin dicapai dari pergerakan (move) dengan urutan yang berbeda.

