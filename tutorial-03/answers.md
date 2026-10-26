# Tutorial 3 Flow of Control (Selection)
## 1. Write statements for each of the following
### a. Determine whether 3x8=27
```java
if (3  *  8  ==  27) {
	System.out.println("3x8 is equal to 27");
} else{
	System.out.println("3x8 is not equal to 27");
}
```

### b. Determine whether an input integer is an odd number or even number
```java 
public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    
    System.out.print("enter a number : "); 
    int i = input.nextInt();
    if (i % 2 == 0) {
        System.out.println( i + "is even");
    } else{
        System.out.println( i + " is odd");
    }

}
```

### c. Determine whether a character is a capital letter
```java 
Scanner input = new Scanner(System.in);
    
    System.out.print("enter a character : "); 
    char c = input.next().charAt(0);
    
    if (Character.isUpperCase(c)) {
        System.out.println( c + " is uppercase");
    } else{
        System.out.println( c + " is lowercase");
    }
```

### d. Display two strings in alphabetical order ignoring their case
```java
if (s1.compareToIgnoreCase(s2) <= 0) {
        System.out.println(s1 + " " + s2);
} else {
        System.out.println(s2 + " " + s1);
}
```

### e. A switch statement that display Sunday, Monday, .., Satudary if the input is 0, 1, …, 6
```java
switch (day) {
        case 1:
            IO.print("Monday");
            break;

        case 2:
            IO.print("Tuesday");
            break;

        case 3:
            IO.print("Wednesday");
            break;

        case 4:
            IO.print("Thursday");
            break;

        case 5:
            IO.print("Friday");
            break;
        case 6:
            IO.print("Saturday");
            break;
        default:
            IO.print("Invalid day");
    }
```

## 2. Correct the error for the following statements
### a. `if (num1 = num2) System.out.println("Number 1 is equal to number 2.");`
Correct answer : 
```java
if (num1 == num2)
        System.out.println("Number 1 is equal to number 2.");
```
use `==` to compare

### b. if (x > y > z) System.out.println("x is the largest number");
Correct answer : 
```java
if (x > y && x > z) {
        System.out.println("x  is the largest number");
 ```
 Combine two comparisons with  `&&` 
### c. 
```java
String s1, s2;
if (s1==s2)
 System.out.println("They are equal strings.");
else (s1!=s2)
 System.out.println("They are not equal strings.");
```
Correct answer : 
```java
String s1 = "woof", s2 = "woof";
if (s1.equals(s2))
    System.out.println("They are equal strings.");
else
    System.out.println("They are not equal strings.");
```
s1 and s2 must be given values before they are read, use `equals` to compare string content, and `else` doesn't take a condition

### d. 
```java
if x>0 or y>0; 
	System.out.println("Either x or y is positive");
```
Correct answer : 
```java
if (x > 0 || y > 0)
    System.out.println("Either x or y is positive");
```
Condition needs parentheses and use `||` as OR

## 3. Write the output for the following statements when x=9 and y=10
### a. 
```java
if (x < 10)
if (y > 10)
System.out.println("*****");
else
System.out.println("#####");
System.out.println("$$$$$");
```
the output : 
`#####`
`$$$$$`
### b.
```java
if (x < 10) {
if (y < 10)
System.out.println("*****");
else{
System.out.println("#####");
```
The output : 
`#####`
`$$$$$`

### c.
```java
if (x < 10) {
if (y < 10)
System.out.println("*****");
System.out.println("#####");
}
else {
System.out.println("$$$$$");
}
```
The output : 
`#####`

### d. 
```java
if (x > 10) {
if (y > 10) {
System.out.println("*****");
System.out.println("#####"); }
else
System.out.println("$$$$$");
}
```
The output : nothing. since x > 10 is `false`so the whole block is skipped

## 4. Find the biggest number among three given integers
```java
    Scanner input = new Scanner(System.in);
    System.out.print("Enter three integers: ");
    int first = input.nextInt();
    int second = input.nextInt();
    int third = input.nextInt();

    int biggest = first;
    if (second > biggest) {
        biggest = second;
    }
    if (third > biggest) {
        biggest = third;
    }
    System.out.println("The biggest number is " + biggest);
```

## 5. Determine whether the Leap year (divisible by 4 but not 100. However, also divisible by 400)
```java
    Scanner keyboard = new Scanner(System.in);
    System.out.print("Enter a year: ");
    int year = keyboard.nextInt();

    boolean isLeap = (year % 4 == 0 && year % 100 != 0) || year % 400 == 0;
    if (isLeap) {
        System.out.println(year + " is a leap year");
    } else {
        System.out.println(year + " is not a leap year");
    }
```