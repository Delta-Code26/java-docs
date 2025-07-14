# 🔒 Encapsulation (Enkapsulasi) dalam Java

**Encapsulation** atau enkapsulasi adalah konsep OOP yang menyatukan data dan method dalam satu unit, serta **menyembunyikan data dari luar**.

Tujuan utamanya adalah:
- Mengontrol akses ke data (melalui method)
- Melindungi data dari perubahan sembarangan

---

## 🧱 Struktur Enkapsulasi

Untuk menerapkan enkapsulasi di Java:

1. Buat field (atribut) sebagai `private`
2. Sediakan method `getter` dan `setter` untuk akses aman

---

## 📦 Contoh:

```java
public class Mahasiswa {
    private String nama;
    private int umur;

    public String getNama() {
        return nama;
    }

    public void setNama(String namaBaru) {
        nama = namaBaru;
    }

    public int getUmur() {
        return umur;
    }

    public void setUmur(int umurBaru) {
        if (umurBaru >= 0) {
            umur = umurBaru;
        }
    }
}
````

---

## 🔍 Penggunaan di Kelas Lain

```java
public class Demo {
    public static void main(String[] args) {
        Mahasiswa mhs = new Mahasiswa();
        mhs.setNama("Marno");
        mhs.setUmur(21);

        System.out.println("Nama: " + mhs.getNama());
        System.out.println("Umur: " + mhs.getUmur());
    }
}
```

💡 Output:

```
Nama: Marno
Umur: 21
```

---

## ❗ Kenapa Harus `private`?

Dengan `private`, data tidak bisa diakses langsung dari luar class:

```java
Mahasiswa mhs = new Mahasiswa();
mhs.nama = "Marno"; // ❌ ERROR: 'nama' has private access
```

---

## ✅ Keuntungan Enkapsulasi

| Keuntungan      | Penjelasan                                |
| --------------- | ----------------------------------------- |
| Keamanan Data   | Atribut hanya bisa diakses melalui method |
| Validasi Nilai  | Bisa dicek dalam setter sebelum menyimpan |
| Mudah Perawatan | Perubahan logika cukup di setter/getter   |
| Modular & Rapi  | Struktur kode lebih terorganisir          |

---

## 🧠 Studi Kasus: Validasi Umur

```java
class Siswa {
    private int umur;

    public void setUmur(int umur) {
        if (umur >= 5 && umur <= 18) {
            this.umur = umur;
        } else {
            System.out.println("Umur tidak valid!");
        }
    }

    public int getUmur() {
        return umur;
    }
}
```

### Penggunaan:

```java
Siswa s = new Siswa();
s.setUmur(4); // Umur tidak valid!
s.setUmur(12);
System.out.println("Umur: " + s.getUmur());
```

---

## 📌 Kesimpulan

| Konsep        | Penjelasan                                 |
| ------------- | ------------------------------------------ |
| `private`     | Menyembunyikan atribut                     |
| Getter/Setter | Akses data dengan aman dan validasi logika |
| Enkapsulasi   | Menggabungkan data dan aksesnya            |

---

➡️ Selanjutnya: [Inheritance (Pewarisan)](inheritance.md)