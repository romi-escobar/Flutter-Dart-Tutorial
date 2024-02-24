## Control Flow Statements
* **_if & else_**
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


```
for (final object in flybyObjects) {
  print(object);
}

for (int month = 1; month <= 12; month++) {
  print(month);
}
```

```
while (year < 2016) {
  year += 1;
}
```