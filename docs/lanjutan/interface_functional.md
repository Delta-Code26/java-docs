# 🔧 Functional Interface di Java

**Functional Interface** adalah interface yang hanya memiliki **satu method abstrak**.  
Cocok digunakan untuk:
- Lambda Expression
- Method Reference
- Pemrograman fungsional

---

## 📌 Ciri Functional Interface

```java
@FunctionalInterface
interface Pesan {
    void kirim(String isi);
}
````

* Hanya **satu method abstrak**
* Boleh memiliki method default atau static
* Anotasi `@FunctionalInterface` **tidak wajib**, tapi dianjurkan (untuk validasi)

---

## 🧠 Contoh Sederhana

```java
@FunctionalInterface
interface Hitung {
    int operasi(int a, int b);
}
```

Pemakaian dengan lambda:

```java
Hitung tambah = (a, b) -> a + b;
System.out.println(tambah.operasi(3, 5)); // Output: 8
```

---

## 📦 Interface Fungsional dari Java

| Interface       | Method Abstrak        | Keterangan                         |
| --------------- | --------------------- | ---------------------------------- |
| `Runnable`      | `run()`               | Tanpa parameter, tanpa return      |
| `Callable<T>`   | `call()`              | Tanpa parameter, return nilai      |
| `Comparator<T>` | `compare(T o1, T o2)` | Untuk perbandingan dua objek       |
| `Consumer<T>`   | `accept(T t)`         | Menerima input, tanpa return       |
| `Supplier<T>`   | `get()`               | Tidak menerima input, return nilai |
| `Function<T,R>` | `apply(T t)`          | Input → Output                     |
| `Predicate<T>`  | `test(T t)`           | Return boolean (true/false)        |

---

## 🔍 Contoh Nyata: Filter Data

```java
List<String> nama = Arrays.asList("Ali", "Budi", "Cici");

Predicate<String> dimulaiDenganC = n -> n.startsWith("C");

nama.stream()
    .filter(dimulaiDenganC)
    .forEach(System.out::println); // Output: Cici
```

---

## 💡 Kenapa Functional Interface Penting?

| Alasan                               | Penjelasan                               |
| ------------------------------------ | ---------------------------------------- |
| Mendukung lambda expression          | Tanpa harus membuat class tambahan       |
| Mendorong kode ringkas dan ekspresif | Dekat dengan paradigma fungsional modern |
| Membuat Java tidak terasa kaku       | Cocok untuk pemrosesan data, event, dsb. |

---

## 🧪 Interface Fungsional Kustom

```java
@FunctionalInterface
interface Cetak {
    void tampil(String isi);
}

public class Demo {
    public static void cetakTeks(Cetak c) {
        c.tampil("Halo dari Java!");
    }

    public static void main(String[] args) {
        cetakTeks(s -> System.out.println(s));
    }
}
```

---

## 📌 Kesimpulan

| Konsep                 | Penjelasan                                |
| ---------------------- | ----------------------------------------- |
| Functional Interface   | Hanya 1 method abstrak                    |
| `@FunctionalInterface` | Untuk validasi compiler (tidak wajib)     |
| Cocok untuk            | Lambda, stream, event, callback           |
| Contoh built-in        | `Runnable`, `Predicate`, `Function`, dsb. |

---

➡️ Lanjutkan eksplorasi ke: [lambda\_expression.md](lambda_expression.md) dan [stream\_api.md](stream_api.md)