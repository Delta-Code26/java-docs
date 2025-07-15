---
title: Konsep Dasar OOP dalam Java
description: Memahami prinsip dasar Object-Oriented Programming (OOP) di Java, termasuk class, object, dan empat pilar OOP
---

# 🧭 Konsep Dasar OOP (Object-Oriented Programming) dalam Java

Java adalah bahasa pemrograman **berorientasi objek** (Object-Oriented Programming, OOP), yang berfokus pada pembuatan **kelas (class)** dan **objek (object)** untuk membangun kode yang **modular**, **fleksibel**, dan **mudah dipelihara**. OOP memungkinkan pengembang untuk memodelkan entitas dunia nyata dalam kode, seperti mobil, mahasiswa, atau hewan. Bagian ini menjelaskan konsep dasar OOP, termasuk class, object, dan empat pilar utama: Encapsulation, Inheritance, Polymorphism, dan Abstraction.

## 🧠 1. Apa Itu Class dan Object?

### Class
**Class** adalah cetak biru (*blueprint*) atau template yang mendefinisikan struktur (data) dan perilaku (aksi) dari sebuah entitas. Class berisi **field** (atribut) dan **method** (fungsi).

```java
public class Mobil {
    // Field
    String merk;
    int tahun;
}
```

### Object
**Object** adalah instance nyata dari class, dibuat menggunakan kata kunci `new`. Object mewakili wujud konkret dari class.

```java
public class MobilDemo {
    public static void main(String[] args) {
        // Membuat object dari class Mobil
        Mobil m1 = new Mobil();
        m1.merk = "Toyota";
        m1.tahun = 2020;
        System.out.println("Mobil: " + m1.merk + ", Tahun: " + m1.tahun);
    }
}
```

**🖨️ Output:**

```text
Mobil: Toyota, Tahun: 2020
```

> 📌 **Catatan**: Class seperti desain rumah, sedangkan object adalah rumah yang dibangun berdasarkan desain tersebut.

## 🎯 2. Empat Pilar OOP

OOP di Java dibangun di atas empat pilar utama yang memungkinkan pembuatan kode yang terstruktur dan efisien.

### a) Encapsulation (Enkapsulasi)
**Encapsulation** menyembunyikan detail implementasi data dan hanya memberikan akses terkontrol melalui **getter** dan **setter**. Ini meningkatkan keamanan dan fleksibilitas kode.

```java
public class Mahasiswa {
    // Field private untuk encapsulation
    private String nama;

    // Getter
    public String getNama() {
        return nama;
    }

    // Setter
    public void setNama(String nama) {
        this.nama = nama;
    }
}
```

### Penggunaan:

```java
public class EncapsulationDemo {
    public static void main(String[] args) {
        Mahasiswa mhs = new Mahasiswa();
        mhs.setNama("Marno");
        System.out.println("Nama: " + mhs.getNama());
    }
}
```

**🖨️ Output:**

```text
Nama: Marno
```

> 💡 **Tips**: Gunakan modifier `private` untuk field dan sediakan method `public` (getter/setter) untuk mengontrol akses.

### b) Inheritance (Pewarisan)
**Inheritance** memungkinkan kelas anak mewarisi field dan method dari kelas induk, mempromosikan *reuse* kode.

```java
public class Hewan {
    public void makan() {
        System.out.println("Hewan sedang makan");
    }
}

class Kucing extends Hewan {
    public void suara() {
        System.out.println("Meong");
    }
}
```

### Penggunaan:

```java
public class InheritanceDemo {
    public static void main(String[] args) {
        Kucing kucing = new Kucing();
        kucing.makan(); // Diwarisi dari Hewan
        kucing.suara(); // Method khusus Kucing
    }
}
```

**🖨️ Output:**

```text
Hewan sedang makan
Meong
```

> 📌 **Catatan**: Gunakan kata kunci `extends` untuk mewarisi kelas induk.

### c) Polymorphism (Polimorfisme)
**Polymorphism** memungkinkan satu method memiliki banyak perilaku tergantung pada objek yang memanggilnya, biasanya melalui **method overriding**.

```java
public class Bentuk {
    public void gambar() {
        System.out.println("Menggambar bentuk");
    }
}

class Lingkaran extends Bentuk {
    @Override
    public void gambar() {
        System.out.println("Menggambar lingkaran");
    }
}
```

### Penggunaan:

```java
public class PolymorphismDemo {
    public static void main(String[] args) {
        Bentuk bentuk = new Lingkaran(); // Polymorphism
        bentuk.gambar();
    }
}
```

**🖨️ Output:**

```text
Menggambar lingkaran
```

> 💡 **Info**: Polymorphism memungkinkan fleksibilitas dengan menggunakan tipe induk untuk merujuk ke objek anak.

### d) Abstraction (Abstraksi)
**Abstraction** menyembunyikan kompleksitas implementasi dan hanya menampilkan fungsi esensial melalui kelas abstrak atau interface.

```java
public abstract class Kendaraan {
    public abstract void jalan();
}
```

```java
public class Mobil extends Kendaraan {
    @Override
    public void jalan() {
        System.out.println("Mobil berjalan di jalan raya");
    }
}
```

### Penggunaan:

```java
public class AbstractionDemo {
    public static void main(String[] args) {
        Kendaraan kendaraan = new Mobil();
        kendaraan.jalan();
    }
}
```

**🖨️ Output:**

```text
Mobil berjalan di jalan raya
```

> 📌 **Catatan**: Gunakan kata kunci `abstract` untuk kelas atau method yang tidak memiliki implementasi langsung.

## 🧪 Studi Kasus: Class dan Object

Berikut adalah contoh sederhana yang menggabungkan konsep class dan object.

```java
public class Mahasiswa {
    // Field
    String nama;
    int umur;

    // Method
    public void sapa() {
        System.out.println("Halo, nama saya " + nama + ", umur " + umur);
    }
}

class MahasiswaDemo {
    public static void main(String[] args) {
        // Membuat object
        Mahasiswa m1 = new Mahasiswa();
        m1.nama = "Marno";
        m1.umur = 22;
        m1.sapa();
    }
}
```

**🖨️ Output:**

```text
Halo, nama saya Marno, umur 22
```

## 📌 Kesimpulan

Empat pilar OOP membentuk dasar untuk membangun aplikasi Java yang terstruktur:

| **Konsep**         | **Penjelasan Sederhana**                          |
|--------------------|--------------------------------------------------|
| **Class**          | Cetak biru untuk mendefinisikan struktur dan perilaku. |
| **Object**         | Instance nyata dari class.                       |
| **Encapsulation**  | Melindungi data dengan akses terkontrol.         |
| **Inheritance**    | Mewarisi fitur dari kelas induk untuk reuse kode.|
| **Polymorphism**   | Satu nama method dengan banyak perilaku.         |
| **Abstraction**    | Menyembunyikan kompleksitas, menampilkan esensi. |

Memahami konsep-konsep ini adalah langkah awal untuk menguasai OOP di Java.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Encapsulation (Enkapsulasi)](encapsulation.md) untuk memahami cara melindungi data dalam class dengan lebih mendalam.

⬅️ Kembali: [Membuat Class dan Object](class_objek.md)