---
layout:     post
title:      Speech Recognition
date:       2016-06-03
summary:    Penjelasan singkat mengenai Speech Recognition
categories: tugas
---

# Speech Recognition

## Information Retrieval

Information Retrieval (IR) adalah pencarian objek informasi berdasarkan kata-kata kunci (*query*) tertentu pada sebuah database. Informasi yang ditemukan dapat berupa lebih dari 1 objek yang sesuai dengan *query* yang dimasukkan. Contohnya adalah pencarian halaman web pada *search engine* dengan menggunakan *query* dari pengguna. Biasanya hasil pencarian akan diurutkan berdasarkan hubungan objek tersebut dengan *query*. Jika objek semakin mendekati *query*, maka objek tersebut akan diurutkan lebih dahulu daripada yang kurang berhubungan. Kebanyakan sistem IR hanya menunjukkan hasil pencarian yang paling mendekati *query*, namun beberapa sistem mempunyai fitur untuk memperluas hasil pencarian yang ditunjukkan.

## Speech Recognition

Speech Recognition (SR) adalah salah satu bidang keilmuan yang mempelajari metodologi dan teknologi untuk komputer dapat mengenali dan menerjemahkan ucapan manusia menjadi teks. Dasar cara kerjanya adalah sistem memecah ucapan menjadi bagian-bagian kecil lalu membandingkan bagian-bagian tersebut dengan data suara pada sistem dan menentukan apakah ucapan tersebut. Kesulitan pada *speech recognition* adalah ucapan manusia tidak selalu baku, terutama dalam percakapan sehari-hari. Contohnya adalah pembicara dapat mengatakan kata "Eh", "Um", "Oh" dsb. yang bukan merupakan sebuah kata melainkan adalah kebiasaan manusia untuk mengatakan hal tersebut saat sedang berpikir. 

Sistem SR dibagi menjadi 2; sistem yang menganalisa ucapan 1 individu yang spesifik disebut *speech dependent*  dan sistem yang menganalisa ucapan berbagai individu adalah *speech independent*. Pembuatan sistem speech independent lebih sulit dari speech dependent karena harus menganalisa ucapan yang berbeda-beda dari banyak orang. Contoh aplikasi *speech recognition* adalah aplikasi Siri pada perangkat smartphone Apple maupun Cortana pada sistem operasi Windows 10.

![](http://cdn.redmondpie.com/wp-content/uploads/2012/01/SiriToggles.png)
Contoh aplikasi Siri yang dapat menganalisa dan memahami ucapan manusia

Penelitian pada *speech recognition* dimulai sejak tahun 1932 pada perusahaan Bell Labs. Perusahaan ini membuat sistem SR *single-speaker dependent* yang berkerja dengan mendeteksi komponen frekuensi pada ucapan manusia. Selanjutnya, Defense Advanced Research Projects Agency (DARPA) melanjutkan pengenmbangan sistem SR dan menghasilkan Effective Affordable Reusable Speech-to-Text (EARS) serta Global Autonomous Language Exploitation (GALE). Google mulai mengembangkan *speech recognition* pada tahun 2007 dan menghasilkan GOOG-411, sebuah sistem direktori berbasis telepon.

## Hidden Markov Model

Hidden Markov model (HMM) adalah representasi statistik sebuah ucapan, contohnya adalah sebuah kata; HMM digunakan karena sinyal suara dapat dilihat sebagai sebuah *stationary process* yang tidak berubah nilainya pada jangka waktu yang sangat kecil. Dalam menganalisa ucapan, HMM akan menghasilkan vektor-vektor dengan dimensi n setiap 10 milidetik. Pada setiap vektor, HMM akan membuat distribusi statistik dari vektor tersebut untuk menunjukkan kemungkinan ucapan yang diterima oleh sistem. 

Sistem *speech recognition* menggunakan HMM dapat dibagi 3; *Recognition* memetakan ucapan menjadi unit-unit akustik, *Feature Extraction* mengubah unit-unit tersebut menjadi fonetik, multi-fonetik dan kata, dan *IR Scoring* menentukan data suara manakah yang sesuai dengan query (hasil dari *Feature Extraction*). *IR Scoring* mempunyai 2 skema penilaian berbeda yaitu *Vector Space Model* (VSM) dan *Language Based*.

Kebanyakan sistem SR menggunakan HMM, namun akhir-akhir ini HMM mulai digantikan dengan *Long Short-Term Memory* (LSTM) yang dapat berkerja lebih baik daripada HMM.

## Speech Recognition Systems

Beberapa sistem SR yang menggunakan HMM adalah *keyword-spotting system* dan *large vocabulary recognition system*. *Keyword-spotting system* hanya mencari kata atau frasa tertentu untuk menganalisa ucapan. Oleh karena itu, sistem ini hanya membutuhkan HMM untuk *keyword* yang diinginkan dan model tambahan untuk mengenali kata-kata selain *keyword*. Sistem seperti ini akurat dan mempunyai biaya yang lebih kecil daripada *large vocabulary recognition system* serta dapat lebih mudah menangani ucapan dari percakapan natural yang cenderung tidak baku.

Sedangkan *large vocabulary recognition system* menggunakan konsep subkata; sistem tidak menggunakan beribu-ribu HMM untuk semua kata, namun menggunakan beberapa ratus HMM yang merepresentasikan subkata. Kata-kata dapat dirangkat dari subkata tersebut. Contohnya adakah kata *right* dapat dibuat dari subkata *R*, *AY*, dan *T*. Selain itu sistem ini membutuhkan model bahasa untuk membatasi kombinasi subkata yang digunakan agar lebih mendekati kata-kata yang memungkinkan. Contoh lagi adalah susunan kata *of the* lebih memungkinkan daripada susunan kata *oaf the* walaupun kedua kata tersebut terdengar serupa.

## Aplikasi

Aplikasi terbesar *speech recognition* adalah untuk menjalankan perintah tertentu hanya dengan mengatakan keyword tertentu. Contohnya adalah pada smartphone seperti Siri maupun pada kendaraan domestik maupun militer serta membantu orang cacat dalam berbicara. *Speech recognition* dapat membantu mempelajari bahasa lain maupun berkomunikasi dengan orang lain yang berbeda bahasa.

#### Referensi

[An Overview of Audio Information Retrieval](http://www.cs.princeton.edu/courses/archive/spr99/cs598b/foote_over.pdf)

[Information Retrieval Methods for Automatic Speech Recognition](http://research.microsoft.com/pubs/118811/Droppo-icassp2010.pdf)

[Voice Recognition](http://www.hitl.washington.edu/research/knowledge_base/virtual-worlds/EVE/I.D.2.d.VoiceRecognition.html)
