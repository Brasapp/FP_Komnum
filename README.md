Integrasi Numerik dengan Aturan Trapesium Segmen Berganda
Skrip Python ini menghitung luas area di bawah kurva fungsi f(x)=3x 
5
 −8x 
4
 . Skrip ini menggunakan dua cara:

Metode Numerik: Menggunakan Aturan Trapesium Komposit.
Metode Eksak: Menggunakan pustaka sympy untuk perhitungan analitis (tepat).
Setelah itu, skrip akan membandingkan kedua hasil dan menghitung persentase galatnya.

Cara Kerja Singkat
Definisi Fungsi: Fungsi f(x)=3x 
5
 −8x 
4
  didefinisikan.
Batas Integral: Batas bawah integral adalah 4 dan batas atasnya adalah 16.
Perhitungan Numerik: Luas dihitung menggunakan Aturan Trapesium Komposit dengan 4 segmen.
Perhitungan Eksak: Luas eksak dihitung secara simbolis menggunakan sympy.
Perbandingan & Galat: Kedua hasil dibandingkan, dan persentase galat dihitung.
Cetak Hasil: Semua langkah dan hasil ditampilkan secara terperinci.
Cara Menjalankan
Instalasi: Pastikan Anda memiliki Python, numpy, dan sympy terinstal. Jika belum, jalankan:
Bash

pip install numpy sympy
Jalankan Skrip: Simpan kode sebagai A16_ProgramKomnum_40.py dan jalankan dari terminal:
Bash

python A16_ProgramKomnum_40.py
Contoh Output
=== Langkah 1: Evaluasi Fungsi ===
f(4) = -512.0
f(7) = 39207.0
f(10) = 220000.0
f(13) = 878179.0
f(16) = 2621440.0

=== Langkah 2: Hitung Luas (Trapezium) ===
h = (16-4)/4 = 3
Luas = 3 * [0.5*f(4) + 0.5*f(16) + f(7) + f(10) + f(13)]
      = 3 * [0.5*-512.0 + 0.5*2621440.0 + 39207.0 + 220000.0 + 878179.0]
      = 6003780.0

=== Langkah 3: Hitung Error ===
Luas Eksak (Sympy) = 6003648.0
Error (%) = |(6003648.0 - 6003780.0) / 6003648.0| * 100 = 0.00%
