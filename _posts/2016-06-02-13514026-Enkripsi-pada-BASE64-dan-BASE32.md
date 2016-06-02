---
layout:     post
title:      Enkripsi pada BASE64 dan BASE32
date:       2016-06-02
summary:    Silakan klik pada judul untuk penjelasan tugas
categories: tugas
---

# Kriptografi

Setiap manusia pasti memiliki *privacy*nya masing-masing. Ada informasi yang tidak boleh diketahui oleh orang lain. Di lain hal, seiring berkembangnya teknologi, informasi dapat diketahui dengan mudah dan cepat melalui internet. Untuk menjaga kerahasiaan, data-data informasi yang ada di internet biasanya disembunyikan menggunakan sistem kriptografi yaitu dengan menyandikan isi informasi (plaintext) tersebut menjadi isi yang tidak dipahami melalui proses enkripsi (enchiper). Dan untuk memperoleh kembali informasi yang asli, dilakukan proses dekripsi (decipher). Kriptografi berasal dari bahasa Yunani “cryptos” artinya secret dan “graphein” yang artinya writing (tulisan). Sehingga kriptografi berarti tulisan rahasia. Jadi kriptografi dapat didefinisikan sebagai perpaduan antara ilmu dan seni.

Biasanya enkripsi dan dekripsi ini banyak dipakai dalam pengiriman pesan. Enkripsi dilakukan pada saat pengiriman dengan cara mengubah data asli menjadi data rahasia, sedangkan dekripsi dilakukan pada saat penerimaan dengan cara mengubah data rahasia menjadi data asli. Jadi data yang dikirimkan selama proses pengiriman adalah data rahasia, sehingga data asli tidak dapat diketahui oleh pihak yang tidak berkepentingan. Beberapa caranya adalah dengan algoritma [Base64] (#base64) dan [Base32] (#base32) yang akan dibahas di bawah. Base64 dan Base32 sebenarnya bukan enkripsi, namun hanyalah sebuah standar dari encoding.

###<a name="base64"></a> BASE 64
Istilah Base64 berasal dari konten pengkodean MIME tertentu.
> **Cara kerja BASE 64**
> *	Kelompokkan pesan setiap 3 karakter (3byte = 24 bit). Bila terdapat sisa di akhir, tambahkan (padding) bit 0 sehingga panjangnya genap 24 bit.
> * Pecah 24 bit tadi menjadi 4 kelompok yang masing-masing beranggotakan 6 bit.
> * Setiap kelompok sekarang punya 26 kemungkinan susunan bit, berarti ada 26 = 64 karakter yang tersedia untuk merepresentasikan 6 bit ini. Petakan setiap kelompok dengan karakter yang terdapat dalam tabel base64.

Base64 disusun oleh 64 karakter yang dimana karakternya berdasarkan RFC 1421 yang terdiri dari (A-Z, a-z, 0-9, +, /) Sehingga totalnya 64. Ditambah satu karakter khusus untuk padding byte yaitu “=”. Bila dalam kelompok 3-byte itu, satu byte terakhir hanya berisi padding bit, maka satu karakter “=” ditambahkan. Bila dua, maka dua karaker “=” (menjadi “==”)

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
