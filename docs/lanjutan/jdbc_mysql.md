# 🗃️ Koneksi Java ke MySQL menggunakan JDBC

**JDBC** (Java Database Connectivity) adalah API resmi Java untuk mengakses database relasional seperti MySQL, PostgreSQL, dll.

Dengan JDBC, kamu bisa:
- Terhubung ke database
- Menjalankan perintah SQL (SELECT, INSERT, UPDATE, DELETE)
- Mengambil hasil query
- Mengelola transaksi

---

## 🔧 Persiapan Awal

1. ✅ Pastikan MySQL aktif di komputer
2. ✅ Buat database: `java_db`
3. ✅ Tambahkan file JDBC driver (`mysql-connector-j-*.jar`) ke project (atau via Maven/Gradle)

---

## 📦 Struktur Tabel Contoh

```sql
CREATE DATABASE java_db;

USE java_db;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nama VARCHAR(100),
    email VARCHAR(100)
);
````

---

## 🔌 Koneksi JDBC: Langkah Dasar

```java
import java.sql.*;

public class Koneksi {
    public static void main(String[] args) {
        String url = "jdbc:mysql://localhost:3306/java_db";
        String user = "root";
        String pass = "";

        try {
            Connection conn = DriverManager.getConnection(url, user, pass);
            System.out.println("Berhasil terkoneksi ke database!");
            conn.close();
        } catch (SQLException e) {
            System.out.println("Gagal koneksi: " + e.getMessage());
        }
    }
}
```

---

## 📄 Menjalankan Query `INSERT`

```java
String sql = "INSERT INTO users (nama, email) VALUES (?, ?)";
PreparedStatement ps = conn.prepareStatement(sql);
ps.setString(1, "Marno");
ps.setString(2, "marno@email.com");
ps.executeUpdate();
```

---

## 📄 Menjalankan Query `SELECT`

```java
String sql = "SELECT * FROM users";
Statement stmt = conn.createStatement();
ResultSet rs = stmt.executeQuery(sql);

while (rs.next()) {
    System.out.println(rs.getInt("id") + " | " +
                       rs.getString("nama") + " | " +
                       rs.getString("email"));
}
```

---

## 📄 Update & Delete

```java
// Update
String sql = "UPDATE users SET nama = ? WHERE id = ?";
PreparedStatement ps = conn.prepareStatement(sql);
ps.setString(1, "Marno Update");
ps.setInt(2, 1);
ps.executeUpdate();

// Delete
String del = "DELETE FROM users WHERE id = ?";
PreparedStatement delps = conn.prepareStatement(del);
delps.setInt(1, 2);
delps.executeUpdate();
```

---

## 📌 Best Practice JDBC

| Tips                        | Penjelasan                                   |
| --------------------------- | -------------------------------------------- |
| Gunakan `PreparedStatement` | Hindari SQL Injection                        |
| Tutup koneksi setelah pakai | Gunakan `try-with-resources` bila perlu      |
| Tangani `SQLException`      | Log semua error dengan detail                |
| Pooling koneksi (lanjutan)  | Gunakan HikariCP/Apache DBCP di sistem besar |

---

## 🔁 Contoh Lengkap

```java
public class UserDAO {
    private Connection conn;

    public UserDAO() throws SQLException {
        conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/java_db", "root", "");
    }

    public void tambahUser(String nama, String email) throws SQLException {
        String sql = "INSERT INTO users (nama, email) VALUES (?, ?)";
        PreparedStatement ps = conn.prepareStatement(sql);
        ps.setString(1, nama);
        ps.setString(2, email);
        ps.executeUpdate();
    }

    public void tampilkanSemua() throws SQLException {
        String sql = "SELECT * FROM users";
        Statement stmt = conn.createStatement();
        ResultSet rs = stmt.executeQuery(sql);

        while (rs.next()) {
            System.out.println(rs.getInt("id") + ": " + rs.getString("nama"));
        }
    }
}
```

---

## 📌 Kesimpulan

| Langkah                           | Penjelasan                    |
| --------------------------------- | ----------------------------- |
| `DriverManager`                   | Mengelola koneksi ke database |
| `Connection`                      | Objek utama koneksi           |
| `Statement` / `PreparedStatement` | Menjalankan SQL               |
| `ResultSet`                       | Menampung hasil SELECT        |
| Koneksi stabil                    | Tutup koneksi setelah selesai |

---

➡️ Selanjutnya: [Collection Framework Lanjutan](collection_framework.md)