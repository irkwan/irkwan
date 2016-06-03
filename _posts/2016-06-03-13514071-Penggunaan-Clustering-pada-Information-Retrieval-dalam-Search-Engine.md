---
layout: post
title: Penggunaan Clustering dalam Information Retrieval pada Search Engine
date: 2016-06-03
summary: Silahkan klik pada judul untuk melihat isi artikel
category: tugas
---

<br>

# Penggunaan *Clustering* dalam *Information Retrieval* pada *Search Engine*

## Information Retrieval
Dalam dunia teknologi, *information retrieval*, atau IR, dapat didefinisikan sebagai pencarian material dari 
suatu pengetahuan abstrak yang memenuhi informasi yang dibutuhkan dari suatu koleksi yang besar. Di konteks teknologi informasi, 
materi yang dicari umumnya berupa file, abstrak untuk pencarian adalah input teks, dan koleksi dapat berupa data yang disimpan 
di komputer. Perbedaan antara *information retrieval* dan *data retrieval* terletak pada hasil yang diberikan. 
Pada IR, hasil yang ditampilkan tidak harus sama persis dengan query. 
Oleh karena itu, seringkali IR menitikberatkan pada pencarian subjek atau topik, sedangkan *data retrieval* 
digunakan untuk pencarian data yang *exact*. Contoh IR yaitu pencarian melalui *search engine*, di mana hasil pencarian 
tidak harus memiliki kata yang sama persis dengan *query*. Di sisi lain, pencarian kata dalam dokumen teks merupakan contoh *data retrieval*.

## Konsep *Clustering*
*Clustering* dikembangkan atas dasar memperoleh informasi yang lebih cepat dalam IR. Konsepnya adalah mengembangkan suatu algoritma untuk 
membuat *cluster* atau kumpulan dokumen yang memiliki karakteristik yang mirip dalam satu *cluster*, namun secara jelas berbeda dengan 
*cluster* lainnya.

<img src = "http://i.imgur.com/BEZxTvq.png">
<br>
Gambar 1. Ilustrasi *clustering*
<br> <br>
Pada gambar di atas, data dikelompokkan menjadi 3 kelompok. Dalam satu *cluster*, data (file) memiliki kemiripan, namun harus dipastikan 
berbeda karakteristiknya dengan *cluster* lainnya.

## *Clustering vs Classification*
Clustering menggunakan unsupervised learning, artinya tidak ada manusia yang mengelompokkan data atau file ke dalam suatu cluster. 
Dalam clustering, distribusi data lah yang menentukan di cluster mana data tersebut akan ditempatkan. Sedangkan dalam klasifikasi, 
digunakan supervised learning, di mana ada orang yang menentukan pada kelompok mana data akan ditempatkan. 
Distribusi data ditentukan oleh aspek penting pada clustering, yaitu jarak data, atau sering dikenal sebagai jarak Euclidean. 
Jarak ini akan menentukan cluster yang terbentuk. Perbedaan jarak dapat memengaruhi jumlah cluster yang dibuat, dan data mana 
yang masuk ke dalam suatu cluster.

## *Clustering* pada *Information Retrieval*
Pada IR, *clustering berdasar* pada *cluster hypothesis*, yang menyatakan bahwa **dokumen dalam satu *cluster* memiliki karakter yang 
mirip dalam aspek relevansi terhadap kebutuhan informasi**. Dari hipotesis ini dapat disimpulkan bahwa jika suatu dokumen dalam suatu 
*cluster* menunjukkan relevansi terhadap *query* pencarian, maka kemungkinan besar dokumen lain dalam *cluster* tersebut juga relevan.
Dua metode utama dalam *clustering* adalah **hierarchial** dan **partitional clustering**. Dalam *partitional clustering*, data yang 
sudah ditempatkan dalam satu *cluster* tidak akan ditempatkan dalam *cluster* lainnya. Dengan kata lain, *partitional clustering* tidak 
memungkinkan terjadinya *overlapping*. Sedangkan *hierarchial clustering* membuat kumpulan *nested clusters* yang disusun menjadi sebuah pohon. 

Perbandingan antara metode IR dengan dan tanpa *clustering* dapat dilihat melalui bagan berikut.
<img src = "http://i.imgur.com/GC4lpGe.png">
<br>
Gambar 2. Alur pemrosesan hasil pencarian pada IFS
<br> <br>
<img src = "http://i.imgur.com/T86py42.png">
<br>
Gambar 3. Alur pemrosesan hasil pencarian dengan *clustering*
<br> <br>
Metode IR tanpa *clustering* yang diilustrasikan di atas adalah **IFS (inverted file search)**, yang merupakan metode yang paling banyak 
digunakan saat ini. Dapat dilihat, indeks yang dipakai berbeda. Dalam clustering, *indexing* telah diadaptasi sehingga *term-list* mengacu 
pada *cluster* tertentu. Hal ini menyebabkan pengambilan data lebih efisien karena tidak perlu menelusuri data di setiap term, cukup 
dengan mencari *cluster*nya saja.

## Evaluasi *Retrieval*
Evaluasi suatu model IR yang paling umum adalah menggunakan ukuran **R** (Recall) dan **P** (Precision). *Recall* didefinisikan sebagai 
rasio cacah dokumen relevan terpanggil dengan cacah total dokumen terpanggil, sedangkan *precision* didefinisikan sebagai rasio antara 
cacah dokumen relevan terpanggil dengan total cacah dokumen relevan dalam koleksi. Parameter yang menggabungkan kedua ukuran ini disebut 
**F-measure**, yang dihitung dengan rumus:
<br>
<img src = "http://i.imgur.com/9Wz0yc9.png">
<br>
Dengan β adalah parameter kepentingan relatif aspek *recall* dan *precision*. Jika *recall* dan *precision* sama penting, maka nilai β = 1.
Nilai F-measure yang lebih tinggi menyatakan kinerja yang lebih baik. Dalam berbagai penelitian, telah ditunjukkan bahwa IR dengan 
*clustering* secara umum menghasilkan nilai F-measure yang lebih baik jika dibandingkan dengan IR tanpa *clustering*.

## Penerapan pada *Search Engine*
Bagaimana *clustering* membantu *search engine*? Seringkali, *query* atau kata kunci pencarian yang kita masukkan memiliki polisemi. 
Contohnya, kata “sel” dapat dihubungkan dengan konteks biologi, tabel data, atau sel penjara. *Search engine* yang mengadaptasi sistem 
*clustering* menyediakan opsi bagi penggunanya untuk menampilkan hasil berdasarkan konteks-konteks tersebut. Contoh *search engine* yang menerapkan metode ini adalah **Yippy**, yang dikembangkan oleh Vivisimo.

<img src = "http://i.imgur.com/SzHh4T2.png">
<br>
Gambar 4. Screenshot *search engine* Yippy
<br> <br>
Pada gambar di atas, dapat dilihat dengan term "cell", pengguna dapat melihat hasil pencarian berdasarkan konteks tertentu. 
Lain halnya dengan *search engine* konvensional, untuk memperoleh hasil pencarian dengan suatu konteks perlu ditelusuri hingga halaman 
lebih lanjut.

#### Referensi
* [Introduction to Information Retrieval Chapter 1. 2009. Cambridge University Press](http://nlp.stanford.edu/IR-book/pdf/01bool.pdf)
* [Introduction to Information Retrieval Chapter 16. 2009. Cambridge University Press](http://nlp.stanford.edu/IR-book/pdf/16flat.pdf)
* [Amir Hamzah. Temu Kembali Informasi Berbasis Kluster untuk Sistem Temu Kembali Informasi Teks Bahasa Indonesia. 2009](http://jurtek.akprind.ac.id/sites/default/files/1-7_Amir.pdf)
* [Ogechukwu N. Iloanusi. Clustering: Applied to Data Structuring and Retrieval. 2011. Nigeria](https://thesai.org/Downloads/Volume2No11/Paper%2016-%20Clustering%20Applied%20to%20Data%20Structuring%20and%20Retrieval.pdf)
* [Hua Jun Zheng, et al. Learning to Cluster Web Search Result](http://research.microsoft.com/pubs/69103/19.pdf)
