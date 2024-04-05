# Shadowing:

   > [!question]- What is variable shadowing in Java?
   > Variable shadowing in Java occurs when a local variable hides a variable with the same name at higher levels of scope.

> [!question]- Explain a scenario where variable shadowing can lead to confusion.
> Shadowing can lead to confusion when programmers inadvertently use the wrong variable, thinking they are accessing another variable with the same name.

> [!question]- How can you avoid variable shadowing in your code?
> Variable shadowing can be avoided by choosing unique variable names and being mindful of variable scopes.
   
   > [!problem]-  Create a Java class with a method that demonstrates variable shadowing. Define a local variable inside the method that has the same name as an instance variable. Print both variables to the console to show the effect of shadowing.
   > ```java 
   > ShadowingExample { 
   > int x = 10; // instance variable
   > 
   > void demo(int x) { 
   > 		System.out.println("Local Variable: " + x); // local variable 
   > 		System.out.println("Instance Variable: " + this.x); // instance variable 
   > 	} 
   > }
   > ```


# Static vs Non-Static

  > [!question]- Differentiate between static and non-static variables.
  > Static variables belong to the class itself, while non-static variables belong to instances of the class.
   
   > [!question]- What is the significance of the keyword 'static' in Java?
   > The 'static' keyword indicates that a variable or method belongs to the class rather than instances of the class.
   
   > [!question]- When would you use a static method versus a non-static method?
   > Static methods are used for operations that don't require instance-specific data, whereas non-static methods operate on instance-specific data.
   
   > [!problem]- Design a Java class that keeps count of the number of instances created. Use a static variable to keep track of the count. Implement a method that increments the count each time a new instance is created.
   > ```java
   >class InstanceCounter {
  > 	static int count = 0; // static variable
   > 
   > 	InstanceCounter() {
  > 		 count++; // increment count each time a new instance is created
>	   }
  >  }
   > ```

# Variable Scope (Local vs Instance Variables):

   > [!question]- Define local and instance variables. 
   > Local variables are declared within a method or block, while instance variables belong to a class and are accessible throughout the class.
   
   > [!question]- Describe the scope of local variables versus instance variables.
   > Local variables have a limited scope within the method or block where they are declared, while instance variables are accessible throughout the class.
   
   > [!question]- Provide an example where understanding variable scope is crucial.
   > Understanding variable scope is crucial for avoiding naming conflicts and accessing variables appropriately within methods and classes.
   
   > [!problem]-  Problem: Write a Java program that declares a local variable within a method and an instance variable in the class. Try to access both variables from another method within the same class. Explain the results.
   > ```java
>class VariableScope { 
>	int instanceVar = 10; // instance variable 
>	
>	void method() { 
>		int localVar = 20; // local variable 
>		System.out.println("Local Variable: " + localVar); 
>		System.out.println("Instance Variable: " + instanceVar); 
>	} 
>}
>```

# Instance Variables vs Class Variables:

> [!question]- Explain the difference between instance variables and class variables.
> Instance variables are specific to each instance of a class, while class variables are shared among all instances of the class.
   
   > [!question]- When would you use an instance variable versus a class variable?
   > Instance variables represent the state of an object, while class variables represent properties shared by all objects of the class.
   
   > [!question]- How is the value of a class variable shared among different instances of the class?
   > The value of a class variable is shared among different instances because it belongs to the class, not individual instances.
   
   > [!problem]- Create a Java class representing a bank account. Implement an instance variable to store the account balance and a class variable to store the interest rate. Write methods to deposit money into the account and calculate the interest.
   > ```java
   > class BankAccount {
   > 	double balance; // instance variable
  > 	static double interestRate; // class variable
  > 	 
  > 	 void deposit(double amount) {
  > 		     balance += amount;
  > 	 }
  > 	 
 > 	  double calculateInterest() {
 > 	      return balance * interestRate;
 > 	  }
>}
>```

# Constants:

   > [!question]- What are constants in Java?
   > Constants in Java are variables whose values cannot be changed once assigned.
   
   > [!question]- How do you declare constants in Java?
   > Constants are declared using the 'final' keyword in Java.
   
   > [!question]- Why might you use constants instead of regular variables?
   > Constants are useful for defining values that should not change throughout the program, enhancing code readability, and avoiding magic numbers.
   
   > [!problem]- Define a Java class that represents mathematical constants. Declare constants for pi and Euler's number. Ensure that these constants cannot be modified once initialized.
   > ```java
   > class MathConstants { 
   > 	static final double PI = 3.14159; 
   > 	static final double EULER_NUMBER = 2.71828; 
   > }
   > ```

# Equals Method:

   > [!question]- Describe the purpose of the `equals` method in Java.
   > The equals method in Java is used to compare the equality of two objects.
   
   > [!question]- Explain the difference between `==` and `.equals()` in Java.
   > == compares object references, while .equals() compares the actual contents or values of objects.
   
   > [!question]- How can you override the `equals` method for custom objects?
   > The equals method can be overridden in custom classes to define custom equality comparisons based on object attributes.
   
   > [!problem]- Create a Java class representing a geometric shape. Override the equals method to compare two shapes based on their area. Test the equals method with different shapes.
   > ```java
   > class Shape {
  > 	 double area;
  >  
  > 	 @Override
  > 	 public boolean equals(Object obj) {
  >       Shape other = (Shape) obj;
  >       return this.area == other.area;
  > 	 }
  >  }
  > ```

# toString Method:

   > [!question]- What is the purpose of the `toString` method in Java?
   > The toString method in Java returns a string representation of an object.
   
   > [!question]- How do you override the `toString` method for custom objects?
   > To override the toString method for custom objects, you implement the method in your class and provide the desired string representation.
   
   > [!question]- Provide an example of when you might use the `toString` method.
   > toString method is often used to print meaningful information about objects or for debugging purposes.
   
   > [!problem]- Design a Java class to represent a book. Implement a toString method that returns a string containing information about the book such as title, author, and publication year.
   > ```java
   > class Book {
>	String title;
>	String author;
>	int publicationYear;
  >  
  > 	 @Override
  > 	 public String toString() {
  >      return "Title: " + title + ", Author: " + author + ", Year: " + publicationYear;
 >   }
>}
>```

# Default Constructor:

> [!question]- What is a default constructor?
> A default constructor is a constructor with no parameters.
   
   > [!question]- When does Java provide a default constructor?
   > Java provides a default constructor if no constructors are explicitly defined in a class.
   
   > [!question]- How can you explicitly define a default constructor?
   > You can explicitly define a default constructor by providing a constructor with no parameters.
   
   > [!problem]-  Define a Java class representing a car. Implement a default constructor that initializes the car's make and model to default values. Instantiate an object of the car class using the default constructor and print its details.
   > ```java
   > class Car {
   > 	String make;
   > 	String model;
>
>	Car() {
>		make = "Toyota";
>		model = "Camry";
>	}
>}
>```

# Copy Constructor:

   > [!question]- What is a copy constructor?
   > A copy constructor is a constructor that creates a new object by copying the attributes of an existing object.
   
   > [!question]-  How does a copy constructor differ from other constructors?
   > Unlike other constructors, a copy constructor takes an object of the same class as its parameter.
   
   > [!question]-  Provide an example scenario where a copy constructor is useful.
   > Copy constructors are useful for creating deep copies of objects or initializing new objects based on existing ones.
   
   > [!problem]- Write a Java class representing a person. Implement a copy constructor that creates a new person object with the same attributes as another person object. Test the copy constructor with different person objects.
   > ```java
   > class Person {
 >   String name;
 >   int age;
 >   
>    Person(Person other) {
 >       this.name = other.name;
 >       this.age = other.age;
>    }
>}
>```

# Method Overloading:

> [!question]- Define method overloading.
> Method overloading is the practice of defining multiple methods in the same class with the same name but different parameter lists.

> [!question]- How does method overloading differ from method overriding?
> Method overloading differs from method overriding in that it involves methods with the same name in the same class, while method overriding involves methods with the same signature in a superclass-subclass relationship.

> [!question]-  Provide an example of method overloading.
> Example: Having multiple constructors in a class with different parameter lists.

> [!problem]-  Create a Java class with multiple methods named calculateArea that calculate the area of different shapes such as circle, rectangle, and triangle. Implement method overloading for the calculateArea method.
> ````java
> class AreaCalculator {
> 
> double calculateArea(double radius) {
> return Math.PI * radius * radius;
>    }
>
>    double calculateArea(double length, double width) {
>        return length * width;
>    }
>
>    double calculateArea(double base, double height) {
>        return 0.5 * base * height;
> 	  }
>   }

#  Method Overriding:

> [!question]- Explain method overriding in Java.
> Method overriding in Java occurs when a subclass provides a specific implementation of a method that is already provided by its superclass.

> [!question]- What are the conditions for method overriding?
> The method in the subclass must have the same name, return type, and parameters as the method in the superclass.

> [!question]- Provide an example of method overriding.
> Example: Overriding the toString method in a subclass to provide a custom string representation.

> [!problem]-  Define a Java class representing a vehicle with a method named accelerate. Create subclasses for car and bicycle. Override the accelerate method in both subclasses to provide different behavior.
> ```java
> class Vehicle {
>    void accelerate() {
>        System.out.println("Vehicle is accelerating...");
>    }
>}
>
>class Car extends Vehicle {
 >   @Override
 >   void accelerate() {
>        System.out.println("Car is accelerating...");
>    }
>}
>
>class Bicycle extends Vehicle {
>    @Override
>    void accelerate() {
 >       System.out.println("Bicycle is accelerating...");
 >   }
>}

# Getters:

> [!question]- What is the purpose of a getter method?
> The purpose of a getter method is to retrieve the value of a private instance variable from outside the class.

> [!question]- How do you define a getter method in Java?
> Getter methods are defined by providing a public method that returns the value of the private instance variable.

> [!question]- Why might encapsulation require the use of getter methods?
> Encapsulation often requires the use of getter methods to access private instance variables indirectly, maintaining data integrity and control over access.

> [!problem]- Design a Java class representing a student. Implement private instance variables for student's name, age, and grade. Provide getter methods to access these variables from outside the class.
> ```java
> class Student { 
> 	private String name; 
> 	private int age; 
> 	private char grade; 
> 
> 	String getName() { 
> 		return name; 
> 	}
> 
> 	int getAge() { 
> 		return age; 
> 	} 
> 	
> 	char getGrade() {
> 		return grade; 
> 	}
> }
> ```

# Setters:

> [!question]- What is the purpose of a setter method?
> The purpose of a setter method is to modify the value of a private instance variable from outside the class.

> [!question]- How do you define a setter method in Java?
> Setter methods are defined by providing a public method that accepts a parameter and assigns it to the private instance variable.

> [!question]- Why is validation important in setter methods?
> Validation in setter methods ensures that only valid values are assigned to instance variables, maintaining data integrity and preventing unintended changes.

> [!problem]-  Extend the student class from the previous problem with setter methods for modifying the student's age and grade. Ensure that the setter method for the grade validates the input to be within a valid range.
> ```java
> class Student {
 >	private int age;
 >	private char grade;
 >	
 >	void setAge(int newAge) {
> 	       if (newAge >= 0) {
 > 	          age = newAge;
 >		}
  > 	}
  >  
  > 	 void setGrade(char newGrade) {
 >		if (newGrade >= 'A' && newGrade <= 'F') {
 > 	          grade = newGrade;
 >		}
  >	}
>}
>```

#  Object References:

> [!question]- Explain what an object reference is in Java.
> An object reference in Java is a variable that stores the memory address of an object rather than the object itself.

> [!question]- How are object references used in Java?
> Object references are used to access and manipulate objects in Java programs.

> [!question]- Describe the difference between an object and an object reference.
> The difference between an object and an object reference is that an object represents the actual instance of a class, while an object reference is a variable that holds the memory address of that instance.

> [!problem]- Create a Java class representing a person. Instantiate two person objects and assign one object reference to the other. Modify the properties of one person object and observe the changes reflected in the other object.
> ```java
> class Person {
>	String name;
>	int age;
>}
>
>public class Main {
>    public static void main(String[] args) {
>        Person person1 = new Person();
>        Person person2 = new Person();
>        person1 = person2; // both references point to the same object
>        person1.name = "John";
>        System.out.println(person2.name); // Output: John
>    }
>}
>```

#  Memory Diagrams:

> [!question]- What is a memory diagram in Java?
> A memory diagram in Java is a visual representation of memory allocation and object references during program execution.

> [!question]- How do memory diagrams help in understanding Java programs?
> Memory diagrams help in understanding Java programs by illustrating how objects are created, stored in memory, and referenced by variables.

> [!question]- Provide a simple example of a memory diagram for a Java program.
> Example: Drawing boxes to represent objects, arrows to represent object references, and labels to indicate variable names and values in memory.

> [!problem]- Design a simple Java program that creates objects of different classes and visualize their memory allocation using memory diagrams. Include references between objects where applicable.



