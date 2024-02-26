## Class 
A `class` is a blueprint for creating objects.  
It defines the properties (attributes) and behaviors (methods) that objects of that class will have. Classes are fundamental to object-oriented programming (OOP) and are used to model real-world entities or abstract concepts in your code.

**_Class Declaration_**: use the `class` keyword followed by the class name and a pair of curly braces containing the class members (properties and methods). Class names typically follow the convention of starting with an uppercase letter.
* **_Properties_**: (also known as fields or attributes) are variables that belong to each instance of the class. They define the state of the object.
* **_Methods_**: are functions defined within a class that perform operations or provide functionality related to the class.  
* **_Constructors_**: special methods used for initializing objects when they are created. In Dart, a constructor with the same name as the class is a shorthand for initializing properties.
* **_Objects (Instances)_**: create objects (instances) of that class using the `new` keyword or by invoking the class constructor directly.

```dart
class MyClass {
  // Properties
  int myProperty;
  // Constructor
  MyClass(this.myProperty);
  // Methods
  void myMethod() {
    print('This is a method in MyClass');
  }
}

void main() {
  MyClass myObject = new MyClass(10);
  MyClass anotherObject = MyClass(20);       //(Dart 2.1 and later)

  print(myObject.myProperty); // Output: 10
  print(anotherObject.myProperty); // Output: 20 
}
```

**_Inheritance_**: allows that one class (subclass) to inherit properties and methods from another class (superclass).  
`extends` is a keyword used to indicate that one class (the subclass) is inheriting properties and methods from another class (the superclass). Subclasses can add new members, override existing ones, or use the inherited members directly.  
`super` is a keyword used to refer to the superclass from within the subclass. When you call `super()` in the constructor of a subclass, you're calling the constructor of the superclass. This allows you to initialize the inherited members of the superclass. It can also be used to access methods and properties of the superclass from within the subclass.
```dart
class SubClass extends MyClass {
  // Constructor
  SubClass(int myProperty) : super(myProperty);

  // Additional methods or overrides
}
```

**_Encapsulation_**: this means you can control the access to properties and methods of a class using access modifiers (`public`, `private`, and `protected`).
```dart
class MyClass {
  int _privateProperty; // Private property

  void _privateMethod() { // Private method
    print('This is a private method');
  }

  // Public method to access private property and method
  void accessPrivate() {
    print(_privateProperty);
    _privateMethod();
  }
}
```

**_Static Members_**: define static properties and methods that belong to the class itself rather than to individual instances.
```dart
class MyClass {
  static int staticProperty = 10; // Static property

  static void staticMethod() {    // Static method
    print('This is a static method');
  }
}
```

<br><br>

## Abstract Class
Abstract classes serve as blueprints for other classes. They cannot be instantiated directly but are meant to be subclassed. Abstract classes can contain abstract methods, which are methods declared without an implementation. Subclasses of abstract classes must provide implementations for all the abstract methods defined in the superclass. 
_Abstract classes are useful for defining a common interface or behavior that multiple classes can share._


**_Declaration:_** You declare an abstract class using the `abstract` keyword before the `class` keyword. Abstract classes can have abstract methods (methods without an implementation) or concrete methods (methods with an implementation).
* **Abstract Methods:** Abstract methods are declared without providing an implementation. They end with a semicolon instead of a method body. Subclasses must provide implementations for all abstract methods.
```dart
abstract class AbstractClass {
  void abstractMethod(); // Abstract method
  void concreteMethod() {
    print('Concrete method');
  }
}
```

**_Subclassing:_** You can extend an abstract class by subclassing it. Subclasses must either provide implementations for all abstract methods or be marked as abstract themselves.
```dart
class SubClass extends AbstractClass {
  @override
  void abstractMethod() {
    print('Implementation of abstract method');
  }
}
```

**_Instantiation:_** You cannot create an instance of an abstract class directly. Attempting to do so will result in a compilation error. However, you can create instances of concrete subclasses.
```dart
AbstractClass abstractObject = SubClass();
```

<br><br>

## @override
It's an annotation used to indicate that a method in a subclass is overriding a method with the same signature from its superclass. It is optional but highly recommended for clarity and to catch potential errors during compilation.
* **_Usage_**: place `@override` immediately above the method declaration in the subclass that is overriding a method from the superclass.
```dart
class SuperClass {
  void method() {
    print('SuperClass method');
  }
}

class SubClass extends SuperClass {
  @override
  void method() {
    print('SubClass method'); // Overriding the method from SuperClass
  }
}
```

* **_Purpose_**: It serves as a marker to explicitly indicate that a method is intended to override a method in the superclass.

* **_Safety_**: While not strictly required, using `@override` helps catch potential errors during compilation.

* **_Documentation_**: It serves as documentation, making it clear to other developers that the method is overriding a method from the superclass.

<br><br>

## Custom Operators
Dart allows you to override operators within your classes to provide custom behavior for existing operators when they're used with instances of your classes.  
To override an operator, you define a method in your class with a special name that Dart recognizes as the operator you want to override.<br>  
List of Overridable Operators:
* Arithmetic operators: `+`, `-`, `*`, `/`, `%`, `~/`
* Relational operators: `<`, `>`, `<=`, `>=`, `==`
* Unary operators: `-`, `~`
* Type test operators: `as`, `is`, `is!`
* Bitwise operators: `&`, `|`, `^`, `~`, `<<`, `>>`, `>>>`
* Assignment operators (indirectly by overriding the corresponding binary operator): `+=`, `-=`, etc.
* Indexing operators: `[]`, `[]=`
* The call method: `call()` 
```dart
class Vector {
  final int x, y;

  Vector(this.x, this.y);

  // Overriding the + operator
  Vector operator +(Vector other) {
    return Vector(x + other.x, y + other.y);
  }
}

final v1 = Vector(1, 2);
final v2 = Vector(3, 4);
final v3 = v1 + v2; // Uses the overridden + operator.
```

**_Example: Overriding `==` and `hashCode`_**  
When you override the equality operator `==`, you should also override the `hashCode` getter to maintain consistency. This is because Dart uses `hashCode` to compare objects in collections like sets and maps.
This example ensures that `Person` instances with the same name are considered equal and have the same hash code.
```dart
class Person {
  final String name;

  Person(this.name);

  @override
  bool operator ==(Object other) =>
      identical(this, other) ||
      other is Person &&
          runtimeType == other.runtimeType &&
          name == other.name;

  @override
  int get hashCode => name.hashCode;
}
```

<br><br>

## Extensions 
An extension allows you to add functionalities to existing classes without modifying them or creating a subclass. This is particularly useful for adding new methods or getters to classes from a third-party library, or for any class that you don't have the ability to change directly. Extensions can be applied to any type, including built-in types like `String`, `List`, `int`, etc.

* **_Define an Extension_**: use the `extension` keyword followed by the name of the extension and the `on` keyword to specify the type you're extending. Then, within curly braces `{}`, you define the new functionalities.  
After defining an extension, you can use it just like any other method on the type you've extended. Using the `StringExtension` from above:
```dart
extension StringExtension on String {
  // Adds a method to the String class that repeats the string n times.
  String repeat(int times) => this * times;
}

void main() {
  String message = "Hello";
  print(message.repeat(3)); // Prints "HelloHelloHello"
}
```
* Extensions are scoped. They must be imported to be used if they are defined in a different file.
* If the class already has a method with the same name as an extension method, the class's own method takes precedence.
* Extensions can't add properties or methods to the type itself (static methods or properties). They can only add instance level functionalities.
* Inside an extension method, the `this` keyword refers to the instance of the object on which the extension method is called. Dart is aware of the type, so you can use all the properties and methods of the extended type without explicit casting.

<br><br>


## Factory Constructors ??

<br><br>

## Class Cluster ??



