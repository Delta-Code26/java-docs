# 🧠 Ekspresi (Expression) dalam Java

**Expression** adalah pernyataan dalam kode yang **menghasilkan suatu nilai**.  
Setiap ekspresi memiliki tipe data tertentu (int, boolean, String, dll.) dan bisa digunakan dalam operasi, pengambilan keputusan, dan logika program.

---

## 📌 Contoh Ekspresi Sederhana

```java
int a = 5;
int b = 10;
int c = a + b; // a + b adalah ekspresi
````

* `5` → ekspresi literal
* `a + b` → ekspresi aritmatika
* `c = a + b` → ekspresi penugasan (assignment)

---

## 🧮 Jenis Ekspresi dalam Java

| Jenis       | Contoh                     | Penjelasan                   |
| ----------- | -------------------------- | ---------------------------- |
| Literal     | `42`, `"Halo"`, `true`     | Nilai tetap                  |
| Aritmatika  | `a + b`, `x * 10`          | Operasi matematika           |
| Relasional  | `a > b`, `x == y`          | Menghasilkan boolean         |
| Logika      | `a > 5 && b < 10`          | Kombinasi ekspresi boolean   |
| Penugasan   | `x = 7`, `total += 1`      | Menyimpan nilai ke variabel  |
| Unary       | `-a`, `!isBenar`, `++x`    | Satu operand                 |
| Ternary     | `(a > b) ? a : b`          | Pemilihan nilai              |
| Method Call | `System.out.println("Hi")` | Ekspresi dengan efek samping |

---

## 🔁 Ekspresi vs Statement

* **Ekspresi** menghasilkan nilai
* **Statement** adalah perintah lengkap (bisa mengandung ekspresi)

```java
int x = 3 + 4; // Statement, mengandung ekspresi "3 + 4"
```

---

## 🧪 Contoh dalam `if` dan `while`

```java
if (nilai >= 75) { // nilai >= 75 adalah ekspresi boolean
    System.out.println("Lulus");
}

while (i < 10) {  // i < 10 adalah ekspresi boolean
    i++;          // i++ adalah ekspresi unary
}
```

---

## 📌 Kenapa Penting?

Memahami ekspresi:

* Membantu menulis kode yang ringkas dan efisien
* Penting saat debugging atau membaca logika
* Dasar untuk memahami operator dan control flow

---

## 💡 Tips

* Semua ekspresi punya **tipe data**: int, boolean, double, dll.
* Jangan bingung dengan **statement** — ekspresi bisa menjadi bagian dari statement
* Beberapa ekspresi punya **efek samping** (misal: `x++`, `System.out.println()`)

---

## 📌 Kesimpulan

| Konsep       | Penjelasan                                  |
| ------------ | ------------------------------------------- |
| Expression   | Pernyataan yang menghasilkan nilai          |
| Digunakan di | Penugasan, percabangan, perulangan, return  |
| Jenis umum   | Aritmatika, logika, relasional, unary, dst. |
| Dasar dari   | Operator, perhitungan, dan struktur logika  |

---

➡️ Lanjut ke: [operator.md](operator.md) atau [kontrol\_alur.md](kontrol_alur.md)

```