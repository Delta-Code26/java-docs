# 🎖️ Enum (Enumerasi) dalam Java

**Enum** (singkatan dari *enumeration*) adalah tipe data khusus di Java yang memungkinkan kita menyimpan **sekumpulan nilai tetap** (konstanta) dalam satu blok.

Sederhananya:
> `enum` = sekumpulan `final static` value yang dikemas rapi

---

## 🔧 Contoh Penggunaan Enum

```java
public enum Role {
    ADMIN,
    MANDOR,
    PEKERJA
}
````

Cara menggunakannya:

```java
public class User {
    Role role;

    public User(Role role) {
        this.role = role;
    }

    public void printRole() {
        System.out.println("Peran: " + role);
    }

    public static void main(String[] args) {
        User u = new User(Role.MANDOR);
        u.printRole(); // Output: Peran: MANDOR
    }
}
```

---

## 📋 Kelebihan Enum

* Nilai enum **tidak bisa berubah** (konstanta)
* Kode jadi **lebih aman**, tidak rawan typo
* Bisa digunakan dalam **switch-case**
* Enum di Java adalah **class khusus**, bisa punya method & constructor

---

## 🎯 Enum dalam `switch`

```java
public class ContohSwitch {
    public static void main(String[] args) {
        Role role = Role.PEKERJA;

        switch (role) {
            case ADMIN:
                System.out.println("Akses penuh");
                break;
            case MANDOR:
                System.out.println("Akses manajemen tim");
                break;
            case PEKERJA:
                System.out.println("Akses lihat data pribadi");
                break;
        }
    }
}
```

---

## 🧠 Enum dengan Constructor & Method

```java
public enum Grade {
    PEMOTONG(0.4),
    PENYUSUN(0.35),
    PENGUTIP(0.25);

    private final double persentase;

    Grade(double persentase) {
        this.persentase = persentase;
    }

    public double getPersentase() {
        return persentase;
    }
}
```

Penggunaan:

```java
System.out.println("Pemotong: " + Grade.PEMOTONG.getPersentase());
// Output: Pemotong: 0.4
```

---

## 📌 Best Practice Enum

* Gunakan enum untuk **data tetap & terbatas**
* Enum membuat kode lebih **bersih, aman, dan terstruktur**
* Cocok untuk: status, kategori, role, jenis pekerjaan, level prioritas, dll

---

## 🧪 Studi Kasus: Status Panen

```java
public enum StatusPanen {
    TERJADWAL,
    SELESAI,
    DITUNDA
}
```

```java
public class Panen {
    StatusPanen status;

    public Panen(StatusPanen status) {
        this.status = status;
    }

    public void cekStatus() {
        switch (status) {
            case TERJADWAL:
                System.out.println("Panen akan dilakukan sesuai jadwal.");
                break;
            case SELESAI:
                System.out.println("Panen telah selesai.");
                break;
            case DITUNDA:
                System.out.println("Panen ditunda karena cuaca.");
                break;
        }
    }
}
```

---

## 📌 Kesimpulan

| Konsep  | Penjelasan                                         |
| ------- | -------------------------------------------------- |
| `enum`  | Tipe data untuk kumpulan nilai tetap               |
| Gunanya | Menghindari hardcode string/int dalam logic        |
| Bisa    | Digunakan dalam switch, punya method & constructor |

---

➡️ Selanjutnya: [Inner Class (Class dalam Class)](inner_class.md)