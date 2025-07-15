---
title: Array dan ArrayList dalam Java
description: Memahami penggunaan Array dan ArrayList untuk menyimpan dan mengelola kumpulan data di Java
---

# 🧮 Array dan ArrayList dalam Java

Dalam pemrograman Java, **Array** dan **ArrayList** adalah dua struktur data yang digunakan untuk menyimpan **kumpulan data** secara berurutan. Keduanya memiliki kegunaan spesifik: Array cocok untuk data dengan ukuran tetap, sedangkan ArrayList menawarkan fleksibilitas dengan ukuran dinamis. Bagian ini menjelaskan cara menggunakan Array dan ArrayList, perbedaan utama, serta metode penting untuk mengelola data.

## 1️⃣ Array: Struktur Data dengan Ukuran Tetap

**Array** adalah struktur data yang menyimpan elemen-elemen dengan tipe data yang sama dalam ukuran yang **tetap** (tidak dapat diubah setelah dideklarasikan). Array efisien untuk akses cepat berdasarkan indeks, tetapi kurang fleksibel untuk operasi seperti penambahan atau penghapusan elemen.

### Deklarasi dan Inisialisasi Array:

```java
public class ArrayDemo {
    public static void main(String[] args) {
        // Deklarasi dengan ukuran
        int[] angka = new int[3];
        angka[0] = 10;
        angka[1] = 20;
        angka[2] = 30;

        // Deklarasi langsung
        String[] nama = {"Ali", "Budi", "Cici"};
    }
}
```

### Iterasi Array:

```java
public class ArrayIterationDemo {
    public static void main(String[] args) {
        int[] angka = {10, 20, 30};

        // Menggunakan for loop
        for (int i = 0; i < angka.length; i++) {
            System.out.println("Angka ke-" + i + ": " + angka[i]);
        }

        // Menggunakan for-each
        String[] nama = {"Ali", "Budi", "Cici"};
        for (String n : nama) {
            System.out.println("Nama: " + n);
        }
    }
}
```

**🖨️ Output:**

```text
Angka ke-0: 10
Angka ke-1: 20
Angka ke-2: 30
Nama: Ali
Nama: Budi
Nama: Cici
```

### Keterbatasan Array:
- **Ukuran Tetap**: Tidak dapat menambah atau menghapus elemen setelah deklarasi.
- **Fungsionalitas Terbatas**: Tidak memiliki method bawaan untuk operasi seperti pencarian atau penghapusan.
- **Rawan Kesalahan**: Akses di luar batas array menyebabkan `ArrayIndexOutOfBoundsException`.

## 2️⃣ ArrayList: Struktur Data dengan Ukuran Dinamis

**ArrayList** adalah bagian dari **Java Collection Framework (JCF)** yang menyediakan struktur data dinamis untuk menyimpan elemen. ArrayList dapat mengubah ukurannya secara otomatis dan mendukung berbagai method untuk manipulasi data. ArrayList hanya dapat menyimpan objek (bukan tipe primitif), sehingga tipe primitif seperti `int` harus menggunakan *wrapper class* seperti `Integer`.

### Deklarasi dan Penggunaan:

```java
import java.util.ArrayList;

public class ArrayListDemo {
    public static void main(String[] args) {
        ArrayList<String> buah = new ArrayList<>();
        buah.add("Mangga");
        buah.add("Durian");
        buah.add("Kelapa");

        System.out.println("Daftar buah: " + buah);
    }
}
```

**🖨️ Output:**

```text
Daftar buah: [Mangga, Durian, Kelapa]
```

> 📌 **Catatan**: Pastikan untuk mengimpor `java.util.ArrayList` sebelum menggunakan ArrayList.

### Method Penting ArrayList:

| **Method**           | **Keterangan**                          |
|----------------------|----------------------------------------|
| `add(item)`          | Menambahkan elemen ke akhir daftar.    |
| `get(index)`         | Mengambil elemen pada indeks tertentu. |
| `set(index, item)`   | Mengganti elemen pada indeks tertentu. |
| `remove(index)`      | Menghapus elemen pada indeks tertentu. |
| `size()`             | Mengembalikan jumlah elemen.           |
| `clear()`            | Menghapus semua elemen.                |
| `contains(item)`     | Memeriksa apakah elemen ada di daftar. |

### Contoh Penggunaan Method:

```java
import java.util.ArrayList;

public class ArrayListMethodDemo {
    public static void main(String[] args) {
        ArrayList<String> tim = new ArrayList<>();
        tim.add("Mandor");
        tim.add("Pemotong");
        tim.add("Penyusun");

        // Mengakses elemen
        System.out.println("Elemen pertama: " + tim.get(0));

        // Mengganti elemen
        tim.set(1, "Pemanen");
        System.out.println("Setelah diganti: " + tim);

        // Menghapus elemen
        tim.remove(2);
        System.out.println("Setelah dihapus: " + tim);

        // Mengecek ukuran
        System.out.println("Jumlah anggota tim: " + tim.size());
    }
}
```

**🖨️ Output:**

```text
Elemen pertama: Mandor
Setelah diganti: [Mandor, Pemanen, Penyusun]
Setelah dihapus: [Mandor, Pemanen]
Jumlah anggota tim: 2
```

## ⚖️ Perbandingan Array vs. ArrayList

| **Fitur**         | **Array**                          | **ArrayList**                      |
|-------------------|------------------------------------|------------------------------------|
| **Ukuran**        | Tetap (tidak dapat diubah)         | Dinamis (dapat bertambah/kurang)   |
| **Tipe Data**     | Primitif atau objek                | Hanya objek (gunakan wrapper class untuk primitif) |
| **Import**        | Tidak perlu                        | Perlu `java.util.ArrayList`        |
| **Method Bantu**  | Terbatas (hanya `.length`)         | Banyak (`add`, `remove`, dll.)     |
| **Performa**      | Lebih cepat untuk akses sederhana  | Sedikit lebih lambat, tapi fleksibel |

> 💡 **Tips**: Gunakan **Array** untuk data dengan ukuran tetap dan performa tinggi, dan **ArrayList** untuk data yang sering berubah atau memerlukan manipulasi.

## 🔁 Konversi Antara Array dan ArrayList

### Array ke ArrayList:

```java
import java.util.ArrayList;
import java.util.Arrays;

public class ArrayToArrayListDemo {
    public static void main(String[] args) {
        String[] data = {"A", "B", "C"};
        ArrayList<String> list = new ArrayList<>(Arrays.asList(data));
        System.out.println("ArrayList: " + list);
    }
}
```

**🖨️ Output:**

```text
ArrayList: [A, B, C]
```

### ArrayList ke Array:

```java
import java.util.ArrayList;

public class ArrayListToArrayDemo {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("A");
        list.add("B");
        String[] arrayBaru = list.toArray(new String[0]);
        System.out.println("Array: " + Arrays.toString(arrayBaru));
    }
}
```

**🖨️ Output:**

```text
Array: [A, B]
```

## 🧪 Studi Kasus: Sistem Daftar Pekerja

Berikut adalah contoh penggunaan ArrayList untuk mengelola daftar nama pekerja dalam proyek.

```java
import java.util.ArrayList;

public class PekerjaDemo {
    public static void main(String[] args) {
        ArrayList<String> pekerja = new ArrayList<>();
        pekerja.add("Ali");
        pekerja.add("Budi");
        pekerja.add("Cici");

        // Iterasi dengan for loop
        for (int i = 0; i < pekerja.size(); i++) {
            System.out.printf("Pekerja %d: %s%n", i + 1, pekerja.get(i));
        }

        // Menambahkan pekerja baru
        pekerja.add("Dedi");
        System.out.println("Setelah menambah pekerja: " + pekerja);
    }
}
```

**🖨️ Output:**

```text
Pekerja 1: Ali
Pekerja 2: Budi
Pekerja 3: Cici
Setelah menambah pekerja: [Ali, Budi, Cici, Dedi]
```

## 📌 Kesimpulan

Array dan ArrayList adalah alat penting untuk mengelola kumpulan data:

| **Konsep**    | **Penjelasan**                                         |
|---------------|-------------------------------------------------------|
| **Array**     | Struktur statis, efisien, cocok untuk ukuran tetap.    |
| **ArrayList** | Struktur dinamis, fleksibel, cocok untuk manipulasi data. |
| **Pilihan**   | Gunakan ArrayList untuk kebanyakan aplikasi modern.    |

> 🎯 **Tujuan Utama**: Memilih struktur data yang tepat (Array atau ArrayList) bergantung pada kebutuhan ukuran dan fleksibilitas.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [HashMap dan Struktur Data Key-Value](hashmap.md) untuk memahami cara menyimpan data dengan pasangan kunci-nilai.

⬅️ Kembali: [Polymorphism (Polimorfisme)](polymorphism.md)