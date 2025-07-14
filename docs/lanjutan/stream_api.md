# 🌊 Stream API di Java

**Stream API** diperkenalkan di Java 8 untuk memproses koleksi data seperti `List`, `Set`, dll., dengan cara yang:

✅ Lebih deklaratif  
✅ Lebih efisien  
✅ Lebih readable  

> Think: `data.stream().filter().map().collect()` 🎯

---

## 🔧 Cara Membuat Stream

```java
List<String> nama = Arrays.asList("Ali", "Budi", "Cici");
Stream<String> stream = nama.stream();
````

---

## 🚀 Operasi Stream

| Jenis        | Operasi                                 | Contoh                            |
| ------------ | --------------------------------------- | --------------------------------- |
| Intermediate | `filter`, `map`, `sorted`               | Mengubah atau menyaring data      |
| Terminal     | `forEach`, `collect`, `count`, `reduce` | Mengakhiri dan menghasilkan hasil |

---

## 🎯 Contoh: Filter Nama

```java
List<String> nama = Arrays.asList("Ali", "Budi", "Cici");

nama.stream()
    .filter(n -> n.startsWith("C"))
    .forEach(System.out::println);
// Output: Cici
```

---

## 🔄 `map()`: Mengubah Isi Koleksi

```java
List<String> nama = Arrays.asList("Ali", "Budi", "Cici");

List<String> hurufBesar = nama.stream()
    .map(String::toUpperCase)
    .collect(Collectors.toList());

System.out.println(hurufBesar); // [ALI, BUDI, CICI]
```

---

## 📦 `collect()`: Mengubah Stream Jadi Koleksi

```java
List<Integer> angka = Arrays.asList(1, 2, 3, 4);

List<Integer> genap = angka.stream()
    .filter(n -> n % 2 == 0)
    .collect(Collectors.toList());

System.out.println(genap); // [2, 4]
```

---

## 🔢 `count()`: Menghitung Jumlah Elemen

```java
long jumlah = nama.stream().count();
```

---

## 🔁 `sorted()`: Mengurutkan Elemen

```java
List<String> urut = nama.stream()
    .sorted()
    .collect(Collectors.toList());

System.out.println(urut); // [Ali, Budi, Cici]
```

---

## 🔍 `findFirst()` dan `anyMatch()`

```java
Optional<String> pertama = nama.stream().findFirst();
boolean adaC = nama.stream().anyMatch(n -> n.startsWith("C"));
```

---

## 🔂 `reduce()`: Menggabungkan Elemen

```java
int total = Arrays.asList(1, 2, 3, 4).stream()
    .reduce(0, (a, b) -> a + b);

System.out.println(total); // 10
```

---

## 📌 Studi Kasus: Gaji Pekerja

```java
class Pekerja {
    String nama;
    double gaji;

    public Pekerja(String nama, double gaji) {
        this.nama = nama;
        this.gaji = gaji;
    }

    public double getGaji() { return gaji; }
    public String getNama() { return nama; }
}
```

```java
List<Pekerja> data = Arrays.asList(
    new Pekerja("Ali", 1500),
    new Pekerja("Budi", 1800),
    new Pekerja("Cici", 2000)
);

double total = data.stream()
    .mapToDouble(Pekerja::getGaji)
    .sum();

System.out.println("Total gaji: " + total);
```

---

## ⚠️ Catatan

* Stream **sekali pakai**
* Tidak mengubah data asli (immutable)
* Bisa digabung dengan lambda, method reference, dan generics

---

## 📌 Kesimpulan

| Operasi     | Fungsi                      |
| ----------- | --------------------------- |
| `filter()`  | Menyaring data              |
| `map()`     | Mengubah data               |
| `sorted()`  | Mengurutkan                 |
| `collect()` | Menghasilkan koleksi baru   |
| `reduce()`  | Menggabungkan ke satu nilai |
| `forEach()` | Iterasi akhir               |

---

➡️ Selanjutnya: [Multithreading (Thread & Runnable)](multithreading.md)