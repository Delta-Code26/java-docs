# 🔀 Kontrol Alur dalam Java (if, else, switch)

Kontrol alur adalah struktur dalam Java yang memungkinkan program mengambil **keputusan** berdasarkan kondisi tertentu.

Dengan kontrol alur, kita bisa membuat program yang **berpikir** dan **bereaksi** terhadap data.

---

## 🧠 1. Pernyataan `if`

Struktur dasar:
```java
if (kondisi) {
    // kode dijalankan jika kondisi true
}
````

### Contoh:

```java
int usia = 20;
if (usia >= 18) {
    System.out.println("Anda sudah dewasa.");
}
```

---

## 🔀 2. `if` - `else`

Gunakan `else` untuk kondisi sebaliknya:

```java
if (kondisi) {
    // jika true
} else {
    // jika false
}
```

### Contoh:

```java
int nilai = 55;
if (nilai >= 60) {
    System.out.println("Lulus");
} else {
    System.out.println("Tidak Lulus");
}
```

---

## 🧱 3. `if` - `else if` - `else`

Untuk banyak kondisi:

```java
if (kondisi1) {
    // aksi 1
} else if (kondisi2) {
    // aksi 2
} else {
    // aksi default
}
```

### Contoh:

```java
int nilai = 80;

if (nilai >= 90) {
    System.out.println("A");
} else if (nilai >= 80) {
    System.out.println("B");
} else if (nilai >= 70) {
    System.out.println("C");
} else {
    System.out.println("D");
}
```

---

## 🎚️ 4. Operator Logika dalam `if`

Gabungkan beberapa kondisi:

```java
if (x > 10 && x < 20) {
    // antara 10 dan 20
}
```

| Operator | Fungsi |    |      |
| -------- | ------ | -- | ---- |
| `&&`     | dan    |    |      |
| \`       |        | \` | atau |
| `!`      | bukan  |    |      |

---

## 🎛️ 5. Pernyataan `switch`

Alternatif lebih rapi daripada `if-else` berantai ketika mengevaluasi satu variabel dengan banyak kemungkinan nilai.

```java
switch (variabel) {
    case nilai1:
        // aksi
        break;
    case nilai2:
        // aksi
        break;
    default:
        // aksi default
}
```

### Contoh:

```java
int hari = 3;
switch (hari) {
    case 1:
        System.out.println("Senin"); break;
    case 2:
        System.out.println("Selasa"); break;
    case 3:
        System.out.println("Rabu"); break;
    default:
        System.out.println("Hari tidak diketahui");
}
```

---

## 🧪 Studi Kasus: Menentukan Ganjil/Genap

```java
int angka = 7;

if (angka % 2 == 0) {
    System.out.println("Genap");
} else {
    System.out.println("Ganjil");
}
```

---

## 📌 Kesimpulan

| Struktur  | Kegunaan                                   |
| --------- | ------------------------------------------ |
| `if`      | Mengecek kondisi benar                     |
| `else`    | Aksi jika kondisi salah                    |
| `else if` | Mengecek banyak kondisi                    |
| `switch`  | Menangani banyak pilihan nilai dengan rapi |

---

➡️ Selanjutnya: [Perulangan (Loop) dalam Java](perulangan.md)