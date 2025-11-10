## Constructor
**Constructor** adalah **method** yang digunakan untuk menginisialisasi **properties** dari sebuah class. Dalam **inheritance**, **subclass** akan memanggil **constructor** dari **superclass** terlebih dahulu sebelum menginisialisasi **properties** dari **subclass**. Berikut contoh penggunaan **constructor** di **inheritance**.
```java
class Superclass {
    public Superclass() {
        System.out.println("Superclass constructor");
    }
}

class Subclass extends Superclass{
    public Subclass() {
        System.out.println("Subclass constructor");
    }
}

public class Main {
    public static void main(String[] args) {
        Subclass subclass = new Subclass();
    }
}
```
Output:
```java
Superclass constructor
Subclass constructor
```
Contoh lain:
```java
class Superclass {
    public Superclass() {
        System.out.println("Superclass constructor");
    }
    public Superclass(int a) {
        System.out.println("Superclass constructor with parameter, a value: " + a);
    }
}

class Subclass extends Superclass{
    public Subclass() {
        System.out.println("Subclass constructor");
    }

    public Subclass(int a) {
        System.out.println("Subclass constructor with an int parameter");
    }

    public Subclass(float a) {
        super((int)a);
        System.out.println("Subclass constructor with a float parameter");
    }

    public Subclass(int a, int b) {
        System.out.println("Subclass constructor with two parameters");
    }
}

public class Main {
    public static void main(String[] args) {
        Subclass subclass1 = new Subclass();
        Subclass subclass2 = new Subclass(10);
        Subclass subclass3 = new Subclass(20.5f);
        Subclass subclass4 = new Subclass(10, 20);
    }
}
```
Output:
```java
Superclass constructor
Subclass constructor
Superclass constructor
Subclass constructor with an int parameter
Superclass constructor with parameter, a value: 20
Subclass constructor with a float parameter
Superclass constructor
Subclass constructor with two parameters
```
Dapat dilihat pada contoh di atas, apabila **constructor** pada **subclass** tidak mem-spesifikkan **constructor** mana yang akan dipanggil pada **superclass**, maka **constructor** tanpa parameter akan dipanggil secara **otomatis**. Apabila **constructor** pada **class** mem-spesifikkan **constructor** mana yang akan dipanggil, maka **constructor** yang dipanggil adalah **constructor** yang dispesifikkan. Untuk mem-spesisfikkan **constructor** mana yang akan dipanggil, kita dapat menggunakan **super keyword** diikuti dengan **parameter** yang sesuai dengan **constructor** yang ingin dipanggil.

Contoh **yang salah**:
```java
class Superclass {
    public Superclass(int a) {
        System.out.println("Superclass constructor with parameter, a value: " + a);
    }
}

class Subclass extends Superclass{
    public Subclass(int a) {
        System.out.println("Subclass constructor with an int parameter");
    }
}

public class Main {
    public static void main(String[] args) {
        Subclass subclass = new Subclass(10);
    }
}
```
Output:
```java
ERROR!
```
Hal ini terjadi karena **constructor** pada **subclass** mencoba memanggil **constructor** pada **superclass** tanpa parameter, yang mana **tidak ada**.

## Destructor
**Destructor** adalah **method** yang digunakan untuk menghapus **properties** dari sebuah class. Walaupun pada bahasa Java tidak terdapat **destructor**, namun kita dapat menggunakan **finalize()** untuk menggantikan **destructor**.

Dalam **inheritance**, **subclass** akan memanggil **destructor** dari **subclass** terlebih dahulu sebelum menghapus **properties** dari **superclass**. **Destructor** tidak dapat dipanggil secara langsung, **destructor** akan dipanggil secara **otomatis** ketika sebuah objek dihapus dari memori. Berikut contoh penggunaan **destructor** di **inheritance**.
```java
class Superclass {
    public Superclass() {
        System.out.println("Superclass constructor");
    }

    public void finalize() {
        System.out.println("Superclass destructor");
    }
}

class Subclass extends Superclass {
    public Subclass() {
        System.out.println("Subclass constructor");
    }

    public void finalize() {
        System.out.println("Subclass destructor");
    }
}

public class Main {
    public static void main(String[] args) {
        Subclass subclass = new Subclass();
        subclass = null;
        System.gc(); // Call garbage collector
    }
}
```
Output dari contoh di atas adalah indeterministic,karena **garbage collector** bisa saja **tidak langsung** menghapus objek dari memori. Berikut adalah outputnya apabila **garbage collector** langsung menghapus objek dari memori.
```java
Superclass constructor
Subclass constructor
Subclass destructor
Superclass destructor
```

## An Example of Using the Static Keyword in the Context of Inheritance
**Static keyword** adalah keyword yang digunakan untuk membuat **properties** dan **methods** yang dapat diakses tanpa harus membuat objek terlebih dahulu, dan membuat **properties** dan **methods** menjadi terikat kepada **class** bukan **objek**. Berikut contoh penggunaan **static keyword** dalam konsep **inheritance**.
```java
class Animal {
    static int numberOfAnimals = 0;
    String name;

    public Animal(String name) {
        this.name = name;
        numberOfAnimals++;
    }

    public void animalInfo() {
        System.out.println("Animal: " + name);
    }
}

class Dog extends Animal {
    public Dog(String name) {
        super(name);
    }
}

class Cat extends Animal {
    public Cat(String name) {
        super(name);
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog1 = new Dog("Buddy");
        dog1.animalInfo();
        Dog dog2 = new Dog("Max");
        dog2.animalInfo();
        Cat cat1 = new Cat("Whiskers");
        cat1.animalInfo();

        System.out.println("Total number of animals: " + Animal.numberOfAnimals);
    }
}

```
Output:
```java
Animal: Buddy
Animal: Max
Animal: Whiskers
Total number of animals: 3
```

# Bacaan
- [Inheritance](https://www.w3schools.com/java/java_inheritance.asp)
- [Java Inheritance](https://www.geeksforgeeks.org/inheritance-in-java/)
- [Java Inheritance (Tutorials Point)](https://www.tutorialspoint.com/java/java_inheritance.htm)
- [Java Inheritance (Javatpoint)](https://www.javatpoint.com/inheritance-in-java)
- [Java Super Keyword](https://www.w3schools.com/java/ref_keyword_super.asp)
- [Java Super Keyword (Javatpoint)](https://www.javatpoint.com/super-keyword)
- [Java Final Keyword (Javatpoint)](https://www.javatpoint.com/final-keyword)
- [Java Static Keyword (Javatpoint)](https://www.javatpoint.com/static-keyword-in-java)
- [Java Constructor](https://www.w3schools.com/java/java_constructors.asp)
- [Java Constructor (Javatpoint)](https://www.javatpoint.com/java-constructor)
- [Belajar Java: Inheritance](https://www.petanikode.com/java-oop-inheritance/)

