## Introduction
* Every app requires the **_top-level `main()` function_**, where execution starts. 
* Functions that don't explicitly return a value have the **_`void` return type_**.
* Every dart instruction should end with a semicolon ";"


## Important Definitions
* **_Compile-time_**: refers to the period when your code is being translated from human-readable source code into machine-executable instructions. Any errors detected during compile-time are known as compile-time errors.

* **_Runtime_**: refers to the period when your compiled program is executed by the computer's processor The compiled code is loaded into memory and executed instruction by instruction. Program state, such as variable values and object instances, is manipulated during runtime. Any errors or exceptions that occur during program execution are known as runtime errors.

* **_Dot Notation (`.`)_**: is used to access an object's properties or to call its methods.
  * **Properties:** Access or modify the properties of an object.
    ```dart
    var person = Person(name: 'Alice', age: 30);
    print(person.name); // Accessing property
    person.age = 31; // Modifying property
    ```
  * **Methods:** Invoke methods on an object to perform actions.
    ```dart
    person.describe(); // Calling a method
    ```
  * **Chaining:** Dot notation can be chained to access properties or methods in a sequence.
    ```dart
    var manager = company.getManager().getManagerName();
    // getManager() is a method call that returns an object
    // getManagerName() is called on the returned object
    ```

* **_Comments_**: 
```
// This is a normal, one-line comment.

/// This is a documentation comment, used to document libraries,
/// classes, and their members. Tools like IDEs and dartdoc treat
/// doc comments specially.

/* Comments like these are also supported. */
```

## Keywords
