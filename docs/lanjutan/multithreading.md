# 🧵 Multithreading di Java

**Multithreading** adalah teknik untuk menjalankan banyak alur (thread) dalam satu program secara **simultan/paralel**.

Setiap thread berjalan secara mandiri dan bisa dikelola bersama — sangat berguna untuk:
- Aplikasi real-time
- Proses background (ex: loading, sync)
- Responsif UI (di Android / Swing)
- Server concurrency (web, API)

---

## 📌 Dua Cara Membuat Thread

### 1. Extend `Thread` Class

```java
public class Tugas extends Thread {
    public void run() {
        System.out.println("Thread berjalan: " + getName());
    }

    public static void main(String[] args) {
        Tugas t = new Tugas();
        t.start(); // BUKAN t.run()
    }
}
````

---

### 2. Implement `Runnable` Interface

```java
public class Tugas implements Runnable {
    public void run() {
        System.out.println("Tugas dijalankan oleh: " + Thread.currentThread().getName());
    }

    public static void main(String[] args) {
        Thread t = new Thread(new Tugas());
        t.start();
    }
}
```

---

## 🔁 Perbedaan `start()` vs `run()`

| Metode    | Apa yang Terjadi                                          |
| --------- | --------------------------------------------------------- |
| `start()` | Membuat thread baru, lalu menjalankan `run()` di dalamnya |
| `run()`   | Menjalankan method biasa, tanpa thread baru               |

---

## 🧪 Contoh: Loop Multithread

```java
class CetakAngka implements Runnable {
    public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println(Thread.currentThread().getName() + ": " + i);
        }
    }

    public static void main(String[] args) {
        Thread t1 = new Thread(new CetakAngka(), "Thread A");
        Thread t2 = new Thread(new CetakAngka(), "Thread B");

        t1.start();
        t2.start();
    }
}
```

---

## ⏱️ Sleep dan Delay

```java
public class DelayDemo {
    public static void main(String[] args) throws InterruptedException {
        System.out.println("Mulai...");
        Thread.sleep(2000); // delay 2 detik
        System.out.println("Selesai setelah delay");
    }
}
```

---

## 🎯 Prioritas Thread

```java
Thread t = new Thread(...);
t.setPriority(Thread.MAX_PRIORITY); // atau MIN_PRIORITY / NORM_PRIORITY
```

---

## ⛔ Interupsi Thread

```java
public class InterupsiDemo {
    public static void main(String[] args) {
        Thread t = new Thread(() -> {
            while (!Thread.currentThread().isInterrupted()) {
                System.out.println("Berjalan...");
            }
        });
        t.start();
        t.interrupt(); // mengirim sinyal interupsi
    }
}
```

---

## ⚠️ Tantangan Multithreading

* **Race condition** → dua thread menulis/membaca data bersamaan
* **Deadlock** → dua thread saling menunggu kunci
* **Thread safety** → pastikan akses ke resource dibatasi

Solusinya: Gunakan `synchronized`, `Lock`, atau struktur data `Concurrent`

---

## 📌 Kesimpulan

| Konsep      | Penjelasan                                |
| ----------- | ----------------------------------------- |
| Thread      | Jalur eksekusi paralel dalam satu program |
| `run()`     | Method yang dijalankan oleh thread        |
| `start()`   | Memulai thread                            |
| `Runnable`  | Interface untuk membuat thread fleksibel  |
| `sleep(ms)` | Memberi delay sementara                   |
| Bahaya Umum | Race condition, deadlock, thread-safe     |

---

➡️ Selanjutnya: [Sinkronisasi Thread (synchronized)](synchronized.md)