# 📦 Package & Import dalam Java

Dalam Java, package digunakan untuk **mengelompokkan class-class terkait** agar proyek lebih rapi dan modular.

Mirip seperti folder dalam komputer, package menyimpan class sesuai kategori atau fungsinya.

---

## 🧱 Apa Itu Package?

```java
package nama_package;
````

Didefinisikan di **baris pertama file Java**, sebelum deklarasi class.

Contoh:

```java
package utils;

public class Kalkulator {
    public int tambah(int a, int b) {
        return a + b;
    }
}
```

---

## 🛠️ Struktur Direktori Package

Jika kita punya:

```
project/
├── Main.java
└── utils/
    └── Kalkulator.java
```

Isi `Kalkulator.java`:

```java
package utils;

public class Kalkulator {
    public int kali(int a, int b) {
        return a * b;
    }
}
```

Isi `Main.java`:

```java
import utils.Kalkulator;

public class Main {
    public static void main(String[] args) {
        Kalkulator k = new Kalkulator();
        System.out.println("Hasil: " + k.kali(4, 5));
    }
}
```

💡 Output:

```
Hasil: 20
```

---

## 📥 Import: Menggunakan Class dari Package Lain

```java
import nama_package.NamaClass;
```

Contoh:

```java
import java.util.Scanner;
```

Gunakan `import java.util.*;` untuk mengimpor semua class dari package tersebut.

---

## 📦 Package Bawaan Java (`java.*`)

| Package     | Deskripsi                          |
| ----------- | ---------------------------------- |
| `java.lang` | Class dasar (String, Math, Object) |
| `java.util` | Struktur data (ArrayList, HashMap) |
| `java.io`   | Input/Output stream                |
| `java.net`  | Networking                         |
| `java.time` | Tanggal dan waktu (Java 8+)        |

---

## 🏗️ Membuat Package Kustom

```bash
mkdir utils
touch utils/Kalkulator.java
```

Isi file:

```java
package utils;

public class Kalkulator {
    public static int tambah(int a, int b) {
        return a + b;
    }
}
```

---

## ⚙️ Kompilasi dan Jalankan Program dengan Package

```bash
javac utils/Kalkulator.java
javac Main.java
java Main
```

Jika package berada di dalam folder lain, gunakan `-cp` (classpath).

---

## 📌 Kesimpulan

| Konsep        | Penjelasan                                                   |
| ------------- | ------------------------------------------------------------ |
| Package       | Cara Java mengorganisasi class ke dalam folder               |
| Import        | Digunakan untuk memakai class dari package lain              |
| Best Practice | Gunakan nama unik seperti `com.nama.app` untuk project besar |

---

➡️ Selanjutnya: [Exception Handling (Penanganan Error)](exception_handling.md)