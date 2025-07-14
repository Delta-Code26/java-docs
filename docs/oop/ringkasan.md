# 🧾 Ringkasan OOP & Studi Kasus

Setelah mempelajari semua pilar **Object-Oriented Programming (OOP)**, saatnya kita merangkum dan melihat bagaimana semuanya bekerja dalam praktik nyata.

---

## 🧱 Ringkasan Empat Pilar OOP

| Pilar          | Konsep Inti                                                         |
|----------------|---------------------------------------------------------------------|
| Encapsulation  | Menyembunyikan data, hanya akses via getter/setter                 |
| Inheritance    | Pewarisan method & atribut dari class induk ke class anak          |
| Polymorphism   | Banyak bentuk: satu interface, banyak implementasi                 |
| Abstraction    | Menyembunyikan kompleksitas, hanya menampilkan fitur utama         |

---

## 📘 Studi Kasus: Sistem Rekap Panen Sawit (Sederhana)

Bayangkan kita sedang membuat sistem untuk mencatat hasil panen kelapa sawit. Setiap pekerja memiliki peran berbeda dalam satu tim (pemotong, penyusun, pengutip), dan kita ingin menghitung gaji mereka berdasarkan kontribusi masing-masing.

---

## 1. Buat Class Abstrak: `Pekerja`

```java
abstract class Pekerja {
    protected String nama;

    public Pekerja(String nama) {
        this.nama = nama;
    }

    abstract double hitungGaji(double totalBerat);
}
````

---

## 2. Buat Class Turunan

### a) Pemotong

```java
class Pemotong extends Pekerja {
    Pemotong(String nama) {
        super(nama);
    }

    double hitungGaji(double totalBerat) {
        return totalBerat * 0.4;
    }
}
```

### b) Penyusun

```java
class Penyusun extends Pekerja {
    Penyusun(String nama) {
        super(nama);
    }

    double hitungGaji(double totalBerat) {
        return totalBerat * 0.35;
    }
}
```

### c) Pengutip

```java
class Pengutip extends Pekerja {
    Pengutip(String nama) {
        super(nama);
    }

    double hitungGaji(double totalBerat) {
        return totalBerat * 0.25;
    }
}
```

---

## 3. Implementasi Main

```java
public class DemoPanen {
    public static void main(String[] args) {
        double beratPanen = 1000; // kg

        Pekerja p1 = new Pemotong("Ali");
        Pekerja p2 = new Penyusun("Budi");
        Pekerja p3 = new Pengutip("Cici");

        System.out.println(p1.nama + ": RM " + p1.hitungGaji(beratPanen));
        System.out.println(p2.nama + ": RM " + p2.hitungGaji(beratPanen));
        System.out.println(p3.nama + ": RM " + p3.hitungGaji(beratPanen));
    }
}
```

💡 Output:

```
Ali: RM 400.0
Budi: RM 350.0
Cici: RM 250.0
```

---

## 🎓 Kesimpulan Akhir

| Konsep        | Realisasi dalam Studi Kasus                   |
| ------------- | --------------------------------------------- |
| Encapsulation | Atribut `nama` disimpan secara protected      |
| Inheritance   | Semua class mewarisi dari `Pekerja`           |
| Polymorphism  | Pemanggilan `hitungGaji()` sesuai objek nyata |
| Abstraction   | `Pekerja` sebagai class abstrak               |

---

## 📎 Catatan Tambahan

* Dalam proyek besar, struktur OOP akan dipadukan dengan database dan API
* Prinsip OOP penting untuk membuat kode **fleksibel, reusable, dan scalable**
* Gunakan OOP untuk semua entitas bisnis: `User`, `Gaji`, `Panen`, `Tim`, dll

---

➡️ Selesai! Kamu sekarang siap membangun aplikasi Java dengan dasar OOP yang kokoh 🏗️

⬅️ Kembali: [Abstraction (Abstraksi)](abstraction.md)