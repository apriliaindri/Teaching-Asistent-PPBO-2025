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