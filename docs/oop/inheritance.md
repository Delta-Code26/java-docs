# 🧬 Inheritance (Pewarisan) dalam Java

**Inheritance** adalah kemampuan class untuk mewarisi properti dan method dari class lain.

Dengan inheritance:
- Kita bisa membuat **class turunan (child/subclass)**
- Kode menjadi **lebih efisien dan tidak berulang**
- Mewujudkan hubungan **"is-a"** antar class

---

## 🧱 Struktur Dasar Inheritance

Gunakan keyword `extends` untuk membuat class turunan:

```java
class Induk {
    void salam() {
        System.out.println("Halo dari kelas induk!");
    }
}

class Anak extends Induk {
    void perkenalan() {
        System.out.println("Saya dari kelas anak.");
    }
}
````

---

## 🔁 Menggunakan Inheritance

```java
public class Demo {
    public static void main(String[] args) {
        Anak a = new Anak();
        a.salam();         // diwarisi dari class Induk
        a.perkenalan();    // method milik class Anak
    }
}
```

💡 Output:

```
Halo dari kelas induk!
Saya dari kelas anak.
```

---

## 🏗️ Hierarki "Is-a"

```java
class Kendaraan { }
class Mobil extends Kendaraan { }

Mobil adalah Kendaraan → ✅
```

---

## 🎯 Overriding: Mengubah Perilaku Method Induk

Subclass bisa **mengganti** method dari superclass.

```java
class Hewan {
    void suara() {
        System.out.println("Hewan bersuara...");
    }
}

class Kucing extends Hewan {
    @Override
    void suara() {
        System.out.println("Meong");
    }
}
```

---

## 🔑 Keyword Penting

| Keyword     | Fungsi                                              |
| ----------- | --------------------------------------------------- |
| `extends`   | Membuat class turunan                               |
| `super`     | Mengakses konstruktor/field/method dari superclass  |
| `@Override` | Memberi tahu bahwa method menimpa method superclass |

---

## 🧪 Studi Kasus: Pegawai dan Manager

```java
class Pegawai {
    String nama;
    int gaji;

    void info() {
        System.out.println(nama + " bergaji " + gaji);
    }
}

class Manager extends Pegawai {
    int bonus;

    void totalGaji() {
        int total = gaji + bonus;
        System.out.println("Total gaji: " + total);
    }
}
```

### Penggunaan:

```java
public class Demo {
    public static void main(String[] args) {
        Manager m = new Manager();
        m.nama = "Marno";
        m.gaji = 5000;
        m.bonus = 2000;

        m.info();       // dari Pegawai
        m.totalGaji();  // method di Manager
    }
}
```

---

## 🛠️ Constructor dan `super`

Constructor superclass dapat dipanggil dari subclass:

```java
class Person {
    String nama;
    Person(String n) {
        nama = n;
    }
}

class Mahasiswa extends Person {
    Mahasiswa(String n) {
        super(n); // memanggil constructor induk
    }
}
```

---

## 📌 Kesimpulan

| Konsep      | Penjelasan                               |
| ----------- | ---------------------------------------- |
| Inheritance | Class anak mewarisi class induk          |
| extends     | Digunakan untuk pewarisan                |
| super       | Mengakses constructor/field/method induk |
| Overriding  | Menyesuaikan method dari class induk     |

---

➡️ Selanjutnya: [Polymorphism (Polimorfisme)](polymorphism.md)