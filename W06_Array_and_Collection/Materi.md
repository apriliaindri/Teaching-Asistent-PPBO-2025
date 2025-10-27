## Method dalam Interface Collection

Berikut adalah method dalam interface Collection:

| Method                        | Deskripsi                                                                                                    |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------ |
| `add(Object)`                 | Method ini digunakan untuk menambahkan sebuah objek ke dalam collection.                                        |
| `addAll(Collection c)`        | Method ini menambahkan semua elemen dalam collection yang diberikan ke dalam collection ini.                     |
| `clear()`                     | Method ini menghapus semua elemen dari collection ini.                                                         |
| `contains(Object o)`          | Method ini mengembalikan nilai true jika collection ini mengandung elemen yang ditentukan.                     |
| `containsAll(Collection c)`   | Method ini mengembalikan nilai true jika collection ini mengandung semua elemen dalam collection yang diberikan. |
| `equals(Object o)`            | Method ini membandingkan objek yang ditentukan dengan collection ini untuk kesamaan.                           |
| `hashCode()`                  | Method ini digunakan untuk mengembalikan nilai hash code untuk collection ini.                                  |
| `isEmpty()`                   | Method ini mengembalikan nilai true jika collection ini tidak mengandung elemen.                                 |
| `iterator()`                  | Method ini mengembalikan iterator untuk elemen-elemen dalam collection ini.                                     |
| `max()`                       | Method ini digunakan untuk mengembalikan nilai maksimum yang ada dalam collection.                              |
| `parallelStream()`            | Method ini mengembalikan sebuah Parallel Stream dengan collection ini sebagai sumbernya.                       |
| `remove(Object o)`            | Method ini digunakan untuk menghapus objek yang diberikan dari collection. Jika terdapat nilai duplikat, maka method ini akan menghapus kemunculan pertama objek tersebut. |
| `removeAll(Collection c)`     | Method ini digunakan untuk menghapus semua objek yang disebutkan dalam collection yang diberikan dari collection ini. |
| `removeIf(Predicate filter)`  | Method ini digunakan untuk menghapus semua elemen dalam collection ini yang memenuhi predikat yang diberikan. |
| `retainAll(Collection c)`     | Method ini digunakan untuk menyimpan hanya elemen-elemen dalam collection ini yang terdapat dalam collection yang ditentukan. |
| `size()`                      | Method ini digunakan untuk mengembalikan jumlah elemen dalam collection.                                        |
| `spliterator()`               | Method ini digunakan untuk membuat sebuah Spliterator untuk elemen-elemen dalam collection ini.               |
| `stream()`                    | Method ini digunakan untuk mengembalikan sebuah Sequential Stream dengan collection ini sebagai sumbernya.      |
| `toArray()`                   | Method ini digunakan untuk mengembalikan sebuah array yang berisi semua elemen dalam collection ini.            |

Dengan Framework Collection, Anda dapat mengelola data lebih mudah dengan memanfaatkan collection yang efisien dalam aplikasi Java.

#### b. LinkedList  
Kelas LinkedList adalah salah satu cara untuk menyimpan dan mengatur data dalam bentuk rangkaian elemen yang saling terhubung. LinkedList menyimpan tiap elemen (disebut node) secara terpisah di memori.

Setiap node memiliki dua bagian:
1. Data: Digunakan menyimpan nilai atau informasi.
2. Pointer (address): Digunakan untuk menyimpan alamat menuju node berikutnya.

Karena tiap node saling terhubung lewat pointer, maka kita bisa menambah atau menghapus elemen dengan mudah tanpa harus memindahkan seluruh data, seperti pada array.

**Namun, untuk mencari elemen tertentu, LinkedList harus melalui node satu per satu dari awal, jadi lebih lambat dibanding array dalam pencarian langsung.**

Contoh LinkedList:

```java
// Contoh LinkedList
LinkedList<Integer> ll = new LinkedList<Integer>();

// Menambahkan elemen baru di akhir list
for (int i = 1; i <= 5; i++)
    ll.add(i);

// Menghapus elemen pada indeks 3
ll.remove(3);

// Menampilkan LinkedList setelah penghapusan
System.out.println(ll);

// Menampilkan elemen satu per satu
for (int i = 0; i < ll.size(); i++)
    System.out.print(ll.get(i) + " ");
```

Ada 2 cara dalam remove(), yaitu sebagai berikut: 

```java 
LinkedList<Integer> ll = new LinkedList<>();
ll.add(10);
ll.add(15);
ll.add(20);
ll.remove(2);
System.out.println(ll);
```

```java
ll.remove(Integer.valueOf(20));
```

#### c. Vector  
Vector juga memungkinkan pembuatan array dinamis dalam Java. Vector identik dengan ArrayList dalam hal implementasi. Namun, perbedaan utama antara vektor dan ArrayList adalah bahwa Vektor disinkronkan dan ArrayList tidak disinkronkan. Maksud dari "sinkronisasi" di sini adalah:

**Vector:** Ketika Anda menggunakan Vector untuk menyimpan data, itu berarti operasi-operasi seperti penambahan, penghapusan, atau iterasi ke dalamnya akan secara otomatis dilindungi dari akses konkuren oleh beberapa thread. Artinya, hanya satu thread yang dapat mengakses Vector pada satu waktu. Hal ini memastikan keamanan dalam kasus penggunaan bersama (multithreaded) di mana beberapa thread dapat mengakses Vector secara bersamaan.

**ArrayList:** Sebaliknya, ArrayList tidak memiliki sinkronisasi otomatis. Hal ini berarti jika Anda menggunakannya dalam lingkungan multithreaded, Anda harus secara manual mengimplementasikan mekanisme sinkronisasi, seperti penguncian (locking), untuk melindungi akses ke ArrayList dari beberapa thread. Jika Anda tidak melakukan ini, maka Anda berisiko menghadapi masalah seperti race condition (thread saling berebut mengakses resource) dan ketidak-konsistenan data jika beberapa thread mencoba mengubah ArrayList secara bersamaan tanpa koordinasi.

Contoh Vector:

```java
// Contoh Vector
Vector<Integer> v = new Vector<Integer>();

// Menambahkan elemen baru di akhir list
for (int i = 1; i <= 5; i++)
    v.add(i);

// Menghapus elemen pada indeks 3
v.remove(3);

// Menampilkan Vector setelah penghapusan
System.out.println(v);

// Menampilkan elemen satu per satu
for (int i = 0; i < v.size(); i++)
    System.out.print(v.get(i) + " ");
```

#### d. Stack
Kelas Stack memodelkan dan mengimplementasikan struktur data Stack. Kelas ini didasarkan pada prinsip dasar *last-in-first-out* (LIFO). Selain operasi dasar push dan pop, kelas ini menyediakan tiga fungsi tambahan: `empty`, `search`, dan `peek`. Kelas ini juga dapat disebut sebagai subclass dari Vector.

Contoh Stack:

```java
// Contoh Stack
Stack<String> stack = new Stack<String>();
stack.push("FATISDA");
stack.push("FMIPA");
stack.push("FP");
stack.push("FKIP");

// Iterator untuk Stack
Iterator<String> itr = stack.iterator();

// Menampilkan Stack
while (itr.hasNext()) {
    System.out.print(itr.next() + " ");
}

System.out.println();

stack.pop();

// Iterator untuk Stack
itr = stack.iterator();

// Menampilkan Stack
while (itr.hasNext()) {
    System.out.print(itr.next() + " ");
}
```