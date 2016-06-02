---
layout:     post
title:      Enkripsi pada BASE64 dan BASE32
date:       2016-06-02
summary:    Silakan klik pada judul untuk penjelasan tugas
categories: tugas
---

---

---

By:  Johan 13514026

---

---


# Kriptografi

Setiap manusia pasti memiliki *privacy*nya masing-masing. Ada informasi yang tidak boleh diketahui oleh orang lain. Di lain hal, seiring berkembangnya teknologi, informasi dapat diketahui dengan mudah dan cepat melalui internet. Untuk menjaga kerahasiaan, data-data informasi yang ada di internet biasanya disembunyikan menggunakan sistem kriptografi yaitu dengan menyandikan isi informasi (plaintext) tersebut menjadi isi yang tidak dipahami melalui proses enkripsi (enchiper). Dan untuk memperoleh kembali informasi yang asli, dilakukan proses dekripsi (decipher). Kriptografi berasal dari bahasa Yunani “cryptos” artinya secret dan “graphein” yang artinya writing (tulisan). Sehingga kriptografi berarti tulisan rahasia. Jadi kriptografi dapat didefinisikan sebagai perpaduan antara ilmu dan seni.

Biasanya enkripsi dan dekripsi ini banyak dipakai dalam pengiriman pesan. Enkripsi dilakukan pada saat pengiriman dengan cara mengubah data asli menjadi data rahasia, sedangkan dekripsi dilakukan pada saat penerimaan dengan cara mengubah data rahasia menjadi data asli. Jadi data yang dikirimkan selama proses pengiriman adalah data rahasia, sehingga data asli tidak dapat diketahui oleh pihak yang tidak berkepentingan. Beberapa caranya adalah dengan algoritma [Base64] (#base64) dan [Base32] (#base32) yang akan dibahas di bawah. Base64 dan Base32 sebenarnya bukan enkripsi, namun hanyalah sebuah standar dari encoding.

###<a name="base64"></a> BASE 64
Istilah Base64 berasal dari konten pengkodean MIME tertentu.
> **Cara kerja BASE 64**
> *	Kelompokkan pesan setiap 3 karakter (3byte = 24 bit). Bila terdapat sisa di akhir, tambahkan (padding) bit 0 sehingga panjangnya genap 24 bit.
> * Pecah 24 bit tadi menjadi 4 kelompok yang masing-masing beranggotakan 6 bit.
> * Setiap kelompok sekarang punya 2^6 kemungkinan susunan bit, berarti ada 2^6 = 64 karakter yang tersedia untuk merepresentasikan 6 bit ini. Petakan setiap kelompok dengan karakter yang terdapat dalam tabel base64.

Base64 disusun oleh 64 karakter yang dimana karakternya berdasarkan RFC 1421 yang terdiri dari (A-Z, a-z, 0-9, +, /) Sehingga totalnya 64. Ditambah satu karakter khusus untuk padding byte yaitu “=”. Bila dalam kelompok 3-byte itu, satu byte terakhir hanya berisi padding bit, maka satu karakter “=” ditambahkan. Bila dua, maka dua karaker “=” (menjadi “==”)

|        Bit       |  Desimal | Karakter |      Bit      |  Desimal | Karakter |
|:----------------:|:--------:|:--------:|:-------------:|:--------:|:--------:|
|      000 000     |     0    |     A    |    100 000    |    32    |     g    |
|      000 001     |     1    |     B    |    100 001    |    33    |     h    |
|      000 010     |     2    |     C    |    100 010    |    34    |     i    |
|      000 011     |     3    |     D    |    100 011    |    35    |     j    |
|      000 100     |     4    |     E    |    100 100    |    36    |     k    |
|      000 101     |     5    |     F    |    100 101    |    37    |     l    |
|      000 110     |     6    |     G    |    100 110    |    38    |     m    |
|      000 111     |     7    |     H    |    100 111    |    39    |     n    |
|      001 000     |     8    |     I    |    101 000    |    40    |     o    |
|      001 001     |     9    |     J    |    101 001    |    41    |     p    |
|      001 010     |    10    |     K    |    101 010    |    42    |     q    |
|      001 011     |    11    |     L    |    101 011    |    43    |     r    |
|      001 100     |    12    |     M    |    101 100    |    44    |     s    |
|      001 101     |    13    |     N    |    101 101    |    45    |     t    |
|       001 110    |    14    |     O    |    101 110    |    46    |     u    |
|      001 111     |    15    |     P    |    101 111    |    47    |     v    |
|      010 000     |    16    |     Q    |    110 000    |    48    |     w    |
|      010 001     |    17    |     R    |    110 001    |    49    |     x    |
|      010 010     |    18    |     S    |    110 010    |    50    |     y    |
|      010 011     |    19    |     T    |    110 011    |    51    |     z    |
|      010 100     |    20    |     U    |    110 100    |    52    |     0    |
|      010 101     |    21    |     V    |    110 101    |    53    |     1    |
|      010 110     |    22    |     W    |    110 110    |    54    |     2    |
|      010 111     |    23    |     X    |    110 111    |    55    |     3    |
|      011 000     |    24    |     Y    |    111 000    |    56    |     4    |
|      011 001     |    25    |     Z    |    111 001    |    57    |     5    |
|      011 010     |    26    |     a    |    111 010    |    58    |     6    |
|      011 011     |    27    |     b    |    111 011    |    59    |     7    |
|      011 100     |    28    |     c    |    111 100    |    60    |     8    |
|      011 101     |    29    |     d    |    111 101    |    61    |     9    |
|      011 110     |    30    |     e    |    111 110    |    62    |     +    |
|      011 111     |    31    |     f    |    111 111    |    63    |     /    |

> <img src="https://github.com/Johansentosa/IRK-img/blob/master/tabel%20base64.PNG">

> tabel indeks BASE 64

######contoh penggunaan base64 dalam melakukan encoding karakter
> _Plaintext_ = "ilmu rekayasa komputasi"

> Hasil yang didapatkan = "aWxtdSByZWtheWFzYSBrb21wdXRhc2k="

<img src = "https://github.com/Johansentosa/IRK-img/blob/master/Capture.PNG">

Pada contoh diatas dibagi per 3 karakter menjadi ilm, u r, eka, ….dst. Kata “ilm” diganti menjadi “aWxt”. Pada tabel ASCII, huruf i, l, m disimpan sebagai 105, 108, dan 109, atau dengan kata lain 01101001, 01101100, 01101101 pada binary atau bilangan berbasis 2. Apabila ketiga byte tersebut digabungkan, maka akan dihasilkan 24 bit buffer yaitu 011010010110110001101101. Angka tersebut dikonversi sehingga berbasis 64, dengan membagi 24bit tersebut menjadi masing-masing 6bit. Maka dihasilkan 4 bagian. Kemudian masing-masing bagian tersebut dikonversi ke nilai yang ada di Base64.
Jika pada terakhir terdapat sekelompok karakter yang dimiliki tidak bernilai 3Byte (24 bit) maka akan dilakukan padding. Pading dilakukan dengan menambahkan karakter ‘=’

<p>
<div align="center">
<img src="https://github.com/Johansentosa/IRK-img/blob/master/contoh.PNG">
</div>
</p>


###<a name="base32"></a> BASE 32
Base 32 pada dasarnya sama seperti base 64. Hanya saja pada base 32 menggunakan susunan 32 karakter yang terdiri dari (A-Z, 2-7) ditambah 1 karakter khusus untuk padding byte yaitu “=”. Ini merupakan standar yang sudah didefinisikan dari RFC 4648. 0 dan 1 dilewati karena adanya kemiripan dengan huruf O dan l.

> **Cara kerja BASE 32**
> *	Kelompokkan pesan setiap 5 karakter (5byte = 40 bit). Bila terdapat sisa di akhir, tambahkan (padding) bit 0 sehingga panjangnya genap 40 bit.
> * Pecah 40 bit tadi menjadi 8 kelompok yang masing-masing beranggotakan 5 bit.
> * Setiap kelompok sekarang punya 2^5 kemungkinan susunan bit, berarti ada 2^5 = 32 karakter yang tersedia untuk merepresentasikan 5 bit ini. Petakan setiap kelompok dengan karakter yang terdapat dalam tabel base32.

> <img src="https://github.com/Johansentosa/IRK-img/blob/master/contohB32.PNG">

<p>
<div align="center">
> <img src="https://github.com/Johansentosa/IRK-img/blob/master/tabel%20base32.PNG">

> tabel indeks BASE32
</div></p>

###BASE 64 vs BASE 32

