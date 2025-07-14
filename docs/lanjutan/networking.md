# 🌐 Networking di Java (Client-Server via Socket)

Java mendukung pemrograman jaringan menggunakan **`java.net`**, termasuk:
- Membuat koneksi TCP (client-server)
- Komunikasi antar proses via **Socket**
- Transfer data melalui stream

---

## 📚 Konsep Dasar

| Komponen       | Fungsi                                                        |
|----------------|---------------------------------------------------------------|
| `ServerSocket` | Mewakili server yang menunggu koneksi                         |
| `Socket`       | Koneksi antara client dan server                              |
| `InputStream` / `OutputStream` | Mengirim dan menerima data via jaringan     |

---

## 🖥️ Membuat Server TCP

```java
import java.io.*;
import java.net.*;

public class Server {
    public static void main(String[] args) throws IOException {
        ServerSocket server = new ServerSocket(1234);
        System.out.println("Menunggu koneksi...");

        Socket client = server.accept();
        System.out.println("Client terhubung!");

        BufferedReader input = new BufferedReader(new InputStreamReader(client.getInputStream()));
        PrintWriter output = new PrintWriter(client.getOutputStream(), true);

        String pesan = input.readLine();
        System.out.println("Pesan dari client: " + pesan);

        output.println("Halo juga dari server!");

        client.close();
        server.close();
    }
}
````

---

## 📱 Membuat Client TCP

```java
import java.io.*;
import java.net.*;

public class Client {
    public static void main(String[] args) throws IOException {
        Socket socket = new Socket("localhost", 1234);

        BufferedReader input = new BufferedReader(new InputStreamReader(socket.getInputStream()));
        PrintWriter output = new PrintWriter(socket.getOutputStream(), true);

        output.println("Hai server, saya client!");
        String balasan = input.readLine();
        System.out.println("Dari server: " + balasan);

        socket.close();
    }
}
```

---

## 🧪 Uji Program

1. Jalankan `Server.java` terlebih dahulu
2. Jalankan `Client.java`
3. Perhatikan komunikasi antar dua program

---

## 🔁 Komunikasi Dua Arah (Loop)

Tambahkan loop agar komunikasi bisa dilakukan berulang:

```java
while (true) {
    String pesan = input.readLine();
    if (pesan.equalsIgnoreCase("exit")) break;
    output.println("Server balas: " + pesan);
}
```

---

## 🚨 Tips & Best Practice

| Saran                          | Penjelasan                                      |
| ------------------------------ | ----------------------------------------------- |
| Gunakan `try-with-resources`   | Untuk otomatis menutup koneksi/socket           |
| Tangani Exception dengan benar | Gunakan `try-catch` agar tidak crash            |
| Gunakan multithreading         | Agar server bisa layani banyak client sekaligus |
| Gunakan port > 1024            | Hindari port sistem (0–1023) tanpa izin admin   |

---

## 🧵 Server Multithread (Bonus)

```java
new Thread(() -> {
    try {
        Socket client = server.accept();
        // handle client di thread ini
    } catch (IOException e) {
        e.printStackTrace();
    }
}).start();
```

---

## 📌 Kesimpulan

| Konsep               | Penjelasan                               |
| -------------------- | ---------------------------------------- |
| `ServerSocket`       | Menunggu koneksi client                  |
| `Socket`             | Koneksi TCP aktif antara dua pihak       |
| `Input/OutputStream` | Untuk mengirim/menerima data             |
| Threading            | Diperlukan untuk menangani banyak client |

---

➡️ Selanjutnya: [Koneksi Database MySQL dengan JDBC](jdbc_mysql.md)