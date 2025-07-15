---
title: Operator dan Ekspresi dalam Java
description: Memahami jenis-jenis operator di Java dan cara menggunakannya untuk membentuk ekspresi
---

# ➕ Operator dan Ekspresi dalam Java

**Operator** adalah simbol atau kata kunci yang digunakan untuk melakukan operasi terhadap variabel atau nilai dalam Java. **Ekspresi** adalah kombinasi dari variabel, nilai, dan operator yang menghasilkan nilai baru. Bagian ini menjelaskan jenis-jenis operator utama di Java dan cara penggunaannya dalam program.

## 🎛️ Jenis-Jenis Operator di Java

Java menyediakan beberapa kategori operator untuk berbagai keperluan, mulai dari operasi matematika hingga logika.

### 1. 🧮 Operator Aritmatika

Operator aritmatika digunakan untuk operasi matematika dasar.

| **Operator** | **Nama**           | **Contoh** (`a = 10`, `b = 3`) | **Hasil** |
|--------------|--------------------|--------------------------------|-----------|
| `+`          | Penjumlahan        | `a + b`                        | `13`      |
| `-`          | Pengurangan        | `a - b`                        | `7`       |
| `*`          | Perkalian          | `a * b`                        | `30`      |
| `/`          | Pembagian          | `a / b`                        | `3`       |
| `%`          | Modulo (sisa bagi) | `a % b`                        | `1`       |

> 💡 **Tips**: Operator modulo (`%`) sering digunakan untuk mengecek bilangan genap/ganjil. Contoh: `if (x % 2 == 0)` untuk mengecek bilangan genap.

### 2. ⚖️ Operator Perbandingan (Relasional)

Operator perbandingan digunakan untuk membandingkan dua nilai dan menghasilkan nilai boolean (`true` atau `false`).

| **Operator** | **Arti**                   | **Contoh** (`a = 10`, `b = 3`) |
|--------------|----------------------------|--------------------------------|
| `==`         | Sama dengan                | `a == b` → `false`             |
| `!=`         | Tidak sama dengan          | `a != b` → `true`              |
| `>`          | Lebih besar                | `a > b` → `true`               |
| `<`          | Lebih kecil                | `a < b` → `false`              |
| `>=`         | Lebih besar atau sama dengan| `a >= b` → `true`              |
| `<=`         | Lebih kecil atau sama dengan| `a <= b` → `false`             |

### 3. 💡 Operator Logika (Boolean)

Operator logika digunakan untuk menggabungkan ekspresi boolean, sering digunakan dalam struktur seperti `if` atau `while`.

| **Operator** | **Nama** | **Contoh**               | **Hasil** |
|--------------|----------|--------------------------|-----------|
| `&&`         | AND      | `true && false`          | `false`   |
| `||`         | OR       | `true || false`          | `true`    |
| `!`          | NOT      | `!true`                  | `false`   |

> 📌 **Catatan**: Operator `&&` hanya mengembalikan `true` jika kedua kondisi benar, sedangkan `||` mengembalikan `true` jika salah satu kondisi benar.

### 4. 🖊️ Operator Penugasan

Operator penugasan digunakan untuk menetapkan atau memperbarui nilai variabel.

| **Operator** | **Contoh**     | **Sama Dengan**         |
|--------------|----------------|-------------------------|
| `=`          | `x = 5`        | Menetapkan 5 ke `x`     |
| `+=`         | `x += 2`       | `x = x + 2`             |
| `-=`         | `x -= 2`       | `x = x - 2`             |
| `*=`         | `x *= 2`       | `x = x * 2`             |
| `/=`         | `x /= 2`       | `x = x / 2`             |
| `%=`         | `x %= 2`       | `x = x % 2`             |

### 5. ⬆️ Operator Inkrement dan Dekrement

Operator inkrement dan dekrement digunakan untuk menambah atau mengurangi nilai variabel sebesar 1.

| **Operator** | **Contoh** | **Efek**                     |
|--------------|------------|------------------------------|
| `++`         | `x++`      | Menambah `x` sebesar 1       |
| `--`         | `x--`      | Mengurangi `x` sebesar 1     |

> 💡 **Info**:  
> - `x++` (post-increment) mengembalikan nilai `x` sebelum ditambah.  
> - `++x` (pre-increment) mengembalikan nilai `x` setelah ditambah.  
> Contoh: Jika `x = 5`, maka `System.out.println(x++)` mencetak `5`, tetapi `System.out.println(++x)` mencetak `6`.

## 🧪 Contoh Program

Berikut adalah contoh program yang menggunakan berbagai jenis operator:

```java
public class OperatorDemo {
    public static void main(String[] args) {
        int a = 10, b = 3;
        boolean hasil;

        // Operator Aritmatika
        System.out.println("a + b = " + (a + b)); // Penjumlahan
        System.out.println("a % b = " + (a % b)); // Modulo

        // Operator Perbandingan
        System.out.println("a > b = " + (a > b)); // Lebih besar

        // Operator Logika
        hasil = (a > 5) && (b < 5);
        System.out.println("Logika AND (a > 5 && b < 5): " + hasil);

        // Operator Penugasan
        int x = 5;
        x += 3;
        System.out.println("x setelah += 3: " + x);

        // Operator Inkrement
        x++;
        System.out.println("x setelah x++: " + x);
    }
}
```

**🖨️ Output:**

```text
a + b = 13
a % b = 1
a > b = true
Logika AND (a > 5 && b < 5): true
x setelah += 3: 8
x setelah x++: 9
```

## 📌 Kesimpulan

- Java menyediakan berbagai jenis operator: **aritmatika**, **perbandingan**, **logika**, **penugasan**, dan **inkrement/dekrement**.
- Operator digunakan untuk membentuk **ekspresi** yang menghasilkan nilai baru.
- Pemahaman operator penting untuk memanipulasi data dan membuat logika dalam program.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Kontrol Alur: If, Else, dan Switch](kontrol_alur.md) untuk memahami cara mengatur alur program berdasarkan kondisi.