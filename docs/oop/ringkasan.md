---
title: Ringkasan OOP dan Studi Kasus
description: Merangkum pilar-pilar OOP dan menerapkannya dalam studi kasus sistem rekap panen sawit
---

# 🧾 Ringkasan OOP dan Studi Kasus

Setelah mempelajari pilar-pilar **Object-Oriented Programming (OOP)**, bagian ini merangkum konsep-konsep inti dan menunjukkan penerapannya dalam studi kasus praktis. Studi kasus ini mengilustrasikan bagaimana **Encapsulation**, **Inheritance**, **Polymorphism**, dan **Abstraction** bekerja bersama untuk membangun sistem yang terorganisir dan fleksibel.

## 🧱 Ringkasan Empat Pilar OOP

OOP di Java dibangun di atas empat pilar utama:

| **Pilar**          | **Konsep Inti**                                                                 |
|--------------------|--------------------------------------------------------------------------------|
| **Encapsulation**  | Menyembunyikan data dengan akses terkontrol melalui getter dan setter.          |
| **Inheritance**    | Mewarisi atribut dan method dari kelas induk ke kelas anak untuk reuse kode.   |
| **Polymorphism**   | Memungkinkan satu interface memiliki banyak implementasi melalui overriding.    |
| **Abstraction**    | Menyembunyikan kompleksitas implementasi, hanya menampilkan fungsi esensial.   |

> 💡 **Info**: Pilar-pilar ini memungkinkan pembuatan kode yang modular, mudah dipelihara, dan dapat diskalakan.

## 📘 Studi Kasus: Sistem Rekap Panen Sawit

Mari kita bangun sistem sederhana untuk mencatat hasil panen kelapa sawit. Dalam sistem ini, terdapat tiga jenis pekerja: **Pemotong**, **Penyusun**, dan **Pengutip**, masing-masing dengan peran dan kontribusi berbeda terhadap total berat panen. Gaji mereka dihitung berdasarkan persentase dari total berat panen.

### 1. Membuat Abstract Class: `Pekerja`

Kelas abstrak `Pekerja` mendefinisikan struktur umum untuk semua jenis pekerja, dengan method abstrak untuk menghitung gaji.

```java
abstract class Pekerja {
    protected String nama;

    public Pekerja(String nama) {
        this.nama = nama;
    }

    // Method abstrak untuk diimplementasikan oleh subclass
    abstract double hitungGaji(double totalBerat);

    public String getNama() {
        return nama;
    }
}
```

> 📌 **Catatan**: Atribut `nama` dideklarasikan sebagai `protected` untuk mendukung **encapsulation** dengan akses terbatas ke subclass.

### 2. Membuat Kelas Tur,anan

Kelas turunan mengimplementasikan method `hitungGaji` sesuai peran masing-masing pekerja.

#### a) Pemotong

```java
class Pemotong extends Pekerja {
    public Pemotong(String nama) {
        super(nama);
    }

    @Override
    double hitungGaji(double totalBerat) {
        return totalBerat * 0.4; // 40% dari total berat
    }
}
```

#### b) Penyusun

```java
class Penyusun extends Pekerja {
    public Penyusun(String nama) {
        super(nama);
    }

    @Override
    double hitungGaji(double totalBerat) {
        return totalBerat * 0.35; // 35% dari total berat
    }
}
```

#### c) Pengutip

```java
class Pengutip extends Pekerja {
    public Pengutip(String nama) {
        super(nama);
    }

    @Override
    double hitungGaji(double totalBerat) {
        return totalBerat * 0.25; // 25% dari total berat
    }
}
```

### 3. Implementasi Program Utama

Program utama menunjukkan bagaimana pilar-pilar OOP diterapkan melalui **polymorphism** dan **inheritance**.

```java
public class DemoPanen {
    public static void main(String[] args) {
        double beratPanen = 1000; // Total berat panen dalam kg

        // Membuat objek pekerja dengan polymorphism
        Pekerja p1 = new Pemotong("Ali");
        Pekerja p2 = new Penyusun("Budi");
        Pekerja p3 = new Pengutip("Cici");

        // Menghitung dan menampilkan gaji
        System.out.printf("%s: RM %.2f%n", p1.getNama(), p1.hitungGaji(beratPanen));
        System.out.printf("%s: RM %.2f%n", p2.getNama(), p2.hitungGaji(beratPanen));
        System.out.printf("%s: RM %.2f%n", p3.getNama(), p3.hitungGaji(beratPanen));
    }
}
```

**🖨️ Output:**

```text
Ali: RM 400.00
Budi: RM 350.00
Cici: RM 250.00
```

### Analisis Penerapan OOP

| **Pilar OOP**      | **Realisasi dalam Studi Kasus**                                   |
|--------------------|------------------------------------------------------------------|
| **Encapsulation**  | Atribut `nama` bersifat `protected`, diakses via getter.         |
| **Inheritance**    | Kelas `Pemotong`, `Penyusun`, dan `Pengutip` mewarisi `Pekerja`. |
| **Polymorphism**   | Method `hitungGaji` dipanggil secara polimorfik pada tipe `Pekerja`. |
| **Abstraction**    | Kelas abstrak `Pekerja` menyediakan kontrak untuk `hitungGaji`.  |

## 🎓 Kesimpulan Akhir

Empat pilar OOP—**Encapsulation**, **Inheritance**, **Polymorphism**, dan **Abstraction**—memungkinkan pembuatan kode yang:
- **Modular**: Mudah dikelola dan diperluas.
- **Reusable**: Kode dapat digunakan kembali melalui pewarisan dan polimorfisme.
- **Scalable**: Dapat diintegrasikan dengan sistem yang lebih besar, seperti database atau API.

Studi kasus sistem rekap panen sawit menunjukkan bagaimana pilar-pilar ini bekerja bersama untuk membangun aplikasi yang terstruktur dan efisien.

## 📎 Catatan Tambahan

- Dalam proyek nyata, OOP sering dipadukan dengan teknologi seperti **database** (misalnya, JDBC atau JPA), **API** (RESTful services), atau **framework** (Spring, Hibernate).
- Gunakan OOP untuk memodelkan entitas bisnis seperti `User`, `Gaji`, `Panen`, atau `Tim` untuk menjaga kode tetap terorganisir.
- Pertimbangkan prinsip **SOLID** (Single Responsibility, Open-Closed, dll.) untuk desain OOP yang lebih baik di proyek besar.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Java Collection Framework (JCF)](../advanced/collections.md) untuk memahami cara mengelola kumpulan data secara efisien dalam program Java.

⬅️ Kembali: [Abstraksi dalam Java](abstraction.md)