An exception is an error caused when there is unwanted behavior in a program that causes it to halt. At this point I have dealt with many errors that throw exceptions.

When an exception occurs at runtime a special type of object known as a exception object is create and stored in memory. This process is known as throwing an exception and it causes the program to terminate. Unless there is code written to handle the exception. 

When an exception is thrown a message is displayed on the console, this is an example.
```java
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException:
			Index 3 out of bounds for length 3
			at BadArray.main(BadArray.java:15)
```

This is how you read it:
- First line indicates the name of the exception, in this case, ArrayIndexOutOfBoundsException
	- The exception is an instance of the ArrayIndexOutOfBoundsException in the java.lang package
- The second line is what caused the error, 3 is an a invalid index for an array of length 3
- The third line is where the exception occurred, in this case on line 15

**Note:** Some errors are not programmer fault and can be handled. Some errors don't need to be "handled" in the traditional sense but good program architure can eliminate them. 

An example of this is if a program is implementing the Scanner class and using the nextInt(); method to read from a file. If the value cant be saved as an integer then the program will throw a ImputMismatchException. 

In order to handle an error like this you must write a section of code known as an exception handler. An exception handler catches and responds to an error in the way a programmer wants, if you don't write an exception handler then java will call the default exception handler which prints a message like the one we saw above then halts the program. 

# Handling an Exception with a *try* Statement

We have seen try blocks before in python, they are similar in java. The general format is as follows:
```java
try{
	// try block statements...
}
catch (ExceptionType variable ){
	// catch block statemnts...
}
```

**Note:** in order to properly handle exceptions you must import the class that the error is in to properly handle the Exception. That statement would look like this:
```java
java.util.InputMismatchException;
```

**Note:** you can handle more than one exception in one catch block just separate each block by a pipe (the logical or operator a.k.a '|' )
```java
try{
	// try block statements...
}
catch (ExceptionType variable | IOException | inputMismatchedException ){
	// catch block statemnts...
}
```
# Exception classes
There is an extensive hierarchy of classes in the java API that allows for Exceptions to be thrown and handled, here is a small part of that hierarchy:

![The flowchart describes IOException, and RunTimeException classes in the Java class hierarchy.](https://cite-media.pearson.com/legacy_paths/68af68d2-5d78-4692-8d08-3a50a765822e/FG_11_003_NEW.png "Figure 11-3 click to zoom")

Classes that are inherited from the Error class are exceptions that occur when a critical error occurs that is not necessarily the fault of the programmer, this could occur in the API or the JVM. Classes inherited from the exception class are non terminal programmer errors.

## Exceptions can be handled polymorphically
In a catch block you can utilize the hierarchy of the tree above to catch Exceptions that are derived. For example if you wanted to catch FileNotFoundError and EOFException you could put "IOException" in the catch variable declaration and it would know how to handle both cases. 

# Understanding the Stack Trace / Call Stack
When a method throws an error sometimes it has to be passed through many other methods before the program is fully halted. For example Method A calls Method B which calls method C which prints the Exception message to the console. The last lines of the Exception message are whats known as the Stack trace.

```java
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException:
			Index 3 out of bounds for length 3
			at BadArray.produceError(BadArray.java:24)
			at BadArray.myMethod(BadArray.java:18)
			at BadArray.main(BadArray.java:11)
```

Breaking down the lines of the message:
1) Tells the error is an ArrayIndexOutOfBoundsException
2) Tells us why (this line is not here for all exceptions)
3) Tells us where the error occurred that caused the exception it was in the '*produceError*' method 
4) Tells us where that method was called in this case '*myMethod*'
5) Tells us where "myMethod" was called

## Passing an Error up the Stack
When a method deep in a program throws an Exception and it is not properly handled in said method it *bubbles up* the stack, at each level / in each class it tests to see if the method has the proper code to handle the exception. If the Exception makes it all the way to the main method then it is passed to the default exception handler. 
# Helpful methods for ADV. File I / O
- The **getMessage** method will display the default error message for any exception. 
- the **printStackTrace** method will print the stack trace of an exception

# Introduction to Recursion
A recursive method is one that calls itself form within itself. A method calling another method is not a foreign concept. Method A can call Method B which can call Method C. In a recursive function the method calls itself. this is an example of a recursive method:
```java
Public Class EndlessRecursion
{	
	Public Static Message()
	{ 
	 System.out.print("This is a recursive method.");
	 message();
	}
}
```

This is a recursive method that prints "this is a recursive method" indefinitely, or until your computer crashes. Recursive methods are not unlike loops in that they need a terminating condition. This is a better example of a recursive method. 
```java
Public Class Recursive
{	
	Public Static Message(int n)
	{
		if (n > 0)
		{
		System.out.print("This is a recursive method.");
		message(n - 1);
		}
	}
}
```

This method that controls the looping / recursive calls, it will print the message n times. The method starts by passing in a number, then it prints the message and calls *message* again with the value (n -1) thus de-incrementing the call and proving a condition to terminate the loop. 

**Note:** The number of times a method calls itself is called the depth of recursion. 

# Solving Problems with Recursion
A problem can be solved with recursion if it can be broken down into successive smaller problems that are identical to the overall problem. 

However, recursion can be less efficient than solving iteratavely. Recursion requires more overhead for teh JVM than iteration. So it is not the case that recursion is always the best option but it is inportant to consider it as an option. 