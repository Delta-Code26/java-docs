# ➕ Operator & Ekspresi dalam Java

Dalam Java, **operator** digunakan untuk melakukan operasi terhadap nilai atau variabel.  
Sementara **ekspresi** adalah kombinasi dari nilai, variabel, dan operator yang menghasilkan nilai baru.

---

## 🎛️ Jenis-Jenis Operator Java

### 1. 🧮 Operator Aritmatika

Digunakan untuk operasi matematika dasar:

| Operator | Nama        | Contoh `a = 10`, `b = 3` | Hasil |
|----------|-------------|--------------------------|-------|
| `+`      | Penjumlahan | `a + b`                  | `13`  |
| `-`      | Pengurangan | `a - b`                  | `7`   |
| `*`      | Perkalian   | `a * b`                  | `30`  |
| `/`      | Pembagian   | `a / b`                  | `3`   |
| `%`      | Modulo (sisa bagi) | `a % b`         | `1`   |

> 💡 Modulo sering digunakan untuk mengecek genap/ganjil: `if (x % 2 == 0)`

---

### 2. ⚖️ Operator Perbandingan (Relasional)

Digunakan untuk membandingkan dua nilai dan menghasilkan `true` atau `false`.

| Operator | Arti                | Contoh        |
|----------|---------------------|---------------|
| `==`     | Sama dengan         | `a == b`      |
| `!=`     | Tidak sama dengan   | `a != b`      |
| `>`      | Lebih besar         | `a > b`       |
| `<`      | Lebih kecil         | `a < b`       |
| `>=`     | Lebih besar sama    | `a >= b`      |
| `<=`     | Lebih kecil sama    | `a <= b`      |

---

### 3. 💡 Operator Logika (Boolean)

Digunakan untuk operasi logika, sering digunakan dalam `if`, `while`, dan ekspresi boolean.

| Operator | Nama        | Contoh         | Hasil      |
|----------|-------------|----------------|------------|
| `&&`     | AND         | `true && false`| `false`    |
| `||`     | OR          | `true || false`| `true`     |
| `!`      | NOT         | `!true`        | `false`    |

---

### 4. 🖊️ Operator Penugasan

Digunakan untuk memberikan dan memperbarui nilai variabel.

| Operator | Contoh      | Sama Dengan     |
|----------|-------------|-----------------|
| `=`      | `x = 5`     | menetapkan 5 ke x |
| `+=`     | `x += 2`    | `x = x + 2`     |
| `-=`     | `x -= 2`    | `x = x - 2`     |
| `*=`     | `x *= 2`    | `x = x * 2`     |
| `/=`     | `x /= 2`    | `x = x / 2`     |
| `%=`     | `x %= 2`    | `x = x % 2`     |

---

### 5. ⬆️ Operator Inkrement & Dekrement

Digunakan untuk menambah/mengurangi nilai satu per satu.

| Operator | Contoh      | Efek               |
|----------|-------------|--------------------|
| `++`     | `x++`       | Tambah 1           |
| `--`     | `x--`       | Kurangi 1          |

> 💡 `x++` (post-increment) berbeda dengan `++x` (pre-increment)

---

## 🧪 Contoh Program

```java
public class OperatorDemo {
    public static void main(String[] args) {
        int a = 10, b = 3;
        boolean hasil;

        System.out.println("a + b = " + (a + b));
        System.out.println("a > b = " + (a > b));
        System.out.println("a % b = " + (a % b));

        hasil = (a > 5) && (b < 5);
        System.out.println("Logika AND: " + hasil);

        int x = 5;
        x += 3;
        System.out.println("x setelah += 3: " + x);
    }
}
````

---

## 📌 Kesimpulan

* Java menyediakan berbagai jenis operator: aritmatika, logika, perbandingan, dan penugasan.
* Operator membantu kita membuat ekspresi dan logika dalam program.
* Kombinasi operator membentuk *ekspresi* yang menghasilkan suatu nilai.

---

➡️ Selanjutnya: [Kontrol Alur: If, Else, dan Switch](kontrol_alur.md)