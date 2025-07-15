---
title: Tipe Data dan Variabel dalam Java
description: Memahami tipe data primitif, tipe data referensi, dan aturan penamaan variabel dalam Java
---

# 🧠 Tipe Data dan Variabel dalam Java

Dalam pemrograman Java, **tipe data** menentukan jenis nilai yang dapat disimpan oleh sebuah **variabel**, seperti angka, teks, atau nilai logika. Variabel berfungsi sebagai *wadah* untuk menyimpan data di memori komputer. Bagian ini menjelaskan tipe data, aturan penamaan variabel, dan cara penggunaannya dengan contoh.

## 🔤 Apa Itu Variabel?

Variabel adalah *wadah* dalam memori untuk menyimpan data. Setiap variabel memiliki tiga komponen utama:

- **Nama** (identifier): Nama unik untuk mengidentifikasi variabel.
- **Tipe data**: Jenis data yang dapat disimpan (misalnya, angka, teks, atau logika).
- **Nilai**: Data yang disimpan dalam variabel.

### Contoh Deklarasi dan Inisialisasi Variabel:

```java
int umur = 25;
String nama = "Marno";
boolean aktif = true;
```

## 📦 Jenis-Jenis Tipe Data di Java

Java memiliki dua kategori utama tipe data: **primitif** dan **referensi**.

### 1. 📊 Tipe Data Primitif

Tipe data primitif adalah tipe dasar bawaan Java yang menyimpan nilai langsung di memori. Berikut adalah 8 tipe data primitif:

| **Tipe**   | **Ukuran** | **Rentang Nilai / Contoh**         | **Keterangan**                     |
|------------|------------|------------------------------------|------------------------------------|
| `byte`     | 8 bit      | -128 hingga 127                    | Bilangan bulat kecil               |
| `short`    | 16 bit     | -32.768 hingga 32.767              | Bilangan bulat sedang              |
| `int`      | 32 bit     | -2.147.483.648 hingga 2.147.483.647| Bilangan bulat umum                |
| `long`     | 64 bit     | -2⁶³ hingga 2⁶³-1                  | Bilangan bulat sangat besar        |
| `float`    | 32 bit     | 3.14f                              | Bilangan desimal presisi rendah    |
| `double`   | 64 bit     | 3.1415926535                       | Bilangan desimal presisi tinggi    |
| `char`     | 16 bit     | 'A', '\u0041'                      | Karakter tunggal (Unicode)         |
| `boolean`  | 1 bit      | `true` atau `false`                | Nilai logika benar/salah           |

> 📌 **Catatan**:  
> - Nilai `float` harus diakhiri dengan huruf `f` (contoh: `3.14f`).  
> - Nilai `long` diakhiri dengan huruf `L` untuk membedakannya dari `int` (contoh: `123456789L`).

### 2. 🧱 Tipe Data Referensi

Tipe data referensi menyimpan alamat memori dari objek, bukan nilai langsung. Beberapa contohnya meliputi:

| **Tipe Referensi** | **Contoh**                 | **Keterangan**                     |
|--------------------|----------------------------|------------------------------------|
| `String`           | `"Halo, Java!"`            | Teks atau rangkaian karakter       |
| `Array`            | `{1, 2, 3}`                | Kumpulan elemen dengan tipe sama   |
| `Class`            | `Scanner`, `Math`          | Objek dari kelas tertentu          |

> 💡 **Info**:  
> Tipe data referensi biasanya digunakan untuk struktur data yang lebih kompleks, seperti objek atau koleksi.

## 📝 Deklarasi dan Inisialisasi Variabel

### 1. Deklarasi Tanpa Inisialisasi

Mendeklarasikan variabel tanpa memberikan nilai awal:

```java
int x;
String nama;
```

> **Catatan**: Variabel yang hanya dideklarasikan tanpa inisialisasi tidak dapat digunakan sampai diberi nilai.

### 2. Deklarasi dengan Inisialisasi

Mendeklarasikan sekaligus memberikan nilai awal:

```java
int umur = 25;
boolean aktif = true;
```

### 3. Deklarasi Banyak Variabel Sekaligus

Mendeklarasikan beberapa variabel dengan tipe yang sama dalam satu baris:

```java
int a = 1, b = 2, c = 3;
```

## 🔐 Aturan Penamaan Variabel

Agar kode tetap valid dan mudah dibaca, ikuti aturan penamaan variabel berikut:

- **Dimulai dengan huruf atau underscore (`_`)**: Tidak boleh dimulai dengan angka.
- **Tanpa spasi**: Gunakan camelCase atau underscore untuk nama yang panjang.
- **Case-sensitive**: `umur` ≠ `Umur`.
- **Hindari kata kunci Java**: Kata seperti `int`, `class`, `public`, dll., tidak boleh digunakan sebagai nama variabel.

### Contoh Nama Variabel yang Valid:

```java
String namaLengkap;
int _nilaiAkhir;
double tinggiBadan;
```

### Contoh Nama Variabel yang Tidak Valid:

```java
int 1angka;           // Error: Tidak boleh dimulai dengan angka
String nama lengkap;  // Error: Tidak boleh ada spasi
int class;            // Error: Menggunakan kata kunci Java
```

## 🧪 Contoh Program Lengkap

Berikut adalah contoh program yang menggunakan berbagai tipe data dan variabel:

```java
public class TipeDataDemo {
    public static void main(String[] args) {
        int umur = 21;
        double tinggi = 172.5;
        char inisial = 'M';
        boolean mahasiswa = true;
        String nama = "Marno";

        System.out.println("Nama: " + nama);
        System.out.println("Umur: " + umur + " tahun");
        System.out.println("Tinggi: " + tinggi + " cm");
        System.out.println("Inisial: " + inisial);
        System.out.println("Status Mahasiswa: " + mahasiswa);
    }
}
```

**🖨️ Output:**

```text
Nama: Marno
Umur: 21 tahun
Tinggi: 172.5 cm
Inisial: M
Status Mahasiswa: true
```

## 📌 Kesimpulan

- Java memiliki dua jenis tipe data: **primitif** (nilai langsung) dan **referensi** (alamat memori objek).
- Variabel digunakan untuk menyimpan data dengan tipe tertentu.
- Penamaan variabel harus mengikuti aturan sintaks Java agar kode valid dan mudah dibaca.
- Tipe data menentukan jumlah memori yang digunakan dan cara data diproses.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Operator dan Ekspresi dalam Java](operator.md) untuk memahami cara memanipulasi data dalam program.