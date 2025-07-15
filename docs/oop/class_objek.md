---
title: Membuat Class dan Object dalam Java
description: Memahami konsep dasar class, object, dan constructor dalam Object-Oriented Programming di Java
---

# 🏗️ Membuat Class dan Object dalam Java

Dalam **Object-Oriented Programming (OOP)** di Java, **class** dan **object** adalah konsep dasar yang menjadi fondasi pembuatan program berbasis objek. **Class** adalah cetak biru (*blueprint*) yang mendefinisikan struktur dan perilaku, sedangkan **object** adalah instance nyata dari class tersebut. Bagian ini menjelaskan cara membuat class, object, dan constructor, serta peran field dan method dalam OOP.

## 1. ✏️ Membuat Class

**Class** adalah template yang mendefinisikan:
- **Field (atribut)**: Data atau properti yang dimiliki class.
- **Method**: Fungsi atau aksi yang dapat dilakukan oleh class.

### Contoh Class:

```java
public class Mahasiswa {
    // Field
    String nama;
    int umur;

    // Method
    void sapa() {
        System.out.println("Halo, saya " + nama);
    }
}
```

- **Field**: `nama` (String) dan `umur` (int) menyimpan data mahasiswa.
- **Method**: `sapa()` mendefinisikan perilaku untuk mencetak sapaan.

## 2. 🧪 Membuat dan Menggunakan Object

**Object** adalah instance dari class yang dibuat menggunakan kata kunci `new`. Object memungkinkan kita untuk menggunakan field dan method yang didefinisikan dalam class.

### Contoh Membuat Object:

```java
public class MahasiswaDemo {
    public static void main(String[] args) {
        // Membuat object dari class Mahasiswa
        Mahasiswa mhs1 = new Mahasiswa();
        
        // Mengisi field
        mhs1.nama = "Marno";
        mhs1.umur = 21;

        // Memanggil method
        mhs1.sapa();
    }
}
```

**🖨️ Output:**

```text
Halo, saya Marno
```

> 📌 **Catatan**: Object dibuat dengan `new` diikuti oleh nama class dan tanda kurung, misalnya `new Mahasiswa()`.

## 3. ⚙️ Constructor: Inisialisasi Object

**Constructor** adalah method khusus yang dipanggil secara otomatis saat object dibuat. Constructor memiliki nama yang sama dengan class dan tidak memiliki tipe kembalian. Constructor biasanya digunakan untuk menginisialisasi field.

### Contoh Class dengan Constructor:

```java
public class Mahasiswa {
    String nama;
    int umur;

    // Constructor
    public Mahasiswa(String nama, int umur) {
        this.nama = nama;
        this.umur = umur;
    }

    // Method
    void sapa() {
        System.out.println("Saya " + nama + ", umur " + umur);
    }
}
```

### Contoh Pemanggilan:

```java
public class MahasiswaConstructorDemo {
    public static void main(String[] args) {
        // Membuat object dengan constructor
        Mahasiswa mhs1 = new Mahasiswa("Marno", 21);
        mhs1.sapa();
    }
}
```

**🖨️ Output:**

```text
Saya Marno, umur 21
```

> 💡 **Tips**: Gunakan kata kunci `this` untuk membedakan field class dari parameter constructor dengan nama yang sama.

## 4. 🧱 Perbedaan Field, Method, dan Constructor

| **Elemen**     | **Fungsi**                                           |
|----------------|-----------------------------------------------------|
| **Field**      | Menyimpan data atau properti class.                 |
| **Method**     | Mendefinisikan perilaku atau aksi class.            |
| **Constructor**| Menginisialisasi object saat dibuat dengan `new`.   |

## 5. 🧠 Studi Kasus: Class `Mobil`

Berikut adalah contoh lengkap yang menggabungkan class, object, dan constructor untuk memodelkan mobil.

```java
public class Mobil {
    // Field
    String merk;
    int tahun;

    // Constructor
    public Mobil(String merk, int tahun) {
        this.merk = merk;
        this.tahun = tahun;
    }

    // Method
    void info() {
        System.out.printf("Merk: %s, Tahun: %d%n", merk, tahun);
    }
}

class DemoMobil {
    public static void main(String[] args) {
        // Membuat object
        Mobil m1 = new Mobil("Toyota", 2020);
        Mobil m2 = new Mobil("Honda", 2022);

        // Memanggil method
        m1.info();
        m2.info();
    }
}
```

**🖨️ Output:**

```text
Merk: Toyota, Tahun: 2020
Merk: Honda, Tahun: 2022
```

## 📌 Kesimpulan

Class dan object adalah fondasi OOP di Java:

| **Konsep**         | **Penjelasan**                                    |
|--------------------|--------------------------------------------------|
| **Class**          | Blueprint yang mendefinisikan field dan method.  |
| **Object**         | Instance nyata dari class, dibuat dengan `new`.  |
| **Constructor**    | Method khusus untuk menginisialisasi object.     |
| **Field & Method** | Menyimpan data dan mendefinisikan perilaku.      |

Memahami cara membuat class dan object adalah langkah awal untuk menguasai OOP dan membangun aplikasi yang terstruktur.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Encapsulation (Enkapsulasi)](encapsulation.md) untuk memahami cara melindungi data dalam class.

⬅️ Kembali: [Ringkasan OOP dan Studi Kasus](ringkasan.md)