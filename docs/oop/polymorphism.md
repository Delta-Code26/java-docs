---
title: Polymorphism (Polimorfisme) dalam Java
description: Memahami konsep polimorfisme dalam OOP untuk mendukung fleksibilitas kode melalui method overloading dan overriding di Java
---

# 🌀 Polymorphism (Polimorfisme) dalam Java

**Polymorphism** (polimorfisme) berasal dari kata Yunani *poly* (banyak) dan *morph* (bentuk), yang berarti kemampuan sebuah method atau objek untuk memiliki **banyak bentuk perilaku**. Dalam Java, polimorfisme memungkinkan method yang sama untuk berperilaku berbeda tergantung pada objek yang memanggilnya. Ini meningkatkan fleksibilitas dan reusabilitas kode, mendukung prinsip **Open/Closed** dalam desain OOP (kode terbuka untuk ekstensi, tertutup untuk modifikasi).

Polimorfisme di Java terdiri dari dua jenis utama:
1. **Compile-time Polymorphism** (Static): Dicapai melalui *method overloading*.
2. **Runtime Polymorphism** (Dynamic): Dicapai melalui *method overriding*.

## 🔧 Jenis-Jenis Polimorfisme

### 1. Compile-Time Polymorphism (Method Overloading)
**Method overloading** terjadi ketika sebuah kelas memiliki beberapa method dengan **nama yang sama** tetapi **parameter yang berbeda** (dalam jumlah, tipe, atau urutan). Kompiler menentukan method mana yang dipanggil berdasarkan parameter saat kode dikompilasi.

#### Contoh Overloading:

```java
public class Kalkulator {
    public int tambah(int a, int b) {
        return a + b;
    }

    public double tambah(double a, double b) {
        return a + b;
    }

    public int tambah(int a, int b, int c) {
        return a + b + c;
    }
}
```

#### Penggunaan:

```java
public class KalkulatorDemo {
    public static void main(String[] args) {
        Kalkulator k = new Kalkulator();
        System.out.println("2 + 3 = " + k.tambah(2, 3));
        System.out.println("2.5 + 3.5 = " + k.tambah(2.5, 3.5));
        System.out.println("1 + 2 + 3 = " + k.tambah(1, 2, 3));
    }
}
```

**🖨️ Output:**

```text
2 + 3 = 5
2.5 + 3.5 = 6.0
1 + 2 + 3 = 6
```

> 📌 **Catatan**: Overloading terjadi saat **compile-time**, karena kompiler memilih method berdasarkan tanda tangan (*signature*) method.

### 2. Runtime Polymorphism (Method Overriding)
**Method overriding** terjadi ketika subclass menyediakan implementasi baru untuk method yang diwarisi dari superclass. Method yang di-*override* harus memiliki nama, parameter, dan tipe kembalian yang sama, ditandai dengan anotasi `@Override` untuk kejelasan.

#### Contoh Overriding:

```java
public class Hewan {
    public void suara() {
        System.out.println("Hewan bersuara...");
    }
}

class Kucing extends Hewan {
    @Override
    public void suara() {
        System.out.println("Meong");
    }
}

class Anjing extends Hewan {
    @Override
    public void suara() {
        System.out.println("Guk Guk");
    }
}
```

#### Penggunaan:

```java
public class HewanDemo {
    public static void main(String[] args) {
        Hewan h1 = new Kucing(); // Polymorphism
        Hewan h2 = new Anjing(); // Polymorphism

        h1.suara();
        h2.suara();
    }
}
```

**🖨️ Output:**

```text
Meong
Guk Guk
```

> 💡 **Info**: Method yang dipanggil ditentukan saat **runtime** berdasarkan tipe objek aktual, bukan tipe referensi (Hewan).

## 🎯 Polymorphism dengan Referensi Superclass

Polimorfisme sering digunakan dengan referensi superclass untuk merujuk ke objek subclass, memungkinkan fleksibilitas dalam menangani berbagai tipe objek secara seragam.

### Contoh:

```java
public class PolymorphismDemo {
    public static void main(String[] args) {
        Hewan[] hewan = { new Kucing(), new Anjing() };
        for (Hewan h : hewan) {
            h.suara(); // Memanggil method sesuai tipe objek
        }
    }
}
```

**🖨️ Output:**

```text
Meong
Guk Guk
```

> 📌 **Catatan**: Polimorfisme runtime memungkinkan kode untuk bekerja dengan tipe yang berbeda tanpa perlu tahu tipe spesifiknya.

## ⚠️ Mengapa Polimorfisme Penting?

Polimorfisme adalah kunci untuk membangun kode yang fleksibel dan mudah diperluas:

| **Manfaat**            | **Penjelasan**                                              |
|------------------------|------------------------------------------------------------|
| **Modularitas**        | Kode dapat menangani berbagai tipe objek dengan antarmuka yang sama. |
| **Skalabilitas**       | Mudah menambahkan subclass baru tanpa mengubah kode utama.  |
| **Prinsip Open/Closed**| Kelas dapat diperluas tanpa memodifikasi kode yang ada.     |
| **Reusabilitas**       | Satu antarmuka dapat digunakan untuk banyak implementasi.   |

## 🧪 Studi Kasus: Sistem Kendaraan

Berikut adalah contoh polimorfisme yang memodelkan kendaraan dengan perilaku berbeda untuk setiap jenis.

```java
public class Kendaraan {
    public void jalan() {
        System.out.println("Kendaraan bergerak...");
    }
}

class Mobil extends Kendaraan {
    @Override
    public void jalan() {
        System.out.println("Mobil melaju di jalan raya");
    }
}

class Motor extends Kendaraan {
    @Override
    public void jalan() {
        System.out.println("Motor menyusuri gang kecil");
    }
}
```

### Penggunaan:

```java
public class KendaraanDemo {
    public static void main(String[] args) {
        Kendaraan[] kendaraan = { new Mobil(), new Motor() };
        for (Kendaraan k : kendaraan) {
            k.jalan(); // Memanggil method sesuai tipe objek
        }
    }
}
```

**🖨️ Output:**

```text
Mobil melaju di jalan raya
Motor menyusuri gang kecil
```

## 📌 Kesimpulan

Polimorfisme memungkinkan fleksibilitas dalam desain kode:

| **Jenis Polimorfisme** | **Teknik**               | **Waktu Terjadi**      |
|------------------------|--------------------------|------------------------|
| **Compile-time**       | Method Overloading       | Saat kompilasi         |
| **Runtime**            | Method Overriding        | Saat program berjalan  |
| **Tujuan Umum**        | Fleksibilitas dan reusabilitas kode |                    |

> 🎯 **Tujuan Utama**: Polimorfisme memungkinkan satu antarmuka untuk mendukung banyak implementasi, membuat kode lebih modular dan mudah diperluas.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Abstraction (Abstraksi)](abstraction.md) untuk memahami cara menyembunyikan kompleksitas implementasi.

⬅️ Kembali: [Inheritance (Pewarisan)](inheritance.md)
