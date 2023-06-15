 # C-SHARP LANGUAGE LESSON 1


## WHAT IS C#?

C# is pronounced "C-Sharp".

It is an object-oriented programming language created by Microsoft that runs on the .NET Framework.

C# has roots from the C family, and the language is close to other popular languages like C++ and Java.

The first version was released in year 2002. The latest version, C# 11, was released in November 2022.

C# is used for:

Mobile applications
Desktop applications
Web applications
Web services
Web sites
Games
VR
Database applications
And much, much more!

## SYNTAX

```
using System;

namespace HelloWorld
{
  class Program
  {
    static void Main(string[] args)
    {
      Console.WriteLine("Hello World!");    
    }
  }
}
```

Output:

```
Hello Wordl!
```


### Example Explained

***Line 1:*** using System means that we can use classes from the System namespace.

***Line 2:*** A blank line. C# ignores white space. However, multiple lines makes the code more readable.

***Line 3:*** namespace is used to organize your code, and it is a container for classes and other namespaces.

***Line 4:*** The curly braces {} marks the beginning and the end of a block of code.

***Line 5:*** class is a container for data and methods, which brings functionality to your program. Every line of code that runs in C# must be inside a class. In our example, we named the class Program.

Don't worry if you don't understand how using System, namespace and class works. Just think of it as something that (almost) always appears in your program, and that you will learn more about them in a later chapter.

***Line 7:*** Another thing that always appear in a C# program, is the Main method. Any code inside its curly brackets {} will be executed. You don't have to understand the keywords before and after Main. You will get to know them bit by bit while reading this tutorial.

***Line 9:*** Console is a class of the System namespace, which has a WriteLine() method that is used to output/print text. In our example it will output "Hello World!".

If you omit the using System line, you would have to write System.Console.WriteLine() to print/output text.

***Note:*** Every C# statement ends with a semicolon ;.

***Note:*** C# is case-sensitive: "MyClass" and "myclass" has different meaning.

Note: Unlike Java, the name of the C# file does not have to match the class name, but they often do (for better organization). When saving the file, save it using a proper name and add ".cs" to the end of the filename. To run the example above on your computer, make sure that C# is properly installed: Go to the Get Started Chapter for how to install C#. The output should be:


```
Hello Wordl!
```

## VARIABLES

Variables are containers for storing data values.

In C#, there are different types of variables (defined with different keywords), for example:

- int - stores integers (whole numbers), without decimals, such as 123 or -123
- double - stores floating point numbers, with decimals, such as 19.99 or -19.99
- char - stores single characters, such as 'a' or 'B'. Char values are surrounded by single quotes
- string - stores text, such as "Hello World". String values are surrounded by double quotes
- bool - stores values with two states: true or false


***Declaring (Creating) Variables***

To create a variable, you must specify the type and assign it a value:

Syntax:

```
type variableName = value;
```

Where type is a C# type (such as int or string), and variableName is the name of the variable (such as x or name). The equal sign is used to assign values to the variable.

To create a variable that should store text, look at the following example:

Example:

Create a variable called name of type string and assign it the value "John":

```
string name = "John";
Console.WriteLine(name);
```

To create a variable that should store a number, look at the following example:

Example:

Create a variable called myNum of type int and assign it the value 15:

```
int myNum = 15;
Console.WriteLine(myNum);
```

You can also declare a variable without assigning the value, and assign the value later:

Example:

```
int myNum;
myNum = 15;
Console.WriteLine(myNum);
```

Note that if you assign a new value to an existing variable, it will overwrite the previous value:

Example:

Change the value of myNum to 20:

```
int myNum = 15;
myNum = 20; // myNum is now 20
Console.WriteLine(myNum);
```

***Other Types***

A demonstration of how to declare variables of other types:

Example:

```
int myNum = 5;
double myDoubleNum = 5.99D;
char myLetter = 'D';
bool myBool = true;
string myText = "Hello";
```

### Constants

If you don't want others (or yourself) to overwrite existing values, you can add the const keyword in front of the variable type.

This will declare the variable as "constant", which means unchangeable and read-only:

Example:

```
const int myNum = 15;
myNum = 20; // error
```

The const keyword is useful when you want a variable to always store the same value, so that others (or yourself) won't mess up your code. An example that is often referred to as a constant, is PI (3.14159...).

***Note:*** You cannot declare a constant variable without assigning the value. If you do, an error will occur: A const field requires a value to be provided.


### Display Variables

The ***WriteLine()*** method is often used to display variable values to the console window.

To combine both text and a variable, use the + character:

Example:

```
string name = "John";
Console.WriteLine("Hello " + name);
```

You can also use the + character to add a variable to another variable:

Example:

```
string firstName = "John ";
string lastName = "Doe";
string fullName = firstName + lastName;
Console.WriteLine(fullName);
```

For numeric values, the + character works as a mathematical operator (notice that we use int (integer) variables here):

Example:

```
int x = 5;
int y = 6;
Console.WriteLine(x + y); // Print the value of x + y
```

### Multiple Variables

***Declare Many Variables***

To declare more than one variable of the same type, use a comma-separated list:

Example:

```
int x = 5, y = 6, z = 50;
Console.WriteLine(x + y + z);
```

You can also assign the same value to multiple variables in one line:

```
int x, y, z;
x = y = z = 50;
Console.WriteLine(x + y + z);
```

