---
title: Package dan Import dalam Java
description: Memahami cara mengelompokkan kelas dengan package dan mengimpor kelas dari package lain di Java
---

# 📦 Package dan Import dalam Java

**Package** adalah mekanisme di Java untuk mengelompokkan kelas-kelas terkait ke dalam satu namespace, mirip seperti folder dalam sistem file. Package membantu menjaga kode tetap terorganisir, mencegah konflik nama, dan mendukung modularitas. **Import** digunakan untuk mengakses kelas atau anggota dari package lain tanpa harus menulis nama package secara penuh.

### Tujuan Package dan Import
- **Organisasi Kode**: Mengelompokkan kelas berdasarkan fungsi atau modul.
- **Enkapsulasi**: Menyembunyikan implementasi dan mengurangi konflik nama.
- **Reusabilitas**: Memudahkan penggunaan ulang kelas di proyek lain.

## 🧱 Deklarasi Package

Package dideklarasikan di **baris pertama** file Java menggunakan kata kunci `package`. Nama package biasanya menggunakan huruf kecil dan mengikuti konvensi seperti `com.nama.perusahaan.modul`.

### Contoh Deklarasi Package:

```java
package com.example.utils;

public class Kalkulator {
    public int tambah(int a, int b) {
        return a + b;
    }
}
```

> 📌 **Catatan**: Nama package harus sesuai dengan struktur direktori tempat file Java disimpan. Misalnya, kelas di atas harus berada di folder `com/example/utils`.

## 🛠️ Struktur Direktori Package

Package mencerminkan struktur direktori fisik. Contoh struktur proyek:

```
project/
├── Main.java
└── com/
    └── example/
        └── utils/
            └── Kalkulator.java
```

### Isi `com/example/utils/Kalkulator.java`:

```java
package com.example.utils;

public class Kalkulator {
    public int kali(int a, int b) {
        return a * b;
    }
}
```

### Isi `Main.java`:

```java
import com.example.utils.Kalkulator;

public class Main {
    public static void main(String[] args) {
        Kalkulator kalk = new Kalkulator();
        System.out.println("Hasil perkalian: " + kalk.kali(4, 5));
    }
}
```

**🖨️ Output:**

```text
Hasil perkalian: 20
```

## 📥 Mengimpor Kelas dengan `import`

Kata kunci `import` digunakan untuk mengakses kelas atau anggota dari package lain. Ada tiga cara umum untuk mengimpor:

1. **Impor Spesifik**:

```java
import com.example.utils.Kalkulator;
```

2. **Impor Seluruh Package**:

```java
import com.example.utils.*;
```

3. **Impor Static** (untuk anggota static):

```java
import static com.example.utils.Kalkulator.tambah;
```

> 💡 **Tips**: Hindari penggunaan `import com.example.utils.*` dalam proyek besar, karena dapat memperlambat kompilasi dan membuat kode kurang jelas.

### Contoh Impor Static:

```java
package com.example.utils;

public class Kalkulator {
    public static int tambah(int a, int b) {
        return a + b;
    }
}
```

```java
import static com.example.utils.Kalkulator.tambah;

public class StaticImportDemo {
    public static void main(String[] args) {
        System.out.println("Hasil penjumlahan: " + tambah(3, 4));
    }
}
```

**🖨️ Output:**

```text
Hasil penjumlahan: 7
```

## 📦 Package Bawaan Java

Java menyediakan beberapa package bawaan yang sering digunakan:

| **Package**     | **Deskripsi**                              |
|-----------------|--------------------------------------------|
| `java.lang`     | Kelas dasar seperti `String`, `Math`, `Object` (diimpor otomatis). |
| `java.util`     | Struktur data seperti `ArrayList`, `HashMap`. |
| `java.io`       | Operasi input/output seperti `FileReader`, `BufferedWriter`. |
| `java.net`      | Fungsionalitas jaringan seperti `Socket`.   |
| `java.time`     | Penanganan tanggal dan waktu (Java 8+).    |

## 🏗️ Membuat Package Kustom

Untuk membuat package kustom, ikuti langkah-langkah berikut:
1. Buat struktur direktori yang sesuai dengan nama package (misalnya, `com/example/utils`).
2. Deklarasikan package di baris pertama file Java.
3. Simpan file Java di direktori yang sesuai.

### Contoh Membuat Package:

Struktur direktori:
```
project/
└── com/
    └── example/
        └── utils/
            └── Kalkulator.java
```

Isi `Kalkulator.java`:

```java
package com.example.utils;

public class Kalkulator {
    public static int kurang(int a, int b) {
        return a - b;
    }
}
```

Penggunaan di `Main.java`:

```java
import com.example.utils.Kalkulator;

public class Main {
    public static void main(String[] args) {
        System.out.println("Hasil pengurangan: " + Kalkulator.kurang(10, 4));
    }
}
```

**🖨️ Output:**

```text
Hasil pengurangan: 6
```

## ⚙️ Kompilasi dan Menjalankan Program dengan Package

Untuk mengkompilasi dan menjalankan program dengan package, pastikan struktur direktori benar dan gunakan perintah `javac` dan `java` dari root proyek.

### Contoh:

```bash
# Kompilasi
javac com/example/utils/Kalkulator.java
javac Main.java

# Jalankan
java Main
```

Jika package berada di direktori lain, gunakan opsi `-cp` (classpath):

```bash
java -cp . Main
```

> 💡 **Tips**: Pastikan Anda berada di direktori root proyek saat menjalankan perintah `java`, atau tentukan classpath dengan benar.

## 📌 Best Practice Package

- **Konvensi Penamaan**: Gunakan nama package yang unik, seperti `com.nama.perusahaan.modul` (misalnya, `com.example.utils`).
- **Struktur Modular**: Kelompokkan kelas berdasarkan fungsi, seperti `model`, `utils`, atau `service`.
- **Hindari Nama Generik**: Gunakan nama spesifik untuk menghindari konflik, misalnya `com.example.database` bukan hanya `database`.
- **Gunakan Impor Spesifik**: Hindari `import *` untuk menjaga kejelasan dan performa kompilasi.

## 🧪 Studi Kasus: Aplikasi Karyawan

Berikut adalah contoh penggunaan package untuk mengelompokkan kelas dalam aplikasi karyawan.

Struktur direktori:
```
project/
├── Main.java
└── com/
    └── example/
        ├── model/
        │   └── Karyawan.java
        └── utils/
            └── GajiCalculator.java
```

### Isi `com/example/model/Karyawan.java`:

```java
package com.example.model;

public class Karyawan {
    private String nama;
    private double gaji;

    public Karyawan(String nama, double gaji) {
        this.nama = nama;
        this.gaji = gaji;
    }

    public String getNama() {
        return nama;
    }

    public double getGaji() {
        return gaji;
    }
}
```

### Isi `com/example/utils/GajiCalculator.java`:

```java
package com.example.utils;

import com.example.model.Karyawan;

public class GajiCalculator {
    public static double hitungBonus(Karyawan karyawan) {
        return karyawan.getGaji() * 0.1; // Bonus 10%
    }
}
```

### Isi `Main.java`:

```java
import com.example.model.Karyawan;
import com.example.utils.GajiCalculator;

public class Main {
    public static void main(String[] args) {
        Karyawan karyawan = new Karyawan("Ali", 5000.0);
        double bonus = GajiCalculator.hitungBonus(karyawan);
        System.out.printf("Karyawan: %s, Bonus: %.2f%n", karyawan.getNama(), bonus);
    }
}
```

**🖨️ Output:**

```text
Karyawan: Ali, Bonus: 500.00
```

## 📌 Kesimpulan

Package dan import adalah alat penting untuk mengelola kode di Java:

| **Konsep**        | **Penjelasan**                                       |
|-------------------|-----------------------------------------------------|
| **Package**       | Mengelompokkan kelas ke dalam namespace terorganisir. |
| **Import**        | Mengakses kelas atau anggota dari package lain.     |
| **Best Practice** | Gunakan nama unik dan struktur modular untuk proyek besar. |

> 🎯 **Tujuan Utama**: Package dan import meningkatkan modularitas, mencegah konflik nama, dan memudahkan pengelolaan kode dalam proyek besar.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Generics dalam Java](generics.md) untuk memahami cara membuat kode yang lebih fleksibel dan type-safe.

⬅️ Kembali: [Inner Class (Class di Dalam Class)](inner_class.md)