# Csharp_Study_Note


#### Main Data Types  
`string` for words, phrases, or any alphanumeric data for presentation, not calculation  
`char` for a single alphanumeric character  
`int` for a whole number  
`decimal` for a number with a fractional component  
`bool` for a true/false value  

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
