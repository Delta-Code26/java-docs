# 🧭 Konsep Dasar OOP (Object-Oriented Programming) dalam Java

Java adalah bahasa pemrograman **berorientasi objek**, yang berarti semuanya dibangun atas dasar **kelas (class)** dan **objek (object)**.

Dengan OOP, kita bisa membuat kode yang **modular, fleksibel, dan mudah dirawat**.

---

## 🧠 1. Apa Itu Object dan Class?

### Class
Blueprint atau cetakan untuk membuat objek.

```java
class Mobil {
    String merk;
    int tahun;
}
````

### Object

Hasil nyata dari class (instansiasi).

```java
Mobil m1 = new Mobil();
```

---

## 🎯 2. Empat Pilar OOP

### a) **Encapsulation (Enkapsulasi)**

Menyembunyikan detail implementasi, hanya memberikan akses yang diperlukan melalui **method getter/setter**.

```java
class Mahasiswa {
    private String nama;

    public void setNama(String n) {
        nama = n;
    }

    public String getNama() {
        return nama;
    }
}
```

> ✅ Gunakan `private` untuk menjaga keamanan data, dan `public` untuk akses terkontrol.

---

### b) **Inheritance (Pewarisan)**

Mewarisi atribut dan method dari class induk ke class anak.

```java
class Hewan {
    void makan() {
        System.out.println("Hewan sedang makan");
    }
}

class Kucing extends Hewan {
    void suara() {
        System.out.println("Meong");
    }
}
```

> 💡 Gunakan keyword `extends` untuk pewarisan.

---

### c) **Polymorphism (Polimorfisme)**

Satu method bisa memiliki **banyak bentuk** tergantung objeknya.

```java
class Bentuk {
    void gambar() {
        System.out.println("Menggambar bentuk");
    }
}

class Lingkaran extends Bentuk {
    void gambar() {
        System.out.println("Menggambar lingkaran");
    }
}
```

### Method Overriding

Mengubah perilaku method di class anak.

---

### d) **Abstraction (Abstraksi)**

Menyembunyikan kompleksitas dan hanya menunjukkan fitur penting.

```java
abstract class Kendaraan {
    abstract void jalan();
}
```

> Gunakan `abstract` untuk mendefinisikan class/metode yang belum memiliki implementasi.

---

## 🧪 Studi Kasus: Class dan Object

```java
class Mahasiswa {
    String nama;
    int umur;

    void sapa() {
        System.out.println("Halo, nama saya " + nama);
    }
}

public class Demo {
    public static void main(String[] args) {
        Mahasiswa m1 = new Mahasiswa();
        m1.nama = "Marno";
        m1.umur = 22;
        m1.sapa();
    }
}
```

💡 Output:

```
Halo, nama saya Marno
```

---

## 📌 Kesimpulan

| Konsep        | Arti Sederhana                     |
| ------------- | ---------------------------------- |
| Class         | Cetakan/desain                     |
| Object        | Wujud nyata dari class             |
| Encapsulation | Proteksi dan pengaturan akses data |
| Inheritance   | Pewarisan fitur dari class lain    |
| Polymorphism  | Satu nama method, banyak perilaku  |
| Abstraction   | Menyederhanakan kompleksitas       |

---

➡️ Selanjutnya: [Membuat Class dan Objek](class_objek.md)