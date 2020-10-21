In this playground, we will see about Java 8 Stream Map.

<a href="https://java2blog.com/java-8-stream/" target="_blank" rel="noopener noreferrer">Java 8 Stream</a>'s map method is intermediate operation and consumes single element forom input Stream and produces single element to output Stream.

It simply used to convert Stream of one type to another.

Let's see method signature of Stream's map method.

```java
<R> Stream<R>	map(Function<? super T,? extends R>mapper)
```
Map applies the mapper function on input Stream and generates the output Stream.

Here mapper function is <a href="https://java2blog.com/java-8-functional-interface-example/" target="_blank" rel="noopener noreferrer">functional interface</a> which takes one input and provides one output.

![Stream map](https://java2blog.com/wp-content/uploads/2020/10/StreamMap.jpg)

Let's understand with the help of example.

Create a class named Student which will have two attributes name and age.
```java
package org.tech.io;

public class Student {
	
	String name;
	int age;
	
	public Student(String name, int age) {
		super();
		this.name = name;
		this.age = age;
	}
	
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public int getAge() {
		return age;
	}
	public void setAge(int age) {
		this.age = age;
	}
}

```
Create main class named StreamMapMain.java
```java
package org.tech.io;
 
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;
 
public class StreamMapMain {
 
	public static void main(String args[])
	{
		List<Student> listOfStudents = createListOfStudents();
		
		// Using map function to convert Stream<Student> to Stream<String>
		List<String> listOfStudentNames=listOfStudents.stream()
										.map(s -> s.getName()) 
										.collect(Collectors.toList());
		listOfStudentNames.forEach(System.out::println);
	}		
	
	public static List<Student> createListOfStudents()
	{
		List<Student> listOfStudents=new ArrayList<>();
		Student s1= new Student("Anchit",20);
		Student s2= new Student("Peter",19);
		Student s3= new Student("Martin",22);
		Student s4= new Student("Sam",21);
		listOfStudents.add(s1);
		listOfStudents.add(s2);
		listOfStudents.add(s3);
		listOfStudents.add(s4);
		return listOfStudents;
	}
}
 
```
When you will run above program, you will get below output:
<pre>
Anchit
Peter
Martin
Sam
</pre>
As you can see, we have used map to convert Stream<Student> to Stream<String> to retrieve list of student Names.

You can use <a href="https://java2blog.com/java-8-method-reference/" target="_blank" rel="noopener noreferrer">method reference</a> as below
```java
List<String> listOfStudentNames=listOfStudents.stream()
										.map(Student::getName()) 
										.collect(Collectors.toList());
```

Other Java 8 tutorials you may also like:
<ul>
<li><a href="https://java2blog.com/java-8-tutorial/" target="_blank" rel="noopener noreferrer">Java 8 tutorial</a></li>
<li><a href="https://java2blog.com/java-8-parallel-stream/" target="_blank" rel="noopener noreferrer">Java 8 Parallel Stream</a></li>
<li><a href="https://java2blog.com/java-8-interview-questions/" target="_blank" rel="noopener noreferrer">Java 8 interview questions</a></li>
<li><a href="https://java2blog.com/lambda-expressions-in-java-8/" target="_blank" rel="noopener noreferrer">Java 8 lambda expression</a></li>
</ul>

