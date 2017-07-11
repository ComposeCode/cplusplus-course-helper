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

This course has been written for Windows, so we will now install Visual Studio. Linux steps will be covered at a later date:

1) First download Visual Studio Community 2017 (previously known as Express edition) from this Link: (https://www.visualstudio.com/downloads/)[https://www.visualstudio.com/downloads/]. You can of course use an older version or an Enterprise or Professional edition of Visual Studio.

2) Open the .exe, when prompted for workload type, Select Universal Windows Platform Development and Desktop Development with C++ and then hit next.

3) Let the application install, eventually you will end up at a screen like this. Note I have both Enterprise and two different versions of the community edition installed.

## Writing your first C++ Application

If you're on Windows and are running Visual Studio, first create a new solution and project:

1) First launch Visual Studio from your start menu. You may be prompted to create a Visual Studio Profile, feel free to do so and log in. Eventually you should see a screen like this:

2) Next, we go to File at the Top left -> go to New -> then hit Project. We will choose a blank project. In the list of project templates, find Visual C++, then hit Visual C++, in the drop down select General and then hit Empty Project. Give the project a name, I.E HelloWorld and hit OK.

** Note that this list has lots of build in project types, like Windows Forms applications, .NET applications and websites. We will create a basic Windows console application.

3) When the Wizard comes up to build your Win32 Application, just hit the finish button. This will create an empty solution and project for us to work with.

4) Now we will add a new file which will contain our source code. Right click the Source Files folder inside the Solution Explorer, go to Add -> New Item -> Visual C++ (code) -> C++ File (.cpp) -> Call the file Main.cpp and hit add.

5) Once you've added main CPP, add the following code to the file and save it (hit ctrl+s or go to File -> Save)

```
  #include <iostream>

  int main()
  {
     std::cout << "Hello World!" << std::endl;
     return 0;
  }
```

6) Once the file has been saved, it can now be built and run. Go to Build menu at the top menu bar -> Build Solution to compile the development build. We can now run our application.

7) To run the application, you can either go directly to the project folder and run the compiled executable (HelloWorld.exe, found in My Documents/Visual Studio 2017/Projects/HelloWorld/Debug/ if using the default path) or you can run the application directly within the IDE. If you press the green triangle icon within the IDE, it will run the program.

8) You will notice that the program opens and closes very quickly. This is because we have created a console application which runs and does not wait for any input. We can add some more code to keep the application open. Above the return 0; line, add the code getchar(); so you have the following:

```
  #include <iostream>

  int main()
  {
     std::cout << "Hello World!" << std::endl;
     getchar();
     return 0;
  }
```

9) Now rebuild the application again, either by using the menu or by pressing ctrl + shift + b. This will create a new executable.

10) Run the application again, this time the prompt will stay open and display "Hello World!".

This application will output the text "Hello World" on the display when executed. The value 0 is returned to the operating system when it is executed. The extra line we added, getchar(); causes the system to run the getchar() function, which causes the application to get input from the user. This code will be explored in more detail in the section chapter. The import part is already done: we now have a working compiler we can use to build C++ code throughout the rest of the course.

## Understanding Compile Errors

There are two types of errors in programs: run time errors and compile time errors. Run time errors occur when a program is executed. For example, you could be playing a game, which runs fine for several hours but then suddenly crashes. Another common example is the blue screen of death which occurs on Windows Systems, usually from a kernel run-time error.

Compile time errors are picked up by the compiler when compiling the application. The compiler is able to detect syntax errors, such as typos in variable names or invalid syntax which doesn't follow C++ convention. For example, try removing a semi colon at the end of the getchar() line in the Hello World application we built previously, and then try rebuilding the application. You should get an error like this:  

```
Severity	Code	Description	Project	File	Line	Suppression State
Error	C2143	syntax error: missing ';' before 'return'	HelloWorld	c:\users\conta\onedrive\documents\visual studio 2017\projects\helloworld\helloworld\main.cpp	7
Error (active)	E0065	expected a ';'	HelloWorld	c:\Users\conta\OneDrive\Documents\Visual Studio 2017\Projects\HelloWorld\HelloWorld\main.cpp	7
```

This shows that the compiler has picked up the error and realised that we have missed a semicolon out. Put the colon back in and then try removing other pieces of the code and recompiling the code. Doing this can help you get to grips with some common errors.

In additional to compile time errors, we also have compile time warnings. Compile time warnings usually indicate the compiler has detected a potential issue with your program, sometimes with a remedy. The main difference between errors and warnings is that warnings can usually be ignored and the application will still execute, but there is no guarantee if it will run correctly with the detected error.

## Summary

This chapter provided a brief introduction to C++ and we have compiled our first application. We have installed and configured our IDE ready for the rest of the course. We have looked at compile time and run time bugs. 
