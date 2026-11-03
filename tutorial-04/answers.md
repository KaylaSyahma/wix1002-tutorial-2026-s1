# Tutorial 4 Flow of Control (Repetition)
## 1. Write statement for each of the following
### a. Find the largest integer so that n^3 is less than 2000
```java
int n = 0;
// use n+1 to check the next integer value so n is the last value that passed
while ((n+1) * (n+1) * (n+1) < 2000) {
	n++;
}
System.out.println("the largest integer is : " + n);
```

### b. Display the square number of the first twelve integers starting from 1
```java
for (int i = 1; i <= 12; i++){
	System.out.println(i + "squared = " + i * i);
}
```
### c. Display a 4-by-5 matrix using random number within 0 to 100
```java
Random random = new Random(); 
for (int row = 1; row <= 4; row++) { 		// 4 rows
    for (int col = 1; col <= 5; col++) { 		// 5 columns in each row
        System.out.printf("%5d", random.nextInt(101));   // 0 to 100, "%5d" -> right-aligns each number in five characters
    }
    System.out.println();      // end the row
}
```
### c.  Sum from 1 to a given number 
```java
Scanner keyboard = new Scanner(System.in);
System.out.print("Enter a number: ");
int number = keyboard.nextInt();
int sum = 0;

for (int i = 1; i <= number; i++) {
	   sum += i; // adding the value i to the existing sum
}
System.out.println("Sum of 1 to " + number + " = " + sum);
```

### d. Compute the sum of the series : 1/25 + 2/24 +3/23 … + 25/1 in two decimal places
```java
double sum = 0;
for (int i = 1; i <= 25; i++) {
    sum += (double) i / (26 - i);   // divide i by 26 - i
}
System.out.printf("Sum = %.2f%n", sum);   // %.2f -> rounds the display to two decimal places
```

## 2. Correct the error for the following statements
### a. 
```java
for (x = 10; x > 0; x++)
sum += x;
```
Correction : 
```java
int sum = 0;
for (int x = 10; x > 0; x--)
    sum += x;
```
declare and initialise x and sum. Using `x++` will make an infinite looping because every number will be > 0. 

### b. 
```java
do
    x += 2;
    y += x;
    System.out.println(x + " and " + y);
while (x < 100)
```
Correction:
```java
int x = 0, y = 0;
do {
    x += 2;
    y += x;
    System.out.println(x + " and " + y);
} while (x < 100);
```
a function budy of more than one statement needs braces. end the while statement with a semicolon

### c. 
```java
for ( x==1, y==20; x < y, x++, y-=2);
System.out.println(x & " " & y);
```
Correction:
```java
int x, y;
for (x = 1, y = 20; x < y; x++, y -= 2)
System.out.println(x + " " + y);
```
to assign a value use `=` instead of `==`. The tree parts inside the braces are separated by semicolon. semicolon after the header makes an empty body. use `+` instead of `&`.

### d. 
```java
i =1;
while(i<10) {
    if (i==10)
        System.out.println("Program End");
}
```
Correction:
```java
int i = 1;
while (i <= 10) {
    if (i == 10)
        System.out.println("Program End");
    i++;
}
```
`i` was never updated so the loop never ends. with i < 10, the "program end" could never print.

## 3. Write the statement that display the first ten values of the fibonacci sequence. given the formula f1 = 1, f2 = 1, fn = fn−1 + fn−2.

```java
int previous = 1, current = 1;       // f1 and f2
System.out.print(previous + " " + current);
for (int n = 3; n <= 10; n++) {
    int next = previous + current;   // fn = fn-1 + fn-2
    System.out.print(" " + next);
    previous = current;              // slide the window forward
    current = next;
}
System.out.println(); 
```

### 4. Display the string in reverse order
```java
Scanner keyboard = new Scanner(System.in);
System.out.print("Enter a string: ");
String text = keyboard.nextLine();

String reversed = "";
for (int i = text.length() - 1; i >= 0; i--) {
       reversed += text.charAt(i);
}
System.out.println("Reverse: " + reversed);
```