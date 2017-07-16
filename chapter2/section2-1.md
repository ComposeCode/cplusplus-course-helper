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

Note: Complex C++ programs are split into multiple files to make them more readable. Typically this means multiple C++ header files (files that end in h) and multiple C++ code files ending in cpp. If something is defined in HeaderA.h and is referenced in file Code.cpp, the HeaderA.h file should be referenced 
