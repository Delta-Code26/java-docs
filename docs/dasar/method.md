# 🔧 Method & Parameter dalam Java

**Method** adalah blok kode yang dirancang untuk melakukan tugas tertentu.  
Dengan method, kita bisa **mengelola kode lebih rapi**, **menghindari duplikasi**, dan **mengulang logika tanpa menulis ulang**.

---

## 🧱 Struktur Dasar Method

```java
tipeKembalian namaMethod(parameter) {
    // blok kode
}
````

### Contoh:

```java
void sapa() {
    System.out.println("Halo, Dunia!");
}
```

Method `sapa()` tidak mengembalikan nilai (`void`) dan tidak menerima parameter.

---

## 🔁 Memanggil Method

Untuk menjalankan method, cukup panggil namanya:

```java
public class Demo {
    static void sapa() {
        System.out.println("Halo, Dunia!");
    }

    public static void main(String[] args) {
        sapa(); // memanggil method
    }
}
```

---

## 🎯 Method dengan Parameter

Kita bisa mengirimkan nilai ke dalam method sebagai **parameter**.

```java
static void sapa(String nama) {
    System.out.println("Halo, " + nama + "!");
}
```

### Contoh Pemanggilan:

```java
sapa("Marno");
sapa("Dunia");
```

💡 Output:

```
Halo, Marno!
Halo, Dunia!
```

---

## 🔁 Method dengan Nilai Kembalian

Jika method menghasilkan output, gunakan `return` dan tentukan tipe data:

```java
static int tambah(int a, int b) {
    return a + b;
}
```

### Contoh:

```java
int hasil = tambah(5, 3);
System.out.println("Hasil = " + hasil);
```

💡 Output:

```
Hasil = 8
```

---

## 🔀 Overloading Method

Java memungkinkan dua method dengan **nama sama**, tapi **parameter berbeda**. Ini disebut *method overloading*.

```java
static void cetak(String teks) {
    System.out.println(teks);
}

static void cetak(int angka) {
    System.out.println("Angka: " + angka);
}
```

Pemanggilan `cetak("Hai")` dan `cetak(5)` akan memilih versi method yang sesuai.

---

## 📚 Studi Kasus: Hitung Luas Persegi Panjang

```java
static int hitungLuas(int panjang, int lebar) {
    return panjang * lebar;
}

public static void main(String[] args) {
    int luas = hitungLuas(5, 3);
    System.out.println("Luas = " + luas);
}
```

---

## 📌 Kesimpulan

| Konsep      | Penjelasan                                  |
| ----------- | ------------------------------------------- |
| Method      | Blok kode yang bisa digunakan berulang      |
| Parameter   | Data yang dikirimkan ke dalam method        |
| Return      | Nilai yang dikembalikan oleh method         |
| Overloading | Method dengan nama sama tapi parameter beda |

---

➡️ Selanjutnya: [Konsep OOP: Object-Oriented Programming](../oop/konsep.md)