# 🗂️ HashMap dalam Java

**HashMap** adalah struktur data dari Java Collection Framework yang menyimpan **pasangan kunci-nilai (key-value)**.

Mirip seperti:
```

"NIM"  -> "12345"
"Nama" -> "Marno"
"Role" -> "Pekerja"

````

---

## 🧱 Deklarasi Dasar

```java
import java.util.HashMap;

HashMap<String, String> data = new HashMap<>();
````

---

## 🔧 Operasi Dasar HashMap

| Method                 | Keterangan                           |
| ---------------------- | ------------------------------------ |
| `put(key, value)`      | Menambahkan pasangan kunci-nilai     |
| `get(key)`             | Mengambil nilai berdasarkan kunci    |
| `remove(key)`          | Menghapus pasangan berdasarkan kunci |
| `containsKey(key)`     | Mengecek apakah kunci tersedia       |
| `containsValue(value)` | Mengecek apakah nilai tersedia       |
| `size()`               | Jumlah pasangan                      |
| `clear()`              | Menghapus semua data                 |

---

## 📘 Contoh:

```java
HashMap<String, String> user = new HashMap<>();

user.put("id", "001");
user.put("nama", "Marno");
user.put("role", "Mandor");

System.out.println(user.get("nama")); // Output: Marno
```

---

## 🔁 Iterasi HashMap

### 1. Dengan `keySet()`:

```java
for (String key : user.keySet()) {
    System.out.println(key + ": " + user.get(key));
}
```

### 2. Dengan `entrySet()`:

```java
for (Map.Entry<String, String> entry : user.entrySet()) {
    System.out.println(entry.getKey() + " => " + entry.getValue());
}
```

---

## 🧪 Studi Kasus: Rekap Gaji Pekerja

```java
HashMap<String, Double> gaji = new HashMap<>();

gaji.put("Ali", 500.0);
gaji.put("Budi", 450.0);
gaji.put("Cici", 470.0);

for (String nama : gaji.keySet()) {
    System.out.println(nama + " menerima RM " + gaji.get(nama));
}
```

---

## ⚖️ HashMap vs ArrayList

| Fitur       | HashMap                     | ArrayList           |
| ----------- | --------------------------- | ------------------- |
| Akses data  | Berdasarkan `key`           | Berdasarkan `index` |
| Struktur    | Tidak berurutan (unordered) | Urutan tetap        |
| Cocok untuk | Lookup cepat, data acak     | Koleksi berurutan   |

---

## ⚠️ Catatan Penting

* Kunci harus **unik**
* Nilai bisa **berulang**
* HashMap **tidak menjaga urutan input**
* Gunakan `LinkedHashMap` jika ingin versi yang menjaga urutan

---

## 📌 Kesimpulan

| Konsep                | Penjelasan                                 |
| --------------------- | ------------------------------------------ |
| HashMap               | Struktur data untuk pasangan key-value     |
| Keunggulan            | Akses cepat, fleksibel, cocok untuk lookup |
| Biasa digunakan untuk | Konfigurasi, user, mapping, cache          |

---

➡️ Selanjutnya: [File I/O (Baca & Tulis File)](file_io.md)