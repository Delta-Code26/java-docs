# 🏗️ Membuat Class dan Object dalam Java

Dalam OOP Java, semua dimulai dari **class** dan **object**.  
Class adalah blueprint. Object adalah instance-nya — seperti cetakan dan hasil cetakannya.

---

## 1. ✏️ Membuat Class

Class menyimpan:
- **Atribut (field)** → data
- **Method (fungsi)** → aksi

### Contoh:
```java
public class Mahasiswa {
    String nama;
    int umur;

    void sapa() {
        System.out.println("Halo, saya " + nama);
    }
}
````

---

## 2. 🧪 Membuat dan Menggunakan Object

Gunakan keyword `new` untuk membuat object.

```java
public class Demo {
    public static void main(String[] args) {
        Mahasiswa mhs1 = new Mahasiswa();
        mhs1.nama = "Marno";
        mhs1.umur = 21;

        mhs1.sapa(); // output: Halo, saya Marno
    }
}
```

---

## 3. ⚙️ Constructor: Membuat Object Lebih Efisien

**Constructor** adalah method khusus yang otomatis dipanggil saat object dibuat.

```java
class Mahasiswa {
    String nama;
    int umur;

    // Constructor
    Mahasiswa(String n, int u) {
        nama = n;
        umur = u;
    }

    void sapa() {
        System.out.println("Saya " + nama + ", umur " + umur);
    }
}
```

### Contoh Pemanggilan:

```java
Mahasiswa mhs1 = new Mahasiswa("Marno", 21);
mhs1.sapa();
```

💡 Output:

```
Saya Marno, umur 21
```

---

## 4. 🧱 Perbedaan Field, Method, dan Constructor

| Elemen      | Fungsi                                  |
| ----------- | --------------------------------------- |
| Field       | Menyimpan data dalam class              |
| Method      | Menjalankan aksi atau logika            |
| Constructor | Inisialisasi object saat dibuat (`new`) |

---

## 5. 🧠 Studi Kasus: Class `Mobil`

```java
class Mobil {
    String merk;
    int tahun;

    Mobil(String m, int t) {
        merk = m;
        tahun = t;
    }

    void info() {
        System.out.println("Merk: " + merk + ", Tahun: " + tahun);
    }
}

public class DemoMobil {
    public static void main(String[] args) {
        Mobil m1 = new Mobil("Toyota", 2020);
        Mobil m2 = new Mobil("Honda", 2022);

        m1.info();
        m2.info();
    }
}
```

💡 Output:

```
Merk: Toyota, Tahun: 2020  
Merk: Honda, Tahun: 2022
```

---

## 📌 Kesimpulan

| Konsep         | Penjelasan                           |
| -------------- | ------------------------------------ |
| Class          | Blueprint: berisi data dan method    |
| Object         | Wujud nyata class (hasil `new`)      |
| Constructor    | Method khusus untuk inisialisasi     |
| Field & Method | Properti dan aksi dari sebuah object |

---

➡️ Selanjutnya: [Encapsulation (Enkapsulasi)](encapsulation.md)
