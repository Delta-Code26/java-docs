---
title: Kontrol Alur dalam Java (if, else, switch)
description: Memahami struktur kontrol alur seperti if, else, else if, dan switch untuk pengambilan keputusan dalam Java
---

# 🔀 Kontrol Alur dalam Java (if, else, switch)

**Kontrol alur** memungkinkan program Java membuat **keputusan** berdasarkan kondisi tertentu. Dengan struktur seperti `if`, `else`, `else if`, dan `switch`, program dapat mengeksekusi blok kode yang berbeda sesuai dengan logika yang ditentukan. Bagian ini menjelaskan cara menggunakan struktur kontrol alur untuk membuat program yang lebih dinamis dan responsif.

## 🧠 1. Pernyataan `if`

Pernyataan `if` mengeksekusi blok kode jika kondisi tertentu bernilai `true`.

### Struktur:

```java
if (kondisi) {
    // Kode dijalankan jika kondisi true
}
```

### Contoh:

```java
public class IfDemo {
    public static void main(String[] args) {
        int usia = 20;
        if (usia >= 18) {
            System.out.println("Anda sudah dewasa.");
        }
    }
}
```

**🖨️ Output:**

```text
Anda sudah dewasa.
```

## 🔀 2. Pernyataan `if-else`

Pernyataan `else` menangani kasus ketika kondisi `if` bernilai `false`.

### Struktur:

```java
if (kondisi) {
    // Kode dijalankan jika kondisi true
} else {
    // Kode dijalankan jika kondisi false
}
```

### Contoh:

```java
public class IfElseDemo {
    public static void main(String[] args) {
        int nilai = 55;
        if (nilai >= 60) {
            System.out.println("Lulus");
        } else {
            System.out.println("Tidak Lulus");
        }
    }
}
```

**🖨️ Output:**

```text
Tidak Lulus
```

## 🧱 3. Pernyataan `if-else if-else`

Pernyataan `else if` digunakan untuk mengevaluasi beberapa kondisi secara berurutan. Jika semua kondisi `if` dan `else if` bernilai `false`, blok `else` (jika ada) akan dijalankan.

### Struktur:

```java
if (kondisi1) {
    // Kode untuk kondisi1 true
} else if (kondisi2) {
    // Kode untuk kondisi2 true
} else {
    // Kode default jika semua kondisi false
}
```

### Contoh:

```java
public class IfElseIfDemo {
    public static void main(String[] args) {
        int nilai = 80;
        if (nilai >= 90) {
            System.out.println("Grade: A");
        } else if (nilai >= 80) {
            System.out.println("Grade: B");
        } else if (nilai >= 70) {
            System.out.println("Grade: C");
        } else {
            System.out.println("Grade: D");
        }
    }
}
```

**🖨️ Output:**

```text
Grade: B
```

## 🎛️ 4. Operator Logika dalam `if`

Operator logika seperti `&&` (AND), `||` (OR), dan `!` (NOT) digunakan untuk menggabungkan beberapa kondisi dalam pernyataan `if`.

| **Operator** | **Fungsi** | **Contoh**                  | **Hasil**          |
|--------------|------------|-----------------------------|--------------------|
| `&&`         | AND        | `(x > 10 && x < 20)`       | `true` jika keduanya benar |
| `||`         | OR         | `(x < 5 || x > 15)`        | `true` jika salah satu benar |
| `!`          | NOT        | `!true`                    | `false`            |

### Contoh:

```java
public class LogicalOperatorDemo {
    public static void main(String[] args) {
        int x = 15;
        if (x > 10 && x < 20) {
            System.out.println("x berada di antara 10 dan 20");
        }
    }
}
```

**🖨️ Output:**

```text
x berada di antara 10 dan 20
```

## 🎚️ 5. Pernyataan `switch`

Pernyataan `switch` adalah alternatif untuk `if-else` berantai, cocok untuk mengevaluasi satu variabel terhadap beberapa nilai konstan.

### Struktur:

```java
switch (variabel) {
    case nilai1:
        // Kode untuk nilai1
        break;
    case nilai2:
        // Kode untuk nilai2
        break;
    default:
        // Kode default jika tidak ada case yang cocok
}
```

- **`break`**: Menghentikan eksekusi `switch` setelah case cocok.
- **`default`**: Opsional, dijalankan jika tidak ada `case` yang cocok.

### Contoh:

```java
public class SwitchDemo {
    public static void main(String[] args) {
        int hari = 3;
        switch (hari) {
            case 1:
                System.out.println("Senin");
                break;
            case 2:
                System.out.println("Selasa");
                break;
            case 3:
                System.out.println("Rabu");
                break;
            default:
                System.out.println("Hari tidak diketahui");
        }
    }
}
```

**🖨️ Output:**

```text
Rabu
```

> 💡 **Tips**: Lupa menambahkan `break` akan menyebabkan eksekusi berlanjut ke `case` berikutnya (*fall-through*), yang bisa menjadi bug jika tidak diinginkan.

## 🧪 Studi Kasus: Menentukan Ganjil/Genap

Berikut adalah contoh program untuk menentukan apakah sebuah angka ganjil atau genap menggunakan `if-else`:

```java
public class GanjilGenap {
    public static void main(String[] args) {
        int angka = 7;
        if (angka % 2 == 0) {
            System.out.println("Angka " + angka + " adalah genap");
        } else {
            System.out.println("Angka " + angka + " adalah ganjil");
        }
    }
}
```

**🖨️ Output:**

```text
Angka 7 adalah ganjil
```

## 📌 Kesimpulan

Struktur kontrol alur memungkinkan program Java membuat keputusan berdasarkan kondisi:

| **Struktur**   | **Kegunaan**                                      |
|----------------|--------------------------------------------------|
| `if`           | Mengevaluasi kondisi tunggal                     |
| `else`         | Menangani kasus ketika kondisi `if` salah        |
| `else if`      | Mengevaluasi beberapa kondisi secara berurutan   |
| `switch`       | Menangani banyak nilai konstan dengan rapi       |

> 📌 **Catatan**: Gunakan `switch` untuk nilai diskrit (seperti angka atau enum) dan `if-else` untuk kondisi yang lebih kompleks atau rentang nilai.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Konsep OOP: Object-Oriented Programming](../oop/konsep.md) untuk memahami cara membangun program berbasis objek.