## Important Keywords
`return` is used to exit a function and optionally return a value to the caller. When a `return` statement is encountered in a function, it immediately terminates the function's execution and returns control to the caller.

`break` is used to exit a loop or a switch statement prematurely. When a `break` statement is encountered, it immediately terminates the loop or switch statement in which it appears, and control is transferred to the statement immediately following the loop or switch.


<br><br>

## Control Flow Statements
**_if & else_**  
They are conditional statements used for making decisions in your code based on certain conditions. These statements allow your program to execute different blocks of code depending on whether a condition is true or false.
* **if Statement**: If the condition evaluates to true, the code inside the `if` block is executed. If the condition is false, the code inside the `if` block is skipped.
```dart
if (condition) {
  // Code to execute if condition is true
}
```

* **if-else Statement**: If the condition in the `if` statement is true, the code inside the `if` block is executed. Otherwise, the code inside the `else` block is executed.
```dart
if (condition) {
  // Code to execute if condition is true
} else {
  // Code to execute if condition is false
}
```

* **if-else if-else Statement**: allows you to check multiple conditions sequentially and execute different blocks of code based on which condition is true. You can have multiple `else if` blocks between the initial `if` and final `else` block.
```dart
if (condition1) {
  // Code to execute if condition1 is true
} else if (condition2) {
  // Code to execute if condition2 is true
} else {
  // Code to execute if none of the conditions are true
}
```

* **_Nested if Statements_**: You can nest `if` statements inside other `if` statements to create more complex conditional logic.

<br><br>

## switch   
Allows you to efficiently handle multiple cases based on the value of a single expression.
Syntax:
* `switch`: Keyword indicating the start of the switch statement.
* `expression`: The value being evaluated.
* `case`: Keyword indicating a case label followed by a value.
* `value1`, `value2`, etc.: Possible values that `expression` can match.
* `break`: Keyword to end the execution of the switch statement. If omitted, execution will continue to the next case.
* `default`: Optional label used when none of the cases match `expression`. It's similar to the `else` block in an if-else statement.
```dart
// Syntax
switch (expression) {
  case value1:
    // Code to execute if expression equals value1
    break;
  case value2:
    // Code to execute if expression equals value2
    break;
  // Add more cases as needed
  default:
    // Code to execute if expression doesn't match any case
}
```


