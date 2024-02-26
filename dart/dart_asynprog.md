## Asynchronous Programming
They allow you to perform tasks that might take time to complete, such as I/O operations or network requests, without blocking the execution of your code.<br><br>


### Future
`Future` is an object representing a potential value or error that will be available at some point in the future.  
It allows you to execute code asynchronously and receive the result when it becomes available.  
A Future can complete with a value (success) or an error (failure). You can attach callbacks to a Future to handle its completion or error states using methods like `.then()`, `.catchError()`, or `.whenComplete()`.

### async
`async` is used to mark a function as asynchronous. An asynchronous function can perform asynchronous operations, such as awaiting Futures, without blocking the execution of other code.  
Async functions can contain `await` expressions, which pause the execution of the function until a Future completes.  
Async functions always return a Future, even if you don't explicitly return one. Dart automatically wraps the function's return value in a Future.

### await
`await` is used inside an async function to pause its execution until a Future completes.  
It allows you to work with asynchronous code in a synchronous-like manner, making asynchronous code easier to read and write.
- Await can only be used inside async functions.
- When you `await` a Future, the async function is paused until the Future completes, and then resumes with the result of the Future.
- Await can be used with any object that implements the Future interface, not just Future instances.

### Example:

```dart
// fetchUserData is an asynchronous function that returns a Future.
Future<int> fetchUserData() async {
  // Simulate a network request with a 2-second delay
  await Future.delayed(Duration(seconds: 2));
  return 42; // Simulated user data
}

void main() async {
  print('Fetching user data...');
  try {
    //`await fetchUserData()` pauses the execution of `main` until the Future returned by `fetchUserData` completes.
    var userData = await fetchUserData();
    print('User data: $userData');
  } catch (error) {
    print('Error fetching user data: $error');
  }
  print('End of program');
}
```
<br><br>

## Streams
`Stream` carries data. The data doesn't come all at once but arrives over time. You can "watch" the stream and react to each piece of data as it comes.
Streams are perfect when you're dealing with data that arrives over time, like user input (like key presses or mouse clicks), notifications from a web server, reading files that are too large to fit into memory all at once

**_Listening to a Stream_**  
To use a Stream, you "listen" to it. You do this with the `.listen()` method. When you catch something, you can decide what to do with it.
```dart
stream.listen((data) {
  print("I got this from the stream: $data");
});
```
**_Creating Streams_**
* **From a List**: If you have a list of items, you can turn it into a stream, letting each item flow one by one.
```dart
var dataStream = Stream.fromIterable([1, 2, 3, 4, 5]);
```
* **From Future**: If you have a Future (a single piece of data that will be available later), you can turn it into a stream too.
```dart
var futureStream = Stream.fromFuture(Future.value('Hello!'));
```
* **Manually**: Sometimes, you want to control when and what data flows through the stream. You can use a `StreamController` for that.
```dart
var controller = StreamController();
controller.sink.add('This is a manually added event');
controller.close(); // Don't forget to close it when you're done!
```

**_Handling Stream Events_**
When you listen to a stream, you can handle three types of events:
* **Data Events**: When data arrives (the `.listen()` part).
* **Error Events**: When something goes wrong.
* **Done Events**: When the stream is finished and no more data will arrive.

**_Transforming Streams_**
Streams can be transformed.
```dart
dataStream.where((item) => item % 2 == 0).listen((data) {
  print("Even number: $data");
});
```
