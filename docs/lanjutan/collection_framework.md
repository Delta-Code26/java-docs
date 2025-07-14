# 🧺 Java Collection Framework (JCF) Tingkat Lanjut

Java Collection Framework menyediakan struktur data siap pakai seperti:
- List (ArrayList, LinkedList)
- Set (HashSet, TreeSet)
- Map (HashMap, TreeMap)
- Queue (LinkedList, PriorityQueue)

Struktur data ini sangat efisien, aman, dan mendukung operasi skala besar.

---

## 🔖 Hirarki Umum

```

Collection
├── List
│    ├── ArrayList
│    └── LinkedList
├── Set
│    ├── HashSet
│    └── TreeSet
└── Queue
├── LinkedList
└── PriorityQueue

Map (bukan bagian dari Collection, tapi setara)
├── HashMap
└── TreeMap

````

---

## 📘 List: Urutan dan Duplikasi

```java
List<String> daftar = new ArrayList<>();
daftar.add("Ali");
daftar.add("Ali"); // duplikasi diperbolehkan
````

* `ArrayList`: Akses cepat
* `LinkedList`: Sisip/hapus cepat

---

## 🔐 Set: Unik dan Tidak Berurutan

```java
Set<String> unik = new HashSet<>();
unik.add("Marno");
unik.add("Marno"); // hanya 1 yang disimpan
```

* `HashSet`: Unordered
* `TreeSet`: Otomatis terurut (asc)

---

## 🧭 Map: Key-Value

```java
Map<String, Integer> umur = new HashMap<>();
umur.put("Marno", 25);
umur.put("Budi", 30);

System.out.println(umur.get("Marno")); // 25
```

* `HashMap`: Tidak berurutan
* `TreeMap`: Key otomatis diurutkan
* `LinkedHashMap`: Urut sesuai input

---

## 📦 Queue & Deque

```java
Queue<String> antrian = new LinkedList<>();
antrian.add("User1");
antrian.add("User2");
System.out.println(antrian.poll()); // User1 keluar
```

* FIFO (first in first out)
* Bisa dipakai untuk sistem antrean, notifikasi, dll.

---

## 🔁 Iterator & For-Each

```java
for (String nama : daftar) {
    System.out.println(nama);
}

// atau pakai Iterator
Iterator<String> itr = daftar.iterator();
while (itr.hasNext()) {
    System.out.println(itr.next());
}
```

---

## 💥 Synchronized Collection

```java
List<String> aman = Collections.synchronizedList(new ArrayList<>());
```

Untuk koleksi yang thread-safe.

---

## 🧠 Pilih Struktur Data yang Tepat

| Kasus                           | Gunakan                                 |
| ------------------------------- | --------------------------------------- |
| Data berurutan, boleh duplikat  | `ArrayList` atau `LinkedList`           |
| Data unik, tidak penting urutan | `HashSet`                               |
| Data unik & perlu urut          | `TreeSet`                               |
| Peta key → value                | `HashMap` atau `TreeMap`                |
| Antrean proses/data             | `Queue` (`LinkedList`, `PriorityQueue`) |

---

## 📌 Kesimpulan

| Struktur | Ciri Khas                            |
| -------- | ------------------------------------ |
| List     | Urutan tetap, boleh duplikasi        |
| Set      | Tidak duplikat, tidak selalu terurut |
| Map      | Key-value, akses cepat               |
| Queue    | Antrean data, FIFO                   |

---