---
title: Abstraksi dalam Java
description: Memahami konsep abstraksi dalam Java melalui abstract class dan interface untuk menyederhanakan kompleksitas
---

# 🧼 Abstraksi dalam Java

**Abstraksi** adalah salah satu pilar utama Object-Oriented Programming (OOP) yang memungkinkan kita **menyembunyikan detail implementasi** dan hanya menampilkan **fungsi esensial** kepada pengguna. Dengan abstraksi, kode menjadi lebih sederhana, mudah digunakan, dan fleksibel untuk pengembangan lebih lanjut.

> **Analogi**: Saat mengendarai mobil, Anda hanya perlu tahu cara menginjak pedal gas dan rem tanpa memahami cara kerja mesin secara detail. Abstraksi bekerja dengan cara yang sama dalam pemrograman.

## 🧠 Tujuan Abstraksi

- **Menyederhanakan Kompleksitas**: Menyembunyikan detail teknis yang tidak perlu diketahui pengguna.
- **Meningkatkan Fleksibilitas**: Memungkinkan perubahan implementasi tanpa memengaruhi kode lain.
- **Menyediakan Kontrak Jelas**: Menentukan apa yang harus dilakukan tanpa menjelaskan bagaimana melakukannya.

## 👑 Cara Menerapkan Abstraksi di Java

Java mendukung abstraksi melalui dua mekanisme utama:
1. **Abstract Class**: Kelas yang dapat memiliki kombinasi method abstrak (tanpa implementasi) dan method konkret (dengan implementasi).
2. **Interface**: Kontrak murni yang mendefinisikan method tanpa implementasi (meskipun sejak Java 8, interface dapat memiliki method `default` dan `static`).

## 1. 🧱 Abstract Class

**Abstract class** adalah kelas yang dideklarasikan dengan kata kunci `abstract` dan **tidak dapat diinstansiasi langsung**. Kelas ini dapat memiliki:
- Method abstrak (tanpa isi, harus diimplementasikan oleh subclass).
- Method konkret (dengan isi, dapat digunakan langsung).

### Struktur:

```java
abstract class Kendaraan {
    // Method abstrak (wajib diimplementasikan oleh subclass)
    abstract void jalan();

    // Method konkret (dapat digunakan langsung)
    void info() {
        System.out.println("Ini kendaraan umum");
    }
}
```

### Subclass:

```java
class Mobil extends Kendaraan {
    @Override
    void jalan() {
        System.out.println("Mobil berjalan di jalan raya");
    }
}
```

### Penggunaan:

```java
public class AbstractClassDemo {
    public static void main(String[] args) {
        Kendaraan kendaraan = new Mobil();
        kendaraan.jalan(); // Memanggil method dari subclass
        kendaraan.info();  // Memanggil method konkret dari abstract class
    }
}
```

**🖨️ Output:**

```text
Mobil berjalan di jalan raya
Ini kendaraan umum
```

> 📌 **Catatan**: Subclass harus mengimplementasikan semua method abstrak dari parent class, kecuali jika subclass juga dideklarasikan sebagai `abstract`.

## 2. 💡 Interface

**Interface** adalah kontrak murni yang mendefinisikan method yang harus diimplementasikan oleh kelas yang menggunakannya. Semua method dalam interface bersifat `public` dan `abstract` secara default (sebelum Java 8). Sejak Java 8, interface dapat memiliki method `default` dan `static`.

### Struktur:

```java
interface Hewan {
    void suara(); // Method abstrak
}
```

### Implementasi:

```java
class Kucing implements Hewan {
    @Override
    public void suara() {
        System.out.println("Meong");
    }
}
```

### Penggunaan:

```java
public class InterfaceDemo {
    public static void main(String[] args) {
        Hewan hewan = new Kucing();
        hewan.suara(); // Memanggil implementasi dari Kucing
    }
}
```

**🖨️ Output:**

```text
Meong
```

> 💡 **Info**: Sejak Java 8, interface dapat memiliki method `default` untuk menyediakan implementasi default, memungkinkan fleksibilitas tanpa memaksa semua kelas implementor mengoverride method tersebut.

### Contoh Interface dengan Method `default`:

```java
interface Hewan {
    void suara();
    default void makan() {
        System.out.println("Hewan ini sedang makan");
    }
}
```

## 🔍 Abstract Class vs. Interface

Berikut adalah perbandingan antara `abstract class` dan `interface`:

| **Fitur**                  | **Abstract Class**                          | **Interface**                              |
|----------------------------|---------------------------------------------|--------------------------------------------|
| **Keyword**                | `abstract class`                            | `interface`                                |
| **Konstruktor**            | Bisa memiliki konstruktor                   | Tidak bisa memiliki konstruktor            |
| **Implementasi Method**    | Bisa memiliki method konkret dan abstrak    | Hanya method abstrak (kecuali `default`/`static`) |
| **Multiple Inheritance**   | Tidak mendukung (hanya satu parent class)   | Mendukung (bisa implementasi banyak interface) |
| **Field**                  | Bisa memiliki field (variabel instance)     | Hanya konstanta (`public static final`)    |
| **Kapan Digunakan**        | Logika umum yang dibagi antar subclass      | Kontrak murni untuk perilaku tertentu      |

> 📌 **Tips**: Gunakan `abstract class` jika ada logika atau state yang dapat dibagi, dan gunakan `interface` untuk mendefinisikan kontrak yang harus dipatuhi oleh banyak kelas.

## 🧪 Studi Kasus: Sistem Pembayaran

Berikut adalah contoh penggunaan abstraksi untuk sistem pembayaran dengan `abstract class`:

```java
abstract class Pembayaran {
    abstract void proses(); // Method abstrak untuk diproses oleh subclass
}

class TransferBank extends Pembayaran {
    @Override
    void proses() {
        System.out.println("Memproses transfer bank...");
    }
}

class EWallet extends Pembayaran {
    @Override
    void proses() {
        System.out.println("Memproses pembayaran via E-Wallet...");
    }
}

public class PaymentDemo {
    public static void main(String[] args) {
        Pembayaran pembayaran1 = new TransferBank();
        Pembayaran pembayaran2 = new EWallet();
        pembayaran1.proses();
        pembayaran2.proses();
    }
}
```

**🖨️ Output:**

```text
Memproses transfer bank...
Memproses pembayaran via E-Wallet...
```

### Contoh dengan Interface:

```java
interface PaymentProcessor {
    void processPayment();
    default void logTransaction() {
        System.out.println("Transaksi dicatat");
    }
}

class CreditCard implements PaymentProcessor {
    @Override
    public void processPayment() {
        System.out.println("Memproses pembayaran kartu kredit...");
    }
}

public class PaymentProcessorDemo {
    public static void main(String[] args) {
        PaymentProcessor processor = new CreditCard();
        processor.processPayment();
        processor.logTransaction();
    }
}
```

**🖨️ Output:**

```text
Memproses pembayaran kartu kredit...
Transaksi dicatat
```

## 📌 Kesimpulan

Abstraksi adalah kunci untuk membuat kode yang modular dan mudah dipelihara:

| **Konsep**         | **Penjelasan**                                      |
|--------------------|----------------------------------------------------|
| **Abstraksi**      | Menyembunyikan detail implementasi, menampilkan fungsi esensial |
| **Abstract Class** | Kelas dengan logika umum dan method abstrak/konkret |
| **Interface**      | Kontrak murni untuk mendefinisikan perilaku        |
| **Manfaat**        | Menyederhanakan kode, meningkatkan fleksibilitas   |

🎯 Dengan abstraksi, developer fokus pada **apa** yang dilakukan sistem, bukan **bagaimana** implementasinya.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Ringkasan OOP dan Studi Kasus Proyek](ringkasan.md) untuk melihat penerapan semua konsep OOP dalam proyek nyata.