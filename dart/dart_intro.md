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

* **_PascalCase_**:
* **_camelCase_**:

* **_Comments_**: 
```
// This is a normal, one-line comment.

/// This is a documentation comment, used to document libraries,
/// classes, and their members. Tools like IDEs and dartdoc treat
/// doc comments specially.

/* Comments like these are also supported. */
```

## Generics 
They enable you to write classes, interfaces, and functions that work with any type, without losing the type information. Generics are often used with collections (like lists, sets, and maps) to specify the type of items they contain, but they can also be used to define the type of parameters, return types, and more in custom classes and methods.

#### Generics in Classes

You can define a generic class by appending `<T>` (or any other placeholder name) to the class name. `T` is a type variable, a placeholder for the actual type that will be specified when the class is instantiated.

```dart
class Box<T> {
  T value;

  Box(this.value);
}

void main() {
  var boxInt = Box<int>(123);
  var boxString = Box<String>('Hello');
}
```

#### Generics in Functions

Similarly, you can define generic functions with type parameters:

```dart
T first<T>(List<T> list) {
  return list[0];
}

void main() {
  int firstInt = first<int>([1, 2, 3]);
  String firstString = first<String>(['a', 'b', 'c']);
}
```

#### Generics in Interfaces and Mixins

Generics can also be applied to interfaces and mixins to make them more flexible:

```dart
abstract class Cache<T> {
  T getByKey(String key);
  void setByKey(String key, T value);
}
```

### Bounded Types

You can restrict the types that can be used with your generics by specifying bounds:

```dart
class NumberBox<T extends num> {
  T value;

  NumberBox(this.value);
}

void main() {
  var boxInt = NumberBox<int>(123);
  var boxDouble = NumberBox<double>(3.14);
  // var boxString = NumberBox<String>('Hello'); // This will cause a compile-time error
}
```

In the example above, `T extends num` means that `T` can be any type that is a subtype of `num` (like `int` or `double`), ensuring `NumberBox` can only be instantiated with numeric types.



