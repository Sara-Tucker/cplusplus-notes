
# Hello World
```c++
#include <iostream>

int main()
{
	std::cout << "Hello World!" << std::endl;
}
```
`#`  - preprocessor directive
:: - scope resolution operator that allows look-ups for objects by name within a namespace.
<< - the stream 'insertion operator', which inserts an object into the stream object. "stream << content"

<br>
<br>

# Strings:
Function | Description
---
length() | Returns the length of the string.
find() | Search for a certain substring inside a string and returns the position of the first character of the substring. 
substr() | This function is used to create a substring from a given string. 

<br>
<br>

**Get input:**  
```c++
#include <iostream>
using namespace std;

int main()
{
	int value;
	cout << "Enter a value: " << endl;
	cin >> value;
}
```

**Convert input to int:**  
```c++
// Convert input (does not account for an exception)
#include <string>
using namespace std;

int main()
{
	string myString = "42";
	int myNum = stoi(myString);
}
```
```c++
// Convert input (accounts for an exception)
string consoleInput;
int input;
bool incorrect = false;

do
{
    if (incorrect)
        cout << "Your input was not valid. Please try again.\n";
	
    cout << "Enter a number: ";
    cin >> consoleInput;
    incorrect = true;
} while (int.TryParse(consoleInput, out input) == false);// C# code

// input is now == (int)consoleInput
```

<br>
<br>

**Type conversion:**  
```c++
// Cast float to int
float x = 1234.7f;
int a = (int)x;
```
```c++
// String to int
stoi(x);
```
```c++
// Numbers to string
y = to_string(x);
```
```c++
// Other
static_cast{DataTypesHere}(x);
```
```c++
// Change float decimal places (only when printing)
cout << fixed << setprecision(2) << x;
```

<br>
<br>

**Random:**  
```c++
#include <random>
using namespace std;

int main()
{
	random_device device;
	default_random_engine engine(device());
	uniform_int_distribution<int> r(minValue, maxValue);

	int randNum = r(engine);
}
```

<br>
<br>

**Conditional Operator '?:'** - Returns one of two values depending on the value of a Boolean expression.  
```c++
// The condition evaluates to true or false. If true then #1 is returned, if false then #2 is returned.
condition ? first_expression : second_expression;

classify = (input > 0) ? "positive" : "negative";  
```

<br>
<br>

**enum** - An enum/enumeration is a set of named integer constants.
```c++
enum ShippingMethod
{
	Regular = 1,
	Priority = 2,
	Express = 3
};

int shMethod = ShippingMethod::Express;
cout << shMethod; // 3
```

<br>
<br>

### DateTime: (doesn't work)
```c++
#include <ctime>

time_t now = time(0);

cout << "Number of sec since January 1,1970 is:: " << now << endl;

tm* ltm = localtime_s(&now);

// print various components of tm structure.
cout << "Year:" << 1900 + ltm->tm_year << endl;
cout << "Month: " << 1 + ltm->tm_mon << endl;
cout << "Day: " << ltm->tm_mday << endl;
cout << "Time: " << 5 + ltm->tm_hour << ":";
cout << 30 + ltm->tm_min << ":";
cout << ltm->tm_sec << endl;



#include <ctime>

// Get current date:
time_t now = time(0);
var today = DateTime.Today;

// Access units of DateTime:
Console.WriteLine(now.Hour);
Console.WriteLine(now.Minute);

// Add or subtract units to DateTime:
var tomorrow = now.AddDays(1);
var yesterday = now.AddDays(-1);

// Print DateTimes:
Console.WriteLine(now.ToLongDateString);
Console.WriteLine(now.ToShortDateString);
Console.WriteLine(now.ToLongTimeString);
Console.WriteLine(now.ToShortTimeString);

Console.WriteLine(now.ToString("")); //inside "" shows all the options for printing.
```









<br>
<br>
<br>
<br>

<br>
<br>

# Functions
```c++
// Declaration
int multiply(int a, int b = 7); // Default values for parameters can only be specified in declarations.

// Definition
int multiply(int a, int b)
{
	return a * b; 
}
```

**Prototype declaration**:
The prototype must specify the return type (void), the name of the function (foo), and the argument list variable types (int), but *the names of the arguments are NOT required.*
```c++
void foo(int); // Prototype declaration of foo, seen by main
				// Must specify return type, name, and argument list types

int main()
{
	foo(2); // OK: foo is known, called even though its body is not yet defined
}

void foo(int x) //Must match the prototype
{
	// Define body of foo here
}
```

One common way to integrate this into the organization of source files is to make a header file containing all of the prototype declarations:
```c++
// foo.h
void foo(int); // prototype declaration

// foo.cpp
#include "foo.h" // foo's prototype declaration is "hidden" in here

void foo(int x)
{
	// foo's body definition
}
```

<br>
<br>




what is a header (file)?
The header files contain the definition of the functions and macros we are using in our program.







<br>
<br>
<br>
<br>
<br>
<br>


<br>
<br>

**Exception Handling:**  
An exception is a problem that arises during the execution of a program.

Exceptions provide a way to transfer control from one part of a program to another. C# exception handling is built upon four keywords:

- try − try actions that may not succeed, and is followed by one or more catch blocks.
- catch − defines an exception handler
- finally − cleans up resources afterward. The finally block is used to execute a given set of statements, whether an exception is thrown or not thrown. For example, if you open a file, it must be closed whether an exception is raised or not.
- throw − Creates an exception.

<br>

Use a try block around the statements that might throw exceptions.  
Once an exception occurs in the try block, the flow of control jumps to the first associated exception handler (the catch keyword is used to define an exception handler)  
If no exception handler for a given exception is present, the program stops executing with an error message.  
Code in a finally block is executed even if an exception is thrown. Use a finally block to release resources, for example to close any streams or files that were opened in the try block.

<br>

```c++
try {
   // statements causing exception
} catch( ExceptionName e1 ) {
   // error handling code
} catch( ExceptionName e2 ) {
   // error handling code
} catch( ExceptionName eN ) {
   // error handling code
} finally {
   // statements to be executed
}
```
```
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/exceptions/using-exceptions
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/exceptions/exception-handling
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/exceptions/creating-and-throwing-exceptions
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/exceptions/how-to-handle-an-exception-using-try-catch
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/exceptions/how-to-execute-cleanup-code-using-finally
```

<br>
<br>

**Debugging:**  
Set breakpoints and watch variable values with: Debug -> Windows -> Autos/Locales

Keep the console window open in debug mode:
```c++
Console.WriteLine("Press any key to exit.");
System.Console.ReadKey();
```

<br>
<br>

**Access modifier** - The accessibility of a member or type.
```
Public - visible/accessible anywhere  
Private - only visible/accessible in the entire block where it's defined

Private is the default access modifier if none was declared.
```

<br>
<br>

**Methods:**  
Method Signature:  
Name of the method, the number of parameters, and the type of parameters.

Method Overloading:  
Having methods with the same name but different signatures.
```c++
public void Move(int x, int y) {}
public void Move(Point newLocation) {}
public void Move(Point newLocation, int speed) {}
```

<br>

Method Parameter Modifiers:

Params modifier:  
specifies that this parameter takes a varying number of arguments.
```c++
public class Calculator
{
    public int Add(int[] numbers)
    {
    }
}
var result = calculator.Add(new int[]{ 1, 2, 3, 4});

public class Calculator
{
    public int Add(params int[] numbers)
    {
    }
}
var result = calculator.Add(1, 2, 3, 4);
```
Ref and Out modifier are bad to use.

<br>
<br>
<br>

Read only:  
readonly int a;

<br>

OOP:
- Encapsulation (information hiding)
    - Define fields as private
	- Provide public getter/setter methods
- Inheritance
- Polymorphism

<br>

```c++
if (!String.IsNullOrEmpty(stringName))
    //
```

<br>

Private fields should be written as:  
private int _camelCase;

<br>
<br>

---

<br>
<br>

### Properties:
```c++
using System;
public class PlayerInput
{
    private float horizontalData;
    private float verticalData;
    // We don't want other classes changing this data so it is private.
    // However, another class needs to read the data from these variables.
    // But since they are private they are only visable in this class.


    // We could write public methods that allow us to get or set these private variables:
    public float GetHorizontalData()
    {
        return horizontalData;
    }

    public void SetHorizontalData(float hData)
    {
        horizontalData = hData;
    }
}


// And then call them from another class:
public class IDK
{
    float hInput;

    public void Main()
    {
        PlayerInput PIObject = new PlayerInput();
	
	hInput = PIObject.horizontalData;
	// Error: PIObject.horizontalData is private and not accessable outside of PIObject.
        // You cannot get the private data.
	
	PIObject.horizontalData = 3.22f;
	// Error: PIObject.horizontalData is private and not accessable outside of PIObject.
        // You cannot set the private data.

        // Using the public methods to access the private data:
        hInput = PIObject.GetHorizontalData();
        PIObject.SetHorizontalData(3.22f);
	
        Console.WriteLine(hInput);
        Console.WriteLine(PIObject.GetHorizontalData());
    }
}

// But instead you could do it in a much easier way using properties.
```

<br>

**Property** - A class member that provides access to fields of a class.

A get property accessor is used to return the value, and a set property accessor is used to assign a new value.

<br>

Example:
```c++
// Create a property:
// propfull + Tab
// prop + Tab


//Get input data
float m_h;
public float H { get { return m_h; } } //Read only
float m_v;
public float V { get { return m_v; } } //Read only 

bool m_inputEnabled = false;
public bool InputEnabled { get { return m_inputEnabled; } set { m_inputEnabled = value; } }


public void GetInputKey()
{
    if (m_inputEnabled)
    {
        m_h = Input.GetAxisRaw("Horizontal");
        m_v = Input.GetAxisRaw("Vertical");
    }
}



// And then from another class:
void Update ()
{
    if (playerMover.isMoving)
    {
        return;
    }

    playerInput.GetInputKey();

    if (playerInput.V == 0)
    {
        if (playerInput.H < 0)
        {
            playerMover.MoveLeft();
        }
        else if (playerInput.H > 0)
        {
            playerMover.MoveRight();
        }
    }
    else if (playerInput.H == 0)
    {
        if (playerInput.V < 0)
        {
            playerMover.MoveBackward();
        }
        else if (playerInput.V > 0)
        {
            playerMover.MoveForward();
        }
    }
}
```

<br>

Useful things you can do with properties but can't if the variables were just public:
```c++
public bool InputEnabled
{
    get { return inputEnabled; }
    set
    {
        inputEnabled = value;
        Debug.Log("Input changed to: " + inputEnabled);
        // Everytime the value is changed its value is printed to the console.
    }
}

public float Health
{
    get { return health; }
    set
    {
        health = value;
	Object.UpdateHPUI(health);
	// When hp is changed the property automatically updates the UI.
    }
}
```

<br>

Initialize an auto-implemented property:
```c++
public string FirstName { get; set; } = "Jane";
```

<br>
<br>

---

<br>
<br>

### Anonymous Function (lambda expression):
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/statements-expressions-operators/lambda-expressions

A function definition that is not bound to an identifier and contains only one executable statement.

Lambdas allow you to write quick throw away functions without naming them. They also provide a nice way to write closures.

Anonymous functions are often referred to as lambdas and often are introduced using the keyword lambda.

This anonymous function allows you to create functions from functions:
```python
def add(x):
    return lambda y: x + y
foo = add(5)
foo(1)


def add**(x)**:
    return lambda y: **x** + y
# The x variable in the lambda expression is referencing the parameter x, so x = x.

def add(x):
    return lambda **y**: x + y
# The lamdba requires the parameter y.

def add(x):
    **return lambda y: x + y**
# Add() returns a lambda.

foo = add(5)
# "foo = lambda y: 5 + y"

foo(1)
# "foo = lambda 1: 5 + 1"
>>> 6
```

<br>
<br>

Closure:  
https://stackoverflow.com/a/7464475/9020002  
https://stackoverflow.com/questions/4103750/closure-because-of-what-it-can-do-or-because-it-does  
https://www.google.com/search?q=programming+closure&ie=utf-8&oe=utf-8&client=firefox-b-1-ab

<br>
<br>

---

<br>
<br>

### Attributes:
A declarative tag that is used to convey information to runtime about the behaviors of various elements like classes, methods, structures, enumerators, etc. in your program.

Attributes add metadata to your program. Metadata is information about the types defined in a program.
```c++
// Declaring an attribute:
[attribute(positional_parameters, name_parameter = value, ...)] element;

[HideInInspector] public RoomNavigation roomNavigation;
```

<br>
<br>

---












# C++ Functions:
A function is simply the idea of taking multiple lines of code and giving it a name so it can be called later.
Function - reusable code that preforms an action and can optionally return data

Create a function:
	def functionname():
		code
Calling a function:
	function_name()
Example:
	def sayhi():
		print('Hi!')
	sayhi()

print() - prints text
	fruit = 'apple'
	print(fruit)
	print('orange')
str() - converts value to a string
	numapples = 5
	print('I have ' + str(numapples) + ' apples.')
input() - gets input from user
	Getting Input:
		input()
		input('What you want to ask for.')
		fruit = input('Enter a fruit.')
		print(fruit + ' is a good fruit.')
int() - converts a string to an integer
	response = input('How far would you like to travel in miles? ')
	distance = int(response)
float() - converts a string to a float








