# 🛠️ Persiapan Lingkungan Pemrograman Java

Sebelum mulai menulis kode Java, kita perlu menyiapkan **lingkungan pengembangan** yang meliputi:

1. Instalasi JDK (Java Development Kit)
2. Instalasi IDE (Integrated Development Environment)
3. Uji Coba Jalankan Program Pertama

---

## 1. ✅ Instalasi JDK (Java Development Kit)

JDK adalah paket perangkat lunak yang berisi compiler, JVM (Java Virtual Machine), dan tools lainnya.

### 🔽 Unduh JDK
- **Oracle JDK** (resmi):  
  [https://www.oracle.com/java/technologies/javase-downloads.html](https://www.oracle.com/java/technologies/javase-downloads.html)
  
- **Alternatif Open Source (lebih ringan)**:  
  - [Adoptium (OpenJDK)](https://adoptium.net/)
  - [Amazon Corretto](https://aws.amazon.com/corretto/)

> 💡 Gunakan **JDK versi 17 atau lebih baru** untuk stabilitas dan fitur terkini.

### 🖥️ Cara Instal (Windows/Mac/Linux)

- **Windows**:  
  Unduh file `.exe`, lalu jalankan seperti instalasi biasa. Setelah itu, tambahkan JDK ke `PATH`.

- **Linux (Ubuntu)**:
  ```bash
  sudo apt update
  sudo apt install openjdk-17-jdk
````

* **MacOS**:
  Gunakan [Homebrew](https://brew.sh/)

  ```bash
  brew install openjdk@17
  ```

### 🔍 Verifikasi Instalasi

Cek apakah Java sudah terinstal:

```bash
java -version
```

---

## 2. 💻 Instalasi IDE (Editor Kode)

Agar lebih mudah menulis dan menjalankan Java, kita gunakan IDE.

### Rekomendasi IDE:

| IDE               | Keterangan                         |
| ----------------- | ---------------------------------- |
| **IntelliJ IDEA** | Powerful, lengkap, dan smart       |
| **Eclipse**       | Ringan dan fleksibel               |
| **VS Code**       | Modern, butuh plugin tambahan Java |
| **NetBeans**      | Sudah built-in Java GUI support    |

> 💡 Untuk pemula: **IntelliJ IDEA Community Edition** sangat direkomendasikan.

---

## 3. 🧪 Menjalankan Program Pertama

Buat file `HelloWorld.java`:

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Halo, dunia!");
    }
}
```

### Kompilasi & Jalankan

```bash
javac HelloWorld.java   # Kompilasi
java HelloWorld         # Jalankan
```

Jika berhasil, akan muncul:

```
Halo, dunia!
```

---

## 📝 Tips Tambahan

* Gunakan **folder khusus** untuk proyek Java-mu.
* Simpan file dengan nama yang sama seperti kelasnya (`HelloWorld.java` untuk `class HelloWorld`)
* Jangan takut membuat kesalahan — debugging adalah bagian dari proses belajar!

---

## 🎉 Siap Belajar Java!

Sekarang kamu sudah siap menulis dan menjalankan program Java. Mari lanjut ke materi pertama: **[Struktur Dasar Program Java](dasar/struktur.md)**

➡️ [Lanjut ke Struktur Program Java](dasar/struktur.md)