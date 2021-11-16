# Mobile Programming

Pertemuan ke-6 </br>
Latihan ke 1 </br>
NIM : 12201770 </br>
Nama : Harun Noviar </br>
Prodi : Informatika - B

## Project 1 startup_namer

Project ke-1 adalah contoh penggunaan framework flutter untuk membuat aplikasi mobile. </br>
Beberapa hal keterangan dari kode baris program diatas antara lain:

- Contoh baris program ini menggunakan material design yang merupakan standar bahasa desain visual pada aplikasi mobile ataupun berbasis web. Dan di dalam framework flutter sendiri sangat banyak widget-widget Material yang sudah disiapkan. Penggunaannya dengan menuliskan diawal program meng-import 'package:flutter/material.dart';
- Baris kode utama program dimulai dengan method main yang menggunakan notasi anak panah (=>) memanggil "MyApp". Notasi anak panah digunakan untuk satu baris pemanggilan fungsi ataupun method.
- Method "MyApp" merupakan extends class dari StatelessWidget, dimana dengan ini menjadikan aplikasi tersebut berupa widget. Dalam flutter hampir semuanya adalah widget termasuk alignment, padding, dan layout.
- StatelessWidget adalah widget yang menggambarkan bagian dari antarmuka pengguna dengan membangun susunan dengan widget lain yang menggambarkan antarmuka pengguna secara lebih konkret.
- Scaffold widget dari librari Material menyediakan sebuah properti bar aplikasi bawaan, judul, dan isi yang menangani widget tree untuk layar beranda. Widget subtree akan lebih rumit lagi.
- tugas utama widget adalah menyediakan method "build" yang menjelaskan cara menampilkan widget dalam hubungannya dengan widget lainnya yaitu widget tingkat rendah.
- Isi dari baris kode program diatas terdiri dari widget "Center" yang berisi anak widget "Text". Widget "Center" mengatur semua subtree widget ke posisi tengah layar.

## Sumber

https://codelabs.developers.google.com/codelabs/first-flutter-app-pt1#2
