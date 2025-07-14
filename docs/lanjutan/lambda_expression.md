# 🔹 Lambda Expression di Java

**Lambda Expression** adalah cara baru dan ringkas untuk menulis **fungsi anonim** (tanpa nama) dalam Java.  
Biasanya digunakan untuk implementasi cepat dari interface fungsional (interface dengan satu method).

---

## 🔧 Format Dasar

```java
(parameter) -> { body }
````

Contoh:

```java
(a, b) -> a + b
() -> System.out.println("Halo!")
```

---

## 🧠 Apa Itu Interface Fungsional?

Interface yang hanya memiliki **satu method abstrak**.
Contoh:

```java
@FunctionalInterface
interface Sapa {
    void ucap();
}
```

---

## 🔄 Sebelum vs Sesudah Lambda

**Tanpa Lambda (Anonymous Class):**

```java
Runnable r = new Runnable() {
    public void run() {
        System.out.println("Berjalan!");
    }
};
```

**Dengan Lambda:**

```java
Runnable r = () -> System.out.println("Berjalan!");
```

---

## 📘 Contoh Lengkap: Comparator

```java
List<String> nama = Arrays.asList("Ali", "Marno", "Budi");

Collections.sort(nama, (a, b) -> a.compareTo(b));
```

---

## 💡 Lambda dengan Interface Kustom

```java
@FunctionalInterface
interface Operasi {
    int hitung(int a, int b);
}

public class Demo {
    public static void main(String[] args) {
        Operasi tambah = (a, b) -> a + b;
        Operasi kali = (a, b) -> a * b;

        System.out.println(tambah.hitung(5, 3)); // 8
        System.out.println(kali.hitung(5, 3));   // 15
    }
}
```

---

## 🔄 Lambda sebagai Parameter

```java
public class Kalkulator {
    public static int hitung(int a, int b, Operasi op) {
        return op.hitung(a, b);
    }

    public static void main(String[] args) {
        System.out.println(hitung(10, 2, (x, y) -> x - y)); // 8
    }
}
```

---

## 🔍 Lambda di Java API: `Consumer`, `Function`, `Predicate`

| Interface       | Method        | Kegunaan                      |
| --------------- | ------------- | ----------------------------- |
| `Consumer<T>`   | `accept(T t)` | Melakukan aksi tanpa return   |
| `Function<T,R>` | `apply(T t)`  | Mengubah data (return value)  |
| `Predicate<T>`  | `test(T t)`   | Mengecek kondisi (true/false) |

Contoh:

```java
Consumer<String> cetak = x -> System.out.println(x);
Predicate<Integer> genap = x -> x % 2 == 0;
Function<String, Integer> panjang = s -> s.length();
```

---

## ✨ Lambda + Stream (Preview)

```java
List<String> nama = Arrays.asList("Ali", "Budi", "Cici");

nama.stream()
    .filter(n -> n.startsWith("C"))
    .forEach(n -> System.out.println(n));
```

---

## 📌 Kesimpulan

| Konsep               | Penjelasan                                        |
| -------------------- | ------------------------------------------------- |
| Lambda               | Fungsi anonim (tanpa class atau method eksplisit) |
| Functional Interface | Hanya satu method abstrak                         |
| Keunggulan           | Ringkas, efisien, ideal untuk pemrosesan koleksi  |

---

➡️ Selanjutnya: [Stream API (Pemrosesan Data Modern)](stream_api.md)