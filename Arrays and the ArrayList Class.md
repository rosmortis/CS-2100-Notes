f# Introduction to Arrays
An array can hold multiple values of the same data type at the same time. Where all primitive data types are made to only store one data type at a time. An array is an object that can store a group of values, not unlike a list in python.

Creating an array is just like creating any other object in java. You declare a reference variable and and use the **new** keyword to create an instance of the array in memory.

This is how you declare an array ref variable:
```java
int[] numbers;
```

This is how you create an instance of an array: 
```java
numbers = new int[6];
```

The number inside the brackets is what's called a size declarator and per the name its job is to declare the length of the array. Unlike in python the array has to be a set length.

Both of the steps above can be done in the same step:
```java
int[] numbers = new int[6];
```

Note that 'int' can be replaced with any of the following data types
- float
- char
- long
- double
- int

When setting the length of an array you need do supply a non-negative whole number to the size declarator, this can be done threw a literal like '6' or you can do it with a known variable / constant. You can also pass in a value red from the user to set the length of the array. 

```java
final int NUM_ELEMENTS = 6;
int[] numbers = new int[NUM_ELEMENTS];
```

# Accessing Array Elements
An array is assigned one variable to hold all the elements but what is an array with out the ability to access individual elements? 

Arrays are zero indexed this is how you would add an element to the array at index zero:

```java
numbers[0] = 20;
```

**Note:** by default java initializes all indices with the value 0.

# Inputting and Outputting Array Contents
It is common to take keyboard input and store it in an array, you do this just like how you would do it with any other variable.

You can also print the contents of an array with `System.out.print()`

Here is an example of both:
```java
// initalize array
final int EMPLOYEES = 3;
int[] hours = new int [EMPLOYEES];

// initalize scanner
Scanner keyboard = new Scanner(System.in);

// read scanner data and assign value to array at index 0
System.out.print('Employee 1: ');
hours[0] = keyboard.nextInt();
```

It is possible to loop through the values in an array with a for loop and some variables. The same operation done above. Can be done faster with a for loop. This Is what it would look like: 
```java
// initalize array
final int EMPLOYEES = 3;
int[] hours = new int [EMPLOYEES];

// initalize scanner
Scanner keyboard = new Scanner(System.in);

// loop and take data
for (int i = 0; i < EMPLOYEES; i++){
	System.out.print("Employee" + (i + 1) + ": ");
	hours[i] = keyboard.nextInt()
}

// print the data
for (int i = 0; i < EMPLOYEES; i++){
	Syste.out.print(values[i]);
}

```


# The Length Field
Each array has a field called length that takes the length of the array. An implementation of the length field looks like this:

```java
int[] values = new int[25];

int size = values.length;
```

'size' will return the size of the array - in this case 25. 

# Array Initialization
Like other variables in java you can initialize and declare them at the same time.

This is what that looks like:
```java
int[] days = {5, 10, 15, 20, 25, 30, 35, 40};
```

# Alternate Array Declaration Notation
Declaring multiple arrays at a time looks like this:
```java
int[] numbers, codes, scores;
```

Declaring one int array and two int variables looks looks like this:
```java
int[] numbers, codes, scores;
```

# Processing Array Elements
Preforming operations on array elements is no different than any other variable. this is how you would multiply the value of 'hours\[3\]' by the payRate:
```java
grossPay = hours[3] * payRate;
```

This is how you can pre and post increment values in an array like this:
```java
// pre-increment
++score[2];

// post-increment
score[2]++;
```


Array elements can be used in relational expressions too:
```java
if ( cost[20] < cost[0]){
	// statement
}
```

here is a while loop that tests to see if the array has elements left in it:
```java
while (value[count] != 0){
	// statements
}
```


# The Enhanced For Loop
Java has what is called an advanced for loop that makes array processing easier

Here is the syntax:
```java
for (dataType elementVaraible ; array){
	// Statement
}
```

This loop iterates once per element of the array, each time the loop iterates it copies an array element to a variable.

In action this would look like this:
```java
int[] numbers = {3, 6, 9};

for (int val : numbers)
	 System.out.println(val);
```

This loop will print the all the values of the array.

**NOTE** an enhanced for loop can NOT be used to do the following:
- If you need to change the contents of an array element
- If you need to work through the array elements in reverse
- If you need to access some of the array elements, but not all of them
- If you need to simultaneously work with two or more arrays
- If you need to refer to the subscript number of a particular element

# Copying Arrays
An array is an object so in order to make a copy of an array you must loop the elements of arrayOne into arrayTwo.
```java
int[] arrayOne = { 5, 10, 15, 20, 25}:
int[] arrayTwo = new int[5]

for (int index = 0; index < arrayOne.length; index++)
	arrayTwo[index] = arrayOne[index];
```

# Passing Arrays as Arguments to Methods
To pass an array to a method you do it like passing it in to anything else:
```java
pubic static void showArray(int[] array){
	 for (int i = 0; i < array.length; i++)
		 System.out.print(array[i] + " ");
}
```

Then a call to this method looks like this:
```java
showArray(numbers);
```

# Array Algorithms and Operations
To compare arrays the \'\=\=\' operator does not work. 
This is the alternate:
```java
int[] firstArray = {2, 4, 6, 8, 10};
int[] secondArray = {2, 4, 6, 8, 10};
boolean arraysEqual = true;
int index = 0;

if (firstArray.lenght != secondArray.length){
	arraysEqual = false;
}

while (arraysEqual && index < firstArray.length){
	if (firstArray[index] != secondArray[index])
		arraysEqual = false;
	index++;
}

if (arraysEqual)
	System.out.print("The arrays are equal");
else
	System.out.print("The Arrays arent equal");
```

# Returning Arrays
To return an array set the return type to a valid data type followed by \[]
```java
public static double[] getArray[]{
// make and return array
}
```

# Sequential Search Algorithm
A sequential search algorithm is used to find a specific piece of data in a larger set. It is common for data to be stored in arrays and thus it is important to be able to search for data in an array. Fundamentally the sequential search algorithm compares each element with a condition and stops when the value is found, or at the end of the array.

This is a basic Sequential Search algorithm:
```java
public static int sequentialSearch(int[] array, int value){
	
	int index;        // Loop control
	int element;      // Element value is found at
	boolean found;    // Flag
	
	// Element 0 is the starting point for the search.
	index = 0;
	
	// Store default values element and found
	element = -1;
	found = false;
	
	// Search array
	while (!found && index < array.length){
		if (array[index] == value){
			found = true;
			element = index;
		}
		index++;
	}
	return element; 
}
```

```java

```
