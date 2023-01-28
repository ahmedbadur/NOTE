# C PROGRAMMING LANGUAGE

## TOKEN

 - Compiler splits incoming code into smallest unit. These units are called **Token**. This process is called **Tokenizing**. Tokens are categorized as follows.

```
keywords: Reserved words given special tasks.
identifier: The name given to software assets. It can not start with a digit character.
constants: They are atoms that express numerical magnitude directly in the source code.
operators: The atoms that carry out the action are called.
string literals: Texts written in double quotes are called.
delimiter: A unique character or string that marks the start or stop of a particular statement, string, or function body set.
```

### Keywords

The following list shows the reserved words in C. These reserved words may not be used as
constant or variable or any other identifier names

```
auto 	  else 	  Long 	    switch
break 	  enum 	  register  typedef
case 	  extern  return    union
char 	  float   short     unsigned
const 	  for     signed    void
continue  goto    sizeof    volatile
default   if      static    while
do        int     struct    _packed
double
```

### Identifiers

A C identifier is a name used to identify a variable, function, or any other user-defined
item. An identifier starts with a letter A to Z or a to z or an underscore _ followed by zero
or more letters, underscores, and digits (0 to 9).
C does not allow punctuation characters such as @, $, and % within identifiers. C is a case
sensitive programming language. Thus, Manpower and manpower are two different
identifiers in C. Here are some examples of acceptable identifiers:

```
ahmed  frm move_name a_1234
myname50 _temp j a23b9 retVal
```

## DATA TYPES

 - The C programming language divides data types into two: **basic types** and **user-defined types**.
Basic Types are divided into two: **integer types** and **floating types**.

### Integer Types

```
char: 1 Byte
_Boll: 1 Byte
short: 2 Byte
int: 2/4/8 Byte
long: 4/8 Byte
long long: 8 Byte
```

### Floating Types

```
float: 4 Byte
double: 8 Byte
long double: 8/16 Byte
```

## STORAGE CLASSES in C


 - Storage classes in C are used to determine the lifetime, visibility, memory location, and initial value of a variable. There are four types of storage classes in C

**Automatic**

**External**

**Static**

**Register**


### Automatic Storage Class 

This is the default storage class for all the variables declared inside a function or a block. Hence, the keyword auto is rarely used while writing programs in C language. Auto variables can be only accessed within the block/function they have been declared and not outside them (which defines their scope). Of course, these can be accessed within nested blocks within the parent block/function in which the auto variable was declared. However, they can be accessed outside their scope as well using the concept of pointers given here by pointing to the very exact memory location where the variables reside. They are assigned a garbage value by default whenever they are declared.  

 - Automatic variables are allocated memory automatically at runtime.
 - The visibility of the automatic variables is limited to the block in which they are defined. The scope of the automatic variables is limited to the block in which they are defined.
 - The automatic variables are initialized to garbage by default.
 - The memory assigned to automatic variables gets freed upon exiting from the block.
 - The keyword used for defining automatic variables is auto.
 - Every local variable is automatic in C by default.

```
#include <stdio.h>

void func()
 {
    int x = 10;
    printf("x = %d\n", x);
    x += 10;
  }

int main()
 {
    func();
    func();
    func();
    func();
 }
```

When we run the printf command;

```
x = 10
x = 10
x = 10
x = 10

D:\AHMED-BADUR\EDUCATION\C PROGRAMMING WORKS\Lesson-01\x64\Debug\Lesson-01.exe (process 4844) exited with code 0.
Press any key to close this window . . .
```

 

### Static Storage Class

This storage class is used to declare static variables which are popularly used while writing programs in C language. Static variables have the property of preserving their value even after they are out of their scope! Hence, static variables preserve the value of their last use in their scope. So we can say that they are initialized only once and exist till the termination of the program. Thus, no new memory is allocated because they are not re-declared. Their scope is local to the function to which they were defined. Global static variables can be accessed anywhere in the program. By default, they are assigned the value 0 by the compiler. 

 - The variables defined as static specifier can hold their value between the multiple function calls.
 - Static local variables are visible only to the function or the block in which they are defined.
 - A same static variable can be declared many times but can be assigned at only one time.
 - Default initial value of the static integral variable is 0 otherwise null.
 - The visibility of the static global variable is limited to the file in which it has declared.
 - The keyword used to define static variable is static.

Example for global space;

```
int x = 10;
```

Example for local space;

```
#include <stdio.h>

void func()
  {
    static int x = 10;
    printf("x = %d\n", x);
    x += 10;
  }

int main()
 {
    func();
    func();
    func();
    func();
 }

```

When we run the printf command;

```
x = 10
x = 20
x = 30
x = 40
```

### Register Storage Class

 - The variables defined as the register is allocated the memory into the CPU registers depending upon the size of the memory remaining in the CPU.
 - We can not dereference the register variables, i.e., we can not use &operator for the register variable.
 - The access time of the register variables is faster than the automatic variables.
 - The initial default value of the register local variables is 0.
 - The register keyword is used for the variable which should be stored in the CPU register. However, it is compiler?s choice whether or not; the variables can be stored in the register.
 - We can store pointers into the register, i.e., a register can store the address of a variable.
 - Static variables can not be stored into the register since we can not use more than one storage specifier for the same variable.

```
#include <stdio.h>

int main()
  {
    register int a;
    printf("%d", a);
  }
```

When we run the printf command;

```
a=0
```

### External Storage Class

 - The external storage class is used to tell the compiler that the variable defined as extern is declared with an external linkage elsewhere in the program.
 - The variables declared as extern are not allocated any memory. It is only declaration and intended to specify that the variable is declared elsewhere in the program.
 - The default initial value of external integral type is 0 otherwise null.
 - We can only initialize the extern variable globally, i.e., we can not initialize the external variable within any block or method.
 - An external variable can be declared many times but can be initialized at only once.
 - If a variable is declared as external then the compiler searches for that variable to be initialized somewhere in the program which may be extern or static. If it is not, then the compiler will show an error.

```
#include <stdio.h>  

int main()  
  {  
     extern int a;   
     printf("%d",a);  
  }  
```

When we run the printf command;

```
main.c:(.text+0x6): undefined reference to `a'
collect2: error: ld returned 1 exit status
```

```
#include <stdio.h>  

int a;   
int main()  
  {  
     extern int a; // variable a is defined globally, the memory will not be allocated to a  
     printf("%d",a);  
  }  
```

When we run the printf command;

```
a=0
```


## VARIABLES

 - A variable is nothing but a name given to a storage area that our programs can
manipulate. Each variable in C has a specific type, which determines the size and layout of
the variable's memory; the range of values that can be stored within that memory; and the
set of operations that can be applied to the variable.

 - The name of a variable can be composed of letters, digits, and the underscore character. It
must begin with either a letter or an underscore. Upper and lowercase letters are distinct
because C is case-sensitive. Based on the 

```
Type 	Description
Char 	Typically a single octet(one byte). This is an integer type.
Int 	The most natural size of integer for the machine.
Float	A single-precision floating point value.
Double  A double-precision floating point value.
Void 	Represents the absence of type.
```


## FUNCTIONS

 - Function is a group of statements that together perform a task. Every C program has at least
one function, which is main(), and all the most trivial programs can define additional
functions.

 - You can divide up your code into separate functions. How you divide up your code among
different functions is up to you, but logically the division usually is so each function
performs a specific task.

- A function declaration tells the compiler about a function's name, return type, and
parameters. A function definition provides the actual body of the function.
The C standard library provides numerous built-in functions that your program can call. For
example, function strcat() to concatenate two strings, function memcpy() to copy one
memory location to another location and many more functions.

 - A function is known with various names like a method or a sub-routine or a procedure, etc

### Defining A Function

 - The general form of a function definition in C programming language is as follows:

```
return_type function_name( parameter list )
{
 body of the function
}
```
A function definition in C programming language consists of a function header and
a function body. Here are all the parts of a function:

 - **Return Type:** A function may return a value. The return_type is the data type of the
value the function returns. Some functions perform the desired operations without
returning a value. In this case, the return_type is the keyword **void**.

- **Function Name:** This is the actual name of the function. The function name and the
parameter list together constitute the function signature.
 
- **Parameters:** A parameter is like a placeholder. When a function is invoked, you pass a
value to the parameter. This value is referred to as actual parameter or argument. The parameter list refers to the type, order, and number of the parameters of a function.
Parameters are optional; that is, a function may contain no parameters.

- **Function Body:** The function body contains a collection of statements that define what
the function does.

Example;

 - Following is the source code for a function called max(). This function takes two parameters
num1 and num2 and returns the maximum between the two:

```
/* function returning the max between two numbers */
int max(int num1, int num2)
{
 /* local variable declaration */
 int result;
 if (num1 > num2)
 result = num1;
 else
 result = num2;
 return result;
}
```

### Function Arguments

 - If a function is to use arguments, it must declare variables that accept the values of the
arguments. These variables are called the formal parameters of the function.

 - The formal parameters behave like other local variables inside the function and are created
upon entry into the function and destroyed upon exit.

 - While calling a function, there are two ways that arguments can be passed to a function:

### Function Call By Value

- The **call by value** method of passing arguments to a function copies the actual value of an
argument into the formal parameter of the function. In this case, changes made to the
parameter inside the function have no effect on the argument.

 - By default, C programming language uses call by value method to pass arguments. In
general, this means that code within a function cannot alter the arguments used to call the
function. Consider the function swap() definition as follows.

```
/* function definition to swap the values */
void swap(int x, int y)
{
 int temp;
 temp = x; /* save the value of x */
 x = y; /* put y into x */
 y = temp; /* put x into y */

 return;
}
```

Now, let us call the function swap() by passing actual values as in the following example:

```
#include <stdio.h>
/* function declaration */
void swap(int x, int y);
int main ()
{
 /* local variable definition */
 int a = 100;
 int b = 200;
 printf("Before swap, value of a : %d\n", a );
 printf("Before swap, value of b : %d\n", b );
 /* calling a function to swap the values */
 swap(a, b);
 printf("After swap, value of a : %d\n", a );
 printf("After swap, value of b : %d\n", b );
 return 0;
}
```

Let us put above code in a single C file, compile and execute it, it will produce the following
result:

```
Before swap, value of a :100
Before swap, value of b :200
After swap, value of a :100
After swap, value of b :200
```

Which shows that there is no change in the values though they had been changed inside
the function.

### Function Call By Reference

 - The **call by reference** method of passing arguments to a function copies the address of an
argument into the formal parameter. Inside the function, the address is used to access the
actual argument used in the call. This means that changes made to the parameter affect
the passed argument.

 - To pass the **value by reference**, argument pointers are passed to the functions just like
any other value. So accordingly you need to declare the function parameters as pointer
types as in the following function swap(), which exchanges the values of the two integer
variables pointed to by its arguments.

```
/* function definition to swap the values */
void swap(int *x, int *y)
{
 int temp;
 temp = *x; /* save the value at address x */
 *x = *y; /* put y into x */
 *y = temp; /* put x into y */

 return;
}
```

Let us call the function swap() by passing values by reference as in the following example:

```
#include <stdio.h>
/* function declaration */
void swap(int *x, int *y);
int main ()
{
 /* local variable definition */
 int a = 100;
 int b = 200;
 printf("Before swap, value of a : %d\n", a );
 printf("Before swap, value of b : %d\n", b );
 /* calling a function to swap the values.
 * &a indicates pointer to a ie. address of variable a and
 * &b indicates pointer to b ie. address of variable b.
 */
 swap(&a, &b);
 printf("After swap, value of a : %d\n", a );
 printf("After swap, value of b : %d\n", b ); 
 return 0;
}
```

Let us put above code in a single C file, compile and execute it, it will produce the following
result:

```
Before swap, value of a :100
Before swap, value of b :200
After swap, value of a :100
After swap, value of b :200
```

Which shows that there is no change in the values though they had been changed inside
the function.


## ASCII CHARACTERS

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <ctype.h>


int main() 
{
	FILE* f = fopen("ascii.txt", "w");
	if (!f) 
	{
		fprintf(stderr, "dosya oluşturulamadı.\n");
		return 1;
	}
	for (int i = 0; i<128; ++i)
	{
		if (iscntrl(i))
		fprintf(f, "%3d %3x  CONTROL CHARACTER\n", i, i);
		else
		{
			fprintf(f, "%3d %3x  %c\n", i, i, i);
		}
	}

	fclose(f);

}
```

ascii.txt has been created.

```
  0   0  CONTROL CHARACTER
  1   1  CONTROL CHARACTER
  2   2  CONTROL CHARACTER
  3   3  CONTROL CHARACTER
  4   4  CONTROL CHARACTER
  5   5  CONTROL CHARACTER
  6   6  CONTROL CHARACTER
  7   7  CONTROL CHARACTER
  8   8  CONTROL CHARACTER
  9   9  CONTROL CHARACTER
 10   a  CONTROL CHARACTER
 11   b  CONTROL CHARACTER
 12   c  CONTROL CHARACTER
 13   d  CONTROL CHARACTER
 14   e  CONTROL CHARACTER
 15   f  CONTROL CHARACTER
 16  10  CONTROL CHARACTER
 17  11  CONTROL CHARACTER
 18  12  CONTROL CHARACTER
 19  13  CONTROL CHARACTER
 20  14  CONTROL CHARACTER
 21  15  CONTROL CHARACTER
 22  16  CONTROL CHARACTER
 23  17  CONTROL CHARACTER
 24  18  CONTROL CHARACTER
 25  19  CONTROL CHARACTER
 26  1a  CONTROL CHARACTER
 27  1b  CONTROL CHARACTER
 28  1c  CONTROL CHARACTER
 29  1d  CONTROL CHARACTER
 30  1e  CONTROL CHARACTER
 31  1f  CONTROL CHARACTER
 32  20   
 33  21  !
 34  22  "
 35  23  #
 36  24  $
 37  25  %
 38  26  &
 39  27  '
 40  28  (
 41  29  )
 42  2a  *
 43  2b  +
 44  2c  ,
 45  2d  -
 46  2e  .
 47  2f  /
 48  30  0
 49  31  1
 50  32  2
 51  33  3
 52  34  4
 53  35  5
 54  36  6
 55  37  7
 56  38  8
 57  39  9
 58  3a  :
 59  3b  ;
 60  3c  <
 61  3d  =
 62  3e  >
 63  3f  ?
 64  40  @
 65  41  A
 66  42  B
 67  43  C
 68  44  D
 69  45  E
 70  46  F
 71  47  G
 72  48  H
 73  49  I
 74  4a  J
 75  4b  K
 76  4c  L
 77  4d  M
 78  4e  N
 79  4f  O
 80  50  P
 81  51  Q
 82  52  R
 83  53  S
 84  54  T
 85  55  U
 86  56  V
 87  57  W
 88  58  X
 89  59  Y
 90  5a  Z
 91  5b  [
 92  5c  \
 93  5d  ]
 94  5e  ^
 95  5f  _
 96  60  `
 97  61  a
 98  62  b
 99  63  c
100  64  d
101  65  e
102  66  f
103  67  g
104  68  h
105  69  i
106  6a  j
107  6b  k
108  6c  l
109  6d  m
110  6e  n
111  6f  o
112  70  p
113  71  q
114  72  r
115  73  s
116  74  t
117  75  u
118  76  v
119  77  w
120  78  x
121  79  y
122  7a  z
123  7b  {
124  7c  |
125  7d  }
126  7e  ~
127  7f  CONTROL CHARACTER
```

### Escape Sequences

```
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <ctype.h>


int main() 
{
	printf("alert (bell)      %d\n", '\a');
	printf("horizontal tab    %d\n", '\t');
	printf("vertical tab      %d\n", '\v');
	printf("newline           %d\n", '\n');
	printf("carriage return   %d\n", '\r');
	printf("form feed         %d\n", '\f');
	printf("backspace         %d\n", '\b');
	printf("null character    %d\n", '\0');
	printf("single quote      %d\n", '\'');
	printf("double quote      %d\n", '\"');
	printf("backslash         %d\n", '\\');
	printf("question mark     %d\n", '\?');
}
```

It will appear as follows.

```
alert (bell)      7
horizontal tab    9
vertical tab      11
newline           10
carriage return   13
form feed         12
backspace         8
null character    0
single quote      39
double quote      34
backslash         92
question mark     63
```


## PRINTF()

 - The printf() function is used to format and print a series of characters and values to the standard output.

**Syntax:**

```
int printf(const char *format-string, argument-list);
```

### Parameters:

```
Name		Description
Format		The format argument is a string containing C language conversion specifications. The conversion specification specifies the notation, alignment, significant digits, field width, and other aspects of the output format. To represent non-printing characters, such as newlines and tabs, the format string may contain escape characters. Below are the details.
Argument-list	Depending on the format string, the function may require additional arguments.
```

 - Format strings specify notation, alignment, significant digits, field width, and other aspects of output formats. It can contain ordinary alphanumeric characters; along with escape characters, conversion specifiers, and other characters. Format specifications are made up of a the percent sign (%) followed by one of the following conversion operators, which determine what printf does with its arguments.

### Conversion Specifiers:

```
Specifier	Description
%%	 	Print a single % character
%c	 	Convert an int to an unsigned character and print the resulting character
%d or%i	 	Print an int as a signed decimal number
%u	 	Print an unsigned as an unsigned decimal number
%o	 	Print an unsigned as an unsigned octal number
%x	 	Hexadecimal notation (using lowercase letters a-f)
%X	 	Hexadecimal notation (using uppercase letters A-F)
%e	 	Exponential notation (using a lowercase e as in 3.1415e+00)
%E	 	Exponential notation (using an uppercase E as in 3.1415E+00)
%f	 	Print a double using a decimal format like [-]ddd.ddd
%g	 	The more compact of %e or %f, insignificant zeros do not print.
%G	 	Same as g, but using an uppercase E
%s	 	Print the string pointed to by a char *
%p	 	Print a void * argument in hexadecimal (ANSI C only)
%n	 	Store the number of characters printed at this point in the integer pointed to by the int * argument. Nothing is printed. (ANSI C only).
```

### Conversion Flags:

 - You can control the alignment of the output using any of these optional flags.

```
Flag		Format	Example
+ (plus)	Always prints a sign character (+ or -).		%+7.2d
- (minus)	Left-justifies the converted argument in its field.	%-7.2d
0 (Zero)	Pad with zeros rather than spaces.			%07.2d
# (hash)	Use an alternate form for the output. The effect 
		differs depending on the conversion specifier.
		-For o, the precision (described below) is increased 
		 so that the first digit printed is a 0
		-For x or X, a non-zero value has a 0x prepended 
		 (or 0X for the X specification)
		-For e, E, f, g or G, the result will always contain a 
		 decimal point, even if no digits follow it. 
		 Additionally, trailing zeros are not removed from 
   		 numbers formatted with g or G
```

Question:

Let's guess the result that will appear on the screen

```
#include <math.h>


int main()
{
	int x = 987654;
	printf("%d", printf("%d", printf("%d",x)));
}
```

The result will be like this.

```
98765461
D:\AHMED-BADUR\EDUCATION\C PROGRAMMING LANGUAGE\C PROGRAMMING WORKS\Lesson-01\x64\Debug\Lesson-01.exe (process 18068) exited with code 0.
Press any key to close this window . . .
```

Since the first value is 987654, the second printf function will return 6 because it is a 6 digit number. 
In the next function, it will return 1 because it is a single digit number. 987654 - 6 - 1. 
So the result will be 98765461.


## SCANF()

 - The C library function int scanf(const char *format, ...) reads formatted input from stdin.

**Syntax:**

```
int scanf(const char *format, ...);
```
 - int is the return type.
 - format is a string that contains the type specifiers(s).
 - “…” indicates that the function accepts a variable number of arguments.

Example type specifiers recognized by scanf:

```
%d to accept input of integers.
%ld to  accept input of long integers
%lld to accept input of long long integers
%f to accept input of real number.
%c to accept input of character types.
%s to accept input of a string.
```

Example:

```
int var;
scanf("%d", &var);
```

The scanf will write the value input by the user into the integer variable var.

### Why &

While scanning the input, scanf needs to store that input data somewhere. To store this input data, scanf needs to known the memory location of a variable. And here comes the ampersand to rescue.
 
 - & is also called as address of the operator.
 - For example, &var is the address of var.

Below is the C program to implement scanf:

```
int main()
{
    int a, b;
   
      printf("Enter first number: ");
      scanf("%d", &a);
   
      printf("Enter second number: ");
      scanf("%d", &b);
   
      printf("A : %d \t B : %d" ,
            a , b);
   
    return 0;
}
```

Output:

```
Enter first number: 5
Enter second number: 6
A : 5      B : 6
```


## OPERATORS


 - An operator is a symbol that tells the compiler to perform specific mathematical or logical functions. C language is rich in built-in operators and provides the following types of operators 

C divides the operators into the following groups:

 - Arithmetic Operators
 - Relational Operators
 - Logical Operators
 - Bitwise Operators
 - Assignment Operators
 - Misc Operators

### Arithmetic Operators

The following table shows all the arithmetic operators supported by the C language. Assume variable A holds 10 and variable B holds 20 then.

```
Operator	Description							Example
+		Adds two operands.						A + B = 30
−		Subtracts second operand from the first.			A − B = -10
*		Multiplies both operands.					A * B = 200
/		Divides numerator by de-numerator.				B / A = 2
%		Modulus Operator and remainder of after an integer division.	B % A = 0
++		Increment operator increases the integer value by one.		A++ = 11
--		Decrement operator decreases the integer value by one.		A-- = 9
```


### Relational Operators

The following table shows all the relational operators supported by C. Assume variable A holds 10 and variable B holds 20 then.

```
Operator	Description							Example
==		Checks if the values of two operands are equal or not. 		(A == B) is not true.
		If yes, then the condition becomes true.			
!=		Checks if the values of two operands are equal or not. 		(A != B) is true.
		If the values are not equal, then the condition becomes true.	
>		Checks if the value of left operand is greater than the value 	(A > B) is not true.
		of right operand. If yes, then the condition becomes true.	
<		Checks if the value of left operand is less than the value 	(A < B) is true.
		of right operand. If yes, then the condition becomes true.	
>=		Checks if the value of left operand is greater than or equal 	(A >= B) is not true.
		to the value of right operand. If yes, then the condition 
		becomes true.	
<=		Checks if the value of left operand is less than or equal to  	(A <= B) is true.
		the value of right operand. If yes, then the condition 
		becomes true.	
```


### Logical Operators

Following table shows all the logical operators supported by C language. Assume variable A holds 1 and variable B holds 0, then.

```
Operator	Description							Example
&&		Called Logical AND operator. If both the operands are 		(A && B) is false.
		non-zero, then the condition becomes true.	
||		Called Logical OR Operator. If any of the two operands is 	(A || B) is true.
		non-zero, then the condition becomes true.	
!		Called Logical NOT Operator. It is used to reverse the 		!(A && B) is true.
		logical state of its operand. If a condition is true, 
		then Logical NOT operator will make it false.	
```

### Bitwise Operators

Bitwise operator works on bits and perform bit-by-bit operation. The truth tables for &, |, and ^ is as follows.

```
p	q     p & q   p | q   p ^ q
0	0	0	0	0
0	1	0	1	1
1	1	1	1	0
1	0	0	1	1
```

The following table lists the bitwise operators supported by C. Assume variable 'A' holds 60 and variable 'B' holds 13, then.

```
Operator	Description								Example
&		Binary AND Operator copies a bit to the result if it exists in both 	(A & B) = 12, i.e., 0000 1100
		operands.	
|		Binary OR Operator copies a bit if it exists in either operand.		(A | B) = 61, i.e., 0011 1101
^		Binary XOR Operator copies the bit if it is set in one operand but 	(A ^ B) = 49, i.e., 0011 0001
		not both.	
~		Binary One's Complement Operator is unary and has the effect of		(~A ) = ~(60), i.e,. -0111101
		'flipping' bits.	
<<		Binary Left Shift Operator. The left operands value is moved left by 	A << 2 = 240 i.e., 1111 0000
		the number of bits specified by the right operand.	
>>		Binary Right Shift Operator. The left operands value is moved right 	A >> 2 = 15 i.e., 0000 1111
		by the number of bits specified by the right operand.	
```


### Assignment Operators

The following table lists the assignment operators supported by the C language.

```
Operator	Description								Example
=		Simple assignment operator. Assigns values from right side operands 	C = A + B will assign the value of A + B to C
		to left side operand	
+=		Add AND assignment operator. It adds the right operand to the left 	C += A is equivalent to C = C + A
		operand and assign the result to the left operand.	
-=		Subtract AND assignment operator. It subtracts the right operand 	C -= A is equivalent to C = C - A
		from the left operand and assigns the result to the left operand.	
*=		Multiply AND assignment operator. It multiplies the right operand 	C *= A is equivalent to C = C * A
		with the left operand and assigns the result to the left operand.	
/=		Divide AND assignment operator. It divides the left operand with 	C /= A is equivalent to C = C / A
		the right operand and assigns the result to the left operand.	
%=		Modulus AND assignment operator. It takes modulus using two 		C %= A is equivalent to C = C % A
		operands and assigns the result to the left operand.	
<<=		Left shift AND assignment operator.					C <<= 2 is same as C = C << 2
>>=		Right shift AND assignment operator.					C >>= 2 is same as C = C >> 2
&=		Bitwise AND assignment operator.					C &= 2 is same as C = C & 2
^=		Bitwise exclusive OR and assignment operator.				C ^= 2 is same as C = C ^ 2
|=		Bitwise inclusive OR and assignment operator.				C |= 2 is same as C = C | 2
```

### Misc Operators

Besides the operators discussed above, there are a few other important operators including sizeof and ? : supported by the C Language.

```
Operator	Description							Example
sizeof()	Returns the size of a variable.					sizeof(a), where a is integer, will return 4.
&		Returns the address of a variable.				&a; returns the actual address of the variable.
*		Pointer to a variable.						*a;
? :		Conditional Expression.						If Condition is true ? 
										then value X : otherwise value Y
```


## SEQUENCE POINTS in C

C is a structured, middle-level programming language that requires the use of a compiler to run programs written in it. The sequence point is defined as any point in the execution of a computer program at which all of the side effects of the previous evaluation of the program's code are completed or effectively completed. However, it also ensures that none of the later evaluations' modifications or side effects are carried out. In other words, a sequence point in imperative programming is any point in the execution of a computer program at which all of the side effects of the previous evaluation are assumed to have been completed.
Before we get into detail on Sequence points, it's important to grasp what are "side effects" we're talking about. Any action that changes the storage of an operand has a side effect. The programmer can intentionally cause side effects to achieve the desired result; in fact, the assignment operator relies on the side effect of changed storage to function. By the following sequence point in the program, C assures that all side effects of a particular expression will be fulfilled. Sequence points are checkpoints in a program where the compiler verifies that an expression's operations are completed.
The most basic sequence points in the C programming language are :

 - Logical AND (&&)
 - Logical OR(||)
 - Conditional(?)
 - Comma(,)

### Side Effects

The order in which expressions are evaluated is not specified in the C program. Since the compiler determines the sequence of evaluation based on context, some unexpected results may arise when using specific operators. These are termed as side effects.

Let's look at some examples to assist us understand the concept of side effects and practice it by yourself on C online compiler.

```
int main()
{
   int a = 3;
   int x = a++*a++;
   printf("%d\n", x);
}
```

The subexpression a++ has a side effect in that it changes the value of a, which creates undefined behaviour because a is also referenced elsewhere in the expression. Hence, the output of the code is also undefined.

So far we have discussed the details of the side effects . Now , let's understand the details of  sequence points which help the compiler from the side effects.

### Logical AND (&&)

The left operand of the logical AND (&&) operator will be fully performed first, including all side effects, before proceeding. The execution process will halt if the left operand evaluates to false, and the other operand will not be executed at all.
Lets understand the working of Logical AND (&&) through a small program.
Consider the following code snippet :

```
#include <stdio.h>  
int func1()
{
    printf ("Hello \n");
    return 1;
}  
int func2()
{
     printf ("Happy Coding!!!");
     return 1;
}  
int main()  
{  
  int a = func1() && func2();    
  return 0;  
}
```

Output:

```
Hello
Happy Coding!!!
```

Since Logical And(&&) defines a sequence point after the first operand, func1() will always be performed first.


### Logical OR (||)

When using logical OR (||), the left operand must be fully performed first, together with all of its side effects, before proceeding. If the left operand evaluates to false (or nonzero), however, the other operand is not executed.
Lets understand the working of Logical OR (||) through a small program.
Consider the following code snippet :

```
#include <stdio.h>  
int func1()
{
    printf ("Hello \n");
    return 1;
}  
int func2()
{
     printf ("Happy Coding!!!");
     return 1;
}  
int main()  
{  
  int a = func1() || func2();    
  return 0;  
}
```

Output:

```
Hello
```

Since Logical OR (||) defines a sequence point after the first operand, func1() will always be performed first. Since the func1() returns 1 (true) ,so func2() is not executed.

You can implement the code on online C editor.


### Conditional(?)

When using the conditional operator, the first operand will be evaluated first, and all of its side effects will be completed before proceeding.
Lets understand the working of Conditional (?) through a small program.
Consider the following code :

```
#include <stdio.h>  
int func1()
{
    printf ("Hello");
    return 1;
    }  
int func2()
{
     printf ("Happy Coding");
     return 1;
     }  
int main()  
{  
  int p = func1() ? func2() : 3 ;    
  return 0;  
}
```

Output:

```
Hello
Happy Coding!!!
```

Since conditional (?) defines a sequence point after the first operand, func1() will always be performed first.


### Comma(,)

When using the comma (,), the first operand will be evaluated first, and all of its side effects will be completed before proceeding.
Lets understand the working of Comma (,) through a small program.
Consider the following code :

```
#include <stdio.h>  
int func1()
{
    printf ("Hello \n");
    return 1;
}  
int func2()
{
     printf ("Happy Coding!!!");
     return 1;
}  
int main()  
{  
  int a = (func1() , func2());    
  return 0;  
}
```

Output:

```
Hello
Happy Coding!!!
```

Since comma (,) defines a sequence point after the first operand, func1() will always be performed first.


## CONDITIONAL (TERNARY) OPERATOR

Besides false, possible falsy expressions are: null, NaN, 0, the empty string (""), and undefined. If condition is any of these, the result of the conditional expression will be the result of executing the expression exprIfFalse.

Syntax:

```
condition ? exprIfTrue : exprIfFalse
```

### Parameters:

**condition:**
An expression whose value is used as a condition.

**exprIfTrue:**
An expression which is executed if the condition evaluates to a truthy value (one which equals or can be converted to true).

**exprIfFalse**
An expression which is executed if the condition is falsy (that is, has a value which can be converted to false).

```
#include <stdio.h>

int main() {
  int age;

  // take input from users
  printf("Enter your age: ");
  scanf("%d", &age);

  // ternary operator to find if a person can vote or not
  (age >= 18) ? printf("You can vote") : printf("You cannot vote");

  return 0;
}
```

Output:

```
Enter your age: 12
You cannot vote
```

### Ternary Operator vs. If/Else Statement

In some of the cases, we can replace the if...else statement with a ternary operator. This will make our code cleaner and shorter.

Let's see an example:

```
#include <stdio.h>

int main() {
  int number = 3;

  if (number % 2 == 0) {
    printf("Even Number");
  }
  else {
    printf("Odd Number");
  }

  return 0;
}
```

We can replace this code with the following code using the ternary operator.

```
#include <stdio.h>

int main() {
  int number = 3;

  (number % 2 == 0) ? printf("Even Number") : printf("Odd Number");

  return 0;
}
```

Here, both the programs are doing the same task, checking even/odd numbers. However, the code using the ternary operator looks clean and concise.


## LOOP STATEMENTS

The looping simplifies the complex problems into the easy ones. It enables us to alter the flow of the program so that instead of writing the same code again and again, we can repeat the same code for a finite number of times. For example, if we need to print the first 10 natural numbers then, instead of using the printf statement 10 times, we can print inside a loop which runs up to 10 iterations.

### Types of C Loops

There are three types of loops in C language that is given below:

**do while**
**while**
**for**

### Do While Loop in C

The do-while loop continues until a given condition satisfies. It is also called post tested loop. It is used when it is necessary to execute the loop at least once (mostly menu driven programs).

Syntax:

```
do{  
//code to be executed  
}while(condition);  
```


### While Loop in C

The while loop in c is to be used in the scenario where we don't know the number of iterations in advance. The block of statements is executed in the while loop until the condition specified in the while loop is satisfied. It is also called a pre-tested loop.

Syntax:

```
while(condition){  
//code to be executed  
}   
```

### For Loop in C

The for loop is used in the case where we need to execute some part of the code until the given condition is satisfied. The for loop is also called as a per-tested loop. It is better to use for loop if the number of iteration is known in advance.

Syntax:

```
for(initialization;condition;incr/decr){  
//code to be executed  
}  
```

Question:

Output will print "C LANGUAGE" 5 times. You will only add or change one character in the code.

```
int main()
{
   int n =5;

   for (int i = 0; i<n; i--)
        printf("C LANGUAGE\n");
}
```

First Solution:

```
int main()
{
   int n =5;

   for (int i = 0; i<n; n--) // (i--) wil be (n--)
        printf("C LANGUAGE\n");
}
```


Second Solution:

```
int main()
{
   int n =5;

   for (int i = 0; -i<n; i--) // (i<n) wil be (-i<n)
        printf("C LANGUAGE\n");
}
```

Third Solution:

```
int main()
{
   int n =5;

   for (int i = 0; i=n; i--) // (i<n) wil be (i+n)
        printf("C LANGUAGE\n");
}
```
