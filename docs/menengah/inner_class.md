---
title: Inner Class (Class di Dalam Class) dalam Java
description: Memahami berbagai jenis inner class untuk mengelompokkan logika terkait dalam Java
---

# 🧬 Inner Class (Class di Dalam Class) dalam Java

**Inner class** adalah kelas yang didefinisikan di dalam kelas lain (*outer class*). Inner class digunakan untuk mengelompokkan logika yang hanya relevan dalam konteks kelas luar, meningkatkan enkapsulasi, dan membuat kode lebih terorganisir. Java mendukung empat jenis kelas bersarang (*nested class*): inner class biasa, static nested class, local inner class, dan anonymous inner class.

### Tujuan Inner Class
- **Enkapsulasi**: Menyembunyikan logika spesifik dalam kelas luar.
- **Organisasi Kode**: Mengelompokkan kelas terkait untuk meningkatkan keterbacaan.
- **Fleksibilitas**: Mendukung implementasi cepat untuk kasus khusus, seperti *event listener*.

## 🧩 Jenis-Jenis Inner Class

Java memiliki empat jenis kelas bersarang:

| **Jenis**                 | **Penjelasan**                                    |
|---------------------------|--------------------------------------------------|
| **Inner Class Biasa**     | Kelas non-static di dalam kelas luar.            |
| **Static Nested Class**   | Kelas static di dalam kelas luar.               |
| **Local Inner Class**     | Kelas yang didefinisikan di dalam method.       |
| **Anonymous Inner Class** | Kelas tanpa nama untuk implementasi sekali pakai. |

## 1️⃣ Inner Class Biasa

Inner class biasa didefinisikan di dalam kelas luar dan memiliki akses ke semua anggota (termasuk `private`) dari kelas luar. Inner class memerlukan instance kelas luar untuk dibuat.

### Contoh:

```java
public class Outer {
    private String message = "Halo dari kelas luar";

    class Inner {
        void display() {
            System.out.println("Pesan dari inner class: " + message);
        }
    }

    public void createInner() {
        Inner inner = new Inner();
        inner.display();
    }

    public static void main(String[] args) {
        Outer outer = new Outer();
        outer.createInner();
    }
}
```

**🖨️ Output:**

```text
Pesan dari inner class: Halo dari kelas luar
```

> 📌 **Catatan**: Inner class biasa hanya dapat dibuat melalui instance kelas luar, misalnya `Outer.Inner inner = new Outer().new Inner()`.

## 2️⃣ Static Nested Class

**Static nested class** adalah kelas bersarang yang dideklarasikan dengan kata kunci `static`. Kelas ini tidak memerlukan instance kelas luar untuk dibuat dan tidak dapat mengakses anggota non-static dari kelas luar secara langsung.

### Contoh:

```java
public class Outer {
    private static String staticMessage = "Halo dari static";

    static class StaticNested {
        void display() {
            System.out.println("Pesan dari static nested class: " + staticMessage);
        }
    }

    public static void main(String[] args) {
        Outer.StaticNested nested = new Outer.StaticNested();
        nested.display();
    }
}
```

**🖨️ Output:**

```text
Pesan dari static nested class: Halo dari static
```

> 💡 **Tips**: Gunakan static nested class untuk logika yang mandiri tetapi masih terkait dengan kelas luar.

## 3️⃣ Local Inner Class

**Local inner class** didefinisikan di dalam blok method atau scope tertentu. Kelas ini hanya dapat digunakan dalam scope tempat didefinisikannya dan sering digunakan untuk logika sementara.

### Contoh:

```java
public class LocalInnerDemo {
    public void display() {
        class Local {
            void sayHello() {
                System.out.println("Halo dari local inner class");
            }
        }

        Local local = new Local();
        local.sayHello();
    }

    public static void main(String[] args) {
        LocalInnerDemo demo = new LocalInnerDemo();
        demo.display();
    }
}
```

**🖨️ Output:**

```text
Halo dari local inner class
```

> 📌 **Catatan**: Local inner class hanya dapat mengakses variabel lokal method jika variabel tersebut bersifat `final` atau *effectively final* (tidak diubah setelah inisialisasi).

## 4️⃣ Anonymous Inner Class

**Anonymous inner class** adalah kelas tanpa nama yang didefinisikan dan diinstansiasi langsung, biasanya untuk mengimplementasikan interface atau memperluas kelas secara sekali pakai, seperti untuk *event listener*.

### Contoh:

```java
interface Greeting {
    void say();
}

public class AnonymousInnerDemo {
    public static void main(String[] args) {
        Greeting greeting = new Greeting() {
            @Override
            public void say() {
                System.out.println("Halo dari anonymous inner class!");
            }
        };
        greeting.say();
    }
}
```

**🖨️ Output:**

```text
Halo dari anonymous inner class!
```

> 💡 **Tips**: Anonymous inner class sering digunakan dalam GUI (misalnya, Swing) atau callback untuk implementasi cepat.

## 📌 Kapan Menggunakan Inner Class?

| **Situasi**                                   | **Jenis Inner Class**         |
|-----------------------------------------------|-------------------------------|
| Logika hanya relevan dalam kelas luar          | Inner Class Biasa            |
| Kelas mandiri tapi terkait kelas luar         | Static Nested Class          |
| Logika sementara dalam satu method             | Local Inner Class            |
| Implementasi cepat untuk interface atau kelas  | Anonymous Inner Class        |

## 🧪 Studi Kasus: Validasi Formulir

Berikut adalah contoh penggunaan inner class biasa untuk memvalidasi data formulir.

```java
public class Form {
    private String nama;
    private String email;

    class Validator {
        boolean isValid() {
            return nama != null && !nama.isEmpty() &&
                   email != null && email.contains("@");
        }
    }

    public Form(String nama, String email) {
        this.nama = nama;
        this.email = email;
    }

    public boolean validate() {
        Validator validator = new Validator();
        return validator.isValid();
    }

    public static void main(String[] args) {
        Form form = new Form("Marno", "marno@example.com");
        System.out.println("Form valid: " + form.validate());

        Form invalidForm = new Form("", "invalid");
        System.out.println("Form invalid: " + invalidForm.validate());
    }
}
```

**🖨️ Output:**

```text
Form valid: true
Form invalid: false
```

## 📌 Kesimpulan

Inner class membantu mengelompokkan logika terkait dalam kode yang terorganisir:

| **Jenis Inner Class**     | **Bisa Static?** | **Akses Anggota Luar?** | **Penggunaan**                     |
|---------------------------|------------------|-------------------------|------------------------------------|
| **Inner Class Biasa**     | ❌ Tidak          | ✅ Ya                    | Logika terkait instance kelas luar |
| **Static Nested Class**   | ✅ Ya             | ❌ Hanya static          | Kelas mandiri terkait kelas luar  |
| **Local Inner Class**     | ❌ Tidak          | ✅ Ya (jika final)       | Logika sementara dalam method     |
| **Anonymous Inner Class** | ❌ Tidak          | ✅ Ya                    | Implementasi sekali pakai         |

> 🎯 **Tujuan Utama**: Inner class meningkatkan enkapsulasi dan organisasi kode dengan mengelompokkan logika yang terkait erat dengan kelas luar.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Level Mahir atau Framework Java](../lanjutan/overview.md) untuk memahami topik lanjutan atau pengenalan ke framework seperti Spring atau Java EE.

⬅️ Kembali: [Enum (Enumerasi)](enum.md)