# Static Class Members
A static class member belongs to the class and not each of the individual classes. Each instance of a class has instance fields and instance methods like getters and setters. 

When a static field or method is created it does not belong to the instance of the class. These are called static fields or static methods. In fact an instance of a class does not even have to exist for these objects to exist. you can think of them asa belonging to the class and not the object.

When a static field is initialized there will only be one copy of it stored in memory. this saves space and time. Instead of storing the data for each object the object has access to the static fields and classes.

initializing a static field looks like this:

```java
private static int instanceCount = 0;
```

Note that all static fields are initialized to zero by default. 

Static methods are callable without being initialized in the main method. This looks similar to calling a function. As long as you assign it to a variable. 

```java
kilometers = Metric.milesToKilometers(10.0);
```

# Passing Objects as Arguments to Methods
It is possible to pass entire objects into methods. This is done the same way you would pass in any thing else, for the example below assume rectangle is a predefined object. 

```java
public static void displayRectangle(Rectangle d){
	System.out.print.("length: " = d.getLenght() +
	"width: " + d.getLength());
}
```

Here 'd' is not a different insistence of the rectangle object it it referencing it is that object just with a different address name. So both objects reference the same object in memory.

# Returning objects from Methods
To return an object from a method, you must set the return type to that of the object you are trying to return. 
```java
public static BankAccount getAccount(){
	// statements
	return new BankAccount(balance);
}
```

# The toString Method
Most methods benefit having a toString method that returns the state of the thing in the method. For example the bank account method defined above could have any value stored as balance at any time. A toString method would return the balance as a string you that you can keep an eye on the value as a programmer.

```java
public String toString(){
	string str = "Trading symbol: " + simbol + 
	"\nShare Price: " + share price;
	
	return str;
}
```

When you write a toString method it is unnecessary to call the method within a print statement you can just pass in the object as an argument.

# Writing an Equals Method
You cannot determine if two objects contain the same data with the dub equals operator so you have to write an Equals method. We can use the 'equals' method defined in the string class to see if strings are equivalent this would look like this: 

```java
if (symbol.equals(object2.simbol)) && sharePrice == object2.sharePrice)
	status = true; // yes the objects are equal
else 
	status = false; // no, the objects arent equal
return status;
```

Or like this: 
```java
public boolean equals(Circle object2){
	boolean status = false;
	
	if (radius == object2.radius)
	status = true;
	
	 return status;
}
```

Note that the 'equals' method can also be a 'greaterThan' method or a 'lessThan' method.

# Methods that Copy Objects 
You can make it easy to copy an object by writing a class that does the copying for you. This is what that looks like:

```java
public Stock copy(){
stock copyObject = new Stock(symbol, sharePrice);

return copyObject;
}
```

# Aggregation
Aggregation is a type of association between two classes where one class contains a reference to another class as one of its instance variables. This relationship represents a "has-a" relationship, meaning that one class has a reference to another class, but does not control the lifetime of the other class. In other words, the contained class can exist independently of the containing class.

When creating aggregations you need to be careful that you don't allow any security holes to show up.
# This
To avoid overshadowing use the this method which tells the method to only manipulate the variable in said method: 

```java
public Stock(String simbol, double sharePrice){
	this.symbol = symbol;
	this.sharePrice = sharePrice;
}
```

# Enumerated Data Type

An enumerated data type consists of a set of predefined values. You can use the data type to create variables that belong to the enumerated data type. 