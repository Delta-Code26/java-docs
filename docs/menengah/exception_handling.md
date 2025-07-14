# 🛑 Exception Handling (Penanganan Error) dalam Java

Tidak semua program berjalan mulus. Error bisa terjadi karena:
- Input tidak valid
- File tidak ditemukan
- Pembagian oleh nol
- Koneksi gagal
- Dan lainnya...

Untuk itulah Java menyediakan mekanisme **exception handling** agar error bisa **ditangani dengan elegan** — bukan bikin program langsung crash.

---

## 🧠 Apa Itu Exception?

Exception adalah kondisi **tidak normal** yang terjadi saat program berjalan (*runtime error*), dan bisa **ditangkap serta ditangani**.

Contoh:
```java
int a = 5 / 0; // ArithmeticException
````

---

## 🧱 Struktur Dasar try-catch

```java
try {
    // kode yang berpotensi error
} catch (ExceptionTipe e) {
    // penanganan error
}
```

Contoh:

```java
public class Demo {
    public static void main(String[] args) {
        try {
            int a = 5 / 0;
        } catch (ArithmeticException e) {
            System.out.println("Terjadi kesalahan: " + e.getMessage());
        }
    }
}
```

💡 Output:

```
Terjadi kesalahan: / by zero
```

---

## 🔁 Blok finally

`finally` akan **selalu dieksekusi**, baik ada exception maupun tidak. Cocok untuk:

* Menutup file
* Melepas koneksi
* Membersihkan resource

```java
try {
    int[] data = {1, 2};
    System.out.println(data[5]);
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Index error!");
} finally {
    System.out.println("Selesai.");
}
```

---

## 🎯 Multiple Catch

Menangkap lebih dari satu tipe exception:

```java
try {
    String s = null;
    System.out.println(s.length());
} catch (ArithmeticException e) {
    System.out.println("Error matematika");
} catch (NullPointerException e) {
    System.out.println("Null error");
}
```

---

## 🎯 Menggunakan `throw`

Digunakan untuk **melempar exception secara manual**:

```java
throw new IllegalArgumentException("Umur tidak boleh negatif");
```

---

## 🎯 Menggunakan `throws`

Digunakan untuk **mendeklarasikan** bahwa method bisa melempar exception:

```java
void bacaFile() throws IOException {
    FileReader fr = new FileReader("data.txt");
}
```

---

## 📚 Hierarki Exception Java

```
Throwable
├── Error (tidak perlu ditangani)
└── Exception
    ├── CheckedException  (harus ditangani)
    └── UncheckedException (boleh ditangani)
```

| Jenis              | Contoh                                    | Harus ditangani? |
| ------------------ | ----------------------------------------- | ---------------- |
| CheckedException   | IOException, SQLException                 | ✅ Ya             |
| UncheckedException | NullPointerException, ArithmeticException | ❌ Opsional       |

---

## 🧪 Studi Kasus: Validasi Umur

```java
class Mahasiswa {
    void setUmur(int umur) {
        if (umur < 0) {
            throw new IllegalArgumentException("Umur tidak boleh negatif");
        }
        System.out.println("Umur: " + umur);
    }
}
```

---

## 📌 Kesimpulan

| Konsep    | Penjelasan                              |
| --------- | --------------------------------------- |
| try-catch | Menangkap dan menangani error           |
| finally   | Eksekusi wajib (cleanup)                |
| throw     | Melempar error secara manual            |
| throws    | Mendeklarasikan bahwa method bisa error |
| Exception | Objek kesalahan yang bisa ditangani     |

---

➡️ Selanjutnya: [Array dan ArrayList](array_list.md)