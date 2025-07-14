# 🧷 Sinkronisasi dengan `synchronized` di Java

Ketika beberapa thread mengakses **data atau resource yang sama**, risiko konflik seperti **race condition** bisa terjadi.  
Untuk mencegahnya, Java menyediakan keyword `synchronized` — seperti lampu merah bagi thread 🚦

---

## 🔥 Masalah Tanpa Sinkronisasi

```java
public class Counter implements Runnable {
    private int hitung = 0;

    public void tambah() {
        hitung++;
    }

    public void run() {
        for (int i = 0; i < 1000; i++) tambah();
    }

    public static void main(String[] args) throws InterruptedException {
        Counter c = new Counter();
        Thread t1 = new Thread(c);
        Thread t2 = new Thread(c);

        t1.start(); t2.start();
        t1.join(); t2.join();

        System.out.println("Total: " + c.hitung); // hasil bisa acak!
    }
}
````

---

## ✅ Solusi: Gunakan `synchronized`

### 🔒 Pada Method

```java
public synchronized void tambah() {
    hitung++;
}
```

### 🔒 Pada Blok

```java
public void tambah() {
    synchronized (this) {
        hitung++;
    }
}
```

---

## 📘 synchronized Static

Jika method static, maka kunci berlaku untuk **class**, bukan objek.

```java
public static synchronized void tulis() {
    // hanya 1 thread bisa akses method ini di seluruh JVM
}
```

---

## 💡 Contoh: ATM Simulasi

```java
class ATM {
    private int saldo = 1000;

    public synchronized void tarik(int jumlah) {
        if (saldo >= jumlah) {
            System.out.println(Thread.currentThread().getName() + " menarik " + jumlah);
            saldo -= jumlah;
            System.out.println("Sisa saldo: " + saldo);
        } else {
            System.out.println("Saldo tidak cukup untuk " + Thread.currentThread().getName());
        }
    }
}
```

---

## 🔍 synchronized vs Lock

| Fitur          | `synchronized`        | `Lock` (java.util.concurrent.locks) |
| -------------- | --------------------- | ----------------------------------- |
| Syntax         | Mudah & ringkas       | Lebih fleksibel                     |
| Fitur lanjutan | Tidak tersedia        | `tryLock`, `interruptible`, dll     |
| Performance    | Kadang kurang efisien | Lebih optimal di sistem kompleks    |

Gunakan `ReentrantLock` jika butuh kontrol lebih dalam.

---

## ⚠️ Best Practice

* Gunakan `synchronized` hanya pada **bagian kritis** (yang akses resource bersama)
* Jangan menyinkronkan terlalu luas (bisa menyebabkan deadlock)
* Hindari nested `synchronized` kecuali benar-benar dibutuhkan
* Gunakan `volatile` untuk variable yang dibaca banyak thread tanpa sync

---

## 📌 Kesimpulan

| Konsep                | Penjelasan                                               |
| --------------------- | -------------------------------------------------------- |
| `synchronized`        | Kunci eksklusif agar hanya 1 thread yang akses blok data |
| `synchronized` method | Otomatis mengunci objek (atau class jika static)         |
| Blok sinkron          | Bisa hanya pada bagian kritis saja                       |
| Tujuan utama          | Mencegah race condition & data inkonsisten               |

---

➡️ Selanjutnya: [Networking (Socket Programming)](networking.md)