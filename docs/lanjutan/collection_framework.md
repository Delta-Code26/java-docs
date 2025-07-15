---
title: Java Collection Framework (JCF) Tingkat Lanjut
description: Memahami struktur data dalam Java Collection Framework seperti List, Set, Map, dan Queue beserta penggunaannya
---

# 🧺 Java Collection Framework (JCF) Tingkat Lanjut

**Java Collection Framework (JCF)** menyediakan sekumpulan struktur data siap pakai yang efisien, aman, dan mendukung operasi skala besar. JCF mencakup antarmuka seperti `List`, `Set`, `Map`, dan `Queue`, serta implementasi seperti `ArrayList`, `HashSet`, `HashMap`, dan `PriorityQueue`. Bagian ini menjelaskan hirarki, karakteristik, dan penggunaan praktis dari JCF, serta panduan untuk memilih struktur data yang tepat.

## 🔖 Hirarki Java Collection Framework

JCF terdiri dari antarmuka utama `Collection` dan `Map`, dengan berbagai implementasi:

```
Collection
├── List
│   ├── ArrayList
│   ├── LinkedList
│   └── Vector (thread-safe, jarang digunakan)
├── Set
│   ├── HashSet
│   ├── LinkedHashSet
│   └── TreeSet
└── Queue
    ├── LinkedList
    ├── PriorityQueue
    └── Deque
        └── ArrayDeque

Map (terpisah dari Collection)
├── HashMap
├── LinkedHashMap
├── TreeMap
└── Hashtable (thread-safe, jarang digunakan)
```

> 📌 **Catatan**: `Map` bukan bagian dari antarmuka `Collection`, tetapi merupakan bagian integral dari JCF karena sering digunakan bersama koleksi lainnya.

## 📘 List: Urutan dan Duplikasi

**List** adalah koleksi yang mempertahankan **urutan elemen** dan **memperbolehkan duplikasi**. Implementasi utama adalah `ArrayList` dan `LinkedList`.

### Contoh:

```java
import java.util.ArrayList;
import java.util.List;

public class ListDemo {
    public static void main(String[] args) {
        List<String> daftar = new ArrayList<>();
        daftar.add("Ali");
        daftar.add("Ali"); // Duplikasi diperbolehkan
        daftar.add("Budi");
        System.out.println("Daftar: " + daftar);
    }
}
```

**🖨️ Output:**

```text
Daftar: [Ali, Ali, Budi]
```

- **ArrayList**: Cepat untuk akses elemen berdasarkan indeks, lambat untuk penyisipan/penghapusan di tengah.
- **LinkedList**: Cepat untuk penyisipan/penghapusan, lambat untuk akses acak.

## 🔐 Set: Unik dan Tidak Selalu Berurutan

**Set** adalah koleksi yang **tidak memperbolehkan duplikasi** dan tidak selalu mempertahankan urutan. Implementasi utama adalah `HashSet` dan `TreeSet`.

### Contoh:

```java
import java.util.HashSet;
import java.util.Set;

public class SetDemo {
    public static void main(String[] args) {
        Set<String> unik = new HashSet<>();
        unik.add("Marno");
        unik.add("Marno"); // Tidak disimpan karena duplikat
        unik.add("Budi");
        System.out.println("Set: " + unik);
    }
}
```

**�二叉️ Output:**

```text
Set: [Budi, Marno]
```

- **HashSet**: Tidak terurut, performa cepat untuk operasi dasar.
- **TreeSet**: Otomatis mengurutkan elemen secara ascending (berdasarkan urutan alami atau comparator).
- **LinkedHashSet**: Mempertahankan urutan penyisipan.

## 🧭 Map: Pasangan Key-Value

**Map** menyimpan data dalam bentuk pasangan **key-value**, di mana setiap kunci unik memetakan ke satu nilai. Implementasi utama adalah `HashMap` dan `TreeMap`.

### Contoh:

```java
import java.util.HashMap;
import java.util.Map;

public class MapDemo {
    public static void main(String[] args) {
        Map<String, Integer> umur = new HashMap<>();
        umur.put("Marno", 25);
        umur.put("Budi", 30);
        System.out.println("Umur Marno: " + umur.get("Marno"));
    }
}
```

**🖨️ Output:**

```text
Umur Marno: 25
```

- **HashMap**: Tidak terurut, performa cepat untuk operasi dasar.
- **TreeMap**: Kunci diurutkan secara ascending.
- **LinkedHashMap**: Mempertahankan urutan penyisipan kunci.

## 📦 Queue dan Deque: Antrean dan Tumpukan

**Queue** mengikuti prinsip **FIFO** (First In, First Out) atau prioritas, cocok untuk sistem antrean. **Deque** (Double-Ended Queue) mendukung operasi dari kedua ujung.

### Contoh Queue:

```java
import java.util.LinkedList;
import java.util.Queue;

public class QueueDemo {
    public static void main(String[] args) {
        Queue<String> antrian = new LinkedList<>();
        antrian.add("User1");
        antrian.add("User2");
        System.out.println("Keluar: " + antrian.poll()); // Mengambil dan menghapus elemen pertama
        System.out.println("Antrian sekarang: " + antrian);
    }
}
```

**🖨️ Output:**

```text
Keluar: User1
Antrian sekarang: [User2]
```

- **LinkedList**: Implementasi `Queue` yang fleksibel, juga mendukung `Deque`.
- **PriorityQueue**: Elemen diurutkan berdasarkan prioritas (alami atau custom).
- **ArrayDeque**: Efisien untuk operasi di kedua ujung (tumpukan atau antrean).

## 🔁 Iterator dan For-Each

Untuk mengakses elemen koleksi, gunakan **for-each** atau **Iterator**.

### Contoh For-Each dan Iterator:

```java
import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

public class IteratorDemo {
    public static void main(String[] args) {
        List<String> daftar = new ArrayList<>();
        daftar.add("Ali");
        daftar.add("Budi");

        // Menggunakan for-each
        System.out.println("Menggunakan for-each:");
        for (String nama : daftar) {
            System.out.println(nama);
        }

        // Menggunakan Iterator
        System.out.println("Menggunakan Iterator:");
        Iterator<String> itr = daftar.iterator();
        while (itr.hasNext()) {
            System.out.println(itr.next());
        }
    }
}
```

**🖨️ Output:**

```text
Menggunakan for-each:
Ali
Budi
Menggunakan Iterator:
Ali
Budi
```

> 💡 **Tips**: Gunakan `for-each` untuk iterasi sederhana, dan `Iterator` jika perlu menghapus elemen selama iterasi (`itr.remove()`).

## 💥 Synchronized Collection

Secara default, koleksi JCF tidak *thread-safe*. Untuk membuat koleksi aman dalam lingkungan multi-thread, gunakan `Collections.synchronizedXXX`.

### Contoh:

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class SynchronizedDemo {
    public static void main(String[] args) {
        List<String> aman = Collections.synchronizedList(new ArrayList<>());
        aman.add("Data1");
        System.out.println("List thread-safe: " + aman);
    }
}
```

**🖨️ Output:**

```text
List thread-safe: [Data1]
```

> 📌 **Catatan**: Untuk performa lebih baik dalam aplikasi multi-thread, pertimbangkan menggunakan kelas dari paket `java.util.concurrent`, seperti `CopyOnWriteArrayList` atau `ConcurrentHashMap`.

## 🧠 Memilih Struktur Data yang Tepat

Memilih struktur data yang sesuai sangat penting untuk efisiensi program:

| **Kasus Penggunaan**                     | **Struktur Data yang Disarankan**                  |
|------------------------------------------|---------------------------------------------------|
| Data berurutan, boleh duplikasi          | `ArrayList` (akses cepat) atau `LinkedList` (sisip/hapus cepat) |
| Data unik, urutan tidak penting          | `HashSet`                                         |
| Data unik, perlu diurutkan               | `TreeSet`                                         |
| Pasangan key-value, akses cepat           | `HashMap`                                         |
| Pasangan key-value, kunci terurut         | `TreeMap`                                         |
| Pasangan key-value, urut berdasarkan input| `LinkedHashMap`                                   |
| Antrean proses/data (FIFO)               | `LinkedList` sebagai `Queue`                      |
| Antrean berdasarkan prioritas            | `PriorityQueue`                                   |
| Tumpukan atau antrean dua arah           | `ArrayDeque`                                      |

## 📌 Kesimpulan

Java Collection Framework menyediakan struktur data yang fleksibel dan efisien untuk berbagai kebutuhan:

| **Struktur** | **Ciri Khas**                              |
|--------------|--------------------------------------------|
| **List**     | Urutan tetap, boleh duplikasi              |
| **Set**      | Elemen unik, tidak selalu terurut          |
| **Map**      | Pasangan key-value, kunci unik             |
| **Queue**    | Antrean data, biasanya FIFO atau prioritas |

JCF adalah alat penting untuk mengelola data dalam program Java secara efisien.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Generics dalam Java](../advanced/generics.md) untuk memahami cara membuat koleksi yang lebih aman dan fleksibel dengan tipe data.
