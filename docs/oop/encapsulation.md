---
title: Encapsulation (Enkapsulasi) dalam Java
description: Memahami konsep enkapsulasi dalam OOP untuk melindungi data dan mengontrol akses di Java
---

# 🔒 Encapsulation (Enkapsulasi) dalam Java

**Encapsulation** (enkapsulasi) adalah pilar utama Object-Oriented Programming (OOP) yang menggabungkan data (field) dan method dalam satu unit (class) sambil **menyembunyikan detail implementasi** dari dunia luar. Dengan enkapsulasi, data hanya dapat diakses melalui method tertentu, seperti **getter** dan **setter**, untuk memastikan keamanan dan validasi.

### Tujuan Enkapsulasi
- **Melindungi Data**: Mencegah perubahan data yang tidak sah.
- **Mengontrol Akses**: Mengatur bagaimana dan kapan data dapat diakses atau diubah.
- **Meningkatkan Perawatan**: Memudahkan perubahan logika tanpa memengaruhi kode lain.

## 🧱 Struktur Enkapsulasi

Untuk menerapkan enkapsulasi di Java:
1. Deklarasikan field sebagai `private` untuk menyembunyikan dari akses langsung.
2. Sediakan method `public` (getter dan setter) untuk mengakses dan memodifikasi data.
3. (Opsional) Tambahkan logika validasi dalam setter untuk memastikan integritas data.

### Contoh Class dengan Enkapsulasi:

```java
public class Mahasiswa {
    // Field private untuk enkapsulasi
    private String nama;
    private int umur;

    // Getter untuk nama
    public String getNama() {
        return nama;
    }

    // Setter untuk nama
    public void setNama(String nama) {
        this.nama = nama;
    }

    // Getter untuk umur
    public int getUmur() {
        return umur;
    }

    // Setter untuk umur dengan validasi
    public void setUmur(int umur) {
        if (umur >= 0) {
            this.umur = umur;
        } else {
            System.out.println("Umur tidak valid!");
        }
    }
}
```

## 🔍 Penggunaan di Kelas Lain

```java
public class MahasiswaDemo {
    public static void main(String[] args) {
        Mahasiswa mhs = new Mahasiswa();
        mhs.setNama("Marno");
        mhs.setUmur(21);
        mhs.setUmur(-5); // Akan menampilkan pesan error

        System.out.printf("Nama: %s, Umur: %d%n", mhs.getNama(), mhs.getUmur());
    }
}
```

**🖨️ Output:**

```text
Umur tidak valid!
Nama: Marno, Umur: 21
```

## ❗ Mengapa Menggunakan `private`?

Dengan menjadikan field `private`, data tidak dapat diakses atau diubah langsung dari luar class, mencegah perubahan yang tidak diinginkan.

### Contoh Akses Langsung yang Salah:

```java
public class MahasiswaErrorDemo {
    public static void main(String[] args) {
        Mahasiswa mhs = new Mahasiswa();
        // mhs.nama = "Marno"; // ❌ Error: 'nama' has private access
    }
}
```

> 💡 **Info**: Enkapsulasi memastikan bahwa data hanya diubah melalui setter, yang dapat mencakup logika validasi.

## ✅ Keuntungan Enkapsulasi

| **Keuntungan**     | **Penjelasan**                                              |
|--------------------|------------------------------------------------------------|
| **Keamanan Data**  | Hanya method getter/setter yang dapat mengakses data.       |
| **Validasi Nilai** | Setter dapat memeriksa nilai sebelum menyimpan (misalnya, umur ≥ 0). |
| **Mudah Perawatan**| Perubahan logika hanya dilakukan di getter/setter, tidak memengaruhi kode lain. |
| **Modularitas**    | Kode lebih terorganisir dan mudah dipahami.                 |

## 🧠 Studi Kasus: Validasi Umur Siswa

Berikut adalah contoh enkapsulasi dengan validasi ketat untuk umur siswa, memastikan umur berada dalam rentang yang sesuai untuk siswa sekolah.

```java
public class Siswa {
    // Field private
    private int umur;

    // Setter dengan validasi
    public void setUmur(int umur) {
        if (umur >= 5 && umur <= 18) {
            this.umur = umur;
            System.out.println("Umur berhasil diatur ke: " + umur);
        } else {
            System.out.println("Umur tidak valid! Harus antara 5 dan 18 tahun.");
        }
    }

    // Getter
    public int getUmur() {
        return umur;
    }
}
```

### Penggunaan:

```java
public class SiswaDemo {
    public static void main(String[] args) {
        Siswa siswa = new Siswa();
        siswa.setUmur(4);  // Akan menampilkan pesan error
        siswa.setUmur(12); // Umur valid
        System.out.println("Umur siswa: " + siswa.getUmur());
    }
}
```

**🖨️ Output:**

```text
Umur tidak valid! Harus antara 5 dan 18 tahun.
Umur berhasil diatur ke: 12
Umur siswa: 12
```

## 📌 Kesimpulan

Enkapsulasi adalah fondasi untuk membangun kode yang aman dan terorganisir:

| **Konsep**         | **Penjelasan**                                          |
|--------------------|--------------------------------------------------------|
| **`private`**      | Menyembunyikan field dari akses langsung.              |
| **Getter/Setter**  | Mengontrol akses dan memungkinkan validasi data.       |
| **Enkapsulasi**    | Menggabungkan data dan logika dalam unit yang terlindungi. |

> 🎯 **Tujuan Utama**: Enkapsulasi memastikan data hanya diubah dengan cara yang terkendali, meningkatkan keamanan dan fleksibilitas kode.

## 📚 Langkah Selanjutnya

Pelajari lebih lanjut tentang [Inheritance (Pewarisan)](inheritance.md) untuk memahami cara mewarisi fitur dari kelas lain.

⬅️ Kembali: [Konsep Dasar OOP](oop_konsep.md)
