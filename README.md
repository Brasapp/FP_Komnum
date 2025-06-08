|	NRP 	|  	Name  	|
| :--------: | :------------: |
| 5025241055 | Pradhipta Raja Mahendra |
| 5025241072 | Arya Rangga |
| 5025241090 | Hajendra Herlambang |
| 5025241098 | Bramantya Saputra |
| 5025241099 | Rendy Tanuwijaya |

# Final Praktikum Komputrasi Numerik

### Integrasi Numerik dengan Aturan Trapesium Segmen Berganda

Skrip Python ini menghitung luas area di bawah kurva fungsi f(x)=3x^5−8x^4

Skrip ini menggunakan dua cara:

Metode Numerik: Menggunakan Aturan Trapesium Segmen Berganda.
Metode Eksak: Menggunakan library sympy untuk perhitungan analitis (tepat).

Kita ingin mencari luas di bawah kurva tersebut.

**Membagi Area Menjadi Segmen (Trapesium):**

Logika utama dari Aturan Trapesium Segmen Berganda adalah membagi area di bawah kurva menjadi beberapa "trapesium" kecil.
Dalam kode ini, kita menentukan n_segments (jumlah segmen). Misalnya, jika n_segments = 4, maka rentang integral (dari 4 sampai 16) akan dibagi menjadi 4 bagian yang sama besar.
Menentukan Lebar Setiap Segmen (h):

**Lebar setiap segmen trapesium (h)** 

dihitung dengan rumus: (batas_atas - batas_bawah) / jumlah_segmen.
Dalam kasus ini, h = (16 - 4) / 4 = 3. Ini berarti setiap trapesium memiliki lebar 3 unit pada sumbu x.
Menentukan Titik-titik (x_points) dan Nilai Fungsi (y_points):

Kita perlu tahu di mana "pilar-pilar" trapesium itu berada. Ini adalah x_points (misalnya 4, 7, 10, 13, 16 untuk 4 segmen). np.linspace digunakan untuk membuat titik-titik ini secara otomatis.
Kemudian, untuk setiap x_points tersebut, kita menghitung nilai fungsi f(x)-nya. Ini adalah tinggi "pilar" trapesium (y_points atau f(x)).
Menghitung Luas Setiap Trapesium:

**Rumus luas trapesium adalah 0.5 * (tinggi_1 + tinggi_2) * lebar.**

Dalam konteks ini, tinggi_1 dan tinggi_2 adalah nilai f(x) pada dua titik x yang berurutan (misalnya f(4) dan f(7) untuk trapesium pertama). lebar adalah h.
Menjumlahkan Luas Semua Trapesium:

Aturan Trapesium Segmen Berganda menggabungkan ini dengan rumus yang lebih efisien: Luas = h * [0.5 * f(x_pertama) + 0.5 * f(x_terakhir) + jumlah_f(x_di_tengah)].
f(x_pertama) adalah y_points[0].
f(x_terakhir) adalah y_points[-1].
jumlah_f(x_di_tengah) adalah np.sum(y_points[1:-1]) yang menjumlahkan semua y_points kecuali yang pertama dan terakhir.
Logika ini bekerja karena titik-titik di tengah (selain yang pertama dan terakhir) menjadi bagian dari dua trapesium yang berdekatan, sehingga kontribusinya dikalikan dua dalam rumus keseluruhan.

Jalankan kode: Simpan kode sebagai A16_ProgramKomnum_40.py dan jalankan dari terminal:

```Bash
python A16_ProgramKomnum_40.py
```

# Contoh Output:

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
