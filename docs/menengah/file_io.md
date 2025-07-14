# 📁 File I/O (Input dan Output File) dalam Java

Java menyediakan API lengkap untuk membaca dan menulis file, baik teks maupun biner.

---

## 📥 Membaca File Teks

### 1. Menggunakan `BufferedReader`

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class BacaFile {
    public static void main(String[] args) {
        try {
            BufferedReader reader = new BufferedReader(new FileReader("data.txt"));
            String baris;
            while ((baris = reader.readLine()) != null) {
                System.out.println(baris);
            }
            reader.close();
        } catch (IOException e) {
            System.out.println("Gagal membaca file: " + e.getMessage());
        }
    }
}
````

---

## 📝 Menulis ke File

### 2. Menggunakan `BufferedWriter`

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class TulisFile {
    public static void main(String[] args) {
        try {
            BufferedWriter writer = new BufferedWriter(new FileWriter("output.txt"));
            writer.write("Data panen berhasil dicatat.");
            writer.newLine();
            writer.write("Total berat: 1234 kg");
            writer.close();
            System.out.println("Berhasil menulis file.");
        } catch (IOException e) {
            System.out.println("Gagal menulis file: " + e.getMessage());
        }
    }
}
```

---

## 🔄 Append (Menambahkan Tanpa Menimpa)

Gunakan `new FileWriter("nama.txt", true)` untuk menambahkan isi tanpa menimpa:

```java
BufferedWriter writer = new BufferedWriter(new FileWriter("log.txt", true));
```

---

## 📄 Cek Apakah File Ada

```java
import java.io.File;

File file = new File("data.txt");

if (file.exists()) {
    System.out.println("File ditemukan!");
} else {
    System.out.println("File tidak ada.");
}
```

---

## 📂 Membuat Folder

```java
File folder = new File("rekap/");
if (!folder.exists()) {
    folder.mkdir();
}
```

---

## ⚠️ Exception yang Umum

| Exception               | Penyebab                           |
| ----------------------- | ---------------------------------- |
| `FileNotFoundException` | File tidak ditemukan               |
| `IOException`           | Error umum I/O (akses, permission) |

---

## 🧪 Studi Kasus: Simpan Nama Pekerja ke File

```java
import java.io.FileWriter;
import java.io.IOException;

public class SimpanPekerja {
    public static void main(String[] args) {
        try {
            FileWriter fw = new FileWriter("pekerja.txt");
            fw.write("Ali\nBudi\nCici");
            fw.close();
            System.out.println("Data pekerja disimpan.");
        } catch (IOException e) {
            System.out.println("Gagal menyimpan: " + e.getMessage());
        }
    }
}
```

---

## 📌 Kesimpulan

| Konsep         | Penjelasan                           |
| -------------- | ------------------------------------ |
| FileReader     | Membaca file karakter per karakter   |
| BufferedReader | Membaca per baris, lebih efisien     |
| FileWriter     | Menulis file karakter per karakter   |
| BufferedWriter | Menulis dengan buffer, lebih efisien |
| File           | Mengelola info dasar file dan folder |

---

➡️ Selanjutnya: [Enum (Konstanta Bertipe Kelas)](enum.md)