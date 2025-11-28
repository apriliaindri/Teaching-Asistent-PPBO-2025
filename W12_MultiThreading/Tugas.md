# Tugas 11 dan 12

## Ketentuan Tugas

Pada tugas ini kalian diminta membuat satu program terpadu yang menggabungkan tiga materi utama yaitu abstract class, interface, dan multithreading. Program yang dibuat harus membangun sistem penilaian mahasiswa menggunakan konsep OOP, kemudian melakukan proses perhitungan nilai mahasiswa dalam dua mode: **mode single-thread dan mode multithreading**. Mahasiswa wajib menampilkan hasil perhitungan pada kedua mode serta membandingkan waktu eksekusi keduanya.

Program ditulis menggunakan Java dan memanfaatkan konsep OOP. Mahasiswa harus membuat: 
- Minimal lima mata kuliah dan lima mahasiswa
- Setiap mahasiswa mengambil minimal tiga mata kuliah, hasil output harus jelas dan menampilkan perbandingan kedua metode perhitungan serta kesimpulan akhir. Penjelasan lebih lanjut simak di bawah ini:

note: program bebas dikreasikan selama masih memenuhi ketentuan (contoh hanya sebagai panduan)

---

## Spesifikasi Program

### 1. Abstract Class dan Interface

Buat sebuah abstract class bernama `MataKuliah` yang berisi atribut dasar seperti nama mata kuliah, jumlah sks, dan nilai. Abstract class ini harus memiliki minimal satu abstract method yaitu `double hitungNilaiAkhir()`. Method tambahan yang bersifat concrete diperbolehkan.

Buat sebuah interface bernama `Penilaian` yang memiliki minimal dua method yaitu `double getBobotNilai()` dan `String getGrade()`.

Buat minimal lima kelas mata kuliah, masing-masing mewarisi `MataKuliah` dan mengimplementasikan `Penilaian`. Setiap kelas mata kuliah bebas menentukan rumus bobot nilai maupun aturan penilaiannya sendiri.

### 2. Data Mahasiswa

Buat minimal lima mahasiswa. Setiap mahasiswa memiliki nama dan daftar mata kuliah yang diambil (minimal tiga mata kuliah). Mahasiswa harus memiliki method untuk menghitung total SKS dan nilai akhirnya. Nilai akhir dihitung berdasarkan rumus
Σ(nilai × sks) dibagi total SKS.

## Contoh
```
Mahasiswa A :
Nilai Kuliah A = 80, SKS = 3
Nilai Kuliah B = 90, SKS = 2
-> ((80*3) + (90*2))5 = 420/5 = 84 (Nilai Final)

Output :
Nama: Mahasiswa A
Mata Kuliah: PBO, Pendidikan Pancasila
Total SKS: 5
Nilai: 84
```

### 3. Mode Perhitungan Single-thread

Program harus menyediakan perhitungan nilai mahasiswa secara biasa (tanpa thread tambahan). Perhitungan dilakukan satu per satu secara berurutan. Output harus mencakup nama mahasiswa, total SKS, nilai akhir, dan grade. Waktu eksekusi harus diukur menggunakan `System.currentTimeMillis()` atau `System.nanoTime()`.

Contoh format waktu:
`Waktu Eksekusi Single-thread: 10 ms`

### 4. Mode Perhitungan Multithreading

Program harus menyediakan versi perhitungan menggunakan multithreading. Buat sebuah class `HitungNilaiThread` yang mengimplementasikan `Runnable` dan menerima objek `Mahasiswa`. Class ini bertugas menghitung nilai akhir mahasiswa dan menampilkan hasilnya.

Setiap mahasiswa diproses oleh satu thread terpisah. Thread dijalankan menggunakan `start()` dan proses utama harus menunggu semua thread selesai menggunakan `join()`. Program harus mengukur waktu eksekusi total pada mode multithreading.

Contoh format waktu:
`Waktu Eksekusi Multithreading: 4 ms`

### 5. Output Wajib

Program harus menampilkan hasil perhitungan pada mode single-thread, hasil perhitungan pada mode multithread, dan perbandingan waktu eksekusi kedua metode.

Format output yang harus ada:

* Hasil lengkap per mahasiswa pada mode single-thread. Contoh:
```
[Single Thread]  
Nama: Mahasiswa A 
Mata Kuliah: ... 
Total SKS: ...  
Nilai Akhir: ...
Waktu Eksekusi: ... ms
```

* Hasil lengkap per mahasiswa pada mode multithread. Contoh:
```
[Thread-1] Mahasiswa A → Total SKS: ..., Nilai Akhir: ...
[Thread-2] Mahasiswa B → Total SKS: ..., Nilai Akhir: ...
...
Waktu Eksekusi Multithread: ... ms
```

* Perbandingan waktu Eksekusi dan Kesimpulannya

Dengan isi file sebagai berikut:
```java
// Nama : ...
// NIM  : ...

public class PPBO_11_12_NIM_NamaLengkap {
    public static void main(String[] args) {
        // ...
    }
}
```

## Pengumpulan:

Tugas dikumpulkan dalam 2 format untuk laporan dalam bentuk Portable Document File (\*.pdf) dengan ketentuan nama berkas **PPBO_11_12_NIM_NamaLengkap.pdf** dan untuk source kode dengan **PPBO_11_12_NIM_NamaLengkap.java.** atau  **PPBO_11_12_NIM_NamaLengkap.zip.** (apabila lebih dari 1 file).

## Tenggat Waktu Pengerjaan

Tenggat waktu pengerjaan Kelas C Informatika Tugas ini adalah hari **Jumat, 5 Desember 2025, pukul 23.59.**
