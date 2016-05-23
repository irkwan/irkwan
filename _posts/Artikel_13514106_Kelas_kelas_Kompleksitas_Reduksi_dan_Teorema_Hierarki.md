# Kelas-kelas Kompleksitas: Reduksi dan Teorema Hierarki

## Kelas Kompleksitas
### Definisi
Kelas kompleksitas adalah himpunan permasalahan yang kompleksitasnya memiliki keterhubungan. Biasanya, suatu kelas kompleksitas dapat dituliskan dalam bentuk:
> suatu himpunan permasalahan yang dapat diselesaikan menggunakan mesin abstrak M dengan O(f(*n*)) dari sumber R, di mana *n* adalah ukuran masukan.

Untuk lebih sederhananya, permasalahan dapat dikatakan termasuk dalam kelas kompleksitas yang sama jika memiliki kesamaan pada faktor-faktor berikut ini.
- Tipe permasalahan komputasi, misalnya permasalahan keputusan (*decision problems*), permasalahan fungsi (*function problems*), permasalahan penghitungan (*counting problems*), permasalahan optimasi (*optimization problems*), dll.
- Model komputasi, misalnya mesin Turing (deterministik/non-deterministik), sirkuit Boolean, sirkuit monoton, dll.
- Sumber yang dibatasi dan pembatasnya, biasanya kedua hal ini dinyatakan bersama, misalnya waktu polinom, ruang logaritmik, kedalaman konstan, dll.

Berikut ini adalah beberapa contoh kelas kompleksitas.
Kelas Kompleksitas | Model Komputasi | Batasan Sumber
:---:|:---:|:---:
DTIME(*f(n)*)|Mesin Turing deterministik|Waktu *f(n)*
P|Mesin Turing deterministik|Waktu poli*(n)*
EXPTIME|Mesin Turing deterministik|Waktu 2<sup>poly*(n)*</sup>