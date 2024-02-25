
# The Increment and De-increment Operators

++ and -- are operators the add and subtract on form their operands

Here is a code block where we implement an increment:

```java
number++;
```

Here we de-increment number:

```java
number--;
```

## The Difference Between Postfix and Prefix Modes

The code below is a postfix example which causes the number to increment after it has been used in the expression.

```java
number = 4;
System.out.print(number++);

>> 4
>> 5
```

In prefix mode this is what would happen: 

```java
number = 4;
System.out.print(++number);

>> 5
```

# The While Loop

The general function of the While loop is the same in java as it is in python. The boolean is tested and, and if it is true, statement is executed then the Boolean is tested again if it is true then the statement is executed this cycle repeats until the expression is false.

```java
While (BooleanExpression)
{
	Statement;
	Statement;
	// as many statements as you want
}
```

Each loop is known as an **iteration**

## The Wile Loop as a Pretest loop

It is t to note that the While loop will only execute if the boolean expression is true so you need to be sure that you are passing in a variable that evaluates to True.

## Notes for Block Statements

- It is important to remember to inclose a block of statements in curly braces
- Don't put **statements** and **loop headers** in the same line

## While Loop Input Validation

This code tests for an integer in the range 0 - 100

```java
int number;

// Create a Scanner object for keyboard input.
Scanner keyboard = new Scanner(System.in);

// Get a number from the user.
System.out. print ("Enter a number in the range of 1 through 100: ");
number = keyboard.nextInt();

// Validate the input.
while (number < 1 || number > 100)

{
	System.out.print("Invalid input. Enter a number in the range " +
						"of 1 through 100: ");
number = keyboard.nextInt ();
｝
```

The user is prompted to enter an integer this is called the **Priming Read.**


# The Do While Loop

The Do While loop is a posttest loop which means its Boolean is tested after every expression. It behaves similarly to an inverted while loop. This is the syntax:

```java
do 
{
	Statement;
	Ststement;
	// as amy statements as you want
} while (BooleanExpression);
```

**Note:** the do while loop must be terminated with a semicolon.

This type of loop is used when you want to make sure that at least one run will occur. For example if I wanted to take an average of test scores but wanted to be able to re-use the code block. I could use a do while loop with a prompt to repeat as the loop header if the user wanted to take another average.

# The For Loop

there are two types of loops conditional loops and controlled loops. A conditional loop executes as long as some condition is true and you have no way of controlling how many iterations it does. Sometimes you want to control exactly how many iterations a loop has. 

## Elements all controlled loops must have

1) It must initialize a control variable to a starting value

2) It must test the control variable by comparing it to a maximum value. When the control variable reaches the maximum value, the loop terminates. 

3) It must update the control variable during every iteration. Most commonly done via increment or deincrement operators

## For Loop Syntax

```java
for (Initialization; Test; Update)
{
	Statement;
	Statement; 
}
```

- The first expression is the initialization expression. It is normally used to initialize a control variable to its starting value.

- The second expression is the test expression. This is a boo lean expression that controls the execution of the loop.

- The third expression is the update expression. It executes at the end of each iteration. Typically, this is a statement that increments the loop's control variable.

In action this look like:

```java
for (count = 1; count <=5; count++)
	System.out.print("Hello World")
```

This code block prints "Hello World" five times. It is entirely possible to pass in a starting variable. You can also pass in more than one starting variable. in java it is also common to see iteration counters, they are done the same way as in python.

## Break an Continue Statements

The **break** statement terminates the loop early. 

the **continue** statement causes the loop to terminate it current iteration ad begin the next. 