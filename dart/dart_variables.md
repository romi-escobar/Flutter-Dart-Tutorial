## Variables
* Variables store references.
* Because every variable in Dart refers to an object (an instance of a class) you can usually use constructors to initialize variables. Some of the built-in types have their own constructors.
<br><br>

`var` is used to declare a variable without explicitly specifying its type. Dart uses type inference to determine the variable's type based on the value it is assigned at the point of declaration (This process happens at compile-time, ensuring that the variable's type is always known to the compiler). Once the type is inferred, the variable's type is fixed, and it cannot be reassigned to a value of a different type later on.
```dart
var x = 5;          // `x` is inferred to be of type `int`.
var y = "Hello";    // `y` is inferred to be of type `String`.
var z = 3.14;       // `z` is inferred to be of type `double`.
```
<br>

`object` is used to declare a variable that could hold a value of any type at runtime.
Use it when you need a variable to hold different types of values or when you are working with APIs that can return multiple types.
```dart
object myVar = 42;      // myVar is currently an int
myVar = 'Hello, Dart!'; // Now it's a String
myVar = [1, 2, 3];      // Now it's a List of integers
```
<br>

`dynamic` tells the Dart analyzer and compiler that the type of a variable is not known at compile-time and can change during runtime. It can hold values of any type, and its type can change dynamically based on the value assigned to it.
```dart
dynamic dynamicVar = 42; // dynamicVar is inferred as an int
dynamicVar = 'Hello'; // dynamicVar is now inferred as a String
dynamicVar = [1, 2, 3]; // dynamicVar is now inferred as a List<int>
```
<br>

`late` is used to indicate that a non-nullable variable will be initialized later before it is used. It provides a way to defer the initialization of variables until the point where their values are known. 
```dart
late int myNumber;

void initializeNumber() {
  myNumber = 42; // Initializing `myNumber` before it is used
}

void main() {
  initializeNumber(); // Ensure `myNumber` is initialized before being used
  print(myNumber); // Using `myNumber` after initialization
}
```
<br>

`const` is used to declare compile-time constants. The value assigned to it must be known at compile-time. `const` variables are implicitly `final`, meaning they cannot be reassigned once initialized. 
<br><br>

`final` is used to declare variables whose values cannot be changed after they are initialized. The value assigned to it can be known at runtime. It can only be initialized once.
