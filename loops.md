# C++ Loops:

## for loop:
Repeats a codeblock until a condition evaluates to false. Used when you know when to stop looping because you know the condition that needs to change.
```c++
// Create a for loop:
// for + Tab

for (initializer; condition; iterator)
{
    codeblock
}

//Example:
for (int i = 0; i <= 5; i++)
{
    codeblock
}
```

<br>

## foreach loop:
Executes a codeblock for each element in a collection. Used when you know when to stop looping because you know it will loop until every element has been iterated over.
```c++
for (datatype elementName : collectionName)
{
    //codeblock
}

int myNumbers[] = {1, 2, 3, 4, 5};
for (int i : myNumbers)
{
    cout << i << endl;
}
```

<br>

## while loop:
Repeats a codeblock until a condition evaluates to false.

How to make:
- The while condition usually is made with: ==  or  >  or  <  
- The condition should be defined outside of the loop.  
- The code block will alter a variable that is part of the condition.  
- Eventually the condition will evaluate to false.
```c++
defined condition;
while (condition == true)
{
    //codeblock
}


int count = 0;
while (count < 5)
{
    cout << count;
    count++;
}


bool finished = false;
while (!finished)
{
    if (condition)
        finished = true;
    else
    {
        //codeblock
    }
}
```

<br>

## do-while loop:
```c++
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
} while (int.TryParse(consoleInput, out input) == false);
```

<br>
<br>

## break statement:
The break statement terminates the entire loop.

Weird example...!
```c++
int numbers[] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};
char letters[] = {'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j'};

for (int x = 0; x < sizeof(numbers) / sizeof(int); x++)
{
	cout << "num = " << numbers[x] << endl;

	for (int y = 0; y < sizeof(letters) / sizeof(char); y++)
	{
		if (y == x)
		{
			break;
			// the break is used only once, to skip printing the letter 'a' at 0
			// its a weird example.
		}
		cout << letters[y] << endl;
	}
	cout << endl;
}

// Output:
// num = 0
// num = 1
//  a
// num = 2
//  a  b
// num = 3
//  a  b  c
```

<br>
<br>

## continue statement:
The continue statement passes control to the next iteration of the loop.
```c++
for (int i = 1; i < 11; i++)
{
    if (i < 9)
    {
        continue;
    }
    cout << i << endl;
}

// Output:
// 9
// 10
```
