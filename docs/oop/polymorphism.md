# 🌀 Polymorphism (Polimorfisme) dalam Java

**Polymorphism** berasal dari bahasa Yunani:
> *poly* = banyak, *morph* = bentuk

Dalam Java, polymorphism memungkinkan **satu method/objek** memiliki **banyak bentuk**.  
Artinya, method yang sama bisa bekerja dengan cara berbeda tergantung objeknya.

---

## 🔧 Dua Jenis Polymorphism:

### 1. **Compile-time Polymorphism** (Static) → *Method Overloading*
### 2. **Runtime Polymorphism** (Dynamic) → *Method Overriding*

---

## 1. 🧱 Compile-Time Polymorphism (Method Overloading)

**Overloading** terjadi ketika beberapa method memiliki nama yang sama, namun dengan **parameter berbeda**.

```java
class Kalkulator {
    int tambah(int a, int b) {
        return a + b;
    }

    double tambah(double a, double b) {
        return a + b;
    }

    int tambah(int a, int b, int c) {
        return a + b + c;
    }
}
````

### Penggunaan:

```java
Kalkulator k = new Kalkulator();
System.out.println(k.tambah(2, 3));       // 5
System.out.println(k.tambah(2.5, 3.5));   // 6.0
System.out.println(k.tambah(1, 2, 3));    // 6
```

> 🧠 Overloading terjadi saat **compile time**, karena compiler bisa membedakan berdasarkan parameter.

---

## 2. 🔄 Runtime Polymorphism (Method Overriding)

**Overriding** terjadi saat subclass memberikan implementasi ulang terhadap method dari superclass.

```java
class Hewan {
    void suara() {
        System.out.println("Hewan bersuara");
    }
}

class Kucing extends Hewan {
    @Override
    void suara() {
        System.out.println("Meong");
    }
}

class Anjing extends Hewan {
    @Override
    void suara() {
        System.out.println("Guk Guk");
    }
}
```

---

## 🎯 Polymorphism dengan Referensi Superclass

```java
public class Demo {
    public static void main(String[] args) {
        Hewan h1 = new Kucing();
        Hewan h2 = new Anjing();

        h1.suara(); // Meong
        h2.suara(); // Guk Guk
    }
}
```

> 🧠 Di sini, method `suara()` dieksekusi sesuai dengan **objek aktual**, bukan tipe referensi-nya.

---

## ⚠️ Kenapa Polymorphism Penting?

* ✅ Membuat kode lebih **modular & scalable**
* ✅ Mendukung prinsip **Open/Closed** (OOP Design Principle)
* ✅ Memungkinkan satu antarmuka dipakai untuk banyak implementasi

---

## 🧪 Studi Kasus: Kendaraan

```java
class Kendaraan {
    void jalan() {
        System.out.println("Kendaraan bergerak...");
    }
}

class Mobil extends Kendaraan {
    @Override
    void jalan() {
        System.out.println("Mobil melaju di jalan");
    }
}

class Motor extends Kendaraan {
    @Override
    void jalan() {
        System.out.println("Motor menyusuri gang kecil");
    }
}

public class DemoKendaraan {
    public static void main(String[] args) {
        Kendaraan k1 = new Mobil();
        Kendaraan k2 = new Motor();

        k1.jalan(); // Mobil melaju di jalan
        k2.jalan(); // Motor menyusuri gang kecil
    }
}
```

---

## 📌 Kesimpulan

| Jenis Polymorphism | Teknik                            | Waktu Terjadi      |
| ------------------ | --------------------------------- | ------------------ |
| Compile-time       | Method Overloading                | Saat kompilasi     |
| Runtime            | Method Overriding                 | Saat program jalan |
| Tujuan Umum        | Fleksibilitas & Reusabilitas Kode |                    |

---

➡️ Selanjutnya: [Abstraction (Abstraksi)](abstraction.md)