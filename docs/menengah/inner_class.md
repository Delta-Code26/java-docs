# 🧬 Inner Class (Class di Dalam Class)

Java memungkinkan kita untuk membuat **class di dalam class lain**. Ini disebut **inner class**.  
Tujuannya adalah untuk mengelompokkan class yang **hanya digunakan di dalam induknya**, menjaga struktur kode tetap rapi dan relevan.

---

## 🧩 4 Jenis Inner Class di Java

| Jenis                  | Penjelasan Singkat                                |
|------------------------|---------------------------------------------------|
| Inner Class Biasa      | Class di dalam class                              |
| Static Nested Class    | Inner class yang bersifat static                  |
| Local Inner Class      | Class di dalam method                             |
| Anonymous Inner Class  | Class tanpa nama, langsung digunakan              |

---

## 1️⃣ Inner Class Biasa

```java
public class Luar {
    class Dalam {
        void tampil() {
            System.out.println("Ini class dalam.");
        }
    }

    void jalan() {
        Dalam d = new Dalam();
        d.tampil();
    }

    public static void main(String[] args) {
        Luar l = new Luar();
        l.jalan();
    }
}
````

---

## 2️⃣ Static Nested Class

```java
public class Luar {
    static class Dalam {
        void tampil() {
            System.out.println("Ini static inner class.");
        }
    }

    public static void main(String[] args) {
        Luar.Dalam d = new Luar.Dalam();
        d.tampil();
    }
}
```

* Bisa dibuat **tanpa membuat objek class luar**
* Tidak bisa akses anggota non-static dari class luar

---

## 3️⃣ Local Inner Class (Dalam Method)

```java
public class Demo {
    void tampil() {
        class Lokal {
            void sapa() {
                System.out.println("Halo dari dalam method.");
            }
        }

        Lokal l = new Lokal();
        l.sapa();
    }

    public static void main(String[] args) {
        new Demo().tampil();
    }
}
```

---

## 4️⃣ Anonymous Inner Class

* Digunakan saat membuat **implementasi cepat satu kali pakai**
* Sering dipakai pada listener atau callback

```java
interface Sapa {
    void ucap();
}

public class Demo {
    public static void main(String[] args) {
        Sapa s = new Sapa() {
            public void ucap() {
                System.out.println("Halo dunia!");
            }
        };

        s.ucap();
    }
}
```

---

## 📌 Kapan Menggunakan Inner Class?

| Situasi                                   | Jenis Inner Class yang Cocok |
| ----------------------------------------- | ---------------------------- |
| Struktur hanya digunakan dalam satu class | Inner Class biasa            |
| Tidak butuh akses luar                    | Static Nested Class          |
| Hanya dibutuhkan dalam satu method        | Local Inner Class            |
| Implementasi cepat (1x pakai)             | Anonymous Inner Class        |

---

## 🧪 Studi Kasus: Form Validasi

```java
public class Form {
    private String nama;

    class Validator {
        boolean isValid() {
            return nama != null && !nama.isEmpty();
        }
    }

    public Form(String nama) {
        this.nama = nama;
    }

    public boolean validasi() {
        Validator v = new Validator();
        return v.isValid();
    }

    public static void main(String[] args) {
        Form f = new Form("Marno");
        System.out.println("Valid: " + f.validasi());
    }
}
```

---

## 📌 Kesimpulan

| Jenis Inner Class     | Bisa Static? | Bisa Akses Anggota Luar? | Digunakan Saat               |
| --------------------- | ------------ | ------------------------ | ---------------------------- |
| Inner Class           | ❌ Tidak      | ✅ Ya                     | Class bantu untuk outer      |
| Static Nested Class   | ✅ Ya         | ❌ Tidak                  | Class mandiri tapi terhubung |
| Local Inner Class     | ❌ Tidak      | ✅ Ya (jika final)        | Di dalam method              |
| Anonymous Inner Class | ❌ Tidak      | ✅ Ya                     | Callback, event listener     |

---

➡️ Selanjutnya: [Level Mahir atau Framework Java](../lanjutan/overview.md)