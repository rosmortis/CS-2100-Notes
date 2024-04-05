# What is Inheritance?
The term insect is a generalization of various bugs like Grasshoppers and Bumblebees. This represents an "is a" relationship. For example "A poodle is a dog" or "A Grasshopper is a bug" when a object in programing has an "is a" relationship it means that the object has all the characteristics of the general class plus additional characteristics or methods that make it different from the main class. This allows your parent class to maintain its function while simltanousley optimizing it for another function. 

Typical nomenclature for the "parent class" is the "superclass" and the inherited class is the "subclass" where the subclass inherits the methods of the superclass.

This is what the method header would look like for a subclass of GradedActivity
```java
public class FinalExam extends GradedActivity(){

}
```

If you want to express the relationship here you could say that FinalExam is a GradedActivity. When a FinalExam object is created it has all the members declared within the FinalExam class and all of the non-private members of the GradedActivity class. 

# The SuperClass's Constructor
Because the constructors aren't inherited from the SuperClass there is a special way they execute to work together.  First the SuperClass's no-arg constructor is executed then the SubClass's constructor is executed. The super keyword calls the SuperClass's constructor. A super classes no-arg constructor is always called before a SubClasses constructor. So...
```java
public class SuperClass{

	public SuperClass(int n){
		System.out.print(n);
	}
}
```

Above we define a class SuperClass that has a constructor that prints an integer. Below we create a new class that extends the SuperClass, this class has one constructor that calls the super class constructor using the "super" keyword. 
```Java
public class SubClass extends SuperClass{

	public SubClass(int n){
		super(n);
	}
}
```

# Overriding Superclass Methods
Just like with an equals method or a toString you can override SuperClass methods by writing a method that has the same signature and parameters. When this is done we say that the method overrides the superclass method. This is done when the inherited behavior is not ideal for the intended function of the subclass.

# Overriding versus Overloading
Overriding is when the method has the same signature and the same parameters. overloading is when the method has the same signature but different parameters. 

If you declare a method as final it can not be overridden in a SubClass, that would like this:
```Java
public final void message(){
	// you know the deal
}
```