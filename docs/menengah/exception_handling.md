---
title: Exception Handling (Penanganan Error) dalam Java
description: Memahami cara menangani error menggunakan try-catch, finally, throw, dan throws di Java
---

# 🛑 Exception Handling (Penanganan Error) dalam Java

**Exception handling** adalah mekanisme di Java untuk menangani **error saat runtime** (seperti pembagian oleh nol, file tidak ditemukan, atau input tidak valid) agar program tetap berjalan dengan elegan tanpa *crash*. Dengan exception handling, Anda dapat mendeteksi, menangani, dan memberikan respons yang sesuai untuk kondisi tidak normal.

### Tujuan Exception Handling
- **Mencegah Crash**: Menangani error tanpa menghentikan program.
- **Memberikan Informasi**: Memberikan pesan error yang jelas untuk debugging.
- **Membersihkan Sumber Daya**: Memastikan file atau koneksi ditutup dengan benar.

## 🧠 Apa Itu Exception?

**Exception** adalah objek yang mewakili kondisi tidak normal yang terjadi saat program berjalan (*runtime error*). Exception dapat ditangkap dan ditangani menggunakan blok `try-catch`.

### Contoh Exception:

```java
public class ExceptionDemo {
    public static void main(String[] args) {
        int a = 5 / 0; // ArithmeticException: / by zero
    }
}
```

**🖨️ Output (tanpa penanganan):**

```text
Exception in thread "main" java.lang.ArithmeticException: / by zero
```

## 🧱 Struktur Dasar Try-Catch

Blok `try-catch` digunakan untuk menangkap dan menangani exception.

### Sintaks:

```java
try {
    // Kode yang berpotensi menyebabkan error
} catch (ExceptionTipe e) {
    // Penanganan error
}
```

### Contoh:

```java
public class TryCatchDemo {
    public static void main(String[] args) {
        try {
            int a = 5 / 0;
        } catch (ArithmeticException e) {
            System.out.println("Terjadi kesalahan: " + e.getMessage());
        }
    }
}
```

**🖨️ Output:**

```text
Terjadi kesalahan: / by zero
```

## 🔁 Blok Finally

Blok `finally` selalu dieksekusi, baik terjadi exception maupun tidak. Ini cocok untuk *cleanup* sumber daya, seperti menutup file atau koneksi.

### Contoh:

```java
public class FinallyDemo {
    public static void main(String[] args) {
        try {
            int[] data = {1, 2};
            System.out.println(data[5]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Error: Indeks di luar batas!");
        } finally {
            System.out.println("Blok finally dieksekusi.");
        }
    }
}
```

**🖨️ Output:**

```text
Error: Indeks di luar batas!
Blok finally dieksekusi.
```

> 💡 **Tips**: Gunakan `try-with-resources` untuk menangani sumber daya (seperti file) secara otomatis, mengurangi kebutuhan blok `finally`.

## 🎯 Multiple Catch

Untuk menangani beberapa tipe exception, gunakan beberapa blok `catch`. Urutkan dari exception yang lebih spesifik ke yang lebih umum.

### Contoh:

```java
public class MultipleCatchDemo {
    public static void main(String[] args) {
        try {
            String s = null;
            System.out.println(s.length());
        } catch (NullPointerException e) {
            System.out.println("Error: Objek null!");
        } catch (Exception e) {
            System.out.println("Error umum: " + e.getMessage());
        }
    }
}
```

**🖨️ Output:**

```text
Error: Objek null!
```

> 📌 **Catatan**: Letakkan `Exception` (tipe umum) di akhir, karena exception spesifik seperti `NullPointerException` harus ditangkap terlebih dahulu.

## 🎯 Melempar Exception dengan `throw`

Gunakan `throw` untuk melempar exception secara manual, misalnya untuk memvalidasi input.

### Contoh:

```java
public class ThrowDemo {
    public static void main(String[] args) {
        try {
            validateAge(-5);
        } catch (IllegalArgumentException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }

    static void validateAge(int age) {
        if (age < 0) {
            throw new IllegalArgumentException("Umur tidak boleh negatif");
        }
        System.out.println("Umur valid: " + age);
    }
}
```

**🖨️ Output:**

```text
Error: Umur tidak boleh negatif
```

## 🎯 Mendeklarasikan Exception dengan `throws`

Gunakan `throws` di deklarasi method untuk menunjukkan bahwa method dapat melempar exception tertentu, yang harus ditangani oleh pemanggil.

### Contoh:

```java
import java.io.FileReader;
import java.io.IOException;

public class ThrowsDemo {
    public static void main(String[] args) {
        try {
            bacaFile("data.txt");
        } catch (IOException e) {
            System.out.println("Gagal membaca file: " + e.getMessage());
        }
    }

    static void bacaFile(String path) throws IOException {
        FileReader fr = new FileReader(path);
        fr.close();
    }
}
```

**🖨️ Output (jika file tidak ada):**

```text
Gagal membaca file: data.txt (No such file or directory)
```

## 📚 Hierarki Exception di Java

Semua exception di Java berasal dari kelas `Throwable`, yang terbagi menjadi dua kategori:

```
Throwable
├── Error (tidak perlu ditangani, misalnya OutOfMemoryError)
└── Exception
    ├── Checked Exception (harus ditangani, misalnya IOException)
    └── Unchecked Exception (opsional ditangani, misalnya NullPointerException)
```

### Perbandingan:

| **Jenis**            | **Contoh**                            | **Harus Ditangani?** |
|----------------------|---------------------------------------|----------------------|
| **Checked Exception**| `IOException`, `SQLException`         | ✅ Ya                 |
| **Unchecked Exception**| `NullPointerException`, `ArithmeticException` | ❌ Opsional       |

> 💡 **Tips**: Checked exception memerlukan penanganan eksplisit dengan `try-catch` atau deklarasi `throws`, sedangkan unchecked exception opsional.

## 🧪 Studi Kasus: Validasi Umur Mahasiswa

Berikut adalah contoh penggunaan exception handling untuk memvalidasi umur mahasiswa dan menangani error file dengan `try-with-resources`.

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class MahasiswaDemo {
    public static void main(String[] args) {
        try {
            Mahasiswa mhs = new Mahasiswa();
            mhs.setUmur(-5); // Akan memicu exception
        } catch (IllegalArgumentException e) {
            System.out.println("Error: " + e.getMessage());
        }

        // Menyimpan log ke file
        try (BufferedWriter writer = new BufferedWriter(new FileWriter("log.txt"))) {
            writer.write("Validasi umur selesai.");
            writer.newLine();
            System.out.println("Log berhasil disimpan.");
        } catch (IOException e) {
            System.out.println("Gagal menyimpan log: " + e.getMessage());
        }
    }
}

class Mahasiswa {
    private int umur;

    public void setUmur(int umur) {
        if (umur < 0) {
            throw new IllegalArgumentException("Umur tidak boleh negatif");
        }
        this.umur = umur;
        System.out.println("Umur diatur ke: " + umur);
    }
}
```

**🖨️ Output:**

```text
Error: Umur tidak boleh negatif
Log berhasil disimpan.
```

**Isi file log.txt:**

```text
Validasi umur selesai.
```

## 📌 Kesimpulan

Exception handling adalah alat penting untuk membuat program lebih robust:

| **Konsep**     | **Penjelasan**                                     |
|----------------|---------------------------------------------------|
| **`try-catch`** | Menangkap dan menangani exception.                |
| **`finally`**   | Eksekusi wajib untuk *cleanup* sumber daya.       |
| **`throw`**     | Melempar exception secara manual.                |
| **`throws`**    | Mendeklarasikan exception yang mungkin dilempar.  |
| **Exception**   | Objek yang mewakili error saat runtime.           |

> 🎯 **Tujuan Utama**: Exception handling memungkinkan program untuk menangani error dengan aman, memberikan informasi yang jelas, dan memastikan pembersihan sumber daya.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Enum (Konstanta Bertipe Kelas)](enum.md) untuk memahami cara mendefinisikan konstanta dengan tipe data khusus di Java.

⬅️ Kembali: [File I/O (Input dan Output File)](file_io.md)