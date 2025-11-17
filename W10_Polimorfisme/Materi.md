## Contoh Penerapan Polimorfisme

### 1. Overloading dan Overriding pada Pewarisan

#### a. Overloading pada Pewarisan:

```java
class MathOperation {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }
}

class AdvancedMathOperation extends MathOperation {
    int add(int a, int b, int c) {
        return a + b + c;
    }
}

public class Main {
    public static void main(String[] args) {
        AdvancedMathOperation math = new AdvancedMathOperation();
        
        System.out.println(math.add(2, 3));         // Memanggil metode add(int, int) dari superclass
        System.out.println(math.add(2.5, 3.5));     // Memanggil metode add(double, double) dari superclass
        System.out.println(math.add(2, 3, 4));      // Memanggil metode add(int, int, int) dari subclass
    }
}
```

**Penjelasan:**
- Kelas `MathOperation` memiliki dua metode `add` yang di-*overload* dengan jumlah dan tipe parameter yang berbeda.
- Kelas `AdvancedMathOperation` mewarisi dari `MathOperation` dan menambahkan metode `add` baru yang di-*overload*.

#### b. Overriding pada Pewarisan:

```java
class Animal {
    void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

class Wolf extends Animal {
    @Override
    void makeSound() {
        System.out.println("Wolf roars");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myPet = new Wolf();
        myPet.makeSound();  // Output: Wolf roars
    }
}
```

**Penjelasan:**
- Kelas `Wolf` *mengoverride* metode `makeSound` dari kelas induk `Animal`.
- Saat objek `myPet` dari tipe `Animal` diinisialisasi dengan objek `Wolf`, pemanggilan metode `makeSound` menghasilkan output yang sesuai dengan metode di kelas turunan (`Wolf`).

### 2. Overloading dan Overriding pada Interface

#### a. Overloading pada Interface:

```java
interface Shape {
    void draw();

    void draw(String color);
}

class Circle implements Shape {
    @Override
    public void draw() {
        System.out.println("Drawing a circle");
    }

    @Override
    public void draw(String color) {
        System.out.println("Drawing a " + color + " circle");
    }
}

public class Main {
    public static void main(String[] args) {
        Circle myCircle = new Circle();
        myCircle.draw();               // Output: Drawing a circle
        myCircle.draw("red");          // Output: Drawing a red circle
    }
}
```

**Penjelasan:**
- *Interface* `Shape` memiliki dua metode `draw`, satu tanpa parameter dan satu dengan parameter `color`.
- Kelas `Circle` mengimplementasikan *interface* `Shape` dan memberikan implementasi untuk kedua metode `draw`.

#### b. Overriding pada Interface:

```java
interface Animal {
    void makeSound();
}

class Wolf implements Animal {
    @Override
    public void makeSound() {
        System.out.println("Wolf roars");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myPet = new Wolf();
        myPet.makeSound();  // Output: Wolf roars
    }
}
```

**Penjelasan:**
- *Interface* `Animal` memiliki metode `makeSound`.
- Kelas `Wolf` mengimplementasikan *interface* `Animal` dan memberikan implementasi untuk metode `makeSound`.

### 3. Overloading dan Overriding pada Abstract Class

**a. Overloading pada Abstract Class:**

```java
abstract class Shape {
    abstract void draw();

    void draw(String color) {
        System.out.println("Drawing a " + color + " shape");
    }
}

class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a circle");
    }
}

public class Main {
    public static void main(String[] args) {
        Circle myCircle = new Circle();
        myCircle.draw();               // Output: Drawing a circle
        myCircle.draw("red");          // Output: Drawing a red shape
    }
}
```

**Penjelasan:**
- Kelas abstrak `Shape` memiliki metode abstrak `draw` dan metode `draw` yang di-*overload*.
- Kelas `Circle` mengextends dari `Shape` dan memberikan implementasi untuk metode `draw`.

#### b. Overriding pada Abstract Class:

```java
abstract class Animal {
    abstract void makeSound();
}

class Wolf extends Animal {
    @Override
    void makeSound() {
        System.out.println("Wolf roars");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myPet = new Wolf();
        myPet.makeSound();  // Output: Wolf roars
    }
}
```

**Penjelasan:**
- Kelas abstrak `Animal` memiliki metode abstrak `makeSound`.
- Kelas `Wolf` mengextends dari `Animal` dan memberikan implementasi untuk metode `makeSound`.

### 4. Contoh Lain

#### 1. Operator Overloading (Ad-Hoc Polymorphism)  
Ad-Hoc Polymorphism adalah teknik yang digunakan untuk mendefinisikan method yang sama dengan implementasi berbeda dan argumen berbeda.

**Operator Overloading untuk Bilangan Kompleks:**

```java
class ComplexNumber {
    double real;
    double imaginary;

    ComplexNumber(double real, double imaginary) {
        this.real = real;
        this.imaginary = imaginary;
    }

    // Operator overloading untuk penambahan
    ComplexNumber add(ComplexNumber other) {
        return new ComplexNumber(this.real + other.real, this.imaginary + other.imaginary);
    }
}

public class Main {
    public static void main(String[] args) {
        ComplexNumber num1 = new ComplexNumber(1, 2);
        ComplexNumber num2 = new ComplexNumber(2, 3);

        ComplexNumber sum = num1.add(num2);
        System.out.println("Hasil Penambahan: " + sum.real + " + " + sum.imaginary + "i");
    }
}
```

**Penjelasan:**
- Dalam contoh ini, kita memiliki representasi bilangan kompleks dengan bagian riil dan imajiner.
- Operator overloading digunakan untuk mengizinkan kita menambahkan dua objek bilangan kompleks dengan cara yang intuitif, seperti `num1 + num2`.

#### 2. Generics (Parametric Polymorphism)  
Parametric polymorphism, juga dikenal sebagai generic programming, adalah konsep dalam pemrograman komputer di mana suatu fungsi atau tipe data dapat bekerja dengan berbagai jenis data tanpa menggantungkan diri pada tipe data tertentu.

**Generic Box:**

```java
class Box<T> {
    private T content;

    Box(T content) {
        this.content = content;
    }

    T getContent() {
        return content;
    }
}

public class Main {
    public static void main(String[] args) {
        Box<Integer> intBox = new Box<>(42);
        Box<String> strBox = new Box<>("Halo, Generik!");

        System.out.println("Isi Kotak Integer: " + intBox.getContent());
        System.out.println("Isi Kotak String: " + strBox.getContent());
    }
}
```

**Penjelasan:**
- Dalam contoh ini, kita memiliki kelas `Box` yang dapat menampung berbagai jenis tipe data, seperti kotak angka atau kotak kata.
- Generics memungkinkan kita membuat kelas yang bersifat umum tanpa harus menentukan tipe data secara spesifik.

#### 3. Metode Polimorfik (Polymorphic Algorithms)  
Polymorphic algorithms merujuk pada konsep dalam pemrograman komputer di mana suatu algoritma dapat bekerja dengan berbagai tipe data atau objek, terlepas dari tipe data atau struktur data khusus yang digunakan.  

**Metode Polimorfik untuk Penambahan:**

```java
class MathOperation {
    static int add(int a, int b) {
        return a + b;
    }

    static double add(double a, double b) {
        return a + b;
    }
}

public class Main {
    static <T extends Number> double add(T a, T b) {
        return a.doubleValue() + b.doubleValue();
    }

    public static void main(String[] args) {
        System.out.println("Penambahan (int): " + MathOperation.add(2, 3));
        System.out.println("Penambahan (double): " + MathOperation.add(2.5, 3.5));
        System.out.println("Penambahan Generik: " + add(2, 3.5));
    }
}
```

**Penjelasan:**
- Dalam contoh ini, kita memiliki kelas `MathOperation` dengan metode penambahan yang berbeda untuk tipe data int dan double.
- Melalui metode polimorfik, kita dapat menambahkan angka dengan metode generik tanpa mempedulikan jenis data yang spesifik.

## Bacaan Lebih Lanjut
Untuk mendalami konsep polimorfisme dan konsep lain dalam pemrograman berorientasi objek, silakan merujuk pada sumber-sumber berikut:

### Dokumentasi Resmi:

1. **[The Java™ Tutorials](https://docs.oracle.com/javase/tutorial/):** Panduan resmi dari Oracle memberikan penjelasan rinci tentang konsep OOP, termasuk polimorfisme dalam bahasa Java.

### Sumber Online:

1. **[GeeksforGeeks - Polymorphism in Java](https://www.geeksforgeeks.org/polymorphism-in-java/):** Artikel ini memberikan penjelasan rinci tentang berbagai jenis polimorfisme dalam Java.

2. **[Tutorialspoint - Java Polymorphism](https://www.tutorialspoint.com/java/java_polymorphism.htm):** Tutorialspoint menyediakan tutorial yang mudah dimengerti tentang konsep polimorfisme dalam Java.

3. **[W3Schools - Java Polymorphism](https://www.w3schools.com/java/java_polymorphism.asp):** W3Schools memberikan tutorial singkat dan contoh untuk pemahaman cepat tentang polimorfisme.

### Forum dan Komunitas:

1. **[Stack Overflow](https://stackoverflow.com/):** Platform ini dapat membantu dengan pertanyaan spesifik dan memahami masalah atau konsep tertentu yang berkaitan dengan polimorfisme.
