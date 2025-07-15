---
title: Perulangan (Loop) dalam Java
description: Memahami jenis-jenis perulangan di Java seperti for, while, do-while, serta penggunaan break dan continue
---

# 🔁 Perulangan (Loop) dalam Java

Perulangan memungkinkan eksekusi **blok kode secara berulang** selama kondisi tertentu terpenuhi. Java menyediakan tiga jenis perulangan utama: `for`, `while`, dan `do-while`. Selain itu, terdapat mekanisme seperti `break`, `continue`, dan perulangan bersarang untuk mengontrol alur perulangan.

## 1. 🔃 Perulangan `for`

Perulangan `for` digunakan ketika **jumlah iterasi sudah diketahui** sebelumnya.

### Struktur:

```java
for (inisialisasi; kondisi; perubahan) {
    // Blok kode yang diulang
}
```

- **Inisialisasi**: Menyiapkan variabel pengontrol (misalnya, `int i = 1`).
- **Kondisi**: Mengevaluasi apakah perulangan harus dilanjutkan (misalnya, `i <= 5`).
- **Perubahan**: Memperbarui nilai variabel pengontrol (misalnya, `i++`).

### Contoh:

```java
for (int i = 1; i <= 5; i++) {
    System.out.println("Iterasi ke-" + i);
}
```

**🖨️ Output:**

```text
Iterasi ke-1
Iterasi ke-2
Iterasi ke-3
Iterasi ke-4
Iterasi ke-5
```

## 2. ♻️ Perulangan `while`

Perulangan `while` digunakan ketika **jumlah iterasi tidak diketahui** secara pasti, tetapi perulangan berlanjut selama kondisi tertentu terpenuhi.

### Struktur:

```java
while (kondisi) {
    // Blok kode yang diulang
}
```

### Contoh:

```java
int i = 1;
while (i <= 3) {
    System.out.println("i = " + i);
    i++;
}
```

**🖨️ Output:**

```text
i = 1
i = 2
i = 3
```

> 📌 **Catatan**: Pastikan kondisi dalam `while` akan berhenti pada suatu titik untuk menghindari *infinite loop*.

## 3. 🔄 Perulangan `do-while`

Perulangan `do-while` **menjalankan blok kode minimal satu kali** sebelum memeriksa kondisi.

### Struktur:

```java
do {
    // Blok kode yang diulang
} while (kondisi);
```

### Contoh:

```java
int i = 1;
do {
    System.out.println("Cetak ke-" + i);
    i++;
} while (i <= 2);
```

**🖨️ Output:**

```text
Cetak ke-1
Cetak ke-2
```

> 💡 **Info**: Perulangan `do-while` cocok untuk kasus di mana kode harus dijalankan setidaknya sekali, seperti meminta input pengguna hingga valid.

## 4. 🔂 Perulangan Bersarang (Nested Loop)

Perulangan bersarang adalah perulangan di dalam perulangan lain. Biasanya digunakan untuk pola data kompleks, seperti tabel atau matriks.

### Contoh:

```java
for (int i = 1; i <= 3; i++) {
    for (int j = 1; j <= 2; j++) {
        System.out.println("i = " + i + ", j = " + j);
    }
}
```

**🖨️ Output:**

```text
i = 1, j = 1
i = 1, j = 2
i = 2, j = 1
i = 2, j = 2
i = 3, j = 1
i = 3, j = 2
```

## 5. ⛔ Pengendalian Perulangan: `break` dan `continue`

### `break`

Perintah `break` **menghentikan perulangan sepenuhnya** saat kondisi tertentu terpenuhi.

```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) {
        break;
    }
    System.out.println("i = " + i);
}
```

**🖨️ Output:**

```text
i = 1
i = 2
```

### `continue`

Perintah `continue` **melewati iterasi saat ini** dan melanjutkan ke iterasi berikutnya.

```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) {
        continue;
    }
    System.out.println("i = " + i);
}
```

**🖨️ Output:**

```text
i = 1
i = 2
i = 4
i = 5
```

## 🧪 Studi Kasus: Menjumlahkan 5 Bilangan

Berikut adalah contoh program untuk menjumlahkan bilangan dari 1 hingga 5 menggunakan perulangan `for`:

```java
public class JumlahBilangan {
    public static void main(String[] args) {
        int total = 0;
        for (int i = 1; i <= 5; i++) {
            total += i;
        }
        System.out.println("Total = " + total);
    }
}
```

**🖨️ Output:**

```text
Total = 15
```

## 📌 Kesimpulan

Perulangan adalah alat penting dalam pemrograman untuk menjalankan kode berulang kali. Berikut adalah ringkasan jenis perulangan di Java:

| **Jenis Perulangan** | **Kapan Digunakan**                           |
|----------------------|-----------------------------------------------|
| `for`                | Jumlah iterasi diketahui sebelumnya           |
| `while`              | Jumlah iterasi tidak diketahui pasti          |
| `do-while`           | Blok kode dijalankan minimal satu kali        |
| `break`              | Menghentikan perulangan sepenuhnya            |
| `continue`           | Melewati satu iterasi dan melanjutkan lainnya |

> 💡 **Tips**: Gunakan perulangan yang sesuai dengan kebutuhan program Anda untuk menjaga kode tetap efisien dan mudah dibaca.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Method dan Parameter dalam Java](method.md) untuk memahami cara membuat fungsi dalam program.