# 🧱 Struktur Dasar Program Java

Sebelum membangun aplikasi besar, mari kuasai dulu *fondasi* dari program Java.


## 🔍 Contoh Program Java Paling Sederhana

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Halo, dunia!");
    }
}
````

🖨️ Output:

```text
Halo, dunia!
```

## 🧩 Penjelasan Baris per Baris

### ✅ 1. `public class HelloWorld`

* `class` → mendefinisikan sebuah kelas (*wadah utama* dalam Java)
* `HelloWorld` → nama kelas (**harus sama dengan nama file**)
* `public` → kelas dapat diakses dari mana saja

> 📌 **Catatan:**
> Satu file `.java` hanya boleh memiliki **satu `public class`**, dan nama filenya **harus sama** dengan nama kelasnya.

### ✅ 2. `public static void main(String[] args)`

* `public` → bisa dipanggil dari luar
* `static` → dapat dijalankan tanpa membuat objek
* `void` → tidak mengembalikan nilai
* `main` → titik masuk program (entry point)
* `String[] args` → parameter dari command line

> 💬 *Tanpa method `main()`, program Java tidak akan bisa dijalankan.*

### ✅ 3. `System.out.println("Halo, dunia!");`

* `System` → kelas utilitas Java untuk sistem standar
* `out` → output standar (biasanya ke layar)
* `println()` → mencetak teks dan membuat baris baru

---

## 📁 Struktur File & Folder

```
BelajarJava/
└── HelloWorld.java
```

---

## 🛠️ Cara Kompilasi & Menjalankan Program

### 🧱 1. Kompilasi Program

```bash
javac HelloWorld.java
```

📦 Output: File `HelloWorld.class` akan terbentuk jika tidak ada error.

### ▶️ 2. Jalankan Program

```bash
java HelloWorld
```

---

## ⚠️ Hal-Hal yang Wajib Diingat

| ⚙️ Hal Penting                                        | 💡 Penjelasan                                 |
| ----------------------------------------------------- | --------------------------------------------- |
| Nama file = nama kelas `public`                       | `HelloWorld.java` → `public class HelloWorld` |
| Java bersifat **case-sensitive**                      | `HelloWorld` ≠ `helloworld`                   |
| Setiap statement diakhiri dengan **titik koma (`;`)** | Seperti tanda titik dalam kalimat             |
| Blok kode dibuka `{` dan ditutup `}`                  | Harus seimbang, jangan ada yang tertinggal    |

---

## 🧭 Kesimpulan

Struktur dasar program Java selalu terdiri dari:

✅ Satu **kelas** (`class`)
✅ Satu method utama **`main()`**
✅ Satu atau lebih **statement** di dalamnya, misalnya:

```java
System.out.println("Halo, dunia!");
```

---

📚 Selanjutnya → [Tipe Data & Variabel](tipe_data.md)