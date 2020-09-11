In this playground, we will see about Java 8 Stream Map.

Stream's map method is intermediate operation and consumes single element forom input Stream and produces single element to output Stream.

It simply used to convert Stream of one type to another.

Let's see method signature of Stream's map method.

```java
<R> Stream<R>	map(Function<? super T,? extends R>mapper)
```
Map function applies the mapper function on input Stream and generates the output Stream.

Here mapper function is funtional interface which takes one input and provides one output.


# Welcome!

This Java template lets you get started quickly with a simple one-page playground.

```java runnable
// { autofold
public class Main {

public static void main(String[] args) {
// }

String message = "Hello World!";
System.out.println(message);

//{ autofold
}

}
//}
```


