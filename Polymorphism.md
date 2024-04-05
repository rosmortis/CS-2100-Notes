**CONCEPT:** A superclass reference variable can reference objects of an subclass.

If we have two classes called GradedActivity and FinalExam and FinalExam is derived from GradedActivity in the driver we can declare a GradedActivity reference variable:

```java
GradedActivity exam;
```

This declares exam as a GradedActivity but because FinalExam is derived from GradedActivity. We can use the exam variable to hold a FinalExam object. 

```java 
GradedActivity exam = new finalExam(50, 7);
```

Polymorphism means to take multiple forms, this reference variable is polymorphic because it can take the form of a GradedActivity or / and a FinalExam this is possible because of the 'is-a' relationship that they have to each other. 

Here we do the same thing for three different classes that are derived from GradedActivity:
```java
GradedActivity exam1 = new FinalExam(50, 7);
GradedActivity exam2 = new PassFailActivity(70);
GradedActivity exam3 = new PassFailExam(100, 10, 70);
```
**Note:** When using one of these variable you can only use the methods in GradedActivity and not the methods in the derived class. 

# Polymorphism and Dynamic Binding
When a SuperClass variable references a SubClass object you open a possible problem. If the SubClass has a method that overrides a SuperClass method we have officially run into a problem. The Java Virtual Machine determines at runtime which of the methods to call based on what type the object is

Additionally any class derived from GradedActivity can be passed in as a parameter to a method with a GradedActivity parameter.

# The "instanceof" operator
There is an operator in java called instanceof that can be used to determine if an object is an instance of a certain class, this is the general syntax:
```java
refVar instanceof ClassName;
```
This will return a boolean true if refVar is in fact an instance of the class. It will also return true if refVar is an instance of a SubClass of "ClassName"

# Abstract Classes and Abstract Methods
An abstract class can not be instantiated but another class must be derived from it. An abstract method has no body and must be overridden in a SubClass. 

This is how you declare an abstract method
```java
AccessSpecifier abstract ReturnType MethodName(params);
```

When an abstract method appears in a SuperClass it has no function other than to ensure that each of the SubClasses override it. Similarly abstract classes almost act as a frame work for all of the classes it will inherit. 

**TLDR:**
- Abstract methods and abstract classes are defined with the Abstract keyword.
- Abstract methods have no body, their header must end with a semicolon.
- An abstract method must be overridden in a subclass
- When a class contains an abstract method, it cannot be instantiated it must serve as a SuperClass
- An abstract class can not be instantiated. It must serve as a superclass. 

This could look like this:
```java
public abstract class Phone{
    
    private String phoneNumber;
    
    public void Phone(String s){
        this.phoneNumber = s;
    }
    
    public String getPhoneNumber(){
        return phoneNumber;
    }
    
    public String toString(){
        return String.format("#(%s)", phoneNumber);
    }
    
    public abstract boolean createConnection(Network n);
    public abstract void closeConnection();
}
```

# Interfaces
An interface specifies the behavior for a class. an interface only contains abstract methods and all of the class must be implemented by other classes. The keyword interface must be used to in stead of the keyword class. The methods in an interface have no bodies and are terminated by semicolons.

For example:
```java
public interface Displayable{
	pubic void display();
}
```

Any class that implements the displayable interface must implement the methods in the display method.
```java
public class Person implements Displayable{
	private String name;
	
	public Person(String n){
		name = n;
	}
	
	public void display(){
		System.out.print("my name is " + name);
	}
}
```

When you want a class to implement an interface you use the implements keyword in the class header. When a class implements an interface it is agreeing to provide all of the methods that spesifyed by the interface. 