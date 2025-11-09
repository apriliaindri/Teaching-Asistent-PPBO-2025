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

