# Bash Scripting

# Table of Contents
-[Pre-requisites](#Pre-requisites)
- [Introduction of Bash Scripting](#introduction-of-bash-scripting)

- [Writing and Executing Simple Scripts](#writing-and-executing-simple-scripts)
- [Conditinoal statement](#conditinoal-statement)
- [Control flow](#control-flow)
- [Array](#array)
- [String](#string)
- [Function](#function)
- [File Handling](#file-handling)



## Pre-requisites:

A running version of Linux with access to the command line.

# Introduction of Bash Scripting

### Bash Shell Scripting Definition

### Bash

- Bash is a command language interpreter. 
- It is widely available on various operating systems and is a default command interpreter on most GNU/Linux systems.
- The name is an acronym for the ‘Bourne-Again SHell’.

### Shell

 Shell is a macro processor which allows for an interactive or non-interactive command execution. 

### Scripting

Scripting allows for an automatic commands execution that would otherwise be executed interactively one-by-one.

## Advantages of Bash Scripting:

**Automation**: Simplifies and speeds up repetitive tasks, reducing manual errors.

**Portability**: Runs on Unix, Linux, macOS, and can be adapted for Windows with emulators.

**Flexibility**: Highly customizable, easily modified, and can be integrated with other languages.

**Accessibility**: Requires only a text editor; no special tools needed. Compatible with most operating systems.

**Integration**: Easily integrates with various tools and applications, enhancing automation capabilities.

# Writing and Executing Simple Scripts

#### Step 1.Writing a Bash Script

Open a text editor (nano, vim or vi) and create a new file. Let's call it filename.sh , Here's a simple example script:

```bash

#!/bin/bash

# This is a simple Bash script

echo "Hello, World!"

# Variables 
name="Joy"
echo "My name is $name"

# Command substitution
current_date=$(date)
echo "Current date: $current_date"

```



Save the file and exit the text editor.

#### Step 2. Executing the bash script

To make the script executable, assign execution rights to your user using this command:

```bash
chmod +x filename.sh
```
Here,

- chmod modifies the ownership of a file for the current user :u.
- +x adds the execution rights to the current user. This means that the user who is the owner can now run the script.
- filename.sh is the file we wish to run.

#### Step 3: Executing the Script

Now that your script is executable, You can run the script using any of the mentioned methods:

```bash 
    sh filename.sh
or
    filename.sh
or
    ./filename.sh
```



This will execute the Bash script, and you should see the output on the terminal.

### Output(with Command)

 **Step 1.** shrikant@shrikant:~$ vi Filename.sh

 **Step 2.** shrikant@shrikant:~$ chmod +x Filename.sh

 **Step 3.** shrikant@shrikant:~$ sh Filename.sh

Hello, World!

My name is Joy

Current date: Monday 08 January 2024 10:40:24 AM IST



### Shebang (#!)

 The shebang is placed at the beginning of the script and indicates the path to the interpreter. For Bash scripts, it is commonly:

   ``` bash

#!/bin/bash

```
### Print to Console:

  Use echo to print messages to the console(or Terminal) massages may be  in form text number or value of a variable.

  ```bash

    echo "Hello, World!"

```

### User Input:

Read user input using the read command.

```bash

echo "Enter your name: "
read username
echo "Hello, $username!"
```

#### Output:

Enter your name: 

Shri kant

Hello, Shri kant!
'


### Comment 

Comments start with a # in bash scripting. This means that any line that begins with a # is a comment and will be ignored by the interpreter.


These are examples of comments:

```bash 

# Thisline is comment it will be ignored by the interpreter
# Single line comment

For multi line comment

<< text

this is multi line comment Syntax


text

or
:'

Also this  for multi line Syntax
'

```
### Variable

In Bash, you can use and set the variable values in the following ways:

1. Assign the value directly:

```bash 

name = Aman

```
2. Assign the value based on the output obtained from a program or command, using command substitution. Note that $ is required to access an existing variable's value.

```bash
Name=$name

```

This assigns the value of name to the new variable Name

### Operator

There are five basic operators in bash/shell scripting:

1. Arithmetic Operators.
2. Relational Operators.
3. Boolean Operators.
4. Bitwise Operators.
5. File Test Operators.

#### Arithmetic Operators:

Addition (+): result=$((a + b))

Subtraction (-): result=$((a - b))

Multiplication (*): result=$((a * b))

Division (/): result=$((a / b))

Modulus (%): result=$((a % b)) 

Modulus(%) use for find remender
        
#### Relational Operators:

Equal to (==): [[ $a -eq $b ]]

Not equal to (!=): [[ $a -ne $b ]]

Greater than (>): [[ $a -gt $b ]]

Less than (<): [[ $a -lt $b ]]

Greater than or equal to (>=): [[ $a -ge $b ]]

Less than or equal to (<=): [[ $a -le $b ]]

#### Boolean Operators:

AND (&&): [[ condition1 && condition2 ]]
OR (||): [[ condition1 || condition2 ]]
NOT (!): [[ !condition ]]

#### Bitwise Operators:

Bash doesn't have native bitwise operators. Use external tools like bc or perform bitwise operations using arithmetic operations.

#### File Test Operators:

-e: [[ -e $file_path ]] (file exists)

-f: [[ -f $file_path ]] (regular file)

-d: [[ -d $file_path ]] (directory)

-s: [[ -s $file_path ]] (not empty)

-r: [[ -r $file_path ]] (readable)

-w: [[ -w $file_path ]] (writable)

-x: [[ -x $file_path ]] (executable)



# Conditional statement

Statements that help to execute different code branches based on certain conditions are known as conditional statements.


#### if Statements

```bash
if [ condition ];
then
	statement
fi
```
### Example
```bash
#!/bin/bash

echo "Hi newIntern please enter your Completed Tasks.
"

read Completed_Task

if [ "$Completed_Task" -eq 6 ];

then

  echo "Congratualations Team!, Now you are member of TechInternTeam."

fi

```


You can use if statements in a variety of ways. The generic structure of if statements is as follows:

    
    
Using if statement only: if...then...fi

#### if else Statements

```bash
if [ condition ];
then
	statement
else
	do this by default
fi

```
**Example**

```bash
#!/bin/bash

echo "Please enter a number: "
# user gives a number 
read num
# check  num is greater then zero then print num is positive 

if [ $num -gt 0 ]; then

  echo "$num is positive"
  
# check num is less then zero then print num is negative

elif [ $num -lt 0 ]; then
  echo "$num is negative"
else
# defualt print zero
  echo "$num is zero"
fi
```

Using and if with an else statement: if...then...else...fi statements

#### Multiple else statements

```bash
if [ condition ];
then
	statement
elif [ condition ] 
then
	statement 
else
	do this by default
fi
```
Using multiple else statements with if: if..elif..else..fi

### Case

 A "case" statement is used for conditional branching based on pattern matching. It is similar to a switch statement in other programming languages. The basic syntax of a case statement in Bash looks like this:

```bash

#!/bin/bash

variable="value"

case "$variable" in
  pattern1)
    # code to be executed if variable matches pattern1
    ;;
  pattern2)
    # code to be executed if variable matches pattern2
    ;;
  pattern3|pattern4)
    # code to be executed if variable matches pattern3 or pattern4
    ;;
  *)
    # code to be executed if variable does not match any pattern
    ;;
esac
```

**Example**
```bash
#!/bin/bash

day=$(date +%u)  # Get the current day of the week (1 to 7, where 1 is Monday and 7 is Sunday)
# The date +%u command is used to get the current day of the week

case "$day" in
  1)
    echo "It's Monday. Time to start the week!"
    ;; # Break
  2|3|4|5)
    echo "It's a weekday. Keep going!"
    ;; 
  6)
    echo "It's Saturday. Have a great weekend!"
    ;;
  7)
    echo "It's Sunday. Relax and prepare for the upcoming week."
    ;;
  *)
    echo "Invalid day."
    ;;
esac
```



    

# Control Flow

The shell language also provide several iteration or looping statements. In this article let us review the looping statements which bash provides using some examples.

Bash supports following three types of looping statement

1. For loop

2. While loop

3. Until loop

#### For Loop – First Method

For loops are typically used when the number of iterations is known before entering the bash loop. Bash supports two kinds of for loop. The first form of bash for loop is:

```bash
for varname in list
	do
		commands ##Body of the loop
	done
```
In the above syntax:

for, in, do and done are keywords
List is any list which has list of items
varname is any Bash variable name.

**Example**
```bash
#!/bin/bash
# For loop with number range
for i in {0..5}
do
        echo "Number $i"
done
```
                    

#### For Loop – Second Method

The second form of for loop is similar to the for loop in ‘C’ programming language, which has three expression (initialization, condition and updation).

```bash
for (( expr1; expr2; expr3 ))
         do
		commands
         done

  ```  
	
- In the above bash for command     syntax, before the first iteration, expr1 is evaluated. This is usually used to initialize variables for the loop.
- All the statements between do and done is executed repeatedly until the value of expr2 is TRUE.
- After each iteration of the loop, expr3 is evaluated. This is usually use to increment a loop counter.

**Example**
```bash
#!/bin/bash
# For loop as C-style
for (( i=0; i<=5; i++ ))
do
   echo "Number  $i"
done

```

Bash While Loop

Another iteration statement offered by the shell programming language is the while statement.

**Syntax:**

```bash
while expression
do
	commands
done
```


In the above while loop syntax:

while, do, done are keywords

Expression is any expression which returns a scalar value

While statement causes a block of code to be executed while a provided conditional expression is true.

**Example**

```bash
i=1 # initilized i
while [ $i -le 5 ] # check condition if true the enter in while block else skip the block
do
   echo "Number: $i"
   i=$(( $i + 1 )) # increse i one by one
done
```


### Until Loop

The until statement is very similar in syntax and function to the while statement. The only real difference between the two is that the until statement executes its code block while **its conditional expression is false**, and the while statement executes its code block while **its conditional expression is true**.

**Syntax:**
```bash
until expression
	do
	   commands #body of the loop
	done
```
In the above bash until syntax:
where until, do, done are keywords
expression any conditional expression

**Example**

```bash
#!/bin/bash

seconds=10
until [ $seconds -eq 0 ]; # check condition if false then enter in until block else skip block
 do
    echo "Countdown: $seconds"
    sleep 1 # use pause 1 second
    ((seconds--)) # Decreasement seconds one by one
done

echo "Time's up!"

```

# Array

 An array is a variable that can store multiple values. Bash supports one-dimensional indexed and associative arrays. Here's a basic overview of arrays in Bash:

### Indexed Arrays:

Indexed arrays are arrays where each element is associated with an index starting from 0.

**Declaration:**

```bash

my_array=("value1" "value2" "value3")
# index  :   0         1        2
```
**Accessing Elements:**

```bash

echo ${my_array[0]}  # prints "value1"

```
**Adding Elements:**

```bash

my_array[3]="value4"

```

**Iterating Over Elements:**

```bash

for element in "${my_array[@]}"; #@
do
  echo $element
done
```
**Associative Arrays:**

Associative arrays are arrays where elements are associated with a key.or [key-value pair]

Declaration:

```bash

declare -A my_assoc_array
my_assoc_array=([key1]="value1" [key2]="value2")
```

**Accessing Elements:**

```bash

echo ${my_assoc_array[key1]}  # prints "value1"
```

**Adding Elements:**


```bash

my_assoc_array[key3]="value3"

```

**Iterating Over Elements:**

```bash

for key in "${!my_assoc_array[@]}"; 
do
  echo "Key: $key, Value: ${my_assoc_array[$key]}"

done
```

**Special Variables:**

    ${array[@]}: Represents all the elements in the array.
    ${!array[@]}: Represents all the indices in the array.

**Example:**

```bash

# Indexed Array
fruits=("Apple" "Banana" "Orange")

# Associative Array
declare -A capitals
capitals=([USA]="Washington" [France]="Paris" [Germany]="Berlin")

# Accessing elements
echo "Fruit: ${fruits[0]}"
echo "Capital of USA: ${capitals[USA]}"

# Adding elements
fruits[3]="Grapes"
capitals[Italy]="Rome"

# Iterating over elements
for fruit in "${fruits[@]}"; do
  echo "Fruit: $fruit"
done

for country in "${!capitals[@]}"; do
  echo "Capital of $country: ${capitals[$country]}"
done
```

*Remember that Bash arrays are not strongly typed, so you can mix data types within the same array. Also, arrays in Bash are not limited to a specific size, and they can grow or shrink dynamically.

# String

 Strings are sequences of characters, and they can be manipulated in various ways. Here's an overview of working with strings in Bash:

**1. Creating Strings:**

You can create strings by assigning a sequence of characters to a variable.

```bash

my_string="Hello, World!"
```

**2. Concatenation:**

You can concatenate strings using the concatenation operator (+).

```bash

first_name="Raj"
last_name="Gaurav"
full_name="$first_name + $last_name"
echo $full_name  
# Output: Raj Gaurav

```

**3. String Length:**

To find the length of a string, use the ${#variable} syntax.

```bash

my_string="Hello, World!"
length=${#my_string}
echo $length  # Output: 13
```
**4. Substring:**

You can extract a substring from a string using the ${variable:start:length} syntax.

```bash

my_string="Hello, World!"
substring=${my_string:7:5}
echo $substring  # Output: World
```

**5. Search and Replace:**

You can perform search and replace operations on strings.

```bash

my_string="Hello, World!"
new_string=${my_string/Hello/Hi}
echo $new_string  # Output: Hi, World!
```

**6. Substring Removal:**

Remove a substring from the beginning or end of a string.

```bash

my_string="Hello, World!"
remove_hello=${my_string#Hello, }  # Remove "Hello, " from the beginning
remove_world=${my_string%World!}   # Remove "World!" from the end
echo $remove_hello  # Output: World!
echo $remove_world  # Output: Hello,

```

**7. String Comparison:**

You can compare strings using various operators, such as ==, !=, <, >.

```bash

string1="apple"
string2="orange"

if [ "$string1" == "$string2" ]; then
    echo "Strings are equal"
else
    echo "Strings are not equal"
fi
```
**Example:**

```bash

# String operations example
name="Alice"
greeting="Hello"

echo "$greeting, $name!"
echo "Length of name: ${#name}"

substring=${name:0:3}
echo "Substring: $substring"

new_greeting=${greeting/Hola/Hi}
echo "New Greeting: $new_greeting"

remove_h=${name#H}
echo "Remove 'H': $remove_h"

uppercase_name=${name^^}
echo "Uppercase Name: $uppercase_name"
```
These are some basic string operations in Bash. Keep in mind that Bash is quite flexible, and there are many more string manipulation techniques available depending on your specific needs.



# Function

 Functions allow you to group commands and execute them as a single unit. Functions help make your scripts more modular and maintainable. Here's the basic syntax for defining and using functions in Bash:

```bash

#!/bin/bash

# Function definition
function my_function() {
    # Commands to be executed
    echo "Hello from my function!"
}

# Function call
my_function

```

Alternatively, you can use the shorthand syntax to define a function:

```bash

#!/bin/bash

# Shorthand function definition
my_function() {
    # Commands to be executed
    echo "Hello from my function!"
}

# Function call
my_function
```
You can pass parameters to functions, making them more versatile:

```bash

#!/bin/bash

# Function definition with parameters
function greet() {
    local name="$1"  # Local variable to store the first parameter

    # Commands to be executed
    echo "Hello, $name!"
}

# Function call with an argument
greet "John"
```

Within a function, you can use local variables to avoid polluting the global variable space.

Functions can also return values using the return statement:

```bash

#!/bin/bash

# Function definition with return value
function add() {
    local sum=$(( $1 + $2 ))
    echo $sum
}

# Function call and capture the return value
result=$(add 3 5)
echo "The sum is: $result"

```

Remember that in Bash, all variables are global by default, so using local variables inside functions helps prevent unintentional variable conflicts.

Functions can also be used to structure your script, making it more organized and easier to understand, especially for larger and more complex scripts.


# File Handling

 File handling involves performing operations on files, such as reading from them, writing to them, checking their existence, and more. Here are some common file handling operations in Bash:

**1. Reading from a File:**
Reading a Entire File:

```bash

while IFS= read -r line; do
    echo "$line"
done < filename.txt

```

Reading Line by Line and Processing:

```bash

cat filename.txt | while IFS= read -r line; do
    # Process each line here
    echo "$line"
done
```
**2. Writing to a File:**
Writing a Single Line:

```bash

echo "Hello, World!" > output.txt

Appending to a File:

bash

echo "New content" >> existing_file.txt
```

**3. Checking File Existence:**

```bash

if [ -e "filename.txt" ]; then
    echo "File exists."
else
    echo "File does not exist."
fi
```
**4. Checking if a File is a Directory:**

```bash

if [ -d "directory_name" ]; then
    echo "It's a directory."
else
    echo "It's not a directory."
fi
```

**5. Checking if a File is Readable/Writable/Executable:**

```bash

if [ -r "file.txt" ]; then
    echo "File is readable."
fi

if [ -w "file.txt" ]; then
    echo "File is writable."
fi

if [ -x "script.sh" ]; then
    echo "Script is executable."
fi
```
**6. Copying, Moving, and Renaming Files:**
Copying a File:

```bash

cp source_file.txt destination/
```
Moving/Renaming a File:

```bash

mv old_filename.txt new_filename.txt
```
**7. Deleting a File:**

```bash

rm filename.txt
```
**8. Counting Lines, Words, and Characters in a File:**

```bash

lines=$(wc -l < filename.txt)
words=$(wc -w < filename.txt)
characters=$(wc -c < filename.txt)

echo "Lines: $lines, Words: $words, Characters: $characters"
```

**9. Searching for a String in a File:**

```bash

if grep -q "search_string" filename.txt; then
    echo "String found."
else
    echo "String not found."
fi
```
These are basic examples of file handling in Bash. Depending on your specific use case, you may need to combine these operations or use additional tools to achieve more complex file manipulations. Always consider error handling and edge cases when working with files in scripts.




