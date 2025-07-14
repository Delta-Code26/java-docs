# 🧼 Abstraction (Abstraksi) dalam Java

**Abstraction** adalah proses menyembunyikan detail implementasi dan hanya menampilkan fitur penting kepada pengguna.

Bayangkan saat kamu mengendarai mobil:
> Kamu cukup tahu cara menginjak gas dan rem — kamu **tidak perlu tahu cara kerja mesin**.

---

## 🧠 Tujuan Abstraksi

- Menyederhanakan kompleksitas
- Membuat kode mudah digunakan dan dikembangkan
- Menyediakan kontrak (interface) yang jelas untuk developer

---

## 👑 Dua Cara Menerapkan Abstraksi di Java:

1. **Abstract Class**
2. **Interface**

---

## 1. 🧱 Abstract Class

Class yang **tidak bisa diinstansiasi langsung** dan bisa memiliki method:
- abstract (tanpa isi)
- non-abstract (dengan isi)

### Struktur:
```java
abstract class Kendaraan {
    abstract void jalan(); // wajib diimplementasikan
    void info() {
        System.out.println("Ini kendaraan umum");
    }
}
````

### Subclass:

```java
class Mobil extends Kendaraan {
    void jalan() {
        System.out.println("Mobil berjalan di jalan raya");
    }
}
```

### Penggunaan:

```java
Kendaraan m = new Mobil();
m.jalan(); // Mobil berjalan di jalan raya
m.info();  // Ini kendaraan umum
```

---

## 2. 💡 Interface

Interface adalah **kontrak murni**: semua method-nya bersifat `abstract` secara default (sejak Java 8 bisa punya default dan static method).

```java
interface Hewan {
    void suara();
}
```

### Implementasi:

```java
class Kucing implements Hewan {
    public void suara() {
        System.out.println("Meong");
    }
}
```

### Penggunaan:

```java
Hewan h = new Kucing();
h.suara(); // Meong
```

---

## 🔍 Abstract Class vs Interface

| Fitur                | Abstract Class            | Interface                      |
| -------------------- | ------------------------- | ------------------------------ |
| Keyword              | `abstract`                | `interface`                    |
| Konstruktor          | Bisa                      | Tidak bisa                     |
| Implementasi Method  | Bisa punya method lengkap | Tidak (kecuali default/static) |
| Multiple Inheritance | Tidak bisa                | Bisa                           |
| Digunakan ketika     | Ada logika umum           | Hanya definisi kontrak         |

---

## 🧪 Studi Kasus: Abstraksi Pembayaran

```java
abstract class Pembayaran {
    abstract void proses();
}

class TransferBank extends Pembayaran {
    void proses() {
        System.out.println("Memproses transfer bank...");
    }
}

class EWallet extends Pembayaran {
    void proses() {
        System.out.println("Memproses E-Wallet...");
    }
}
```

### Penggunaan:

```java
Pembayaran p = new TransferBank();
p.proses(); // Memproses transfer bank...
```

---

## 📌 Kesimpulan

| Konsep         | Penjelasan                                       |
| -------------- | ------------------------------------------------ |
| Abstraction    | Menyembunyikan detail dan hanya tampilkan esensi |
| Abstract Class | Partial abstraction (boleh ada method lengkap)   |
| Interface      | Full abstraction (hanya kontrak)                 |
| Tujuan Umum    | Kesederhanaan, struktur, dan fleksibilitas       |

---

🎯 Dengan abstraction, developer cukup tahu **apa yang harus dilakukan**, tanpa tahu **bagaimana dilakukan**.

➡️ Selanjutnya: [Ringkasan OOP dan Studi Kasus Proyek](ringkasan.md)