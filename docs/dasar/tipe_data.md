# 🧠 Tipe Data & Variabel dalam Java

Dalam pemrograman, **tipe data** digunakan untuk menentukan jenis nilai (angka, huruf, logika) yang dapat disimpan dalam sebuah **variabel**.

## 🔤 Apa itu Variabel?

Variabel adalah **wadah** untuk menyimpan data dalam memori.  
Setiap variabel memiliki:
- Nama (identifier)
- Tipe data
- Nilai

### Contoh:
```java
int umur = 25;
String nama = "Marno";
boolean aktif = true;
````

## 📦 Jenis-Jenis Tipe Data di Java

### 1. 📊 **Tipe Data Primitif**

Java memiliki 8 tipe data primitif bawaan:

| Tipe      | Ukuran | Contoh Nilai        | Keterangan               |
| --------- | ------ | ------------------- | ------------------------ |
| `byte`    | 8 bit  | 127                 | Bilangan kecil           |
| `short`   | 16 bit | 32000               | Bilangan sedang          |
| `int`     | 32 bit | 2\.147\.483\.647    | Bilangan bulat umum      |
| `long`    | 64 bit | 9\.223\.372\.036... | Bilangan bulat besar     |
| `float`   | 32 bit | 3.14f               | Bilangan desimal kecil   |
| `double`  | 64 bit | 3.1415926535        | Bilangan desimal presisi |
| `char`    | 16 bit | 'A'                 | Karakter tunggal         |
| `boolean` | 1 bit  | true / false        | Logika benar/salah       |

> 🔍 Catatan: `float` harus ditulis dengan akhiran `f`, misalnya `float pi = 3.14f;`

---

### 2. 🧱 **Tipe Data Referensi**

Selain tipe primitif, Java juga punya tipe referensi, misalnya:

| Tipe Referensi | Contoh            | Keterangan            |
| -------------- | ----------------- | --------------------- |
| `String`       | `"Halo"`          | Teks atau kata        |
| `Array`        | `{1,2,3}`         | Kumpulan elemen       |
| `Class`        | `Scanner`, `Math` | Objek dari class lain |

---

## 📝 Deklarasi dan Inisialisasi Variabel

### 1. Deklarasi Saja

```java
int x;
String nama;
```

### 2. Inisialisasi Sekaligus

```java
int umur = 25;
boolean aktif = true;
```

### 3. Deklarasi Banyak Sekaligus

```java
int a = 1, b = 2, c = 3;
```

---

## 🔐 Aturan Penamaan Variabel

* Harus dimulai dengan huruf atau underscore
* Tidak boleh pakai spasi
* Case-sensitive (`umur` ≠ `Umur`)
* Hindari kata kunci Java (`int`, `class`, `public`, dll)

### Contoh valid:

```java
String namaLengkap;
int _nilaiAkhir;
```

### Contoh tidak valid:

```java
int 1angka;       // Error: tidak boleh mulai dengan angka
String nama lengkap; // Error: tidak boleh ada spasi
```

<!-- --- -->

## 🧪 Contoh Program Lengkap

```java
public class TipeDataDemo {
    public static void main(String[] args) {
        int umur = 21;
        double tinggi = 172.5;
        char inisial = 'M';
        boolean mahasiswa = true;
        String nama = "Marno";

        System.out.println("Nama: " + nama);
        System.out.println("Umur: " + umur + " tahun");
        System.out.println("Tinggi: " + tinggi + " cm");
        System.out.println("Inisial: " + inisial);
        System.out.println("Status Mahasiswa: " + mahasiswa);
    }
}
```

---

## 📌 Kesimpulan

* Java memiliki tipe data **primitif** dan **referensi**
* Variabel digunakan untuk menyimpan nilai
* Penamaan variabel harus mengikuti aturan sintaks
* Tipe data menentukan seberapa banyak memori digunakan dan bagaimana data diproses

---

➡️ Selanjutnya: [Operator dan Ekspresi dalam Java](operator.md)