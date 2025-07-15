---
title: Method dan Parameter dalam Java
description: Memahami cara membuat dan menggunakan method, parameter, nilai kembalian, dan method overloading di Java
---

# 🔧 Method dan Parameter dalam Java

**Method** adalah blok kode yang dirancang untuk melakukan tugas tertentu dan dapat digunakan kembali dalam program. Method membantu menjaga kode tetap **terorganisir**, **mengurangi duplikasi**, dan mempermudah **pengulangan logika** tanpa menulis ulang kode. Bagian ini menjelaskan struktur method, cara memanggilnya, penggunaan parameter, nilai kembalian, dan konsep *method overloading*.

## 🧱 Struktur Dasar Method

Method didefinisikan dengan struktur berikut:

```java
tipeKembalian namaMethod(tipeParameter1 param1, tipeParameter2 param2, ...) {
    // Blok kode
    // (opsional) return nilai;
}
```

- **Tipe Kembalian**: Tipe data hasil method (misalnya, `int`, `String`, atau `void` jika tidak mengembalikan nilai).
- **Nama Method**: Nama unik untuk method, mengikuti aturan penamaan variabel (camelCase).
- **Parameter**: Data masukan (opsional) yang diterima method.
- **Blok Kode**: Logika yang dijalankan oleh method.
- **Return**: Mengembalikan nilai (jika tipe kembalian bukan `void`).

### Contoh Method Tanpa Parameter dan Nilai Kembalian:

```java
void sapa() {
    System.out.println("Halo, Dunia!");
}
```

Method `sapa()` bertipe `void` (tidak mengembalikan nilai) dan tidak menerima parameter.

## 🔁 Memanggil Method

Untuk menjalankan method, panggil namanya di dalam program. Method harus didefinisikan dalam kelas dan dapat dipanggil dari method lain, seperti `main`.

### Contoh Program:

```java
public class MethodDemo {
    static void sapa() {
        System.out.println("Halo, Dunia!");
    }

    public static void main(String[] args) {
        sapa(); // Memanggil method sapa
    }
}
```

**🖨️ Output:**

```text
Halo, Dunia!
```

> 📌 **Catatan**: Keyword `static` memungkinkan method dipanggil tanpa membuat objek kelas. Untuk method non-static, Anda perlu membuat instance kelas terlebih dahulu.

## 🎯 Method dengan Parameter

**Parameter** memungkinkan method menerima data masukan untuk diproses. Parameter didefinisikan dengan tipe data dan nama.

### Contoh Method dengan Parameter:

```java
static void sapa(String nama) {
    System.out.println("Halo, " + nama + "!");
}
```

### Contoh Pemanggilan:

```java
public class MethodParamDemo {
    static void sapa(String nama) {
        System.out.println("Halo, " + nama + "!");
    }

    public static void main(String[] args) {
        sapa("Marno"); // Memanggil dengan parameter "Marno"
        sapa("Dunia"); // Memanggil dengan parameter "Dunia"
    }
}
```

**🖨️ Output:**

```text
Halo, Marno!
Halo, Dunia!
```

## 🔁 Method dengan Nilai Kembalian

Method dapat mengembalikan nilai menggunakan kata kunci `return`. Tipe kembalian harus sesuai dengan tipe data yang dideklarasikan.

### Contoh Method dengan Nilai Kembalian:

```java
static int tambah(int a, int b) {
    return a + b;
}
```

### Contoh Program:

```java
public class MethodReturnDemo {
    static int tambah(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        int hasil = tambah(5, 3); // Menyimpan hasil kembalian
        System.out.println("Hasil = " + hasil);
    }
}
```

**🖨️ Output:**

```text
Hasil = 8
```

> 💡 **Tips**: Gunakan `return` untuk mengakhiri eksekusi method dan mengembalikan nilai. Jika tipe kembalian adalah `void`, `return` bersifat opsional dan digunakan untuk keluar dari method.

## 🔀 Method Overloading

**Method overloading** memungkinkan definisi beberapa method dengan **nama sama** tetapi **parameter berbeda** (dalam jumlah atau tipe). Java akan memilih method yang sesuai berdasarkan parameter yang diberikan saat pemanggilan.

### Contoh Method Overloading:

```java
public class MethodOverloadDemo {
    static void cetak(String teks) {
        System.out.println("Teks: " + teks);
    }

    static void cetak(int angka) {
        System.out.println("Angka: " + angka);
    }

    public static void main(String[] args) {
        cetak("Hai"); // Memanggil method dengan parameter String
        cetak(5);    // Memanggil method dengan parameter int
    }
}
```

**🖨️ Output:**

```text
Teks: Hai
Angka: 5
```

> 📌 **Catatan**: Overloading tidak bergantung pada tipe kembalian, hanya pada jumlah dan tipe parameter.

## 📚 Studi Kasus: Menghitung Luas Persegi Panjang

Berikut adalah contoh program untuk menghitung luas persegi panjang menggunakan method dengan parameter dan nilai kembalian:

```java
public class LuasPersegiPanjang {
    static int hitungLuas(int panjang, int lebar) {
        return panjang * lebar;
    }

    public static void main(String[] args) {
        int luas = hitungLuas(5, 3);
        System.out.println("Luas persegi panjang = " + luas + " cm²");
    }
}
```

**🖨️ Output:**

```text
Luas persegi panjang = 15 cm²
```

## 📌 Kesimpulan

Berikut adalah ringkasan konsep method di Java:

| **Konsep**        | **Penjelasan**                                      |
|-------------------|-----------------------------------------------------|
| **Method**        | Blok kode untuk tugas tertentu, dapat digunakan ulang|
| **Parameter**     | Data masukan yang diterima method                   |
| **Nilai Kembalian**| Nilai yang dihasilkan method menggunakan `return`   |
| **Overloading**   | Method dengan nama sama tetapi parameter berbeda    |

Method adalah fondasi penting untuk membuat kode yang modular dan efisien.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Konsep OOP: Object-Oriented Programming](../oop/k Sony/konsep.md) untuk memahami cara membangun program berbasis objek.