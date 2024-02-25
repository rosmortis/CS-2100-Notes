
# Objects and Classes

An object is a software component that exists in memory and serves a specific purpose in the program. An object is created from a class that contains code describing the object. 

**An object has two general components:**
- An object can store data. The data stored in an object is commonly called fields
- An object can preform operations. The operations that an object can preform are called methods.

A class is like a "blueprint" for java objects.

A class member that holds data is known as a field.

# Classes in the Java API

Most objects that we have used so far have been classes in the Java API. Like the Scanner object and Random. When you create an instance of the scanner object you are making a call to the Scanner class in the Java API. The same is true for the PrintWriter object.

# Primitive Variables vs. Objects

To create a primitive variable you initialize it like this:
```java
int wholeNumber
```

But to create an instance of an Object:
```java
Random rand = new Random();
```

A primitive data type is called a primitive data type because they have no other capabilities other than storing data. 

When working with an object you use two things:
- The object itself, which must be created in memory
- A reference variable that refers to the object

The object in memory holds data of some sort and preforms an operation on that data. The variable only holds the name of that address in memory. 

Here "Random" is like "int" and rand is the variable name.
'new Random' assigns the variable to the Random object.

```java
Random rand = new Random();
```

# Writing a Simple Class, Step by Step

When writing a new class it is helpful to block them out using UML diagrams
- The top row is the name of the class 
- The second row are the fields 
- The third row has the methods. 

| Rectangle |
| ---- |
| length, width |
| setLength() setWidth() getLength() getWidth() getArea() |
The beginning of a simple class looks like this

```java
public class Rectangle {
	Members
}
```

In general the terms, fields, and methods of a class are referred to as its Members.

Here we continue to define the members of the class, 'private' means that the variable may not be accessed by statements outside of the class.

```java
public class Rectangle {
	private double length;
	private double width;
}
```

Now we can write the methods that we defined in the UML table.

```java
public class Rectangle {
	private double length;
	private double width;
	
	/**
		the set lenghth method stores a value in the lenght field
		@param len the value to store in length
	*/
	
	public void setLenght(double len){
		lenth = len;
	}
}
```

Now we can write the getLength method

```java
public class Rectangle {
	private double length;
	private double width;
	
	/**
		the set lenghth method stores a value in the lenght field
		@param len the value to store in length
	*/
	
	public void setLenght(double len){
		lenth = len;
	}
	
	public double getLenth(){
		return length;
	}
	
}
```

# Accessor and Mutator Methods

It is most common to make a class's fields private and provide public methods for accessing and changing those fields. this is key in keeping all of the programs data safe from being over written or unintentionally manipulated. 

A method that gets a value from from a class but doesn't change it is called an **Accessor Method**

a method that stores a value in a field or changes the value of a field in some other way is called a **Mutator**

# Instance Fields and Methods

Each instance of a class has its own set of fields known as instance fields. The methods that operate in an instance of a class are known as instance methods.

# Constructors

A constructor is automatically called when an instance of a class is created. Constructors normally preform some type of task that is pertinent to the program like initialization, set up, or variable storage. Constructors are called constructors because, you guessed it, they construct.

This is generally what a constructor looks like: 

```java
public Rectangle(double len, double w){
length = len;
width = w; 
}
```

This constructor is being used to get information for the class. With out any of this information the class is useless, so you write a constructor that gets that information. 

The method header does not include a return type because you cannot call it. This is what it would look like outside of the method: 

```java
Rectangle box = new Rectangle(7.0, 14.0);
```

It can also be done in two steps where:

```java
Rectangle box;
box = new Rectangle(7.0, 14.0);
```

## The Default Constructor

If you choose not to write a constructor for a class then the default constructor is called. The default constructor accepts no arguments and sets all the fields to zero. 

# Creating a String Object

Because strings are so commonly used in java you can create a String object in the same way you would create an instance of a class. This is done because Java provides methods that can manipulate string objects.

```java
String name = new string("Joe Mahoney");
```


# Overloading Methods and Constructors

You can have one or more method in a class that have the same name, provided they have different parameters. This is done incase you need different methods of preforming the same operation. Here is an example of a good time to implement this:

```java
public int add(int num1, int num2){
	return num1 + num2;
}

public double add(double num1, double num2){
	return num1 + num2;
}
```
# Finding the Classes to Write

Programmers have found that the best way to figure out what classes you will need to write for you program is to:

- Get a written description of the problem domain
- Identify all the nouns (including pronouns and noun phrases) in the description. each of theses is a possible class.
- Redefine the list to include only the classes that are relevant to the problem. 