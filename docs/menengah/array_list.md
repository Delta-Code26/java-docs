# 🧮 Array & ArrayList dalam Java

Saat kamu ingin menyimpan **banyak data sekaligus**, gunakan **Array** atau **ArrayList**.  
Keduanya menyimpan data secara berurutan, namun punya perbedaan besar dari sisi fleksibilitas.

---

## 1️⃣ Array: Ukuran Tetap

Deklarasi array:
```java
int[] angka = new int[3]; // [0, 0, 0]
angka[0] = 10;
angka[1] = 20;
angka[2] = 30;
````

### Deklarasi langsung:

```java
String[] nama = {"Ali", "Budi", "Cici"};
```

### Iterasi:

```java
for (int i = 0; i < angka.length; i++) {
    System.out.println(angka[i]);
}

for (String n : nama) {
    System.out.println(n);
}
```

---

## ⚠️ Keterbatasan Array

* Ukuran tetap, tidak bisa diubah setelah dibuat
* Tidak punya method tambahan seperti tambah/hapus data

---

## 2️⃣ ArrayList: Ukuran Fleksibel

Import dulu:

```java
import java.util.ArrayList;
```

### Deklarasi:

```java
ArrayList<String> buah = new ArrayList<>();
buah.add("Mangga");
buah.add("Durian");
buah.add("Kelapa");
```

---

## 🔄 Method Penting ArrayList

| Method             | Keterangan          |
| ------------------ | ------------------- |
| `add(item)`        | Tambah item         |
| `get(index)`       | Ambil item          |
| `set(index, item)` | Ubah item           |
| `remove(index)`    | Hapus item          |
| `size()`           | Jumlah elemen       |
| `clear()`          | Kosongkan semua isi |
| `contains(item)`   | Cek apakah item ada |

---

### Contoh:

```java
ArrayList<String> tim = new ArrayList<>();
tim.add("Mandor");
tim.add("Pemotong");
tim.add("Penyusun");

for (String t : tim) {
    System.out.println(t);
}
```

---

## ⚖️ Perbandingan Array vs ArrayList

| Fitur        | Array         | ArrayList                     |
| ------------ | ------------- | ----------------------------- |
| Ukuran       | Tetap         | Dinamis                       |
| Type data    | Bisa primitif | Hanya objek/class             |
| Import       | Tidak perlu   | Perlu (`java.util`)           |
| Method bantu | Tidak banyak  | Banyak (`add`, `remove`, dll) |

---

## 🔁 Konversi Antara Array dan ArrayList

### Array → ArrayList

```java
String[] data = {"A", "B", "C"};
ArrayList<String> list = new ArrayList<>(Arrays.asList(data));
```

### ArrayList → Array

```java
String[] arrayBaru = list.toArray(new String[0]);
```

---

## 🧪 Studi Kasus: Simpan Nama Pekerja

```java
ArrayList<String> pekerja = new ArrayList<>();
pekerja.add("Ali");
pekerja.add("Budi");
pekerja.add("Cici");

for (int i = 0; i < pekerja.size(); i++) {
    System.out.println("Pekerja " + (i+1) + ": " + pekerja.get(i));
}
```

---

## 📌 Kesimpulan

| Konsep    | Penjelasan                                           |
| --------- | ---------------------------------------------------- |
| Array     | Struktur data statis, efisien, tapi kurang fleksibel |
| ArrayList | Struktur data dinamis, cocok untuk data harian       |
| Gunakan   | ArrayList untuk kebanyakan kasus dalam aplikasi      |

---

➡️ Selanjutnya: [HashMap dan Struktur Data Key-Value](hashmap.md)