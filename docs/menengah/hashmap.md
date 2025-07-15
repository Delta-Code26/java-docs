---
title: HashMap dalam Java
description: Memahami penggunaan HashMap untuk menyimpan dan mengelola data dengan pasangan kunci-nilai di Java
---

# 🗂️ HashMap dalam Java

**HashMap** adalah bagian dari **Java Collection Framework (JCF)** yang digunakan untuk menyimpan data dalam bentuk **pasangan kunci-nilai (key-value)**. Setiap kunci bersifat **unik** dan dipetakan ke satu nilai, memungkinkan akses data yang cepat berdasarkan kunci. HashMap sangat cocok untuk kasus seperti konfigurasi, pencarian (*lookup*), atau penyimpanan data asosiatif.

Contoh analogi:
- Kunci: "NIM" → Nilai: "12345"
- Kunci: "Nama" → Nilai: "Marno"
- Kunci: "Role" → Nilai: "Pekerja"

## 🧱 Deklarasi dan Inisialisasi

Untuk menggunakan HashMap, impor `java.util.HashMap` dan deklarasikan instance dengan tipe kunci dan nilai.

```java
import java.util.HashMap;

public class HashMapDemo {
    public static void main(String[] args) {
        HashMap<String, String> data = new HashMap<>();
        data.put("id", "001");
        data.put("nama", "Marno");
        data.put("role", "Mandor");

        System.out.println("Nama: " + data.get("nama"));
    }
}
```

**🖨️ Output:**

```text
Nama: Marno
```

> 📌 **Catatan**: HashMap hanya dapat menyimpan objek, sehingga tipe primitif (seperti `int`) harus menggunakan *wrapper class* (seperti `Integer`).

## 🔧 Operasi Dasar HashMap

HashMap menyediakan method untuk mengelola pasangan kunci-nilai:

| **Method**             | **Keterangan**                              |
|------------------------|--------------------------------------------|
| `put(key, value)`      | Menambahkan atau memperbarui pasangan kunci-nilai. |
| `get(key)`             | Mengambil nilai berdasarkan kunci.         |
| `remove(key)`          | Menghapus pasangan berdasarkan kunci.      |
| `containsKey(key)`     | Memeriksa apakah kunci ada.                |
| `containsValue(value)` | Memeriksa apakah nilai ada.                |
| `size()`               | Mengembalikan jumlah pasangan kunci-nilai. |
| `clear()`              | Menghapus semua pasangan kunci-nilai.      |

### Contoh Operasi:

```java
import java.util.HashMap;

public class HashMapOperationsDemo {
    public static void main(String[] args) {
        HashMap<String, String> user = new HashMap<>();
        user.put("id", "001");
        user.put("nama", "Marno");
        user.put("role", "Mandor");

        // Mengambil nilai
        System.out.println("Role: " + user.get("role"));

        // Memeriksa kunci
        System.out.println("Ada kunci 'id'? " + user.containsKey("id"));

        // Menghapus pasangan
        user.remove("id");
        System.out.println("Setelah menghapus 'id': " + user);

        // Mengecek ukuran
        System.out.println("Jumlah pasangan: " + user.size());
    }
}
```

**🖨️ Output:**

```text
Role: Mandor
Ada kunci 'id'? true
Setelah menghapus 'id': {nama=Marno, role=Mandor}
Jumlah pasangan: 2
```

## 🔁 Iterasi HashMap

HashMap dapat diiterasi menggunakan dua pendekatan utama: `keySet()` untuk mengakses kunci atau `entrySet()` untuk mengakses pasangan kunci-nilai secara langsung.

### 1. Iterasi dengan `keySet()`:

```java
import java.util.HashMap;

public class KeySetDemo {
    public static void main(String[] args) {
        HashMap<String, String> user = new HashMap<>();
        user.put("id", "001");
        user.put("nama", "Marno");
        user.put("role", "Mandor");

        for (String key : user.keySet()) {
            System.out.printf("%s: %s%n", key, user.get(key));
        }
    }
}
```

**🖨️ Output:**

```text
id: 001
nama: Marno
role: Mandor
```

### 2. Iterasi dengan `entrySet()`:

```java
import java.util.HashMap;
import java.util.Map;

public class EntrySetDemo {
    public static void main(String[] args) {
        HashMap<String, String> user = new HashMap<>();
        user.put("id", "001");
        user.put("nama", "Marno");
        user.put("role", "Mandor");

        for (Map.Entry<String, String> entry : user.entrySet()) {
            System.out.printf("%s => %s%n", entry.getKey(), entry.getValue());
        }
    }
}
```

**🖨️ Output:**

```text
id => 001
nama => Marno
role => Mandor
```

> 💡 **Tips**: Gunakan `entrySet()` untuk iterasi yang lebih efisien, karena tidak perlu memanggil `get(key)` berulang kali.

## 🧪 Studi Kasus: Rekap Gaji Pekerja

Berikut adalah contoh penggunaan HashMap untuk menyimpan dan menampilkan data gaji pekerja berdasarkan nama sebagai kunci.

```java
import java.util.HashMap;

public class GajiDemo {
    public static void main(String[] args) {
        HashMap<String, Double> gaji = new HashMap<>();
        gaji.put("Ali", 500.0);
        gaji.put("Budi", 450.0);
        gaji.put("Cici", 470.0);

        for (Map.Entry<String, Double> entry : gaji.entrySet()) {
            System.out.printf("%s menerima RM %.2f%n", entry.getKey(), entry.getValue());
        }

        // Menambahkan pekerja baru
        gaji.put("Dedi", 480.0);
        System.out.println("Setelah menambah Dedi: " + gaji);
    }
}
```

**🖨️ Output:**

```text
Ali menerima RM 500.00
Budi menerima RM 450.00
Cici menerima RM 470.00
Setelah menambah Dedi: {Ali=500.0, Budi=450.0, Cici=470.0, Dedi=480.0}
```

## ⚖️ HashMap vs. ArrayList

| **Fitur**         | **HashMap**                        | **ArrayList**                      |
|-------------------|------------------------------------|------------------------------------|
| **Akses Data**    | Berdasarkan kunci (*key*)          | Berdasarkan indeks                 |
| **Struktur**      | Tidak berurutan (*unordered*)      | Berurutan (*ordered*)              |
| **Cocok Untuk**   | Pencarian cepat, data asosiatif    | Koleksi data berurutan             |
| **Duplikasi**     | Kunci harus unik, nilai bisa duplikat | Elemen bisa duplikat             |

## ⚠️ Catatan Penting

- **Kunci Unik**: Setiap kunci dalam HashMap harus unik; jika kunci ditambahkan ulang, nilai lama akan ditimpa.
- **Urutan Tidak Terjamin**: HashMap tidak menjaga urutan input. Gunakan `LinkedHashMap` untuk mempertahankan urutan.
- **Null Values**: HashMap mengizinkan satu kunci `null` dan beberapa nilai `null`.
- **Performa**: HashMap menawarkan pencarian cepat (O(1) rata-rata) berkat struktur hash table-nya.
- **Thread Safety**: HashMap tidak *thread-safe*. Gunakan `ConcurrentHashMap` untuk aplikasi multi-threaded.

## 📌 Kesimpulan

HashMap adalah struktur data yang kuat untuk mengelola pasangan kunci-nilai:

| **Konsep**       | **Penjelasan**                                      |
|------------------|----------------------------------------------------|
| **HashMap**      | Struktur data untuk menyimpan pasangan kunci-nilai. |
| **Keunggulan**   | Akses cepat, fleksibel, cocok untuk *lookup*.      |
| **Penggunaan**   | Konfigurasi, data pengguna, cache, atau mapping.   |

> 🎯 **Tujuan Utama**: HashMap memungkinkan pengelolaan data asosiatif dengan efisiensi tinggi untuk pencarian dan manipulasi.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [File I/O (Baca & Tulis File)](file_io.md) untuk memahami cara membaca dan menulis data ke file di Java.

⬅️ Kembali: [Array dan ArrayList](array_arraylist.md)