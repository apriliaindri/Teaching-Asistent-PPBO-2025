# GUI Programming

## Konsep Dasar
Pada dasarnya, Java hanya dikenal dengan Java Console yang di mana program Java hanya dapat dijalankan pada konsol saja. Kemudian Java semakin berkembang, hingga terciptanya Java GUI (**Graphic User Interface**). GUI bertujuan untuk menambahkan beberapa objek yang tidak bisa dibuat dalam basis text. Objek–objek tersebut dapat berupa tombol, gambar, dan lain-lain. Tujuannya adalah untuk memudahkan user menggunakan program yang dibuat tersebut.

Secara umum, GUI adalah interaksi yang dapat dilaksanakan oleh user melalui menu dan icon yang diperlihatkan dalam modus grafik. Contoh implementasi GUI-based shell adalah sistem operasi Microsoft Windows. Berikut contoh program dengan menggunakan Java GUI:
![Java GUI](image.png)

## GUI pada Java
Java memunyai banyak library untuk membuat GUI, seperti AWT (Abstract Window Toolkit), Swing, JavaFX, SWT (Standard Widget Toolkit), Java Native Access (JNA), JGoodies, Apache Pivot, dan lain-lain. Banyak hal yang bisa dipertimbangkan dalam memilih library GUI, seperti kebutuhan, kecepatan, kemudahan, dan lain-lain. Pada materi ini, kita akan menggunakan **Swing**.

## Swing
Swing adalah library GUI yang dikembangkan oleh Sun Microsystems. Swing menyediakan komponen-komponen GUI yang lebih fleksibel dan dapat diubah-ubah tampilannya. Swing juga mendukung pluggable look and feel, yang memungkinkan kita untuk mengubah tampilan GUI sesuai dengan keinginan kita. Swing juga mendukung MVC (Model View Controller) yang memungkinkan kita untuk memisahkan antara tampilan dengan logika program. Swing juga mendukung drag and drop, clipboard, dan lain-lain. Berikut adalah hirarki dari Swing:

![Hirarki Swing](image-1.png)

## Contoh Program
Berikut adalah contoh program sederhana dengan menggunakan Swing:

```java
import javax.swing.*;

public class App {
    public static void main(String[] args) {
        JFrame frame = new JFrame("My Swing App");
        JButton button = new JButton("Click Me");

        button.setBounds(50, 50, 100, 50);

        frame.add(button);
        frame.setSize(210, 180);
        frame.setLayout(null);
        frame.setVisible(true);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    }
}
```

Penjelasan:
- `JFrame frame = new JFrame("My Swing App");` digunakan untuk membuat frame dengan judul "My Swing App".
- `JButton button = new JButton("Click Me");` digunakan untuk membuat button dengan tulisan "Click Me".
- `button.setBounds(50, 50, 100, 50);` digunakan untuk mengatur posisi dan ukuran button.
- `frame.add(button);` digunakan untuk menambahkan button ke dalam frame.
- `frame.setSize(210, 180);` digunakan untuk mengatur ukuran frame.
- `frame.setLayout(null);` digunakan untuk mengatur layout frame.
- `frame.setVisible(true);` digunakan untuk menampilkan frame.
- `frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);` digunakan untuk menutup frame ketika tombol close ditekan.

Apabila program dijalankan, maka akan muncul jendela seperti berikut:

![App](image-2.png)
