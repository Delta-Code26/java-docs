# 🛠️ Membangun Ekspresi Kustom di Java

Java bukan bahasa fungsional murni, namun kita tetap bisa **membuat ekspresi sendiri** yang:
- Reusable
- Dinamis
- Ringkas
- Modular

---

## 📌 Tujuan

- Menyusun logika sebagai ekspresi, bukan sekadar prosedur
- Menggunakan lambda atau interface fungsional
- Mengabstraksi logika kompleks menjadi kode ringkas

---

## 🧪 Contoh 1: Validasi Data

```java
@FunctionalInterface
interface Validator<T> {
    boolean validate(T value);
}

public class Demo {
    public static void main(String[] args) {
        Validator<String> emailValidator = email -> email.contains("@");

        System.out.println(emailValidator.validate("marno@email.com")); // true
        System.out.println(emailValidator.validate("marno")); // false
    }
}
````

✅ Kita membuat ekspresi `emailValidator` yang bisa digunakan di mana saja.

---

## 🧪 Contoh 2: Ekspresi Matematika Dinamis

```java
@FunctionalInterface
interface Operation {
    int apply(int a, int b);
}

public class Kalkulator {
    public static void main(String[] args) {
        Operation tambah = (a, b) -> a + b;
        Operation kali = (a, b) -> a * b;

        System.out.println(tambah.apply(5, 3)); // 8
        System.out.println(kali.apply(4, 7));   // 28
    }
}
```

---

## 🔁 Kombinasi Ekspresi

```java
Predicate<String> panjangValid = s -> s.length() > 5;
Predicate<String> adaAngka = s -> s.matches(".*\\d.*");

Predicate<String> validPassword = panjangValid.and(adaAngka);

System.out.println(validPassword.test("hello"));     // false
System.out.println(validPassword.test("hello123"));  // true
```

---

## 🔧 Ekspresi Kustom dengan Class

```java
class Ekspresi {
    public static boolean lebihDari(int a, int batas) {
        return a > batas;
    }

    public static boolean antara(int x, int min, int max) {
        return x >= min && x <= max;
    }
}

// Pemakaian
System.out.println(Ekspresi.lebihDari(10, 5)); // true
System.out.println(Ekspresi.antara(7, 5, 10)); // true
```

---

## 💡 Studi Kasus: Rule Engine Mini

```java
interface Rule<T> {
    boolean apply(T data);
}

class RuleEngine {
    public static <T> boolean jalankan(T data, Rule<T> rule) {
        return rule.apply(data);
    }
}

// Pemakaian
Rule<Integer> isGanjil = n -> n % 2 != 0;

System.out.println(RuleEngine.jalankan(7, isGanjil)); // true
```

---

## 📌 Kesimpulan

| Konsep             | Penjelasan                                       |
| ------------------ | ------------------------------------------------ |
| Custom Expression  | Membuat logika reusable menggunakan lambda/class |
| Tujuan             | Menyusun logika sebagai objek atau fungsi        |
| Cocok untuk        | Validasi, kalkulasi, aturan dinamis              |
| Fitur yang dipakai | Functional interface, lambda, predicate          |

---

➡️ Lanjut: [interface\_functional.md](interface_functional.md) atau [lambda\_expression.md](lambda_expression.md)

```

---

### 🔖 Catatan

Topik ini ideal untuk developer Java modern yang ingin:
- Menulis kode ekspresif dan modular
- Menyusun **rule engine mini**, **validator dinamis**, atau **filter data**

Jika kamu tertarik, kita bisa eksplor lebih lanjut ke:
- `rule_engine.md` (menggunakan strategi pola)
- `expression_parser.md` (buat parser ekspresi dari string)