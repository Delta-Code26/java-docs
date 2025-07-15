---
title: File I/O (Input dan Output File) dalam Java
description: Memahami cara membaca dan menulis file teks menggunakan API File I/O di Java
---

# 📁 File I/O (Input dan Output File) dalam Java

Java menyediakan API yang kuat untuk **File Input/Output (I/O)**, memungkinkan program untuk membaca dan menulis data ke file, baik dalam format teks maupun biner. Bagian ini berfokus pada operasi I/O untuk file teks menggunakan kelas seperti `FileReader`, `BufferedReader`, `FileWriter`, dan `BufferedWriter`, serta pengelolaan file dan folder dengan kelas `File`.

### Tujuan File I/O
- **Membaca Data**: Mengambil konten dari file untuk diproses.
- **Menulis Data**: Menyimpan hasil program ke file untuk penyimpanan permanen.
- **Mengelola File/Folder**: Memeriksa keberadaan file atau membuat direktori.

## 📥 Membaca File Teks

Untuk membaca file teks, gunakan `BufferedReader` bersama `FileReader` untuk efisiensi, karena `BufferedReader` membaca data per baris dengan buffer, mengurangi akses langsung ke disk.

### Contoh dengan `BufferedReader` (Menggunakan Try-with-Resources):

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class BacaFileDemo {
    public static void main(String[] args) {
        try (BufferedReader reader = new BufferedReader(new FileReader("data.txt"))) {
            String baris;
            while ((baris = reader.readLine()) != null) {
                System.out.println(baris);
            }
        } catch (IOException e) {
            System.out.println("Gagal membaca file: " + e.getMessage());
        }
    }
}
```

**🖨️ Output (jika data.txt berisi):**

```text
Ali
Budi
Cici
```

> 💡 **Tips**: Gunakan **try-with-resources** untuk memastikan file ditutup secara otomatis, mengurangi risiko kebocoran sumber daya.

## 📝 Menulis ke File Teks

Untuk menulis ke file teks, gunakan `BufferedWriter` bersama `FileWriter` untuk efisiensi dan kemudahan menulis data per baris.

### Contoh dengan `BufferedWriter`:

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class TulisFileDemo {
    public static void main(String[] args) {
        try (BufferedWriter writer = new BufferedWriter(new FileWriter("output.txt"))) {
            writer.write("Data panen berhasil dicatat.");
            writer.newLine();
            writer.write("Total berat: 1234 kg");
            System.out.println("Berhasil menulis file.");
        } catch (IOException e) {
            System.out.println("Gagal menulis file: " + e.getMessage());
        }
    }
}
```

**🖨️ Output (di konsol):**

```text
Berhasil menulis file.
```

**Isi file output.txt:**

```text
Data panen berhasil dicatat.
Total berat: 1234 kg
```

## 🔄 Menambahkan Data ke File (Append)

Untuk menambahkan data tanpa menimpa isi file yang ada, gunakan parameter `true` pada konstruktor `FileWriter`.

### Contoh Append:

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class AppendFileDemo {
    public static void main(String[] args) {
        try (BufferedWriter writer = new BufferedWriter(new FileWriter("log.txt", true))) {
            writer.write("Tambahan data: 2025-07-15");
            writer.newLine();
            System.out.println("Berhasil menambahkan data ke file.");
        } catch (IOException e) {
            System.out.println("Gagal menambahkan data: " + e.getMessage());
        }
    }
}
```

**🖨️ Output (di konsol):**

```text
Berhasil menambahkan data ke file.
```

> 📌 **Catatan**: Parameter `true` pada `FileWriter` mengaktifkan mode *append*. Tanpa parameter ini, file akan ditimpa.

## 📄 Memeriksa Keberadaan File

Kelas `File` digunakan untuk mengelola informasi file dan folder, seperti memeriksa keberadaan file.

### Contoh:

```java
import java.io.File;

public class CekFileDemo {
    public static void main(String[] args) {
        File file = new File("data.txt");
        if (file.exists()) {
            System.out.println("File ditemukan: " + file.getAbsolutePath());
        } else {
            System.out.println("File tidak ada.");
        }
    }
}
```

**🖨️ Output (jika file ada):**

```text
File ditemukan: /path/to/data.txt
```

## 📂 Membuat Folder

Kelas `File` juga dapat digunakan untuk membuat direktori baru.

### Contoh:

```java
import java.io.File;

public class BuatFolderDemo {
    public static void main(String[] args) {
        File folder = new File("rekap");
        if (!folder.exists()) {
            if (folder.mkdir()) {
                System.out.println("Folder 'rekap' berhasil dibuat.");
            } else {
                System.out.println("Gagal membuat folder.");
            }
        } else {
            System.out.println("Folder sudah ada.");
        }
    }
}
```

**🖨️ Output (jika folder belum ada):**

```text
Folder 'rekap' berhasil dibuat.
```

## ⚠️ Exception Umum dalam File I/O

Operasi File I/O sering kali memicu *exception* yang perlu ditangani:

| **Exception**            | **Penyebab**                              |
|--------------------------|------------------------------------------|
| `FileNotFoundException`  | File tidak ditemukan atau tidak dapat diakses. |
| `IOException`            | Error umum I/O, seperti masalah izin atau kegagalan perangkat. |

> 💡 **Tips**: Selalu tangani *exception* dengan try-catch dan gunakan try-with-resources untuk menutup sumber daya secara otomatis.

## 🧪 Studi Kasus: Menyimpan Daftar Pekerja ke File

Berikut adalah contoh penggunaan File I/O untuk menyimpan daftar nama pekerja ke file teks dan membacanya kembali.

```java
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class PekerjaFileDemo {
    public static void main(String[] args) {
        // Menulis daftar pekerja ke file
        try (BufferedWriter writer = new BufferedWriter(new FileWriter("pekerja.txt"))) {
            writer.write("Ali");
            writer.newLine();
            writer.write("Budi");
            writer.newLine();
            writer.write("Cici");
            writer.newLine();
            System.out.println("Data pekerja berhasil disimpan.");
        } catch (IOException e) {
            System.out.println("Gagal menyimpan: " + e.getMessage());
        }

        // Membaca daftar pekerja dari file
        try (BufferedReader reader = new BufferedReader(new FileReader("pekerja.txt"))) {
            System.out.println("Daftar pekerja:");
            String baris;
            int nomor = 1;
            while ((baris = reader.readLine()) != null) {
                System.out.printf("%d. %s%n", nomor++, baris);
            }
        } catch (IOException e) {
            System.out.println("Gagal membaca: " + e.getMessage());
        }
    }
}
```

**🖨️ Output:**

```text
Data pekerja berhasil disimpan.
Daftar pekerja:
1. Ali
2. Budi
3. Cici
```

**Isi file pekerja.txt:**

```text
Ali
Budi
Cici
```

## 📌 Kesimpulan

File I/O adalah alat penting untuk menyimpan dan mengambil data dari file:

| **Konsep**         | **Penjelasan**                                      |
|--------------------|----------------------------------------------------|
| **`FileReader`**   | Membaca karakter demi karakter dari file.          |
| **`BufferedReader`**| Membaca per baris dengan buffer untuk efisiensi.   |
| **`FileWriter`**   | Menulis karakter demi karakter ke file.            |
| **`BufferedWriter`**| Menulis dengan buffer untuk efisiensi.             |
| **`File`**         | Mengelola file dan folder (misalnya, cek keberadaan, buat folder). |

> 🎯 **Tujuan Utama**: File I/O memungkinkan program untuk berinteraksi dengan sistem file, menyimpan data secara permanen, dan mengambil data untuk pemrosesan.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Enum (Konstanta Bertipe Kelas)](enum.md) untuk memahami cara mendefinisikan konstanta dengan tipe data khusus di Java.

⬅️ Kembali: [HashMap dalam Java](hashmap.md)