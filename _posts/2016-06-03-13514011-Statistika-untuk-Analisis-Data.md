---
layout:     post
title:      Statistika untuk Analisis Data
date:       2016-06-03
summary:    Micky Yudi Utama/13514011
categories: tugas
---

## Daftar Isi
* [Pendahuluan](#pendahuluan)
* [Statistika Parametrik](#statistika-parametrik)
   * [ANOVA](#anova)
   * [Korelasi Pearson](#korelasi-pearson)
   * [Uji-T](#uji-t)
   * [Uji-F](#uji-f)
* [Statistika Non-Parametrik](#statistika-non-parametrik)
   * [Uji Ranking Bertanda Wilcoxon](#uji-ranking-bertanda-wilcoxon)
   * [Uji Mann Whitney](#uji-mann-whitney)
   * [Uji Kruskal Wallis](#uji-kruskal-wallis)
   * [Uji Kesamaan Variansi](#uji-kesamaan-variansi)
      * [Uji Hartley](#uji-hartley)
      * [Uji Bartlett](#uji-bartlett)
      * [Uji Levene](#uji-levene)
   * [Uji Cochran C](#uji-cochran-c)
   * [Uji Komparansi Berganda](#uji-komparansi-berganda)
      * [Uji Tukey](#uji-tukey)
      * [Uji Duncan](#uji-duncan)
    * [Uji Dunnett](#uji-dunnett)
  * [Uji Ukuran Kebergantungan](#uji-ukuran-kebergantungan)
    * [Korelasi Spearman](#korelasi-spearman)
    * [Korelasi Kendall Tau](#korelasi-kendall-tau)
* [Kesimpulan](#kesimpulan)
* [Referensi](#referensi)

## Pendahuluan
Statistika merupakan ilmu pengetahuan yang mempelajari bagaimana merencanakan, mengumpulkan, menganalisis, menginterpretasi, dan mempresentasikan data. Berdasarkan kegiatannya, statistika dibagi menjadi dua bagian, yaitu statistika deskriptif (statistika deduktif) dan statistika inferensi (statistika induktif). Statistika deskriptif adalah kegiatan statistika tentang pengumpulan, penyajian, penyederhanaan, dan penentuan ukuran-ukuran khusus dari suatu data tanpa penarikan kesimpulan. Statistika inferensi adalah kegiatan statistika tentang penarikan kesimpulan dan pengambilan keputusan dari suatu data yang ada. 

Salah satu kegunaan dari mempelajari statistika adalah untuk analisis data. Dengan menganalisis data, kita mampu menyimpulkan/memperoleh suatu informasi dari suatu data. Misalnya, jika kita ingin mengetahui manakah algoritma yang lebih cepat dalam melakukan pengurutan antara algoritma insertion dan selection. Seperti yang kita ketahui algoritma insertion dan selection memiliki kompleksitas waktu yang sama yaitu O(n<sup>2</sup>). Dengan memperoleh data waktu eksekusi untuk masing-masing algoritma untuk beberapa jumlah data yang ingin diurutkan, kita dapat mengetahui sebenarnya algoritma mana yang lebih cepat dengan beberapa metode dan uji dalam statistika. Pada artikel ini akan dibahas mengenai beberapa metode yang umumnya digunakan dalam melakukan analisis data.

## Statistika Parametrik
Uji parametrik digunakan ketika data yang ada memenuhi beberapa asumsi. Jika asumsi ada yang tidak terpenuhi, tetapi tetap digunakan uji parametrik maka hasil yang didapat tidak akurat atau bias. Berikut beberapa asumsi pada uji parametrik:
<br>1. Data berdistribusi normal
<br>2. Data memiliki varian yang homogen
<br>3. Jenis data rasio atau interval
<br>4. Hubungan antar data independent

### ANOVA
Metode ANOVA (Analysis of Variance) digunakan untuk mengetahui kesamaan rataan dari beberapa populasi. Metode ANOVA dapat diterapkan ketika data yang ada berdistribusi normal, memiliki variansi yang sama, dan sampel tidak berhubungan satu dengan yang lainnya. Prosedurnya dapat dilihat pada slide [ANOVA](https://core.ac.uk/download/files/379/11707013.pdf) halaman 3-8.

### Korelasi Pearson
Korelasi Pearson digunakan untuk mengetahui ada tidaknya hubungan antara variabel bebas dan variabel tergantung yang berskala interval atau rasio. Nilai korelasi dapat menghasilkan angka positif ataupun angka negatif. Jika nilai korelasi positif, berarti hubungan bersifat searah yang artinya jika variabel bebas membesar, variabel tergantung juga semakin membesar. Jika nilai korelasi negatif, berarti hubungan bersifat tidak searah yang artinya jika nilai variabel bebas membesar, variabel tergantung semakin mengecil. Nilai korelasi berkisar antara 0-1. Prosedurnya dapat dilihat pada [link](http://setabasri01.blogspot.co.id/2011/04/uji-korelasi-pearson.html)

### Uji-T
Uji-T yang juga disebut uji parsial, digunakan untuk menguji pengaruh masing-masing variabel bebas secara individu terhadap variabel terikatnya. Prosedurnya dapat dilihat pada [link](https://titaviolet.wordpress.com/2009/07/17/pengujian-hipotesis-distribusi-uji-t-dan-f-pada-model-regresi-berganda/).

### Uji-F
Uji-F digunakan untuk menguji pengaruh semua variabel bebas secara bersama-sama terhadap variabel terikatnya. Prosedurnya dapat dilihat pada [link](https://titaviolet.wordpress.com/2009/07/17/pengujian-hipotesis-distribusi-uji-t-dan-f-pada-model-regresi-berganda/).

## Statistika Non-Parametrik
Uji parametrik digunakan ketika data yang ingin diuji tidak memenuhi asumsi pada uji parametrik. Uji non-parametrik hanya memiliki sedikit batasan, beberapa diantaranya adalah:
<br>1. Data bersifat independent, kecuali data berpasangan
<br>2. Jenis data dapat ordinal atau nominal
<br>3. Jumlah sampel yang digunakan sedikit, tidak sebanyak pada uji parametrik

### Uji Ranking Bertanda Wilcoxon
Uji Ranking Bertanda Wilcoxon digunakan untuk menguji kondisi (variabel) pada sampel yang berpasangan. Uji ini menggunakan median. Prosedurnya dapat dilihat pada buku [Catatan Kuliah Statistika Non-Parametrik](https://www.dropbox.com/sh/6a0th27cft94cp5/AAAKLrf9A2ZhQy-Nx6v3qrhja/Catatan%20Kuliah%20Statistika%20Non%20Parametrik.pdf?dl=0) halaman 7-8.

### Uji Mann-Whitney
Uji Mann-Whitney digunakan untuk mengetahui apakah terdapat perbedaan respon dari 2 populasi data yang saling independen. Uji ini merupakan alternatif lain dari uji t parametrik ketika data yang yang diambil dalam penelitian lebih lemah dari skala interval. Prosedurnya dapat dilihat pada buku [Catatan Kuliah Statistika Non-Parametrik](https://www.dropbox.com/sh/6a0th27cft94cp5/AAAKLrf9A2ZhQy-Nx6v3qrhja/Catatan%20Kuliah%20Statistika%20Non%20Parametrik.pdf?dl=0) halaman 15-16.

### Uji Kruskal-Wallis
Uji Kruskal-Wallis merupakan uji berbasis peringkat yang bertujuan untuk menentukan adakah perbedaan signifikan secara statistik antara dua atau lebih kelompok variabel independen pada variabel dependen yang berskala data numerik dan skala ordinal. Uji Kruskal Wallis umumnya digunakan untuk menggantikan uji One Way ANOVA apabila asumsi pada uji tersebut ada yang tidak terpenuhi. Selain itu, uji ini juga digunakan sebagai perluasan dari uji Mann Whitney, di mana uji Mann Whitney hanya dapat digunakan pada dua kelompok variabel dependen. Sedangkan uji Kruskal Wallis dapat digunakan pada 2 atau lebih kelompok dependen. Prosedurnya dapat dilihat pada buku [Catatan Kuliah Statistika Non-Parametrik](https://www.dropbox.com/sh/6a0th27cft94cp5/AAAKLrf9A2ZhQy-Nx6v3qrhja/Catatan%20Kuliah%20Statistika%20Non%20Parametrik.pdf?dl=0) halaman 25-26.

### Uji Kesamaan Variansi
Uji ini digunakan untuk mengetahui kesamaan variansi dari 2 atau lebih populasi. Uji ini biasanya diterapkan sebelum menerapkan metode ANOVA karena pada ANOVA dibutuhkan asumsi kesamaan variansi.

#### Uji Hartley
Uji Hartley dikenal dengan prosedur yang relatif mudah, namun memberikan akurasi yang kurang baik. Pada uji ini, data yang digunakan harus memenuhi beberapa asumsi yaitu, data berdistribusi normal dan jumlah data tiap populasi harus sama. Prosedurnya dapat dilihat pada buku [Catatan Kuliah Statistika Non-Parametrik](https://www.dropbox.com/sh/6a0th27cft94cp5/AAAKLrf9A2ZhQy-Nx6v3qrhja/Catatan%20Kuliah%20Statistika%20Non%20Parametrik.pdf?dl=0) halaman 18.

#### Uji Bartlett
Uji Bartlett memberikan akurasi yang lebih baik dibandingkan uji Hartley. Data yang digunakan harus memiliki distribusi normal. Prosedurnya dapat dilihat pada buku [Catatan Kuliah Statistika Non-Parametrik](https://www.dropbox.com/sh/6a0th27cft94cp5/AAAKLrf9A2ZhQy-Nx6v3qrhja/Catatan%20Kuliah%20Statistika%20Non%20Parametrik.pdf?dl=0) halaman 19-20.

#### Uji Levene
Uji Levene memiliki akurasi paling baik dibandingkan dua uji lainnya namun memiliki perhitungan yang sangat rumit. Selain itu, uji ini tidak membutuhkan asumsi. Prosedurnya dapat dilihat pada buku [Catatan Kuliah Statistika Non-Parametrik](https://www.dropbox.com/sh/6a0th27cft94cp5/AAAKLrf9A2ZhQy-Nx6v3qrhja/Catatan%20Kuliah%20Statistika%20Non%20Parametrik.pdf?dl=0) halaman 20-21.

### Uji Cochran C
Ketika kita melakukan uji kesamaan variansi pada suatu data dan pada uji tersebut dihasilkan bahwa populasi tersebut memiliki variansi berbeda, kadangkala kita ingin mengetahui populasi yang mana yang menyebabkan variansi yang berbeda. Hal tersebut dapat diketahui dengan melakukan uji Cochran C. Uji Cochran C digunakan untuk mendeteksi populasi yang mempunyai variansi yang berbeda. Uji Cochran C lebih baik digunakan pada data yang berdistribusi normal. Prosedurnya dapat dilihat pada buku [Catatan Kuliah Statistika Non-Parametrik](https://www.dropbox.com/sh/6a0th27cft94cp5/AAAKLrf9A2ZhQy-Nx6v3qrhja/Catatan%20Kuliah%20Statistika%20Non%20Parametrik.pdf?dl=0) halaman 22-23.

### Uji Komparansi Berganda
Pada ANOVA, ketika hipotesis nol ditolak kita hanya mengetahui bahwa paling tidak ada satu populasi yang memiliki rataan yang berbeda dari rataan populasi lainnya. Untuk mengetahui populasi mana yang memiliki rataan yang berbeda perlu dilakukan uji komparansi berganda.

#### Uji Tukey
Uji Tukey melakukan perhitungan dengan membandingkan tiap 2 populasi sehingga kita mengetahui antara satu populasi dengan satu populasi yang lain memiliki rataan yang sama atau tidak. Prosedurnya dapat dilihat pada buku [Catatan Kuliah Statistika Non-Parametrik](https://www.dropbox.com/sh/6a0th27cft94cp5/AAAKLrf9A2ZhQy-Nx6v3qrhja/Catatan%20Kuliah%20Statistika%20Non%20Parametrik.pdf?dl=0) halaman 30.

#### Uji Duncan
Uji Duncan memiliki konsep yang hampir sama dengan uji Tukey, namun lebih efektif karena uji ini dapat mendeteksi kesamaan rataan dari dua populasi atau lebih secara sekaligus. Uji ini memberikan hasil kelompok-kelompok populasi dengan rataan yang sama. Prosedurnya dapat dilihat pada buku [Catatan Kuliah Statistika Non-Parametrik](https://www.dropbox.com/sh/6a0th27cft94cp5/AAAKLrf9A2ZhQy-Nx6v3qrhja/Catatan%20Kuliah%20Statistika%20Non%20Parametrik.pdf?dl=0) halaman 31-32.

#### Uji Dunnett
Pada uji Dunnett, dibutuhkan populasi kontrol. Uji Dunnett memberikan informasi kesamaan rataan dari populasi kontrol dengan populasi lainnya. Prosedurnya dapat dilihat pada buku [Catatan Kuliah Statistika Non-Parametrik](https://www.dropbox.com/sh/6a0th27cft94cp5/AAAKLrf9A2ZhQy-Nx6v3qrhja/Catatan%20Kuliah%20Statistika%20Non%20Parametrik.pdf?dl=0) halaman 32-33.

### Uji Ukuran Kebergantungan

#### Korelasi Spearman
Korelasi Spearman digunakan untuk menguji hipotesis asosiatif dua variabel bila datanya berskala ordinal. Nilai korelasi ini disimbolkan dengan &rho; (dibaca: rho). Nilai korelasi Spearman berada diantara -1 dan 1. Jika nilainya 0, berarti tidak ada korelasi atau tidak ada hubungan antara variabel independen dan dependen. Jika nilainya 1, berarti terdapat hubungan yang positif antara variabel independen dengan variabel dependen. Jika nilainya -1, berarti terdapat hubungan yang negatif antara variabel independen dengan variabel dependen. Prosedurnya dapat dilihat pada buku [Catatan Kuliah Statistika Non-Parametrik](https://www.dropbox.com/sh/6a0th27cft94cp5/AAAKLrf9A2ZhQy-Nx6v3qrhja/Catatan%20Kuliah%20Statistika%20Non%20Parametrik.pdf?dl=0) halaman 35.

#### Korelasi Kendall Tau
Korelasi Kendall's Tau memiliki sifat yang sama dengan korelasi Spearman, hanya saja dasar pemikirannya berbeda. Nilai korelasi ini disimbolkan dengan &tau; (dibaca: tau). Prosedurnya dapat dilihat pada buku [Catatan Kuliah Statistika Non-Parametrik](https://www.dropbox.com/sh/6a0th27cft94cp5/AAAKLrf9A2ZhQy-Nx6v3qrhja/Catatan%20Kuliah%20Statistika%20Non%20Parametrik.pdf?dl=0) halaman 37.

## Kesimpulan
Artikel ini tentu saja tidak dapat membahas semua uji yang ada pada statistika. Untuk uji-uji tertentu prosedurnya dapat dicari pada internet. Selain menghitung secara manual, saat ini sudah banyak software yang dibuat untuk mempermudah analisis data, seperti menggunakan software XLSTAT dan MiniTab. Alangkah baiknya jika kita ingin melakukan analisis data, kita membahasnya terlebih dahulu kepada yang lebih ahli seperti dosen statistika.

## Referensi
1. http://www.statistik4life.com/2015/10/statistik-parametrik-dan-non-parametrik.html
2. http://tu.laporanpenelitian.com/2014/10/7.html
3. http://statistikceria.blogspot.co.id/2014/06/uji-ranking-bertanda-wilcoxon.html
4. https://mufusai.files.wordpress.com/2013/04/uji-mann-whitney.pdf
5. https://www.dropbox.com/sh/6a0th27cft94cp5/AAAKLrf9A2ZhQy-Nx6v3qrhja/Catatan%20Kuliah%20Statistika%20Non%20Parametrik.pdf?dl=0
6. http://www.statistikian.com/2013/01/uji-f-dan-uji-t.html
7. http://statistikskripsitesis.blogspot.co.id/2014/02/menghitung-uji-hipotesis-rata-rata.html
8. https://core.ac.uk/download/files/379/11707013.pdf
9. https://titaviolet.wordpress.com/2009/07/17/pengujian-hipotesis-distribusi-uji-t-dan-f-pada-model-regresi-berganda/
10. http://setabasri01.blogspot.co.id/2011/04/uji-korelasi-pearson.html
