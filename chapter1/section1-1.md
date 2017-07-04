# Chapter 1, Section 1: Introduction

This chapter provides a brief introduction to C++, we compile our first problem and learn some fundamentals of C++.

## The History of C++

C++ was designed to be a successor to C and it was originally designed in 1970 by Bjarne Stroustroup at Bell Labs in 1979. Since then, C++ has received many incremental improvements. C++ is an object orientated language, that implements concepts such as inheritance, abstraction, polymorphism and encapsulation. The language also introduced Classes, which contain member data and member methods. These constructs exist to allow the programmer to model data and actions he wants to perform on such data with ease.

## The advantages of C++

C++ can be used for both high-level and low-level programming and allows developers to produce low-level applications that can manipulate the low-level functionality of hardware. Despite the fact many newer programming languages have come out since its release, such as Java, C++ has remained relevant and highly popular. The language remains is still the most popular choice for cases where accurate control over the application's resource consumption and performance is required (such as gaming or real-time mathematical simulations). C++ applications are also portable, but may need to be recompiled on different systems if different instruction sets are used.

## What is C++ used for?

C++ has been used for all kinds of different software, from video-games such as Half-life, through to the Linux Kernel, there are many pieces of popular software which have been written in C++. Here are some more examples of popular software packages which have been written in C++:

- Most of Adobe's software suite, including software such as Photoshop, ImageReady, Illustrator and Adobe Premier.
- Google has used C++ to create things such as the Google File System (this is used in Google's search engine) and Chromium.
- Firefox and Thunderbird mail client are both written in C++.
- Many operating systems are written in C++, including several versions of Windows and OSX.
- There are many, many more pieces of software which have been written in C++.

## Programming a C++ Application

C++ applications can be written using simple text-editors or complex IDE environments (such as Microsoft Visual Studio). When the code is written, it must be compiled using a compiler, which converts the source-code into machine-language contained in object files. Finally, the object files are linked using a linker to get an executable (.exe on Windows).

The compilation process takes code written in C++, contained in text files with the .cpp extension and converts them into byte code that the processor can execute. The processor (CPU) in your computer has something called an instruction set, which is a list of possible operations it can perform (such as adding two numbers). Each instruct is typically represented with a byte-code, known as an (opcode)[https://en.wikipedia.org/wiki/Opcode].  

The compiler converts one code file at a time, generating an object file with the extension of .o or .obj, ignoring dependencies that the source code may have on another file. The link then 'joins the dots' and resolves any missing dependencies. If the linking operation is successful, it creates an executable for the programmer to execute and distribute. This entire process is sometimes called 'building', which will usually output an executable binary (.exe on windows) or shared library (DLL on Windows).

This process is different to interpreted programs/languages. For example, scripts written in PHP, Python or Shell (Windows Powershell or BASH) are interpreted at run time. This means that the application does not go through the same build phase and the application code is analysed and executed when the application is run. In order to execute such programs, the interpreter for the specific language the program is written in must be available on your machine. The process of interpretation also impacts performance as the interpreter must 'translate' code written by the programmer to byte-code at run-time.

## Debugging and Understanding Errors

Almost no applications run successfully when they are first written. Any application, including those written in C++, need to be executed many times as part of a testing effort, to remove errors and bugs. After bugs are fixed, the application is rebuilt and the testing process continues. The iterative bug finding and fixing process is known as debugging. A good development environment includes tools which aid programmers in the process of debugging. Most IDE (Integrated development environment, such as Visual Studio), include these tools.

- Explain difference between errors and warnings.
- Explain difference between runtime errors and compile time errors. 

## Integrated Development Environments

An IDE or Integrated Development Environment is typically a piece of software which provides the programmer to write code, compile, link and debug code within a simplified interface. You don't need to use an IDE to write C++. You can use a simple text editor, such as gedit, vi, emacs, or atom and perform the build process manually by invoking compilation and linking using a compiler/linker.

```
  Need steps for installing Visual Studio express.
```

## Writing your first C++ Application

If you're on Windows and are running Visual Studio, first create a new solution and project:

```
  - Need steps for Visual Studio, creating a new solution and project.
```

If you're using a Linux machine or if you're on OSX, create the file main.cpp in a text editor. Add the following code to the file:

```
  #include <iostream>

  int main()
  {
     std::cout << "Hello World!" << std::endl;
     return 0;
  }
```

This application will output the text "Hello World" on the display when executed. The value 0 is returned to the operating system when it is executed.

## Building this Application

If you're on Windows within Visual Studio, you can

```
  need building steps for Visual Studio and Unix
```

## Understanding Compile Errors

- Need some content around errors, purposefully putting in an error to see it during build process.

## Summary

This chapter provided a brief introduction to C++ and we have compiled our first application. We have installed and configured our IDE ready for the rest of the course.
