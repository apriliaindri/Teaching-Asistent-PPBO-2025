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

## Interface yang Mengembangkan Interface Collection
Kerangka kerja collection ini memiliki beberapa interface di mana setiap interface digunakan untuk menyimpan jenis data tertentu. Berikut adalah interface yang ada dalam kerangka kerja ini.

### 1. Interface Iterable
Interface ini adalah interface root untuk seluruh framework Collection. Interface collection membutuhkan iterasi. Oleh karena itu, secara inheren, semua interface dan kelas di bawahnya mengimplementasikan interface ini. Fungsi utama interface ini adalah menyediakan iterator untuk collection. Oleh karena itu, interface ini hanya berisi satu method abstrak, yaitu iterator.

    ```java
    Iterator iterator();
    ```

### 2. Interface `Collection`
Interface ini mengembangkan interface yang dapat diiterasi dan diimplementasikan oleh semua kelas dalam kerangka kerja collection. Interface ini berisi semua method dasar yang dimiliki setiap collection, seperti menambahkan data ke dalam collection, menghapus data, menghapus semua data, dan sebagainya. Semua method ini diimplementasikan dalam interface ini karena method-method ini diimplementasikan oleh semua kelas tanpa memandang style implementasinya. Dengan memiliki method-method ini, interface memastikan bahwa nama-nama method tersebut berlaku universal untuk semua collection. Oleh karena itu, kita dapat mengatakan bahwa interface ini membangun dasar di mana kelas-kelas collection diimplementasikan.

### 3. Interface List
Interface ini adalah turunan dari interface collection. Interface ini memungkinkan data duplikat ada di dalamnya. Interface list ini diimplementasikan oleh berbagai kelas seperti ArrayList, LinkedList, Vector, dan lain-lain. Karena semua kelas turunan mengimplementasikan list, kita dapat membuat objek list dengan salah satu dari kelas-kelas ini.

Contoh:

```java
List<T> al = new ArrayList<>();
List<T> ll = new LinkedList<>();
List<T> v = new Vector<>();
```

Di mana T adalah tipe generik. Artinya, tipe ini dapat digantikan oleh objek yang memenuhi syarat apa pun pada saat proses berjalan, misalnya objek Integer, String, dan sebagainya. Kelas-kelas yang mengimplementasikan interface List adalah sebagai berikut:

#### a. ArrayList  
ArrayList menyediakan array dinamis dalam Java. ArrayList berguna dalam program-program di mana banyak diperlukan manipulasi dalam array. Maka dari itu, ArrayList sering dipakai meskipun relatif lebih lambat dibanding array biasa. Ukuran ArrayList diperbesar secara otomatis jika collection bertambah atau menyusut jika objek dihapus dari collection. ArrayList Java memungkinkan kita untuk mengakses list secara acak. ArrayList tidak dapat digunakan untuk tipe data primitif seperti int, char, dll. Kita memerlukan wrapper classes untuk kasus-kasus tersebut (materi wrapper classes ada di bab 2 \[variabel dan tipe data\]).

Contoh ArrayList:

```java
// Contoh ArrayList
ArrayList<Integer> al = new ArrayList<Integer>();

// Menambahkan elemen baru di akhir list
for (int i = 1; i <= 5; i++)
    al.add(i);

// Menghapus elemen pada indeks 2
al.remove(2);

// Menampilkan ArrayList setelah penghapusan
System.out.println(al);

// Menampilkan elemen satu per satu
for (int i = 0; i < al.size(); i++)
    System.out.print(al.get(i) + " ");
``` 

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

### 4. Interface Queue
Seperti namanya, interface queue menjaga urutan FIFO (First In First Out) seperti antrean di dunia nyata. Interface ini digunakan untuk menyimpan semua elemen di mana urutan elemen dianggap penting. Misalnya, ketika kita mencoba memesan tiket, tiket dijual berdasarkan prinsip first come first serve. Oleh karena itu, orang yang tiba pertama kali dalam queue akan mendapatkan tiket terlebih dahulu. Kita dapat membuat objek queue dengan salah satu dari kelas-kelas ini karena semua kelas turunan ini mengimplementasikan interface queue.

Contohnya:

```java
Queue<T> pq = new PriorityQueue<>(); 
Queue<T> ad = new ArrayDeque<>(); 
```

Implementasi interface queue yang paling sering digunakan adalah PriorityQueue.

#### a. Priority Queue  
PriorityQueue digunakan ketika objek harus diproses berdasarkan prioritas. Meskipun queue mengikuti algoritma First-In-First-Out, kadang-kadang elemen-elemen dalam queue harus diproses sesuai dengan prioritas, maka kelas ini diperlukan. Elemen-elemen dalam priority queue diurutkan berdasarkan urutan alami, atau berdasarkan Comparator yang disediakan pada saat konstruksi queue, tergantung pada konstruktor mana yang digunakan.

Contoh:

```java
PriorityQueue<Integer> pQueue = new PriorityQueue<Integer>();

pQueue.add(10);
pQueue.add(20);
pQueue.add(15);

// Mencetak elemen teratas
System.out.println(pQueue.peek());

// Mencetak elemen teratas lalu menghapusnya dari container PriorityQueue
System.out.println(pQueue.poll());

// Mencetak elemen teratas
System.out.println(pQueue.peek());
```

Output:

```
10
10
15
```

### 5. Interface Deque
Deque, yang juga dikenal sebagai double-ended queue, adalah struktur data di mana kita dapat menambahkan dan menghapus elemen dari kedua ujung queue (double-ended). Interface ini meng-extend interface queue. Kelas yang mengimplementasikan interface ini adalah ArrayDeque. Karena kelas ArrayDeque mengimplementasikan interface Deque, kita dapat membuat objek deque dengan kelas ini.

Contohnya:

```java
Deque<T> ad = new ArrayDeque<>(); 
```

Di mana T adalah tipe objek. Kelas yang mengimplementasikan interface deque adalah ArrayDeque.
