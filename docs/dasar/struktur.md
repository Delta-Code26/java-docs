---
title: Struktur Dasar Program Java
description: Memahami fondasi dasar penulisan program Java dengan contoh sederhana
---

# 🧱 Struktur Dasar Program Java

Sebelum membangun aplikasi besar, penting untuk memahami *fondasi* penulisan kode dalam bahasa pemrograman Java. Bagian ini akan menjelaskan struktur dasar program Java dengan contoh sederhana dan penjelasan rinci.

## 🔍 Contoh Program Java Sederhana

Berikut adalah contoh program Java paling dasar yang menampilkan teks "Halo, dunia!" ke layar:

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Halo, dunia!");
    }
}
```

**🖨️ Output:**

```text
Halo, dunia!
```

## 🧩 Penjelasan Baris per Baris

Mari kita bedah setiap baris dari kode di atas untuk memahami struktur dasarnya.

### 1. `public class HelloWorld`

- **`class`**: Mendefinisikan sebuah kelas, yang merupakan *wadah utama* untuk kode dalam Java.
- **`HelloWorld`**: Nama kelas, yang **harus sama** dengan nama file (dalam hal ini, `HelloWorld.java`).
- **`public`**: Menandakan bahwa kelas ini dapat diakses dari mana saja.

> 📌 **Catatan**:  
> Satu file `.java` hanya boleh memiliki **satu `public class`**, dan nama file harus **identik** dengan nama kelas tersebut.

### 2. `public static void main(String[] args)`

- **`public`**: Method ini dapat diakses dari luar kelas.
- **`static`**: Method dapat dijalankan tanpa perlu membuat objek dari kelas.
- **`void`**: Method tidak mengembalikan nilai apa pun.
- **`main`**: Nama method yang menjadi **titik masuk** (entry point) program Java.
- **`String[] args`**: Parameter untuk menerima argumen dari *command line*.

> 💡 **Info**:  
> Method `main` wajib ada dalam setiap program Java yang dapat dijalankan. Tanpa method ini, program tidak akan bisa dijalankan.

### 3. `System.out.println("Halo, dunia!");`

- **`System`**: Kelas bawaan Java untuk mengakses fungsi sistem standar.
- **`out`**: Objek yang mewakili output standar (biasanya layar atau konsol).
- **`println`**: Method untuk mencetak teks ke layar dan menambahkan baris baru setelahnya.

---

## 📁 Struktur File dan Folder

Struktur file yang umum digunakan untuk program Java sederhana adalah sebagai berikut:

```
BelajarJava/
└── HelloWorld.java
```

> **Catatan**: Pastikan file `.java` disimpan dengan nama yang sesuai dengan nama kelas `public`.

---

## 🛠️ Cara Kompilasi dan Menjalankan Program

Berikut adalah langkah-langkah untuk mengompilasi dan menjalankan program Java:

### 1. Kompilasi Program

Gunakan perintah berikut untuk mengompilasi file `HelloWorld.java`:

```bash
javac HelloWorld.java
```

**📦 Hasil**: Jika tidak ada error, akan dihasilkan file `HelloWorld.class`, yang merupakan bytecode yang dapat dijalankan oleh JVM (Java Virtual Machine).

### 2. Jalankan Program

Setelah dikompilasi, jalankan program dengan perintah berikut:

```bash
java HelloWorld
```

**🖨️ Output**: Program akan mencetak teks `Halo, dunia!` ke konsol.

---

## ⚠️ Hal-Hal Penting yang Harus Diingat

Berikut adalah beberapa aturan penting dalam penulisan program Java:

| **⚙️ Aspek**                                | **💡 Penjelasan**                                                                 |
|---------------------------------------------|-----------------------------------------------------------------------------------|
| Nama file = nama kelas `public`             | Nama file (`HelloWorld.java`) harus sama dengan nama kelas `public` (`HelloWorld`).|
| Java bersifat **case-sensitive**            | `HelloWorld` ≠ `helloworld`. Huruf besar dan kecil dibedakan.                      |
| Statement diakhiri **titik koma (`;`)**     | Setiap pernyataan kode harus diakhiri dengan tanda titik koma.                     |
| Blok kode menggunakan `{` dan `}`           | Setiap blok kode harus dibuka dengan `{` dan ditutup dengan `}`, harus seimbang.   |

---

## 🧭 Kesimpulan

Struktur dasar program Java terdiri dari tiga elemen utama:

1. **Kelas** (`class`): Wadah utama kode program.
2. **Method `main`**: Titik masuk eksekusi program.
3. **Statement**: Perintah-perintah seperti `System.out.println` untuk menjalankan logika program.

Contoh di atas (`System.out.println("Halo, dunia!");`) adalah langkah awal untuk memahami Java.

---

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Tipe Data & Variabel](tipe_data.md) untuk memperdalam pemahaman Anda tentang Java.
