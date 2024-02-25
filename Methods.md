# Intro to Methods
A method is a collection of statements that preforms a set of specific tasks. Methods are most commonly used to break applications down into smaller more manageable pieces divide and conquer if you will.

## Void Methods and Value-Returning Methods

A **void** method preforms a task and then terminates, the print method is an example of this. A **value returning** method preforms the task bit also sends a value back to the code that called it. All methods must be called before they are executed.

this is what it would look like to call a method within another method.

```java
public class SimpleMethod
{
	public static void main(String[] args)
	{
		System.out.println("Hello from the main method.");
		displayMessage();
		System.out.println("Back in the main method.");
	}
	 
	 // The displayMessage method displays a greeting.
	
	public static void displayMessage()
	{
		System.out.println("Hello from the displayMessage method");
	}
}
```

Here we call the method with displayMessage(); because it is a void method it returns to the main method after it is executed.

# Passing Arguments to a Method

When writing a method if you pass in a variable deceleration it limits what you can pass into that method to the data type of that variable. For example: 

```java
Public static void DisplayValue(int num)
{
	Sysytem.out.println("the value is " + num)
}
```
 
 Where "num" can only be an integer. 
 
 It is also reasonable to not declare the data type and only pass in the correct data types.

## The @pram Tag 
When defining a parameter it is important to document exactly what the parameter is is and why it is that way. The best way to do this is by inserting an @param tag followed by a description. 

```java
/**
@param num1 is the first number. 
@param num2 is the second number.
*/
```

# Returning a Value From a Method

When returning a value from a method you should use the @return tag and give a definition of what the method will return.

Use the return Keyword to end the method a return a value back tot e code block that called it. 
