# 🧬 Generics dalam Java

**Generics** memungkinkan kita menulis kode yang bisa bekerja dengan berbagai tipe data tanpa mengorbankan **type safety**.

Tanpa generics:
- Banyak cast
- Rentan runtime error
- Tidak fleksibel

Dengan generics:
- Lebih aman (cek tipe di compile-time)
- Lebih fleksibel (reusable untuk banyak tipe)
- Lebih bersih

---

## 🔰 Motivasi: Sebelum & Sesudah Generics

**Sebelum:**
```java
ArrayList list = new ArrayList();
list.add("Marno");
String nama = (String) list.get(0); // perlu cast
````

**Sesudah:**

```java
ArrayList<String> list = new ArrayList<>();
list.add("Marno");
String nama = list.get(0); // tanpa cast, aman
```

---

## 🔧 Generic Class

```java
public class Kotak<T> {
    private T isi;

    public void setIsi(T isi) {
        this.isi = isi;
    }

    public T getIsi() {
        return isi;
    }
}
```

Penggunaan:

```java
Kotak<String> k1 = new Kotak<>();
k1.setIsi("Sawit");

Kotak<Integer> k2 = new Kotak<>();
k2.setIsi(100);
```

---

## 🧪 Generic Method

```java
public class Util {
    public static <T> void tampilkan(T data) {
        System.out.println(data);
    }
}
```

Pemanggilan:

```java
Util.tampilkan("Selamat datang");
Util.tampilkan(123);
```

---

## ⚙️ Multiple Type Parameters

```java
public class Pasangan<K, V> {
    private K kunci;
    private V nilai;

    public Pasangan(K k, V v) {
        this.kunci = k;
        this.nilai = v;
    }

    public K getKunci() { return kunci; }
    public V getNilai() { return nilai; }
}
```

Penggunaan:

```java
Pasangan<String, Integer> p = new Pasangan<>("Ali", 50);
System.out.println(p.getKunci() + " => " + p.getNilai());
```

---

## 📥 Bounded Type Parameter (`extends`)

```java
public class Pengolah<T extends Number> {
    public double duaKali(T nilai) {
        return nilai.doubleValue() * 2;
    }
}
```

Pemanggilan:

```java
Pengolah<Integer> p = new Pengolah<>();
System.out.println(p.duaKali(5)); // Output: 10.0
```

---

## 📚 Wildcard `?`

| Syntax          | Arti                                      |
| --------------- | ----------------------------------------- |
| `<?>`           | Tipe bebas                                |
| `<? extends T>` | Turunan dari `T` (bisa `T` atau subclass) |
| `<? super T>`   | `T` atau superclass-nya                   |

Contoh:

```java
public void cetakSemua(List<?> daftar) {
    for (Object o : daftar) {
        System.out.println(o);
    }
}
```

---

## 🧠 Studi Kasus: Stack Generik

```java
public class Stack<T> {
    private ArrayList<T> data = new ArrayList<>();

    public void push(T item) {
        data.add(item);
    }

    public T pop() {
        if (!data.isEmpty()) {
            return data.remove(data.size() - 1);
        }
        return null;
    }

    public boolean isEmpty() {
        return data.isEmpty();
    }
}
```

---

## 📌 Kesimpulan

| Konsep          | Penjelasan                                   |
| --------------- | -------------------------------------------- |
| `<T>`           | Parameter generik                            |
| `Kotak<T>`      | Class generik                                |
| `<T extends A>` | Membatasi tipe hanya ke subclass dari A      |
| `<?>`           | Wildcard: tipe bebas                         |
| Keuntungan      | Reusable, type-safe, lebih bersih dan modern |

---

➡️ Selanjutnya: [Lambda Expression (Fungsi Ringkas)](lambda_expression.md)