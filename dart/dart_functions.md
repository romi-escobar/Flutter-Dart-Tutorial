## Functions
Functions are a fundamental building block of the language, allowing you to encapsulate and reuse blocks of code.

* **_Function Declaration_**  
```dart
// Function declaration
returnType functionName(type paramName1, type paramName2, ...) {
    // Function body
    return value; // Return statement
}
```

* **_Function Parameters_**  
   Functions can take zero or more parameters. They are variables that represent the data passed to the function when it is called.

* **_Return Type_**  
   Functions in Dart can return a value of a specified type or `void` if they do not return anything.  before the function name.

* **_Function Invocation_**  
   To invoke or call a function in Dart, you use its name followed by parentheses `()`, optionally passing arguments inside the parentheses if the function expects parameters.
```dart
functionName(arguments);
```

* **_Arrow Functions, "fat arrow" or "lambda" expressions_**  
Provide a concise syntax for defining simple, one-liner functions. Useful for functions that contain a single expression and have a single line of code in their body. 
Arrow functions can also be used for functions with no parameters or functions that return void.
The `=>` symbol separates the parameter list from the function body. The expression is evaluated and returned as the result of the function. The return type of the function is inferred from the context or explicitly specified before the function name.
```dart
returnType functionName(parameters) => expression;

//Example
// Arrow function with parameters
int add(int a, int b) => a + b;
// Arrow function with no parameters
void sayHello() => print('Hello, Dart!');
```

* **_Anonymous Functions (Closures)_**  
They are functions that are defined without a name.  
You can specify zero or more "parameters" inside the parentheses, just like with named functions. The "function body" contains the statements or expressions that make up the function's logic. Anonymous functions end with a semicolon (`;`). This is because anonymous functions are expressions. 
```dart
// Syntax
(parameters) {
  // Function body
};

// Passing Functions as Arguments
var numbers = [1, 2, 3, 4, 5];
var doubled = numbers.map((number) => number * 2);

// Event Handling, such as button clicks or mouse movements.
button.onClick.listen((event) {
  print('Button clicked!');
});

// Callback Functions, when working with asynchronous code
fetchDataFromServer((data) {
  print('Data received: $data');
});
```

* **Optional Parameters**  
They allow you to define functions with parameters that may or may not be provided when the function is called.
    * **Named Parameters**: are specified by name when calling the function. They are enclosed in curly braces `{}` in the function declaration. They are useful when a function has multiple optional parameters, and you want to specify which parameter is being passed explicitly.
    ```dart
    void greet({String name = 'World'}) {
    print('Hello, $name!');
    }

    greet(); // Output: Hello, World!
    greet(name: 'Alice'); // Output: Hello, Alice!
    ```
    * **Positional Parameters**: are specified by their position when calling the function. They are enclosed in square brackets `[]` in the function declaration. They are useful when you want to define optional parameters without specifying their names explicitly.  
    ```dart
    void printNumbers(int a, [int? b, int? c]) {
    print('a: $a, b: $b, c: $c');
    }

    printNumbers(1); // Output: a: 1, b: null, c: null
    printNumbers(1, 2); // Output: a: 1, b: 2, c: null
    printNumbers(1, 2, 3); // Output: a: 1, b: 2, c: 3
    ```

* **_Function Expressions or nested functions_**  
   Define functions within other functions. These inner functions have access to variables declared in the outer function's scope.
```dart
void outerFunction() {
    int outerVar = 10;
    void innerFunction() {
    print(outerVar);
    }
    innerFunction();
}
```


## Top-level Functions
`main()`  
`print()`