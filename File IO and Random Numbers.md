# Terms and Keywords

**Delimiter:** an item that separates other items, the newline character create the delimiter \<newline>. Delimiters do not appear on the console, but in the buffer. In order for data to be read from a file the data must be separated by delimiters. 

# PrintWriter

To use the print writer without writing any newline characters add set of empty quotes to the end of the string you want to write to the file. 

```java
String name = "Ross Wade";
String Phone = "8029172438";
int idNumber = 47859;
PrintWriter outputFile = new PrintWriter("PersonalData.txt");
OutputFile.print(name + " ");
OutputFile.print(phone + " ");
OutputFile.print(idNmber);
outputFile.close();
```

when opened with a text editor the code above produces:

```java
Ross Wade 8029172438 47859
```

## Throws

if a program in the Main method throws an exception without being handled in java it halts the whole program. To allow the method to re-throw an exception add a throw clause to the method header. 

```java
public static void main(String[] args) throws IOException
```


You can also pass a file into the PrintWriter instance: 

```java
String filename;
System.out.print("Enter the file name: ");
fileName = keyboard.nextLine();
PrintWriter outputFile = new PrintWriter(Filename);
```

# Appending Data to a File

When you pass a file to the PrintWriter constructor and the file exists it erases the contents of the file, or it creates a new file if there is not all ready one with the name you passed in. 

To open a pre-existing file for writing without truncating: 

```java
FileWriter fwriter = new FileWriter("MyFriends.txt", true);
PrintWriter fwriter = new PrintWriter(fwriter);
```

This creates a PrintWriter object that appends data to a file.

## Specifying File Location

To specify the location of a file, path to the directory where you would put the file name. Note in Windows OS  "\\" requires escape characters unless you are prompting the user for the file name, because it is initialized as a string.

MacOS:
```java
PrintWriter outputFile = new PrintWriter("H:\Desktop\CS1200\Homework");
```

Windows:
```java
PrintWriter outputFile = new PrintWriter("H:\\Desktop\\CS1200\\Homework");
```


# Reading Data From a File

To read data from a file initialize a Scanner class with inputFile and reference a file to the object. 

```java
File myFile = new File("Coustemers.txt");
Scanner inputFile = new Scanner(myFile);
```

Opening a file to read in one line looks like this:
```java
Scanner inputFile = new Scanner(new File(filename));
```

Remember to close the file!!

## The Read Position

A file read position marks the location of the next item that will be read form the file. When a file opened it is set to the first line and when a line is read it is set to the next line.

After using this code block to read from the file the read position advances one line down: 

```java
String str = inputFile.nextline();
```

## The Has Next Method

When you call the has next method inside our application it returns a Boolean True or False so when we pass it in to a while loop on the end of a file name it will read the read position and read the file until the last line, or until the has next method returns False. 

```java
while (inputfile.hasNext())
```

## Checking for a Files Existence

TO check if a file exists create a file object the use the file class **exists** to determine if the file exists. the method returns true if the file is real and False if the file does not. 

```java
if (file.exists)
```

## Managing Resource Leaks 

You can choose to close a file manually or you can write a try block which will try do do something with a a statement and then it will close automatically. A try block starts like this:

```java
try (Deceleration Statement for auto closeable object)
{
   //statements that work here
}
```

The resource will auto close after it try the statements in the block. 

This is what it looks like being used: 

```java
// Open the file.

try (PrintWriter outputFile = new PrintWriter ("Sequence. txt"))
{
	// Write the numbers 1-10 to the file.
	for (int number = 1; number < 10; number++)
	{
	outputFile.println(number);
	}
}
```

You can declare more than one file at a time in a Try block. 

## Generating Random Numbers

To import the random class:

```java
import java.util.Random;
```

To create an object from the Random class you do so with a statement like this:

```java
Random randomNumbers = new Random();
```

- This declares a variable called randomNumbers of data type Random
- new Random() creates an instance of the Random class
- and the "=" assigns the address of the Random class to the randomNumbers variable

Then to assign a random number to a useable variable:

```java
number = randomNumbers.nextInt(); 
```

Here is a list of statements and how they manipulate the range of the random number: 

```java
// sets upper limmit to 99
number = randomNumbers.nextInt(100);  

// sets upper limmit to 9 then adds 1 so range is 1 - 10
number = randomNumbers.nextInt(10) + 1;  

// sets range between -50 and +49
number = randomNumbers.nextInt(100) - 50;
```


