---
title: Inheritance (Pewarisan) dalam Java
description: Memahami konsep pewarisan dalam OOP untuk mewarisi properti dan method dari kelas induk di Java
---

# 🧬 Inheritance (Pewarisan) dalam Java

**Inheritance** (pewarisan) adalah pilar utama Object-Oriented Programming (OOP) yang memungkinkan sebuah kelas (disebut **subclass** atau **child class**) untuk mewarisi properti (field) dan perilaku (method) dari kelas lain (disebut **superclass** atau **parent class**). Inheritance mempromosikan *reuse* kode, mengurangi duplikasi, dan mendefinisikan hubungan **"is-a"** (misalnya, "Mobil adalah Kendaraan").

### Tujuan Inheritance
- **Efisiensi Kode**: Menggunakan kembali kode dari superclass tanpa menulis ulang.
- **Hierarki yang Jelas**: Membangun hubungan antar kelas berdasarkan hubungan "is-a".
- **Fleksibilitas**: Memungkinkan subclass untuk menyesuaikan atau memperluas perilaku superclass.

## 🧱 Struktur Dasar Inheritance

Gunakan kata kunci `extends` untuk mendefinisikan bahwa sebuah kelas adalah turunan dari kelas lain.

### Contoh Struktur:

```java
public class Induk {
    public void salam() {
        System.out.println("Halo dari kelas induk!");
    }
}

class Anak extends Induk {
    public void perkenalan() {
        System.out.println("Saya dari kelas anak.");
    }
}
```

### Penggunaan:

```java
public class InheritanceDemo {
    public static void main(String[] args) {
        Anak anak = new Anak();
        anak.salam();       // Diwarisi dari Induk
        anak.perkenalan();  // Method milik Anak
    }
}
```

**🖨️ Output:**

```text
Halo dari kelas induk!
Saya dari kelas anak.
```

> 📌 **Catatan**: Subclass mewarisi semua member `public` dan `protected` dari superclass, tetapi tidak member `private`.

## 🏗️ Hubungan "Is-a"

Inheritance mencerminkan hubungan "is-a", di mana subclass adalah jenis spesifik dari superclass.

```java
public class Kendaraan {
    public void info() {
        System.out.println("Ini adalah kendaraan.");
    }
}

class Mobil extends Kendaraan {
    // Mobil adalah Kendaraan
}
```

### Penggunaan:

```java
public class IsADemo {
    public static void main(String[] args) {
        Mobil mobil = new Mobil();
        mobil.info(); // Diwarisi dari Kendaraan
    }
}
```

**🖨️ Output:**

```text
Ini adalah kendaraan.
```

## 🎯 Method Overriding

**Method overriding** memungkinkan subclass untuk menyediakan implementasi baru untuk method yang diwarisi dari superclass. Gunakan anotasi `@Override` untuk memastikan method benar-benar menimpa method superclass.

### Contoh Overriding:

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
```

### Penggunaan:

```java
public class OverridingDemo {
    public static void main(String[] args) {
        Hewan hewan = new Kucing(); // Polymorphism
        hewan.suara();
    }
}
```

**🖨️ Output:**

```text
Meong
```

> 💡 **Info**: Overriding memungkinkan perilaku yang berbeda untuk method yang sama, tergantung pada tipe objek yang sebenarnya.

## 🔑 Keyword Penting

| **Keyword**   | **Fungsi**                                                  |
|---------------|------------------------------------------------------------|
| `extends`     | Menunjukkan bahwa kelas adalah turunan dari kelas lain.     |
| `super`       | Mengakses constructor, field, atau method dari superclass. |
| `@Override`   | Menandakan bahwa method menimpa method dari superclass.    |

### Contoh Penggunaan `super`:

```java
public class Person {
    protected String nama;

    public Person(String nama) {
        this.nama = nama;
    }
}

class Mahasiswa extends Person {
    public Mahasiswa(String nama) {
        super(nama); // Memanggil constructor superclass
    }

    public void info() {
        System.out.println("Nama mahasiswa: " + super.nama);
    }
}
```

### Penggunaan:

```java
public class SuperDemo {
    public static void main(String[] args) {
        Mahasiswa mhs = new Mahasiswa("Marno");
        mhs.info();
    }
}
```

**🖨️ Output:**

```text
Nama mahasiswa: Marno
```

## 🧪 Studi Kasus: Pegawai dan Manager

Berikut adalah contoh inheritance yang memodelkan hubungan antara **Pegawai** dan **Manager**, dengan overriding dan penggunaan `super`.

```java
public class Pegawai {
    protected String nama;
    protected int gaji;

    public Pegawai(String nama, int gaji) {
        this.nama = nama;
        this.gaji = gaji;
    }

    public void info() {
        System.out.printf("%s bergaji %d%n", nama, gaji);
    }
}

class Manager extends Pegawai {
    private int bonus;

    public Manager(String nama, int gaji, int bonus) {
        super(nama, gaji); // Memanggil constructor superclass
        this.bonus = bonus;
    }

    @Override
    public void info() {
        super.info(); // Memanggil method info dari superclass
        System.out.printf("Total gaji (dengan bonus %d): %d%n", bonus, gaji + bonus);
    }
}
```

### Penggunaan:

```java
public class PegawaiDemo {
    public static void main(String[] args) {
        Manager manager = new Manager("Marno", 5000, 2000);
        manager.info();
    }
}
```

**🖨️ Output:**

```text
Marno bergaji 5000
Total gaji (dengan bonus 2000): 7000
```

## 📌 Kesimpulan

Inheritance adalah alat penting untuk membangun hierarki kelas yang efisien:

| **Konsep**       | **Penjelasan**                                          |
|------------------|--------------------------------------------------------|
| **Inheritance**  | Subclass mewarisi field dan method dari superclass.    |
| **`extends`**    | Digunakan untuk mendefinisikan hubungan pewarisan.     |
| **`super`**      | Mengakses member superclass (constructor, field, method). |
| **Overriding**   | Menyesuaikan implementasi method dari superclass.      |

> 🎯 **Tujuan Utama**: Inheritance memungkinkan *reuse* kode dan pembuatan hierarki kelas yang mencerminkan hubungan dunia nyata.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Polymorphism (Polimorfisme)](polymorphism.md) untuk memahami cara method dapat memiliki perilaku berbeda berdasarkan tipe objek.

⬅️ Kembali: [Encapsulation (Enkapsulasi)](encapsulation.md)
