# 🔁 Perulangan (Loop) dalam Java

Perulangan digunakan untuk mengeksekusi blok kode **berulang kali** selama kondisi tertentu masih terpenuhi.

Java menyediakan tiga jenis perulangan utama:
1. `for`
2. `while`
3. `do-while`

---

## 1. 🔃 Perulangan `for`

Digunakan ketika **jumlah perulangan sudah diketahui**.

### Struktur:
```java
for (inisialisasi; kondisi; perubahan) {
    // blok kode
}
````

### Contoh:

```java
for (int i = 1; i <= 5; i++) {
    System.out.println("Iterasi ke-" + i);
}
```

💡 Output:

```
Iterasi ke-1
Iterasi ke-2
Iterasi ke-3
Iterasi ke-4
Iterasi ke-5
```

---

## 2. ♻️ Perulangan `while`

Digunakan ketika **kita tidak tahu pasti jumlah perulangan**, tetapi ingin mengulang selama suatu kondisi terpenuhi.

### Struktur:

```java
while (kondisi) {
    // blok kode
}
```

### Contoh:

```java
int i = 1;
while (i <= 3) {
    System.out.println("i = " + i);
    i++;
}
```

---

## 3. 🔄 Perulangan `do-while`

Perulangan ini **menjalankan kode minimal satu kali**, lalu mengecek kondisi.

### Struktur:

```java
do {
    // blok kode
} while (kondisi);
```

### Contoh:

```java
int i = 1;
do {
    System.out.println("Cetak ke-" + i);
    i++;
} while (i <= 2);
```

---

## 4. 🔂 Perulangan Bersarang (Nested Loop)

Perulangan di dalam perulangan.

### Contoh:

```java
for (int i = 1; i <= 3; i++) {
    for (int j = 1; j <= 2; j++) {
        System.out.println("i = " + i + ", j = " + j);
    }
}
```

---

## 5. ⛔ `break` dan `continue`

### `break`

Menghentikan perulangan sepenuhnya.

```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) break;
    System.out.println(i);
}
```

### `continue`

Melewati 1 iterasi lalu lanjut ke berikutnya.

```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) continue;
    System.out.println(i);
}
```

---

## 🧪 Studi Kasus: Menjumlahkan 5 Bilangan

```java
int total = 0;
for (int i = 1; i <= 5; i++) {
    total += i;
}
System.out.println("Total = " + total);
```

💡 Output:

```
Total = 15
```

---

## 📌 Kesimpulan

| Jenis Loop | Kapan Digunakan                  |
| ---------- | -------------------------------- |
| `for`      | Jumlah iterasi pasti             |
| `while`    | Jumlah iterasi tidak pasti       |
| `do-while` | Selalu dijalankan minimal 1 kali |
| `break`    | Hentikan perulangan              |
| `continue` | Lewati 1 iterasi                 |

---

➡️ Selanjutnya: [Method & Parameter dalam Java](method.md)