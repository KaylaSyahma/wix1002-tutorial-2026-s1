# Tutorial 2 Java Fundamental

## 1. Display the sentence Faculty of Computer Science and Information Technology

### a. one line using multiple Java statements

```java
System.out.print("Faculty of ");
System.out.print("Computer Science and ");
System.out.println("Information Technology");
```

### a. multiple line using one line Java statements

```java
System.out.println("Faculty of\nComputer Science and\nInformation Technology");
```

## 2. Print "SDN" - Software-defined networking

```java
System.out.println("\"SDN\" - Software-defined networking");
```

## 3. Correct The Errors

### a. `System.Println("Java Programming");`

Correct answer : `System.out.println("Java Programming");`, `out` is missing and `println` starts with uppercase P.

### b. `System.in.println("Introduction to Java!")`

Correct answer : `System.out.println("Introduction to Java!");`, use `out` instead of `in` and always end a statement with a semicolon

### c. `System.out.println("\t is the horizontal tab character");`

Correct answer : `System.out.println("\\t is the horizontal tab character");`, the error is already correct if u want to print `\t` as an actual tab, but use double backslash if u want to show the `\t` in the text

### d. `system.out.println("Java is case sensitive!" );`

Correct answer : `System.out.println("Java is case sensitive!" );`, the `System` must begin with uppercase S

## 4. Write statements for each of the following

### a. Declare a variable that used to store the value of a matric number

```java
String matricNumber;
```

### b. Declare a variable that used to store the value of π

```java
double pi;
```

### c. Initialize a variable named M with the value set to false

```java
boolean M = false;
```

### d. Initialize a variable named P with the value set to 8800000000.

```java
long P = 8800000000L;
```

### e. Initialize a variable named letter with the value set to U.

```java
char letter = 'U';
```

### f. Declare a constant variable named PRO. The value of the constant variable is Java

```java
final String PRO = "Java";
```

## 5. Correct the error

**a. final double AMOUNT = "32.5";  
 AMOUNT += 10;
System.out.println("The amount is " + AMOUNT);**

```java
double AMOUNT = 32.5;
AMOUNT += 10;
System.out.println("The amount is " + AMOUNT);
```

Correction : `32.5` isn't a string, and remove `final` because its value is changed
\
**b. string chapter = 'Summary';
System.out.println(chapter);**

```java
String chapter = "Summary";
System.out.println(chapter);
```

Correction : `String` uses an uppercase S and use double quotation marks for text

**c. int num;
++num++;
num1 = num;**

```java
int num = 0;
num++;
num1 = num;
```

Correction = `++num++` is invalid, and `num` must also be assigned a value before its is used

**d. int num = 3000;
System.out.printf("%4.2f\n", num);**

```java
int num = 3000;
System.out.printf(java.util.Locale.US, "%4.2f%n", (double) num);
```

Correction : `%f` requires a supported floating-point argument; passing this int compiles but throws IllegalFormatConversionException when run. Casting fixes it. 4 is a minimum width: 3000.00 is longer and prints fully

**e. String contact;
Scanner keyboard = new Scanner(System.out);
contact = keyboard.nextLine();**

```java
import java.util.Scanner; // At the top of the source file

Scanner keyboard = new Scanner(System.in);
String contact = keyboard.nextLine();
```

Correction : `System.out` does not match a Scanner constructor and must use `System.in` to receive keyboard input. Import Scanner before the class declaration.

## 6. Print the circumference of a circle. The input is diameter. Display the result in three decimal places.

Diameter : 11.8
the circumference of the circle : 37.071

```java
import java.util.Scanner;
import java.util.Locale;

public class CircleArea {
    public static void main(String[] args) {
        Scanner keyboard = new Scanner(System.in).useLocale(Locale.US);

        System.out.print("Diameter : ");
        double diameter = keyboard.nextDouble();

        double circumference = Math.PI * diameter;

        System.out.printf(Locale.US,
            "the circumference of the circle : %.3f%n",
            circumference);
    }
}
```

## 7. Convert inches to meters (1 inch = 2.54cm)

Enter value in inch = 20.17
20.17 inches = 0.51 meters

```java
import java.util.Scanner;
import java.util.Locale;

public class InchToMeter {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in).useLocale(Locale.US);

        System.out.print("Enter value in inch = ");
        double inch = input.nextDouble();

        double meter = inch * 2.54 / 100;

        System.out.printf("%.2f inches = %.2f meters%n", inch, meter);
    }
}
```
