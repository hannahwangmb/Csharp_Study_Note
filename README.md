# C#_Learning_Note


#### Main Data Types  
`string` for words, phrases, or any alphanumeric data for presentation, not calculation  
`char` for a single alphanumeric character  
`int` for a whole number  
`decimal` for a number with a fractional component  
`bool` for a true/false value  

### Literal and Variable Values
#### Variable Declaration  
To create a new variable, first declare the data type of the variable and give it a name: `dataType firstName;`  
##### Variable name rules:
- Can contain alphanumeric characters and the underscore character (1,2,3,...,a,B,c,...,_). Special characters are not allowed.  
- Must begin with an alphabetical letter or an underscore, not a number.
- Case-sensitive.
- Must not be a C# keyword. For example, you cannot use: `decimal decimal;` or `string string;`

##### Implicitly typed local variables
`var message = "Hello world!";`   
- In this case, an implicitly typed local variable is created by using the `var` keyword followed by a variable initialization.    
- A string variable was created using the `var` keyword instead of the `string` keyword. The `var` keyword tells the C# compiler that the data type is implied by the assigned value.   
- Now, the `message` variable is typed to be a `string` and can never be changed.
- NOTE: Variables using the `var` keyword must be initialized. Solely `var message;` will generate an error.

### Basic String Formatting
#### formatting literal strings
`\n` adds a new line.  
`\t` adds a tab.  
`\` escape sequence.  
`@` creates a verbatim string literal that keeps all whitespace formatting and backslash characters in a string.  
`$` allows to use string interpolation to include variables in the string.

#### String Concatenation
```
// Interpolation expression
string message = greeting + " " + firstName + "!";
// or
string message = $"{greeting} {firstName}!";
```
```
// Use string interpolation to combine a literal string and a variable value
string firstName = "Bob"; 
string message = $"Hello {firstName}!";  
Console.WriteLine(message);
```
```
// Use string interpolation with multiple variables and literal strings
int version = 11;  
string updateText = "Update to Windows";  
string message = $"{updateText} {version}";  
Console.WriteLine(message);
```
```
// Avoid intermediate variables
int version = 11;
string updateText = "Update to Windows";
Console.WriteLine($"{updateText} {version}!");
```
```
// Combine verbatim literals and string interpolation
string projectName = "First-Project";
Console.WriteLine($@"C:\Output\{projectName}\Data");
```
### Basic Operations on Numbers
#### Perform addition with implicit data conversion
```
int firstNumber = 12;
int secondNumber = 7;
Console.WriteLine(firstNumber + secondNumber);
(Output: 19)
```
```
string firstName = "Bob";
int widgetsSold = 7;
Console.WriteLine(firstName + " sold " + widgetsSold + " widgets.");
(Output: Bob sold 7 widgets.)
```
```
string firstName = "Bob";
int widgetsSold = 7;
Console.WriteLine(firstName + " sold " + widgetsSold + 7 + " widgets.");
(Output: Bob sold 77 widgets.)
```
```
string firstName = "Bob";
int widgetsSold = 7;
Console.WriteLine(firstName + " sold " + (widgetsSold + 7) + " widgets.");
(Output: Bob sold 14 widgets.)

// However, you should probably avoid performing both a calculation and concatenation in a single line of code. 
```

#### Perform addition, subtraction, multiplication, and division with integers
```
int sum = 7 + 5;
int difference = 7 - 5;
int product = 7 * 5;
int quotient = 7 / 5;

(Output:
Sum: 12
Difference: 2
Product: 35
Quotient: 1)
```
#### Perform division using literal decimal data
```
// These gonna work
decimal decimalQuotient = 7.0m / 5;
decimal decimalQuotient = 7 / 5.0m;
decimal decimalQuotient = 7.0m / 5.0m;
Console.WriteLine($"Decimal quotient: {decimalQuotient}");
```
```
// These won't
int decimalQuotientA = 7 / 5.0m;
int decimalQuotientB = 7.0m / 5;
int decimalQuotientC = 7.0m / 5.0m;
decimal decimalQuotientD = 7 / 5;
```
#### Perform a data type cast from int to decimal
```
int first = 7;
int second = 5;
decimal quotient = (decimal)first / (decimal)second;
Console.WriteLine(quotient);
(Output: 1.4)
```
#### Determine the remainder after integer division
```
Console.WriteLine($"Modulus of 200 / 5 : {200 % 5}");
Console.WriteLine($"Modulus of 7 / 5 : {7 % 5}");
(Output:
Modulus of 200 / 5 : 0
Modulus of 7 / 5 : 2)
```
#### Order of Operations
1. Parentheses (whatever is inside the parenthesis is performed first)
3. Multiplication and Division (from left to right)
4. Addition and Subtraction (from left to right)

#### Increment and decrement
```
int value = 0;     // value is now 0.
value = value + 5; // value is now 5.
value += 5;        // value is now 10.
```
```
int value = 0;     // value is now 0.
value = value + 1; // value is now 1.
value++;           // value is now 2.
```
#### Position the increment and decrement operators
if you use the operator before the value as in ++value, then the increment will happen before the value is retrieved. Likewise, value++ will increment the value after the value has been retrieved.  
```
int value = 1;
value++;
Console.WriteLine("First: " + value);
Console.WriteLine($"Second: {value++}");
Console.WriteLine("Third: " + value);
Console.WriteLine("Fourth: " + (++value));

(Output:
First: 2
Second: 2
Third: 3
Fourth: 4)
```

