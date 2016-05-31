<b> <h1> Berbagai Algoritma Pemecahan <i> Maximum Flow Problem </i> </h1> </b> 

<p> <i> Maximum-flow problem </i> (Permasalahan Aliran Maksimum) merupakan salah satu model yang seringkali digunakan dalam optimasi suatu sistem di dunia nyata sehingga sistem tersebut menghasilkan produksi semaksimal mungkin. <i>Maximum-flow</i> (aliran maksimum) suatu sistem ditinjau untuk mengetahui jumlah maksimum yang dapat dilalui oleh suatu aliran tertentu dari satu sumber ke suatu tampungan. Jumlah yang dialirkan dari sumber sama dengan jumlah yang berada pada tampungan. <i>Maximum-flow problem</i> digambarkan dalam suatu graf berarah dengan masing-masing sisi berperan sebagai arah aliran dan masing-masing sisi memiliki bobot. Ilustrasi singkat mengenai konsep <i>maximum-flow problem</i> akan dijelaskan di bawah ini. </p>
<p> Graf di atas menunjukan aliran yang berasal dari suatu sumber (<i>source</i>) S ke penampungan (<i>sink</i>) T dengan melewati keempat simpul, yaitu V1, V2, V3, dan V4. Anggap sisi-sisi pada graf sebagai pipa. Setiap pipa memiliki bobot. Bobot tersebut menunjukan jumlah aliran (<i>flow</i>) yang telah melewati pipa dari sumber menuju penampungan, serta kapasitas maksimum aliran (/i>capacity</i>) yang dilewati oleh sebuah pipa. Kedua bobot tersebut dituliskan dengan cara jumlah aliran di sebelah kiri dan kapasitas dituliskan sebelah kanan, keduanya dibatasi dengan garis miring ‘/’ atau garis lurus ‘|’. </p>
<p> Dari graf tersebut di atas, akan dicari aliram maksimum yang mungkin dari sumber S ke penampungan T dengan syarat sebagai berikut: <br>
a.	Jumlah aliran pada pipa tidak melebih jumlah kapasitas pipa, <br>
b.	Jumlah aliran yang masuk dari dari satu simpul ke simpul lain. </p>
<p> Untuk mencari aliran maksimum pada graf tersebut bukanlah hal mudah. Harus diperhatikan bahwa setiap sisi memiliki kapasitas yang berbeda-beda, sedangkan jumlah aliran yang melewati pipa dari sumber ke penampungan haruslah sama sehingga aliran maksimum bukan hanya mengenai kapasitas satu sisi, melainkan memperhitungkan kapasitas banyak sisi. Selain itu, sebagian besar simpul berderajat lebih dari satu, artinya aliran mengalami percabangan sehingga perhitungannya menjadi lebih rumit. </p>
<p>     Oleh karena itu, dibuatlah algoritma-algoritma yang dapat memecahkan permasalahan <i>maximum-flow</i> ini. Pada tulisan ini, akan dijelaskan lebih lanjut mengenai algoritma pemecahan <i>maximum-flow problem</i>. </p>

<b> <h3> Algortima Ford-Fulkerson </h3> </b>
<p> Salah satu algoritma pemecahan masalah aliran maksimum paling terkenal adalah Algoritma Ford-Fulkerson. Algoritma ini ditemukan oleh   Algoritma ini memecahkan masalah dengan cara mencari lintasan dari sumber ke penampungan yang masih memiliki kapasitas untuk dilewati sehingga aliran bisa melewati lintasan tersebut dengan jumlah semaksimal mungkin. </p>
<p> Langkah-langkah dalam melakukan algoritma Ford-Fulkerson untuk mencari aliran maksimum adalah sebagai berikut: <br>


