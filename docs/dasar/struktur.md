# 🧱 Struktur Dasar Program Java

Sebelum membuat aplikasi besar, kita perlu memahami *struktur paling dasar* dari program Java.

---

## 🔍 Contoh Program Java Paling Sederhana

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Halo, dunia!");
    }
}
````

Jika dijalankan, akan menghasilkan:

```
Halo, dunia!
```

---

## 🧩 Penjelasan Bagian per Bagian

Mari kita pecah kode di atas:

### 1. `public class HelloWorld`

* **`class`** adalah kata kunci untuk mendefinisikan kelas (wadah utama dalam Java).
* **`HelloWorld`** adalah nama kelas. Nama file **harus sama** dengan nama kelas.
* **`public`** berarti kelas ini dapat diakses dari mana saja.

> 📌 *Satu file Java hanya boleh punya satu `public class` dan namanya harus sama dengan nama file.*

---

### 2. `public static void main(String[] args)`

Ini adalah **method utama** tempat program mulai dijalankan.

* `public` → bisa diakses dari mana saja
* `static` → bisa dijalankan tanpa membuat objek dulu
* `void` → tidak mengembalikan nilai
* `main` → nama fungsi utama
* `String[] args` → argumen dari command line (jarang digunakan di awal)

> 💬 *Tanpa method `main()`, program Java tidak akan bisa dijalankan.*

---

### 3. `System.out.println("Halo, dunia!");`

Digunakan untuk mencetak teks ke layar.

* `System` → kelas sistem standar Java
* `out` → objek output standar (biasanya layar)
* `println()` → cetak teks lalu pindah baris

---

## 📂 Contoh File dan Struktur Folder

```
BelajarJava/
└── HelloWorld.java
```

---

## 🛠️ Cara Kompilasi dan Jalankan

### 1. Kompilasi Program

```bash
javac HelloWorld.java
```

Jika tidak ada error, akan muncul file `HelloWorld.class`.

### 2. Jalankan Program

```bash
java HelloWorld
```

---

## ⚠️ Catatan Penting

| Hal                                                | Penjelasan                                        |
| -------------------------------------------------- | ------------------------------------------------- |
| Nama file harus sama dengan nama kelas public      | `HelloWorld.java` untuk `public class HelloWorld` |
| Java bersifat case-sensitive                       | `HelloWorld` ≠ `helloworld`                       |
| Setiap statement diakhiri dengan `;`               | Wajib seperti titik di akhir kalimat              |
| Blok kode dibuka dengan `{` dan ditutup dengan `}` | Jangan sampai tidak seimbang                      |

---

## ✅ Kesimpulan

Struktur dasar program Java selalu dimulai dari:

* Sebuah **kelas** (`class`)
* Fungsi utama **`main()`**
* Statement di dalamnya (seperti `System.out.println`)

Selanjutnya kita akan belajar tentang:
➡️ [Tipe Data & Variabel](tipe_data.md)