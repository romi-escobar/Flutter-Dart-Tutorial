## Operators Based on Their Position Relative to Operands
* **_Prefix Operators_**
They are placed before their operand. Common prefix operators are `-`, `++` and `--` operators, they negate a value or increase-decrease a value by one. These operators perform the operation and return the new value. 

* **_Infix Operators_**
They are placed between their operands and are the most common type of operators. They include arithmetic operators,  (`+`, `-`, `*`, `/`), relational operators (`==`, `!=`, `<`, `>`, `<=`, `>=`), and logical operators (`&&`, `||`). Infix operators require two operands to operate upon.

* **_Postfix Operators_**
They are placed after their operand. Common postfix operators are `++` and `--` operators, they increase or decrease a value by one. These operators first return the current value of the operand and then perform the increment or decrement operation.

## Operators Based on Their Functionality
### Arithmetic Operators

`+` Addition: Adds two numbers.
`-` Subtraction: Subtracts the second number from the first.
`-expr` Unary minus, also known as negation (reverse the sign of the expression).
`*` Multiplication: Multiplies two numbers.
`/` Division: Divides the first number by the second number, resulting in a double.
`~/` Division returning an integer result by truncating the remainder.
`%` Modulo: Returns the remainder of the division.

### Equality and Relational Operators

`==` Equal: Checks if two values are equal.
`!=` Not equal: Checks if two values are not equal.
`>` Greater than: Checks if the value on the left is greater than the value on the right.
`<` Less than: Checks if the value on the left is less than the value on the right.
`>=` Greater than or equal to: Checks if the value on the left is greater than or equal to the value on the right.
`<=` Less than or equal to: Checks if the value on the left is less than or equal to the value on the right.

### Logical Operators

`!` NOT: Inverts the boolean value.
`&&` AND: Returns true if both operands are true.
`||` OR: Returns true if at least one of the operands is true.

### Type Test Operators

`as` Typecast: Used to cast an object to a particular type.
`is` Type test: True if the object has the specified type.
`is!` Not type test: True if the object does not have the specified type.

### Assignment Operators

`=` Assign: Assigns the value on the right to the variable on the left.
`??=` Assign the value only if the variable is null.
`+=`, `-=`, `*=`, `/=`, `~/=`, `%=`: Compound assignment operators that perform an operation on the variable and assign the result back to the variable.

### Increment and Decrement Operators

`++var` Pre-increment: Increments the variable by 1, then returns the value.
`var++` Post-increment: Returns the value of the variable, then increments it by 1.
`--var` Pre-decrement: Decrements the variable by 1, then returns the value.
`var--` Post-decrement: Returns the value of the variable, then decrements it by 1.

### Conditional Operator

`condition ? expr1 : expr2` Ternary operator: Returns `expr1` if the condition is true, and `expr2` if the condition is false.

### Cascade Operator

`..` Cascade: Allows you to perform a sequence of operations on the same object.

### Null-aware Operators

`?.` Null-aware access: Accesses a property or calls a method on an object only if the object is not null.
`??` Null coalescing: Returns the expression on the left if it's not null, otherwise returns the expression on the right.
`??=` Null-aware assignment: Assigns the value on the right to a variable only if that variable is currently null.
