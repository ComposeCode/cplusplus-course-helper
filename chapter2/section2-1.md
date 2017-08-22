# Chapter 2, Section 1: C++ Program Structure

This chapter covers the structure of a C++ Program. It examines simple concepts like functions and variables and how they fit together to produce C++ applications. We also cover basic input and output operations.

## Examining the Hello World Application

The program written in the first chapter is relatively simple but contains several important and basic building blocks of a C++ program. Here is the original program again for reference:

```
  #include <iostream>

  int main()
  {
     std::cout << "Hello World!" << std::endl;
     return 0;
  }
```

You can break this program up into two parts: preprocessor directives and the main body of the program.

## Preprocessor Directives

Preprocessor directives, such as #define, #include or #idef are used to make programs easy to change and easy to compile in different execution environments. The directives are used to tell the preprocessor to perform specific actions. For example, the preprocessor can replace tokens in the text, insert the contents of other files into the source file, or suppress compilation of part of the file by removing sections of text.

The preprocessor directive we have used in our Hello World application is called #include, which tells the preprocessor to take the contents of the file (iostream, in this case) and include them at the line where the directive is made. iostream is a standard header file that includes functions for input and output streams. This particular header allows us to use the 'std::cout' function to output text.

To summarize, the compiler was able to compile the line of code which uses 'std::cout' because we instructed the preprocessor to include the definition of std::cout.

Note: Complex C++ programs are split into multiple files to make them more readable. Typically this means multiple C++ header files (files that end in h) and multiple C++ code files ending in cpp. If something is defined in HeaderA.h and is referenced in file Code.cpp, the HeaderA.h file should be referenced within the Code.cpp file using an include directive. The include path should be the relative path from Code.cpp to HeaderA.h. Standard headers are typically included using angled brackets such as <windows.h> or <iostream> where as custom headers are usually included using double quote marks.

## The main function

After the include preprocessor directive we see the declaration of the main function:

```
  int main()
```

Functions are basically blocks of code which perform some specific action. These are also sometimes referred to as subroutines or procedures and are similar to functions in mathematics. Quite often a function is written to perform some repeatable task, such as adding two numbers or writing text to files.

The main function is very important in C++ programs and serves a special purpose. This function serves as the entry point for the application, when the program is executed, it is the first part of the program to be run.

Functions can also return values or have values passed into them as part of the action they are designed to perform. For example, lets say we have a function called Addition which adds two numbers, A and B. We could write a function which takes these two values as parameters, and then returns a value which is the sum of A + B. The 'int' part of the main function above indicates that the function returns an integer value (a whole number, which is not a fraction). Most common definitions of the main function return an integer which usually indicates if the program has ran successfully or not.

Another common variant of the main function looks like this:

```
  int main (int argc, char* argv[])
```

This variant of the function has two parameters, an integer called argc and an array of character pointers. We will not cover pointers in this chapter, the important point is to understand how parameters to a function are defined, inside the brackets, by mentioning a type and a parameter name. By defining this second parameter for the main function, it allows command like arguments to be passed to the program at run time.

For example, you may have a program which uses an input from the user in its computation. Below is an example of how such a program may function when run:

```
  hello_world.exe ComposeCode
  Hello, ComposeCode.
```

As we can see, the hello_world.exe program takes the value 'ComposeCode' and then combines it with 'Hello, ' before displaying it to the user. C++ programs can use a range of different input sources, from text input from a keyboard to mouse movement, network adapters, joysticks and gamepads. Such programs can also be written to take a range of different command line arguments of varying type and complexity.

Finally, the curly brackets below -

## std::out and std::endl;

Lets analyse the next line of the Hello World program:

```
  std::cout << "Hello World!" << std::endl;
```

This line of code is actually responsible for writing text out to the screen. The cout part of this statement is responsible for writing the "Hello World" piece of text to the console. cout is a stream defined in the standard std namespace (which is why std:: is appended). Cout is a type of stream and by using the stream insertion operator denoted by << the text "Hello World!" is written to the screen. The final piece of this statement denoted by std::endl is used to end the text written to the stream and is very similar to a carriage return.

Note: that pieces of text, sometimes called strings, are wrapped in double quotes "". Individual characters are sometimes wrapped with single quotes ''. The stream insertion operator << must be used every time a new entity needs to be inserted into the stream.

We cover streams in more details later on in another chapter. Streams are pretty useful and can be used for more than just writing text to a screen, such as reading/writing files from disk.

## Returning a value

The final line of this function is denoted by this code:

```
 return 0;
```

As previously described, functions can return values. This particular statement returns the integer value 0 to the calling program. The convention is to generally return 0 in the event of success or -1 in the event of an error. Typically a parent process executes a child process (such as the Hello World program) and will use the return value to check if it has executed correctly. This is still used a lot on GNU/Linux systems and was very important when operating systems didn't have a graphical interface.

Note: Functions can return other types instead of integer, like arrays, doubles, constants or custom types as we will see later on.

## Namespaces

Namespaces are used to help the compiler understand which piece of code you are referencing. For example, you could have a function called cout defined in two places which the compiler knows about, but by appending the std::, you are telling the compiler specifically to use the cout definition which is part of the standard namespace, thus reducing the chance for a naming conflict.

To make this simpler, it is possible to add the 'using' statement to our original program, to make references to the standard namespace easier:

```
  #include <iostream>
  using namespace std;

  int main()
  {
     cout << "Hello World!" << endl;
     return 0;
  }
```

It is also possible to put the using statement within the function and to refer directly to something within the namespace, instead of refering to the entire namespace:

```
  #include <iostream>

  int main()
  {
     using std::cout;
     using std::endl;
     cout << "Hello World!" << endl;
     return 0;
  }
```

## Using Comments in Code

Code can look like a foreign language if you didn't write it, especially if you have to pickup and improve code which was written by someone else. If not all programming and scripting languages provide the ability to put comments in code. The purpose of comments is to help articulate and explain code in plaintext. If you ever have to revisit some source-code you wrote a long time ago or contribute to an existing project, comments are invaluable. Writing good quality comments comes with time and experience, as you don't want to over-articulate yourself or write comments for self-explaining/simple code.

There are two main ways to write comments in C++, here is the first, used for single line comments:

```
 // This is a single line comment
```

Here is the second, used for multiline comments:

```
 /* This is a multi-line Comment
   which can span over multiple lines of text.
   It is very useful!
 */
```

## Functions

We've already briefly looked at functions in C++ by examining the main function. As specified before, functions are used to break up code into reusable blocks, which can be run in varied sequence. They can also take varied input and return values based on that input. Functions can be used to break up a complicated program into multiple subroutines, making it easier to understand and modify.

Below is a modified version of the hello world program re-written to include an extra function:

```
  #include <iostream>
  using namespace std;

  int HelloWorld() {
    cout << "Hello World!" << endl;
    return 0;
  }

  int main()
  {
     HelloWorld();
     return 0;
  }
```
S
As you can see, the main function has been broken up into two functions, main and the HelloWorld function. The HelloWorld function also returns an integer and does not take any values. Previously the main function invoked cout to write text to the screen. What we can see instead is that the main function now invokes the HelloWorld method which instead uses cout to display text to the screen.

Let's try a more complex example which adds two numbers together and displays their output:

```
  #include <iostream>
  using namespace std;

  int addition(int x, int y) {
    return x + y;
  }

  int main()
  {
     cout << "The Result of 13 + 27 is: " << addition(13, 27) << endl;
     return 0;
  }
```

When executed, the output of this function will be:

```
The Result of 13 + 27 is: 40
```

In this simple program we have introduced a new function called addition. The addition function has two parameters, one called x and the other called y which are both integers. The function returns the result of the addition of these two parameters as an integer, which is done by this line of code:

```
 return x + y;
```

Within the main function we have modified the cout line from our original program so that it now displays a result from this function. In this case, we are just simply adding the result of 13 and 27, which gives 40. We pass these two integer values to the addition function which returns the result as an integer, which is subsequently displayed by the cout function. The addition function defined using a return type (int), a name (addition) and two parameters (int x and y), some statements surrounded in brackets {} and a return statement which returns a value that matches up with the return type.

The important things to take from this example are the use of the addition operator to add two integers together, how a function is declared and how a function is invoked. Not all functions have to have a return type or return a value. The example below shows a function with a void type, that doesn't return any value or type:

```
#include <iostream>
using namespace std;

void consoleOutput() {
  cout << "This is a simple string literal, written to the screen using cout" << endl;
  cout << "Here is the number 5: " << 5 << endl;
  cout << "Performing Division: 297 / 7" << 297/7 << endl;
  cout << "Performing Multiplication: 33 * 9" << 33*9 << endl;
  cout << "Performing Subtraction: 1500 - 150" << 1500-150 << endl;
}

int main()
{
   consoleOutput();
   return 0;
}
```

This program when executed will display 5 lines of output, 3 of which have output from mathematical operations. The main difference in this example is the removal of most of the statements of code from main to the consoleOutput function. This method is executed by the main function and is used to write output to the console. Note that the consoleOutput function is defined with type void, meaning it doesn't return any value. It also doesn't take any parameters unlike the addition function in the previous example.

The first two statements of the consoleOutput function don't do much apart from write some text to the console. The next few lines write output to the screen but also make use of mathematical operators. Through all of the examples, we have now used addition, subtraction, division and multiplication operators. We will look at functions and operators in more detail later on.

# Getting user input through std::cin

Though we have displayed text to the screen, it is also important that we take input from the user. In the next example we will prompt the user to enter some variables and then we will use them in our code. We can use the std::cin (pronounced see-in) function to read text input from the user. We already used the cout function to write text to the screen:

```
  std::cout << "Hello, World!" << std:endl;
```

The insertion operator denoted by << is used to insert data into the output stream as seen in the example above. The extraction operator >> is used to extract data from the input stream which is then written to a variable. Below is an example of how input can be obtained from the user:

```
 std::cin >> UserVariable;
```

When this code is executed, the user is prompted to give input, the result of which is stored in UserVariable. A variable or scalar is a storage location, paired with a symbolic name (an identifier), which contains some known or unknown quantity of information referred to as a value. The variable is a way to reference the stored value. The separation of name and content allows the name to be used independently of the exact information it represents. The identifier in source code can be bound to a value during run time and the value of that variable may thus change during the course of program execution.

In C++, a variable is required to have a type. In this case, the UserVariable could be an integer to represent a number, a string to represent some text or some other type. If we need to take two input variables from the user, we can easily do this with cin:

```
 std:cin >> UserVariable1 >> UserVariable2;
```

In this example, the first value the user enters is written to UserVariable1 and the second variable is written to UserVariable2. The example below combines both the cin and cout operations to show how user input can be obtained and used in a simple application:


```
#include <iostream>
#include <string>
using namespace std;

int main()
{
   int UserAge;
   string UserName;

   cout << "Enter your age: ";
   cin >> UserAge;


   cout << "Enter Your Name: ";
   cin >> UserName;

   cout << "Welcome " << UserName << " You are " << UserAge << " Years Old." endl;

   return 0;
}
```

This simple program takes two values from the end user, a string which represents the user's name and an integer called UserAge which represents the user's age. These values are then displayed to the user at the end of the program. This program shows how we can handle simple user input and output. Variables are covered in more detail in the next chapter.

# Summary

This chapter covered covered functions, simple user input and output, simple variables, comments and namespaces. We created several new programs to demonstrate these functions. 
