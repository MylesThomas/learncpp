# C++

## Learn C++

[Website](https://www.learncpp.com/)

### Chapter 0: Introduction / Getting Started

#### 0.1 Introduction to these tutorials

Notes:
- These tutorials assume 0 previous knowledge
- There will be lots of exammples along the way

Testimonial: "It’s crazy how perfect this website explains C++ concepts and teaches programming. I read the book “Programming: Principles and Practice Using C++” [by Bjarne Stroustrup, the creator of C++] and it was rather confusing…. This website makes it clear the first time, and they explain everything you need to know. Somehow they know what I don’t know, and what I need to know. It’s almost like my future self went back in the past to teach me what mistakes I will make."

Goals:
- Cover programming topics as well as C++
    - Programming style
    - Common pitfalls
    - Debugging
    - Good/bad programming practices
    - Testing

    - "When you finish, you will not only know how to program in C++, you will know how NOT to program in C++, which is arguably as important."

- Provide a lot of examples
    - Avoid unexplained:
        - non-obvious parts
        - new concepts

- Provide practice programs

- Have fun!

Advice:
1. Type in the examples by hand, then compile them yourself(Do not copy and paste!)
2. Try to solve your own problems before asking others for help
3. Experiment with the examples
- Example: Changing numbers/text to see what happens
4. Plan to spend some time with the quizzes
5. Write your own short programs using the concepts you have learned

#### 0.2 Introduction to programming languages

Modern computers are fast, but have significant constraints ie. they must be told exactly what to do

Computer program/application: A set of instructions that the computer can perform in order to perform some task
- Programming: Process of creating a program
- Source code: How to create programs ie. a list of commmands in a text file
- Hardware: The collection of physical parts that make up a computer and execute programs
- Executing/Running a program: When a program is loaded into memory and the hardware sequentially executes each instruction

##### Machine Language

Machine Language/Code: The limited set of instructions that a CPU can understand
- Example: 

```bash
10110000 01100001
```

- Binary digit/bit: 1 or 0
    - Some CPUs: Can only process instructions that are exactly 32 bits
    - Your CPU: x86/x64 ie. can be a variable length
- Different instructions sets: Instructions written for 1 CPU could not be used on a CPU with a different instruction set
    - Programs were not able to be used without major rework, and had to be written all over again

##### Assembly Language

Because machine language is so hard for humans to read/understand, assembly language was invented.

Assembly language: Each instruction is identified by a short abbreviation (instead of a set of bits)
- Same instruction as above in assembly language:


```bash
mov al, 061h
```

Computer cannot understand assembly language directly, so we use an assembler 
- Must translate an assembly program into machine language in order for it to run

Downsides of Assembly language:
- Still requires a lot of instructions to do simple tasks
- Not very portable
    - Need the same hardware otherwise it will have to be re-written

##### High-level languages

High-level languages: New programming languages that allow the user to write programs without being concerned which computer the program will run on
- Examples: C/C++/Pascal
    - Later on: Java/Javascript/Perl

Same instructions as above:

```cpp
a = 97;
```

Just like assembly programs, your computer cannot read this. There are 2 ways to get your computer to understand this code:
1. Compiling
2. Interpreter

Compiler: Program that reads source code and produces a stand-alone executable program that can then be run
- Program can be run without a compiler
- Compiling process:
    - High level language source code -> Compiler -> Executable
    - Executable -> (runs on) Hardware -> Program results

- Languages that use this: C/C++/Pascal (Traditional languages)

Interpreter: Program that directly executes the instructions in the source code without requiring them to be compiled into an executable
- More flexible, but less efficient
    - Interpreting has to occur every single time the program is run ie. we need an interpreter every time (unlike compiler, which is needed 1x)
- Interpreting process: 
    - High level language source code -> Interpreter ->  (runs on) Hardware -> Program results

- Languages that use this: Perl/Javascript (Scripting languages)

Notes:
- Another advantage of compiled programs is you do not need to distribute the source code
    - This is good for a non-open-source environment, where IP protection matters
- Some languages use a mix of traditional/scripting ie. Java

Desirable properties of high level languages:
1. Much easier to read/write
- Commands are closer to natural language that we use everyday
2. Requires fewer instructions to perform the same tasks
- Programs then can be more concise/easier to understand

Example: This is done in 1 line in C++, but 5 or 6 in an assembly language

```bash
a = b * 2 + 5;
```

3. Programs can be compiled/interpreted for many different systems ie. you don't have to change the program to run on different CPUs

Two exceptions to portability:
1. Many Operating Systems (OS) ie. Microsoft Windows contain platform-specific capabilities
- Tradeoff: Portability vs. Ease of writing for 1 OS
- We will avoid this kind of platform-specific code

2. Some compilers support compiler-specific extensions
- If you use these, you won't be able to be compiled by other compilers that do not support the same extensions, without modification (More on this later, once you install a compiler!)

##### Rules, Best practices, and warnings

Rules, Best practices, and warnings:
1. Rule: instructions that you MUST do
- or your program will not work!

2. Best practice: Things that you SHOULD do
- highly recommended because everybody does it that way OR it is superior to the alternatives

3. Warnings: things that you should NOT do
- leads to unexpected results

#### 0.3 Introduction to C/C++

##### Before C++, there was C

C: Developed in 1972
- Systems programming Language to write operating systems with
- Primary goals: Give programmer a lot of control + keep platform independence ie. independence of system
    - minimalistic language that was easy to compile
    - efficient access to memory
    - produced efficient code
    - self-contained (ie. not reliant on other programs) 

- So successful/efficient that Unix was re-written in C
    - in the past: written in assembly code (could only run on specific CPUs)
    - now with C: unix could be recompiled on many types of computer
        - C/Unix had their fortunes tied together!

- Formal standards for C, in order least to greatest portability:
    - K&R standards from the C Programming Language Book(1978)
    - ANSI formal standard (1983)
    - C90: ISO standard (1990)
    - C99: ISO standard (1999)
        - contains many features that were in compilers as extensions and/or had been implemented in C++


##### C++

C++: Extension to C
- "see plus plus"
- 1979: adds many new features to C ie. a "superset of C"
    - not always true: C99 has things not in C++
- claim to fame: Object-oriented programming
- 1998: Standardized by ISO (ensures all compilers adhere to the same set of standards)
- 2003: minor update to the language (C++03) 
- 5 major updates since (each adds new functionality):
    - C++11: new baseline language b/c it added so much new functionality
    - C++14
    - C++17
    - C++20
    - C++23

- Language standard: New formal release of the language
    - named after the year they are released in
    - expectation: 1 every 3 years

##### C and C++'s philosophy

Underlying design: "trust the programmer"
- Wonderful: high degree of freedom
- Dangerous: won't stop you from doing things that are dumb/don't make sense


##### Q: What is C++ good at?

Situations that need the following:
- high performance
- precise control over memory + other resources

Common types of applications:
- Video games
- Real-time systems ie. transportation/manufacturing
- High-performance finance applications ie. HFT
- Graphical applications and simulations
- Embedded software
- Audio/video processing
- AI/Neural Networks

#### 0.4 Introduction to C++ development

"What" step: Before we can write/execute our 1st C++ program, we need to understand in more detail how C++ programs get developed.

Simplistic Approach:
1. Define the problem to solve
2. Design a solution
3. Write a program that implements the solution
4. Compile the program
5. Link object files
6. Test program
7. Debug (iterate back to step 4)

##### Step 1: Define the problem you would like to solve

Conceptually: Easiest part
- Example: "I want to write a program that reads in a file of stock prices and predicts whether the stock will go up or down"

##### Step 2: Determine how you are going to solve the problem

"How" step: Most overlooked in programming
- Some solutions are good, some are bad!
    - Sitting down and coding immediately is usually going to end in a bad result

- Typically, good solutions have the following:
    - Straightforward ie. not complicated/confusing
    - Well-documented (especially for assumptions/limitations)
    - Built modularly ie. can be reused or changed without impacting other parts of the program
    - Robust ie. can recover or give useful error messages

Bug: Technical defect
- popularized because engineers found a moth stuck in the hardware of an early computer, causing it to short circuit

Writing Initial vs. Maintenance:
- Studies have shown:
    - 20%: writing initial code
    - 80%: debugging, updates, changes in environment, internal improvements for realibility/maintainability

Note: This is a GREAT example of the Pareto principle

Takeaway: Take extra time up front (before you starting coding) thinking of the following:
1. Best way to tackle the problem
2. Assumptions being made
3. How you may plan for the future state

##### Step 3: Write the program

Two things needed to write the program:
1. Knowledge of a programming language
2. Text editor

Example of program in a basic text editor:

```cpp
#include <iostream>

int main()
{
    std::cout << "Here is some text.";
    return 0;
}

```

Code editor > Text editor:

Editors for coding have few features that make programming much easier, such as:
1. Line numbering
- very useful for finding errors
2. Syntax highlighting and coloring
- changes colors of certain parts to make it easy to identify
3. Unambiguous/fixed-width font
- "monospace font"
- ensures that 0 and O are easy to discern, l or L or 1, etc.

Example with line numbering and syntax highlighting:

![example with numbering and syntax highlighting](./figures/0_syntax_highlighting.png)


Tip: [Coding Font](https://www.codingfont.com/) allwos you to compare your favorite coding fonts

For advanced readers:

ASCII: character codes
- programming languages use to represent mathematical concepts
- example: !=

Names of files:
- C++ source code: something.cpp
    - Many complex C++ programs have 10's or 100's of .cpp files
- Program: something.exe

Note: source could could be .cc or .cxx, but .cpp is recommended!

We have written our program!

Next steps: convert the source code into something that we can run

#### 0.5 Introduction to compiler, linker, and libraries

Time for steps 4-7!

##### Step 4: Compiling your code

In order to compile C++ source code files, we use a C++ compiler.

C++ Compiler: Sequentially goes through each source code .cpp file in your program, and does the following:
1. Checks that your code follows the rules of the C++ language
- if yes: proceed
- if not: gives you an error w/ line numbers
2. Translates your C++ source code into a machine language file ie. an object file
- Object file: something.o / something.obj

Note: For each .cpp file, there is a .o file
- Source file: Calculator.cpp -> Compile -> Calculator.o
- Source file: Fraction.cpp -> Compile -> Fraction.o
- Source file: Math.cpp -> Compile -> Math.o

##### Step 5: Linking object files and libraries

After the compiler creates the object files, then a 2nd program called the linker kicks in.

Linker: 

The linker has 3 jobs:
1. Take all of the object .o files and combine them into 1 single executable program .exe

2. Link library files
- C++ Standard Library
    - provides a set of capabilities for your programs
    - used in almost every C++ program
    - example: iostream, 
- Optional: Any other libraries used
    - You can download a library that knows how to do things, and use it to help your program

3. Make sure all cross-file dependencies are resolved properly
- Example: if you define something in one.cpp, and use in two.cpp, the linker connects the two together
    - if it cannot connect a reference, an error will be thrown


Building: Full process of converting source code files into an executable file that can be run
- specific executable produced as result of building: "build"

For advanced readers: make/build2 are build automation tools that are used to automate the process of building programs + running automated tests
- powerful tools, but not part of C++ language

##### Steps 6 & 7: Testing and Debugging

Fun part: See if your executable produces the output you were expecting!
- runs and works as expected: cool
- runs and does NOT work as expected: debugging time

##### Integrated Development Environments (IDEs)

Note: Steps 3, 4, 5 and 7 all involve software (editor, compiler, linker, debugger)
- You can use separate programs for each of these activities, but an IDE bundles and integrates all of these features in 1

We will download one in the next section!

Once the linker has linked all .o files and libraries, you will have a .exe executable program file that you can run!

#### 0.6 Installing an Integrated Development Environment (IDE)

Integrated Development Environemnt (IDE): a piece of software designed to make it easy to develop, build and debug your programs

Modern IDE's will include:
- Way to load/save files
- Code editor w/ line numbering + syntax highlighting
- Basic build system
    - lets you compile and link your program into an executable + then run it
- Integrated debugger to make it easier to find/fix software defects
- Way to install plugins so you can modify the IDE, add capabilities such as version control, etc.

Let's install one!

##### Choosing an IDE

1. Download [VSCode](https://code.visualstudio.com/download)
- Settings (Ctrl+,):
    - Default terminal: Command Prompt
    - Default terminal directory (Search 'cwd'): C:\Users\Myles

2. Install Extensions in VSCode:
- Ctrl-Shift-X to get into Extensions Packages we want to download:
    - C/C++
    - C/C++ Extension Pack
    - Code Runner

3. Download the [latest version of MinGW-w64 via MSYS2, which provides up-to-date native builds of GCC, MinGW-w64, and other helpful C++ tools and libraries.](https://www.msys2.org/)

4. Run the installer and follow the steps of the installation wizard.
- Note that MSYS2 requires 64 bit Windows 8.1 or newer.

5. Choose desired Installation Folder and write it down
- C:\msys64

6. Finish the installation with 'Install'
When complete, ensure the Run MSYS2 now box is checked and select Finish. This will open a MSYS2 terminal window for you.

7. In this new terminal, install the MinGW-w64 toolchain by running the following command:

```bash
pacman -S mingw-w64-ucrt-x86_64-gcc

```

Enter Y when prompted whether to proceed with the installation.

8. Do some quick checks in the same terminal:

```bash
gcc --version

```

Note: What I got back (See how it is version 13.2.0):

```bash
gcc.exe (Rev2, Built by MSYS2 project) 13.2.0
Copyright (C) 2023 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
```

9. Add the path to your MinGW-w64 bin folder to the Windows PATH environment variable by using the following steps:
- Windows search bar -> Settings to open your Windows Settings -> Edit environment variables
- User variables -> Path variable -> Edit
- New -> add the MinGW-w64 destination folder ie. C:\msys64\ucrt64\bin
- Select OK to save the updated PATH.

Note: You will need to reopen any console windows for the new PATH location to be available.


10. Restart device so that the PATH knows where MinGW exists

Note: If the for some reason system variable is not there now, here's how you can append it:
- Windows Search Bar > Edit the system environment variables > Environment Variables > System variables > Scroll down to PATH > Edit > Edit > Paste in C:\MinGW\bin > Enter > OK > OK > OK

11. Check your MinGW installation
- To check that your MinGW-w64 tools are correctly installed and available, open a new Command Prompt and type:

```bash
set
```

What you should see (It is because this is where the MinGW applications are located):
- System variables: C:\msys64\ucrt64\bin

More checks:

```bash
gcc -v
gcc --version
g++ --version
gdb --version

```

You should see output that states which versions of GCC, g++ and GDB you have installed. If this is not the case:
- Make sure your PATH variable entry matches the MinGW-w64 binary location where the toolchain was installed. If the compilers do not exist at that PATH entry, make sure you followed the previous instructions.
- If gcc has the correct output but not gdb, then you need to install the packages you are missing from the MinGW-w64 toolset.
    - If on compilation you are getting the "The value of miDebuggerPath is invalid." message, one cause can be you are missing the mingw-w64-gdb package.

12. Update all packages on MSYS2

```bash
pacman -Suy
```

Note: Location of msys2: C:\msys64\msys2.exe

Resources:
- [msys2](https://www.msys2.org/)
- [Visual Studio Code on Windows](https://code.visualstudio.com/docs/setup/windows)
- [Using GCC with MinGW](https://code.visualstudio.com/docs/cpp/config-mingw)

#### 0.7 Compiling your first program

Steps:
1. Create a new project
- This is a container that holds all source code files and data needed to produce an executable/library/website
    - images
    - data files
    - various ide/compiler/linker settings

Best practice: Create a new project for each new program you write!

##### Console Projects

All projects we create will be console projects.

console projects: we create programs that can run from Windows, Linux, or Mac console
- default: no GUI
    - prints text to console
    - read input from keyboard
    - compmiled into stand-alone files
- perfect for learning C++
    - keeps complexity to a minimum

##### Workspaces / solutions

Workspace/solution: a container that can hold 1 or more related projects
- Example: You are writing a game
    - executable 1: single player
    - executable 2: multi-player
        - we make these separate executables, but inside of the same projects (after all, they are part of the same game, so why keep independent?)

Recommendation for when learning: create a new workspace/solution for each program

##### Writing your first program

We will skip over the famous "hello world" example!

Steps:
1. Open a terminal and type the following code:
- projects: folder for all vscode projects
- helloworld: name of the project we will currently work on
- .: open vscode in this current working folder ie. your workspace

```bash
mkdir projects
cd projects
mkdir helloworld
cd helloworld
code .

```

2. Create a new .cpp file

```bash
echo > helloworld.cpp

```

Add in the following source code:

```cpp
#include <iostream>

int main()
{
    std::cout << "Hello World" << std::endl;
}

```

Save your file before moving on.

Note: You can also create a new file in VSCode with File -> New File

3. Run helloworld.cpp
- step 1: ensure we are in the workspace
- step 2: compile
- step 3: run the .exe

```bash
cd "c:\Users\Myles\projects\helloworld\"
g++ helloworld.cpp -o helloworld
helloworld.exe

```

Note: You can also run the program with the play button in the top right of VScode.

##### Q: What are precompiled headers and why are we turning them off?

In large projects (those with many code files), precompiled headers can improve compilation speed by avoiding some redundant compilation that tends to occur in larger projects.
- However, precompiled headers require extra work to use, and for small projects (such as those you’ll create in our tutorials) make little to no difference in compilation times.
- For this reason, we recommend turning precompiled headers off initially, and only enabling them later if and when you find your compilation times suffering.

##### Q: What is the difference between the compile, build, rebuild, clean, and run/start options in my IDE?

Here is what these options typically does:
- build: compiles all MODIFIED code files in the workspace, then links the object files into a .exe (does nothing if no files have been updated)
- clean: removes all cached objects and executables (next time project is built, all files will be recompiled + a new .exe produced)
- rebuild: clean + build
- compile: recompiles a single code file (does not involve linker or produce a .exe)
- run/start: executes the .exe from a prior build (some IDE will do build + run, to ensure it is the most recent code)

#### 0.8 A few common C++ problems

#### 0.9 Configuring your compiler: Build configurations

Build configuration: collection of project settings that determines how your IDE will build your project
- aka: build target
- includes the following:
    - name oe executable
    - directories the IDE will look in for code/libraries
    - whether to keep debugging info
    - how much to have the compiler optimize your program
    - etc.
- In general: Leave build configuration as default!

IDE will setup 2 different build configurations:
1. debug configuration: helps you debug your program
- default: used when writing the program
- turns off all optimizations:
    - makes program larger/slower
    - makes program easy to debug

2. release configuration: used when releasing to the public
- optimized for size/performance:
    - makes program faster/smaller
    - doesn't contain extra debugging info

Comparing size for executable of hello world:
- release: 44kb
- debug: 65kb
    - a lot of difference comes in extra debugging info kept in the debug build

Best practices: 
- developing: use debug build
- testing performance: use release build
- releasing to others: use release build

How to switch between debug/release build:
- VSCode: 
- Command line: 
    - release build: g++ -o my_executable source_code.cpp
    - debug build: g++ -g -o my_executable source_code.cpp
        - -g flag tells compiler to generate debug info

#### 0.10 Configuring your compiler: Compiler extensions

Compiler extensions: compiler-specific behaviors enhance compatibility with versions of the C++ language
- breaks/incompatible with the C++ standard
- will not compile on other compilers

frustrating: these compiler extensions are often enabled by default! (bad for beginners, especially)

Best practice: Disable compiler extensions to remain compliant with C++ standards (Extensions are NEVER necessary)

How to disable: 
- VSCode: 
- G++/Command Prompt:  add `-pedantic-errors` in the command line:

```bash
g++ -g -o my_executable helloworld.cpp -pedantic-errors
```

#### 0.11 Configuring your compiler: Warning and error levels

When you write your programs, the compiler will check to ensure you have followed the rules of C++.
- if you have violated the rules: compiler will emit an error OR warning

error: violating rules of C++
- line number
- text about what was expected

warning: might be an error
- does not halt compilation
- "trust the programmer" makes it not know. so it warns you

Best practice: Don't let warnings pile up ie. Resolve them as you encounter them (as if they were errors)

Sometimes: You may need to tell your compiler to stop emiting a warning (C++ compiler does not allow this, so I will press on)

##### Increasing your warning levels

Default: Compilers generate warnigns about the most obvious issues
- You can request that your compiler be more assertive

Best practice: Turn your warning levels up to the maximum (Especially when learning! will help identify possible issues)

How to increase warning levels:
- VSCode: 
- Command line: add these flags: -Wall -Weffc++ -Wextra -Wconversion -Wsign-conversion

Example:

```
g++ -g -o my_executable helloworld.cpp -pedantic-errors -Wall -Weffc++ -Wextra -Wconversion -Wsign-conversion

```

##### Treat warnings as errors

It is also possible to tell your compiler to treat all warnings as if they were errors ie. it will halt compilation
- This is a good way to enforce the recommendation to fix all warnings, which is good for those who lack self-discipline (most of us do!)

Best practice: Enable "treat warnings as errors"

How to treat warnings as errors:
- VSCode: 
- Command line: add this flag: -Werror

Example:

```
g++ -g -o my_executable helloworld.cpp -pedantic-errors -Werror

```

#### 0.12 Configuring your compiler: Choosing a standard language

There are many versions of C++ available as we know, so how do we pick one?
- Generally: compilers pick a standard ie. C++14

##### Code names for in-progress language standards

When a new language standard is being agreed upon, it is not clear what the finalization year will be. Because of this, there are in-progress language standards (that end up getting replaced)
- example:
    - name: C++11
    - name when being worked on: c++1x

Mappings of these names:
- c++1x = C++11
- c++1y = C++14
- c++1z = C++17
- c++2a = C++20
- c++2b = C++23

##### Which language standard should you choose?

In professional environments: common to choose a language standard that is 1-2 versions back from the latest
- If C++20 is the latest, then many will use C++14/C++17
- Reasons why:
    - ensures that the compiler has had a chance to resolve defects
    - best practices are understood
    - ensures better cross-platform compatibility (compilers on some platforms may not provide full support for newer language standards)

Personal projects/learning: Choose the latest finalized standard ie. right now C++20
- little downside to doing so

##### Author's note

This website currently targets the C++17 standard
- If you can use C++20: take full advantage and do it!

Reminder: When changing your language standard, or any project setting, make the change to all build configurations

##### Setting a language standard

Setting a language standard:
- VSCode: 
- Command prompt/G++: add compiler flags
    - examples (if you have GCC 6 like me):
        - -std=c++11
        - -std=c++14
        - -std=c++17
        - -std=c++20 (would be -std=c++2a in GCC 8/9)

```
g++ -g -o my_executable helloworld.cpp -pedantic-errors -Werror -std=c++17
my_executable.exe

```

##### Testing your compiler for C++17 compatibility

If you have C++17 (or higher), this code will compile without errors/warnings.

```bash
cd projects
mkdir test17
cd test17
echo > test17.cpp

```

```cpp
// test17.cpp
#include <array>
#include <iostream>
#include <string_view>
#include <tuple>
#include <type_traits>

namespace a::b::c
{
    inline constexpr std::string_view str{ "hello" };
}

template <typename... T>
std::tuple<std::size_t, std::common_type_t<T...>> sum(T... args)
{
    return { sizeof...(T), (args + ...) };
}

int main()
{
    auto [iNumbers, iSum]{ sum(1, 2, 3) };
    std::cout << a::b::c::str << ' ' << iNumbers << ' ' << iSum << '\n';

    std::array arr{ 1, 2, 3 };

    std::cout << std::size(arr) << '\n';

    return 0;
}

```

```bash
g++ -g -o my_executable test17.cpp -pedantic-errors -Werror -std=c++17
my_executable.exe

```

##### Testing your compiler for C++20 compatibility

If you have C++20 (or higher), this code will compile without errors/warnings.

```bash
cd projects
mkdir test20
cd test20
echo > test20.cpp

```

```cpp
// test20.cpp
#include <array>
#include <iostream>
#include <span>

struct Foo
{
    int a{ };
    int b{ };
    int c{ };
};

consteval int sum(std::span<const int> a) // std::span and consteval
{
    int s{ 0 };
    for (auto n : a)
        s += n;
    return s;
}

auto sum(auto x, auto y) -> decltype(x + y) // abbreviated function templates
{
    return x + y;
}

int main()
{
    constexpr std::array a{ 3, 2, 1 };
    constexpr int s{ sum(a) };
    std::cout << s << '\n';

    Foo f1{ .a = 1, .c = 3 }; // designated initializers
    std::cout << sum(f1.a, f1.c) << '\n';

    return 0;
}

```

```bash
g++ -g -o my_executable test20.cpp -pedantic-errors -Werror -std=c++20
my_executable.exe

```

Note: C++20 is when consteval was created, and I do not have it!

##### Exporting your configuration

Creating a project template (so that you do not need to reselect all of your settings when making a new project):

1. 

##### Where can I view the C++ standards document?

Standards document: Formal technical document that is the authoritative source for the rules/requirements of a language standard
- not designed for learning
- designed for compiler writers to be able to implement new language standards accurately
    - you will occasionally see people quoting the standards document when explaining how something works

Approved C++ standards: 
- not available for free (can purchase [here](https://isocpp.org/std/the-standard))
- what is fee: draft standards documents that are published for review
    - the last draft standard is usually close enough to the official standard (for most purposes)
    - you can find those [here](https://www.open-std.org/jtc1/sc22/wg21/docs/standards)


### Chapter 1: C++ Basics

Goal of this chapter: Help you understand how basic C++ programs are constructed

#### 1.1 Statements and the structure of a program

##### Statements

Computer program: sequence of instructions

Statement: Type of instruction
- causes the program to perform some action
- most common type of instruction in a C++ program
    - smallest independent unit of computation (acts like sentences in a natural language)

- Most: end in a semicolon 
- In a high level language like C++, 1 statement can compile into many machine language lines of code/instructions

Types of statements:
- Declaration
- Jump
- Expression
- Compound
- Selection (conditionals)
- Iteration (loops)
- Try blocks

##### Functions and the main function

Function: Collection of statements that get executed sequentially
- how C++ statements get grouped into units

Rule: Every C++ program must have a special function named `main`
- When the program runs, the statements inside of main are executed in order

Programs terminate/finish running after the last statement inside of the main function

Function purpose: to do a specific job or useful action
- Examples:
    - max: take largest of 2 numbers
    - calculateGrade: calculate student's grade from a set of test scores
    - printEmployee: print an employee's information

Nomenclature: We add parentheses to the end of functions
- Example: main(), doSomething()

Identifier: name of a function/object/type/template/etc.

##### Dissecting Hello World!

```cpp
// prepocessor directive (we want to use contents of this library)
#include <iostream>

int main() // main function: necessary
{ // function body starts
   std::cout << "Hello world!"; // cout: character output
   return 0; // return statement (0 = everything went okay!)
} // function body ends

```

All programs we write will follow this general template.

##### Syntax and syntax errors

In English, sentences are constructed to specific grammatical rules that you probably learned in school in English
- Rules that governhow sentences are constructed in a language are called syntax
- Example of violating a rule: Not ending a sentence with a period

C++ syntax: How programs must be constructed
- if you violate a rule: syntax error
- Example of violating a rule: Not ending a statement with a semicolon

##### Quiz Time

Question #1: What is a statement?
- instruction in a computer program

Question #2: What is a function?
- a collection of statements

Question #3: What is a statement?
- main()

Question #4: What is a statement?
- first statement inside of main()

Question #5: What symbols are statements in C+ often ended with
- semicolon

Question #6: What is a syntax error?
- compiler error if your program violates the grammar rules of C++ language

Question #7: What is the C++ Standard Library?
- library that ships with C++ that has additional functionality
    - library file: collection of precompiled code that was packaged up for re-use

#### 1.2 Comments

Comment: a readable note that is inserted directly into the source code of the program
- ignored by the compiler
- 2 types of comments (both help programmer document the code)
    - single line comments (//)
    - multi-line comments (/* ... */)

##### Proper use of comments

Three things usually:
1. For what a library/program/function does
- Put this description right before library/program/function

2. Within a library/program/function, describe how the code is going to accomplish the goal
- Understanding the methodology as a whole (so you don't need to read the lines of code)

3. WHY the code is doing something
- Example:

```cpp
// good: The player just drank a potion of blindness, and cannot see
// bad: Set sight range to 0
sight = 0;

```

```cpp
// good: We need to multiply quantity by 2 here because they are bought in pairs
// bad: Calculate the cost of the items
cost = quantity * 2 * storePrice;
```

Takeaways:
- Programmers have to decide between ways of doing things. Comments tell WHY we chose to do what we did
- Comments should be written in a way that makes sense to somebody who has NO IDEA what the code does

Best practice: Comment your code generously ie. speak to somebody who doesn not know how to code
- do NOT assume you'll remember why you made certain choices!!

##### Commenting Out Code

```cpp
// One line

/*
multiple
lines
of
code
*/
```

Why you would comment out code:
1. You are working on new code that won't compile yet
- uncomment when you are ready

2. You have written code that compiles but does not work yet correctly

3. To find the source of an error
- Finding line where you may have messed up

4. Replace one piece of code with another
- Leave it for reference, just in case you go back

##### Summary

Summary:
- WHAT: at the library/program/function level, use comments to describe WHAT
- HOW: inside the library/program/function, use comments to describe HOW
- WHY: at the statement level, use comments to describe WHY

#### 1.3 Introduction to objects and variables

##### Data and values

Data: information that can be moved, processed, or stored by a computer
- programs are collections of instructions taht manipulate data (to produce a result)
- comes from many sources:
    - files
    - databases
    - over a network
    - user input on the keyboard
    - source code of the program itself

- stored in your computer as binary code (not human readable)

Value: 1 single piece of data

##### Random Access Memory (RAM)

Random Access Memory: Where the program gets loaded into
- a series of numbered boxes that stores data while a program is running

Older programming languages: You could directly access memory boxes

##### Objects and variables

In C++, direct memory access is discouraged

Preferred method: Access memory indirectly via an objet

Object: region of storage (usuall memory) that can store a value
- how we access memory indirectly

Instead of "go get the value stored in mailbox number 7532", we say "go get the object stored by this object"

We can focus on object instead of where in the memory these objects are!

Variable: an object with a name
- we often use an identifier to name these variables
- object can be anonymous

Key insight:
- object: stores a value in memory
- variable: object that has a name
    - naming our objects lets us re-use them later

Nomenclature:
- general programming: object = unnamed object in memory/variable/function
- c++: object = narrower definition (excludes functions)

##### Variable Instantiation

Definition: special kind of declaration statement
- at compile time, it notes that we are defining a variable
    - when the compiler sees that identifier, it knows we are referencing that variable

```cpp
// Example:
int x; // name of variable = x, type of variable = int
```

Runtime: When the program is run
- variables are instantiated
- instantiation: fancy word that means the object is created AND assigned a memory address
    - variables must be instantiated before storing values
    - aka: instance

Example: variable x is instantiated at memory location 140
- when the program uses variable x, it accessess the value in memory location 140

declaration vs. definition:
- declaration: 
- definition: 

Compile-time: type of a variable must be known
- example: integers can only hold integers

##### Data types

Data types: tells the compiler what type of value the variable will store

Custom types: Helps make C++ powerful
- C++ lets you create your own custom types

##### Defining multiple variables

These snippets of code are the same:

```cpp
// method 1
int a;
int b;

```cpp
// method 2
int a, b;

```

Common mistakes:

```cpp
// 1. giving each variable a type
int a, int b; // compiler error
// 2. define variables of different types on same line
int a, double b; // not recommended!
```

Best way to do this:

```cpp
int a;
double b;
```

##### Summary

Summary:
- in C++ we use objects to access memory
- Named object: variable
- Variables have the following:
    - identifier
    - type
    - value

##### Quiz Time

Question 1: What is data?
- any information that can be moved/processed/stored by a computer

Question 2: What is a value?
- a letter/number/some useful concept that can be represented by data

Question 3: What is a variable?
- a named region of memory, which can be used to store values

Question 4: What is an identifier?
- name that a variable is accessed by

Question 5: What is a type?
- how the program interprets a value in memory

Question 6: What is an integer?
- number written without a fraction component

#### 1.4 Variable assignment and initialization

##### Variable assignment

Variable assignment: 
- happens after a variable has been defined
- equal sign (=): assignment operator

```cpp
int width; // define variable
width = 5; // assign value of 5 to variable width
```

Copy assignment:
- Default: assignment copies the values of the right-hand side of the = to the variable on left hand side

Example of over-writing an assignment:

```cpp
#include <iostream>

int main()
{
	int width;
	width = 5; // copy assignment of value 5 into variable width

	std::cout << width; // prints 5

	width = 7; // change value stored in variable width to 7

	std::cout << width; // prints 7

	return 0;
}
```

Warning: Do not confuse `=` with `==`
- `=`: assignment
- `==`: check for equality


##### Initialization

Initialization definition + copy-assignment
- combines the 2 steps

Initialization in C++ is complex, so here is an example of 6 ways to initialize variables in C++:

```cpp
int a;         // no initializer (default initialization)
int b = 5;     // initializer after equals sign (copy initialization)
int c( 6 );    // initializer in parenthesis (direct initialization)

// List initialization methods (C++11) (preferred)
int d { 7 };   // initializer in braces (direct list initialization)
int e = { 8 }; // initializer in braces after equals sign (copy list initialization)
int f {};      // initializer is empty braces (value initialization)
```

##### Default initialization

Default initialization: when no initialization value is provided
- variable is left with an indeterminate value

##### Copy initialization

Copy initialization: initializer provided after equals sign
- inherited from C

```cpp
int width = 5; // copy initialization of value 5 into variable width
```

Notes:
- Copy initialization had fallen out of favor in modern C++ 
    - it was less efficient for complex types
    - c++17 remedied this!

For advanced readers: Copy initialization is also used when values are implicity copied/converted, ie. the following situations:
- passing values into a function (by value)
- return from a function (by value)
- catching exceptions (by value)

##### Direct initialization

Direct initialization: when an initializer is provided inside parenthesis
- introduced to allow for more efficient initialization of compmlex objects ie. class types
- fallen out of favor in modern C++
    - list initialization was better, but has its own quirks, so direct initialization is uses sometimes

```cpp
int width( 5 ); // direct initialization of value 5 into variable width
```

For advanced readers: Direct initialization is also used when values are explicitly cast to another type
- can make it hard to differentiate between variables and functions

See here: 

```cpp
int x();  // forward declaration of function x
int x(0); // definition of variable x with initializer 0
```

##### List initialization

List initialization: makes use of curly braces
- modern way to initialize objects
- other names: brace/uniform

3 forms:
- direct 
- copy
- value

```cpp
int width { 5 };    // direct list initialization 
int height = { 6 }; // copy list initialization 
int depth {};       // value initialization 
```

as an aside:
- list initialization was introduced to provide a more consistent init syntax ie. why it is called "uniform"

another pro: disallows "narrowing conversions"

```cpp
int width { 4.5 }; // error: a number with a fractional value can't fit into an int
```

What each type of initialization would do:
- copy: chops off the 0.5
- direct: chops off the 0.5
- list: throws error!

Best practice: Direct list initialization (or value initialization) for all of your variables

```cpp
// reminder:
int width { 5 };    // direct list initialization  
int depth {};       // value initialization 
```

##### Value initialization and zero initialization

Value initialization: When a variable is list initialized using empty braces
- value: 0 or empty (depends on the type)
    - this is called 'zero initialization'

```cpp
// value initialization / zero initialization to value 0
int width {};

```

##### Q: When should I initialize with { 0 } vs {}?

How to choose initialization method:
- explicit initialization: if you're actually using that value
- value initialization: if the value is temporary

```cpp
int x { 0 };    // explicit initialization to value 0
std::cout << x; // we're using that zero value

int x { 0 };    // explicit initialization to value 0
std::cout << x; // we're using that zero value
```

##### Initialize your variables

Best practice: init your variables upon creation

##### Initializing multiple variables

We will talk about this to tell why to avoid it:

```cpp
int a = 5, b = 6;          // copy initialization
int c( 7 ), d( 8 );        // direct initialization
int e { 9 }, f { 10 };     // direct brace initialization
int g = { 9 }, h = { 10 }; // copy brace initialization
int i {}, j {};            // value initialization

```

Common pitfalls:
- top: compiler may not complain about a being uninitialized (can create sporadic results)

```cpp
int a, b = 5; // wrong (a is not initialized!)

int a = 5, b = 5; // correct
```

A good way to see why this is wrong:

```cpp
int a, b( 5 );
int c, d{ 5 };
```

The parentheses and braces are typically placed right next to the variable name, making it clear that a/c did not get the values that b/d did.

##### Unused initialized variables warnings

variable initialized but not used: modern compilers will generate warnings
- this is rarely desirable

C++ will throw an error, so you should probably use/remove the variable.

##### The [[maybe_unused]] attribute in C++17

Consider this example with math/physics values:

```cpp
int main()
{
    double pi { 3.14159 };
    double gravity { 9.8 };
    double phi { 1.61803 };

    // assume some of the above are used here, some are not

    return 0;
}
```

To address this case where we will probably use all of the variables, but might not everytime across files, we can use [[maybe_unused]] attribute!

```cpp
int main()
{
    [[maybe_unused]] double pi { 3.14159 };
    [[maybe_unused]] double gravity { 9.8 };
    [[maybe_unused]] double phi { 1.61803 };

    // the above variables will not generate unused variable warnings

    return 0;
}
```

C++ will also optimize these variables out of the program, so that they have no performance impact.

##### Quiz time

Question 1: 
- What is the difference between initialization and assignment?
    - initialization: gives a variable the initial value ie. 0
    - assignment: gives a varaiable a value (after it is created)

Question 2: 
- What form of initialization should you prefer when you want to initialize a variable with a specific value?
- direct list initialization ie. with braces

Question 3: 
- What are default initialization and value initialization? What is the behavior of each? Which should you prefer?
    - default initialization: int x; this is an indeterminate value
    - value initialization: int x{}; this is like zero-initialization
    - preference: value initialization

#### 1.5 Introduction to iostream: cout, cin, and endl

##### The input/output library

input/output library: io library
- part of C++ standard library, deals with basic input/output
- io = input/output

This header goes at the top of any source code file:

```cpp
#include <iostream>

// rest of code that uses iostream functionality here
```

##### std::cout

`std::cout`: allows us to send data to the console to be printed as text
- cout: character output

insertion operator: `<<`

Another example using 2 insertion operators:

```cpp
#include <iostream> // for std::cout

int main()
{
    int x{ 5 };
    std::cout << "x is equal to: " << x;
    return 0;
}
```

##### std::endl

`std::endl`: moves the cursor to the next line

Example:

```cpp
#include <iostream> // for std::cout and std::endl

int main()
{
    std::cout << "Hi!" << std::endl; // std::endl will cause the cursor to move to the next line of the console
    std::cout << "My name is Alex." << std::endl;

    return 0;
}
```

Tip: We don't need the `std::endl` at the end, but it serves some good purposes:
1. indicates that the line is a complete thought
2. positions the cursor on the next line for more programs/later code
3. some operating systems do not output a new line before showing command prompt again

Best practice: Output a newline whenever a line of output is complete

##### std::cout is buffered

`std::cout` is buffered: Output is NOT sent to the console immediately
- Analogy: Rollercoaster boards, people take off
- similarly, output is sent to the console, but it gets in line before it is sent to the console immediately

So, if your program crashes/pauses/etc. before the buffer goes through, any output waiting in the buffer will NOT be displayed

Why do we use a buffer:
- buffered output: writing to buffer is fast
- non-buffered output: writing to output device is slow
    - we increase performance by doing this as few times as possible

##### std::endl vs '\n'

std::endl: 
- can be innefficient
- does two jobs
    - moves cursor to next line of console
    - flushes the buffer

'\n': also moves the cursor to next line
- preferred method!
    - moves the cursor to next line
    - does NOT flush the buffer
        - increases performance
    - more concise when writing

2 ways of doing so in C++:

```cpp
#include <iostream> // for std::cout

int main()
{
    int x{ 5 };
    std::cout << "x is equal to: " << x << '\n'; // Using '\n' standalone
    std::cout << "And that's all, folks!\n"; // Using '\n' embedded into a double-quoted piece of text (note: no single quotes when used this way)
    return 0;
}
```

Best practice: Use 'n\' > std::endl
- warning: make sure to use the backslash (\), not the forward slash (/)
    - this would cause unexpected behavior

##### std::cin

std::cin: allows us to read input from the keyboard
- cin: character input
- extraction operator: `>>`
- inputs must be stored in a variable

Let's try out an example:

```bash
cd projects
mkdir test
cd test
echo > test.cpp
```

```cpp
// test.cpp
#include <iostream>  // for std::cout and std::cin

int main()
{
    std::cout << "Enter two numbers separated by a space: ";

    int x{}; // define variable x to hold user input (and value-initialize it)
    int y{}; // define variable y to hold user input (and value-initialize it)
    std::cin >> x >> y; // get two numbers and store in variable x and y respectively

    std::cout << "You entered " << x << " and " << y << '\n';

    return 0;
}
```

Now to compile test.cpp into an executable file:

```bash
g++ -g -o my_executable test.cpp -pedantic-errors -Werror -std=c++17
my_executable.exe

```

Best practice: initialize variables first
- there is debate over this because you need to init a variable right before you give it a user-defined value

Note: C++ I/O does not allow for keyboard input without having the user press enter (need pdcurses, FXTUI, cpp-terminal, or notcurses for that!)

##### Summary

Summary:
- std::cin and std::cout always go on the left-hand side of the statement
- std::cin: input (uses `>>`)
- std::cout: output (uses `<<`)

##### Quiz time

Question 1: Consider the following program:

```cpp
#include <iostream>  // for std::cout and std::cin

int main()
{
    std::cout << "Enter a number: "; // ask user for a number
    int x{}; // define variable x to hold user input
    std::cin >> x; // get number from keyboard and store it in variable x
    std::cout << "You entered " << x << '\n';
    return 0;
}

```

Answer:
- when you enter `h`: 0
- when you enter `3.2`: 3
- when you enter `3.7`: 3
- when you enter `-3`: -3
- when you enter `hello`: 0
- when you enter `3000000000`: 2147483647
- when you enter `123abc`: 123

#### 1. Uninitialized variables and undefined behavior

Unlike other languages: C/C++ does NOT init to a given value ie. 0 automatically 
- it gives a garbage value, at that memory address
- uninitialized variable: the garbage variable

Author's note: Initialized and uninitialized are NOT polar opposites:
- initialized: given a known value at definition
- assignment: given a known value after definition
- un-initialized: has not been given a known value

Why this does not matter anymore:
- C long ago: computers were slow so 100,000 initializations mattered
- C++: 100,000 initializations is nothing, no need to optimize


Notes:
- std::cout can give you different variables for uninitialized variables
- most modern compilers will detect that you used an uninitialized variable, and will throw a warning
    - this mistake is one of the most common that novice programmers make!

##### Undefined behavior

Undefined behavior: result of executing code that is not well-defined by C++ language
- does not have any rules to determine what happens
- symptoms:
    - different results each time it is run
    - incorrect results
    - inconsistent ie. sometimes right, sometimes wrong
    - crashes
    - works on some, but not all compilers
    - it may even produce the right code still!

"Undefined behavior is like a box of chocolates. You never know what you are going to get!"

Rule: Take care to avoid all undefined behavior ie. uninitialized variables

##### Implementation-defined behavior and unspecified behavior

Implementation-defined behavior: behavior of some syntax is left up to the COMPILER to define
- must be consistent/documented
- different compilers may produce different results

```cpp
#include <iostream>

int main()
{
	std::cout << sizeof(int) << '\n'; // print how many bytes of memory an int value takes

	return 0;
}
```

Here:
- most compilers: 4
- some compilers: 2 (size of int in bytes may differ)

Unspecified behavior: behavior of some syntax is left up to the IMPLEMENTATION to define
- implementation is not required to document the behavior

Best practice: Avoid Implementation-defined behavior and unspecified behavior (they can cause your program to malfunction)

##### Quiz time

Question 1: What is an uninitialized variable? Why should you avoid using them?
- a variable that has not been given a value via initialization or assignment
- using a stored value will result in undefined behavior

Question #2: What is undefined behavior, and what can happen if you do something that exhibits undefined behavior?
- undefined behavior: result of code whose behavior is not defined by C++
- result: can be anything

#### 1.7 Keywords and naming identifiers

##### Keywords

Keywords: C++ reserves 92 words for its own use
- each has special meaning in C++ language

[here is the list!](https://www.learncpp.com/cpp-tutorial/keywords-and-naming-identifiers/)

Examples of common keywords:
- int
- return
- delete
- public

##### Identifier naming rules

Reminder: Identifier = name of variable/function/type/etc.

Rules for Identifiers:
- cannot be keyword (they are reserved)
- can only be composed of letters, numbers, and underscores (no spaces or symbols)
- must begin with a letter OR underscore (no numbers)

remember: that C++ is case-sentitive
- nValue != nvalue

##### Identifier naming best practices

Best practices:
1. Variable names should begin with a lowercase letter
- if only one word: all lowercase
2. Avoid starting with an underscore
3. Identifiers should make it clear what value they are holding
- especially: when units are not obvious
- think: you want to know what this is in 3 months without looking at rest of code

```cpp
// 1.
int value; // conventional

int Value; // unconventional (should start with lower case letter)
int VALUE; // unconventional (should start with lower case letter)
int VaLuE; // unconventional (see your psychiatrist) ;)

int my_variable_name;   // conventional (separated by underscores/snake_case)
int my_function_name(); // conventional (separated by underscores/snake_case)

int myVariableName;   // conventional (intercapped/CamelCase)
int myFunctionName(); // conventional (intercapped/CamelCase)

int my variable name;   // invalid (whitespace not allowed)
int my function name(); // invalid (whitespace not allowed)

int MyVariableName;   // unconventional (should start with lower case letter)
int MyFunctionName(); // unconventional (should start with lower case letter)

// 2. 
// a count of the number of chars in a piece of text, including whitespace and punctuation
int numberOfChars;
```

Best practice: If working in an existing program, match their code (even if it doesn't conform to lowercase/modern practices - you can use those for your new programs)

##### Quiz time

Question 1: Based on how you should name a variable, indicate whether each variable name is conventional (follows best practices), unconventional (compiler will accept but does not follow best practices), or invalid (will not compile), and why.

```cpp
int sum {}; // good

int apples {}; // bad: starts with underscore

int VALUE {}; // bad: uppercase

int my variable name {}; // bad: has spaces

int TotalCustomers {}; // bad: starts with uppercase

int void {}; // invalid: keyword

int numFruit {}; // good

int numFruit {}; // invalid: starts with number

int meters_of_pipe {}; // good

```

#### 1.8 Whitespace and basic formatting

Whitespace: characters used for formatting
- spaces, tabs, newlines

Used for 3 things:
1. separating language elements
2. inside text
3. formatting code

##### Using whitespace to format code

```cpp
// bad
#include <iostream>
int main(){std::cout<<"Hello world";return 0;}

// good
#include <iostream>

int main()
{
    std::cout
        << "Hello world"; // works fine
    return 0;
}
```

##### Basic formatting

C++ does not enforce formatting, but there are styles that work best for consistency.

Rules:
1. Spaces vs. tabs are both OK
- i use spaces

2. Use one of the following for function braces:

```cpp
// google C++ guide
int main() {
}
// their recommendation:
int main()
{
}
```

3. Statements within curly braces need to be 1 tab / 4 spaces from the opening brace

```cpp
int main()
{
    std::cout << "Hello world!\n"; // tabbed in one tab (4 spaces)
    std::cout << "Nice to meet you.\n"; // tabbed in one tab (4 spaces)
}
```

4. Lines should not be too long
- Best practice: 80 character max. per line

5. If a long line is split with an operator ie. `<<` or `+`, operator should be on next line:

```cpp
std::cout << 3 + 4
    + 5 + 6
    * 7 * 8;
```

6. Use whitespace to align values/comments

```cpp
// hard to read
cost = 57;
pricePerItem = 24;
value = 5;
numberOfItems = 17;
std::cout << "Hello world!\n"; // cout lives in the iostream library
std::cout << "It is very nice to meet you!\n"; // these comments make the code hard to read
std::cout << "Yeah!\n"; // especially when lines are different lengths
// cout lives in the iostream library
std::cout << "Hello world!\n";
// these comments make the code hard to read
std::cout << "It is very nice to meet you!\n";
// especially when all bunched together
std::cout << "Yeah!\n";



// easy to read
cost          = 57;
pricePerItem  = 24;
value         = 5;
numberOfItems = 17;
std::cout << "Hello world!\n";                  // cout lives in the iostream library
std::cout << "It is very nice to meet you!\n";  // these comments are easier to read
std::cout << "Yeah!\n";                         // especially when all lined up

// cout lives in the iostream library
std::cout << "Hello world!\n";

// these comments are easier to read
std::cout << "It is very nice to meet you!\n";

// when separated by whitespace
std::cout << "Yeah!\n";
```

##### Automatic Formatting

Most modern IDEs: help you format code as you type it in ie. automatic indentations, etc.

Best practice: Use the automatic formatting feature to keep code consistent

How to do this in VSCode:
1. Configure formatting settings
- Ctrl+,- -> c_cpp.clang_format_fallback style -> choose one ie. 'Visual Studio (I chose Visual Studio/Microsoft bc it is based on the C++ core guidelines)
2. Optional: Add keyboard shortcut
- search 'format on save' -> turn on

Best practice: Use automatic formatting!


#### 1. Introduction to literals and operators

Literal constant: fixed value in source code
- does not change

Difference between literals/constants and variables:
- literal: 5
- variable: x = 5

##### Operators

Operation: a process involving 0+ input values and produces a new value (output value)
- operator: specific symbol ie. +-*/
- operand: input values

Author's note: Later you will see that we will use the word `operator` and then append the operator symbol after

```cpp
operator+
operator>>
```

arity: number of operands/input values
- 4 types of arity:
    - Unary: acts on 1 operand ie. negative sign
    - Binary: acts on 2 operands ie. addition/subtractions
    - Ternary: acts on 3 operands ie. conditionals
    - Nullary: acts on 0 operands ie. throw operator
    
##### Chaining operators

You can chain operators together like in math:

```cpp
2 * 3 + 4
```

Remember: PEMDAD
1. Parentheses
2. Exponents
3. Multiplication + Division
4. Addition + Subtraction

##### Return values and side effects

Return values and side effects:
- Most operators in C++: Use their operands to calculate a return value
    - -5 returns -5
    - 2 + 3 returns 5
- Some operators: have additional behaviors beyond a return value ie. a "side effect"
    - x = 5 (called for side effect, not a return value)

##### For advanced readers

Return values that return their left operand:
- operator=
- operator<<
- std::cout

Example:

```cpp
// x = (y = 5) - > 1. y is 5 -> 2. y return 5 -> 3. x = 5
x = y = 5;

// (std::cout << "Hello ") << "world!" -> 1. Hello is printed to console  via std::cout 2. std::cout returns std::cout 3. world is printed via std::cout
std::cout << "Hello" << "world!";
```

##### Quiz time

Question 1: Indicate what the following produce:
- `std::cout << 3 + 4 << '\n';`: 7
- `std::cout << 3 + 4 - 5 << '\n';`: 2
- `std::cout << 2 + 3 * 4 << '\n';`: 14

Extra credit: 

```cpp
int x { 2 };
std::cout << (x = 5) << '\n';
```

Answer: 5

##### 1.10 Introduction to expressions

Examples of expressions:

```cpp
// five() is a function that returns the value 5
int five()
{
    return 5;
}

int main()
{
    int a{ 2 };             // initialize variable a with literal value 2
    int b{ 2 + 3 };         // initialize variable b with computed value 5
    int c{ (2 * 3) + 4 };   // initialize variable c with computed value 10
    int d{ b };             // initialize variable d with variable value 5
    int e{ five() };        // initialize variable e with function return value 5

    return 0;
}
```

Expression: Combination of literals/variables/operators/functions calls to calculate 1 value
- process of executing an expression: evaluation
- single value output: result

```cpp
// more examples
2               // 2 is a literal that evaluates to value 2
"Hello world!"  // "Hello world!" is a literal that evaluates to text "Hello world!"
x               // x is a variable that evaluates to the value of x
2 + 3           // operator+ uses operands 2 and 3 to evaluate to value 5
five()          // evaluates to the return value of function five()
```

Note: Expressions evalutate to their own values

Syntax:
```cpp
// type identifier { expression };
int x{ 2 + 3 }; // 2 + 3 is an expression that has no semicolon -- the semicolon is at the end of the statement containing the expression
```

##### Useless expressions statements

Examples that are discarded and useless:

```cpp
3;
```

##### Subexpressions, full expressions, and compound expressions

Example: 

```cpp
// full expression
x = 4 + 5;
```

Subexpressions: part of an expression
- x, 4+5, 4, 5

Full expressions: not a sub-expression

Compound expressions: Contains 2+ operators
- above examples has operator+ and operator=

##### Quiz time

Question 1: What is the difference between a statement and an expression?
- statement: perform an action
- expression: calculate a value

Question 2: indicate whether each of the following lines are statements that do not contain expressions, contain expressions, or ARE expression statements

```cpp
int x; // not an expression (it is a variable definition)
int x = 5; // contains expression
x = 5; //  is an expression
foo(); // is an expression (functions are part of an expression)
std::cout << x; // is an expression (left, binary, right operator makes up an expression)

```

Question 3: Determine what values the following program outputs.

```cpp
#include <iostream>

int main()
{
	std::cout << 2 + 3 << '\n';

	int x{ 6 };
	int y{ x - 2 };
	std::cout << y << '\n';

	int z{ };
	z = x;
	std::cout << z - x << '\n';

	return 0;
}
```

Answer: 5, 4, 0

#### 1.11 Developing your first program

##### Multiply by 2

Best practice: Add 1 piece to a program at a time (instead of writing it all at once)

Steps:

1. Create a new project

```bash
cd projects
mkdir multiply_by_2
cd multiply_by_2
echo > source_code.cpp

```

2. Write optimal source code

```cpp
#include <iostream>

int main()
{
    std::cout << "Enter an integer";

    int num{};
    std::cin >> num;

    std::cout << "Double that number is: " << num * 2 << '\n';

    return 0;
}

```

3. Compile + Run executable

```bash
g++ -g -o my_executable source_code.cpp -pedantic-errors -Werror -std=c++17
my_executable.exe

```

Good job!

##### Quiz time

Question 1: Modify the solution to the “best solution” program above so that it outputs like this (assuming user input 4):

Enter an integer: 4
Double 4 is: 8
Triple 4 is: 12

Answer: 

```cpp
#include <iostream>

int main()
{
    std::cout << "Enter an integer";

    int num{};
    std::cin >> num;

    std::cout << "Double that number is: " << num * 2 << '\n';

    std::cout << "Triple that number is: " << num * 3 << '\n';

    return 0;
}

```


#### 1.x Chapter 1 summary and quiz

...

### Chapter 2: Functions and Files

#### 2.1 Introduction to functions

function: reusable sequence of statements
- designed to do 1 job

user-defined functions: functions that you write yourself

function call: expression that tells the CPU to interrupt the current function and execute another function
- puts a "bookmark" at current point, then calls the function in the call
    - when that function ends, we return to the bookmark/starting point
        - caller function calls the callee/called

Example of user-defined function:

```cpp
returnType functionName() // This is the function header (tells the compiler about the existence of the function)
{
    // This is the function body (tells the compiler what the function does)
}
```

Contents:
- function header
    - return type
    - paramaters
    - function name
- function body

##### Nested functions are not supported

Some other programming langauges allow for syntax like this:

```cpp
#include <iostream>

int main()
{
    void foo() // Illegal: this function is nested inside function main()
    {
        std::cout << "foo!\n";
    }

    foo(); // function call to foo()
    return 0;
}
```

C++ does not. Just write it like this instead:

```cpp
#include <iostream>

void foo() // no longer inside of main()
{
    std::cout << "foo!\n";
}

int main()
{
    foo();
    return 0;
}
```

##### Quiz time

Question 1: In a function definition, what are the curly braces and statements in-between called?
- function body

Question 2: What does the following program print? (Do not compile this program, just trace the code yourself.)

Answer:

```
Starting main()
In doA()
In doB()
In doB()
Ending main()
```

#### 2.2 Function return values (value-returning functions)

##### Return values

when you write a user-defined function, you get to determine whether your function returns a value back

2 things are needed:
1. return type (before function name)
2. return statement (inside of function)

Example:

```cpp
#include <iostream>

// int is the return type
// A return type of int means the function will return some integer value to the caller (the specific value is not specified here)
int returnFive()
{
    // the return statement indicates the specific value that will be returned
    return 5; // return the specific value 5 back to the caller
}

int main()
{
    std::cout << returnFive() << '\n'; // prints 5
    std::cout << returnFive() + 2 << '\n'; // prints 7

    returnFive(); // okay: the value 5 is returned, but is ignored since main() doesn't do anything with it

    return 0;
}
```

Note: Return values will not be printed unless the caller sends them to the console via std::cout. In the last case above, the return value is not sent to std::cout, so nothing is printed.

##### Fixing our challenge program

Here is a our example from before, except we use a function to take in the user input!

```cpp
#include <iostream>

int getValueFromUser() // this function now returns an integer value
{
 	std::cout << "Enter an integer: ";
	int input{};
	std::cin >> input;

	return input; // return the value the user entered back to the caller
}

int main()
{
	int num { getValueFromUser() }; // initialize num with the return value of getValueFromUser()

	std::cout << num << " doubled is: " << num * 2 << '\n';

	return 0;
}
```

##### Revisiting main()

main():
- return type: int
    - this is a status code/exit code
        - 0: good
        - other number: bad

- return statement: return 0

Best practice: `main()` should return 0

##### A value-returning function that does not return a value will produce undefined behavior

value-returning function: function that returns a value
- ie. return type is not `void`

Note: In most cases, compilers will detect if you’ve forgotten to return a value (do not rely on this, though)

Best practice: Make sure your functions with non-void return types return a value in all cases.

##### Function main will implicitly return 0 if no return statement is provided

Exception to the rule: `main()` will return a 0 if no return statement is provided

##### Functions can only return a single value

In future lessons, we will go over how you can get around this (ie. return 1 type that has multiple values in it!)

##### The function author can decide what the return value means

Best practice: document your function with a comment indicating what the return values mean

Example:

```cpp
// Function asks user to enter a value
// Return value is the integer entered by the user from the keyboard
int getValueFromUser()
{
 	std::cout << "Enter an integer: ";
	int input{};
	std::cin >> input;

	return input; // return the value the user entered back to the caller
}
```

##### Reusing functions

Best practice: DRY (Don't Repeat Yourself)

Example where we repeat ourselves (should write a function instead of doing this):

```cpp
#include <iostream>

int main()
{
	int x{};
	std::cout << "Enter an integer: ";
	std::cin >> x;

	int y{};
	std::cout << "Enter an integer: ";
	std::cin >> y;

	std::cout << x << " + " << y << " = " << x + y << '\n';

	return 0;
}
```

Note: Opposite of DRY = WET (Write everything twice)

##### Conclusion

Functions let us reduce redundancy in our programs!

##### Quiz time


#### 2.3 Void functions (non-value returning functions)

##### Void return values

void: tells the compiler that this function does not return a value

Example:

```cpp
#include <iostream>

// void means the function does not return a value to the caller
void printHi()
{
    std::cout << "Hi" << '\n';

    // This function does not return a value so no return statement is needed
}

int main()
{
    printHi(); // okay: function printHi() is called, no value is returned

    return 0;
}
```

##### Void functions don’t need a return statement

##### Void functions don’t need a return statement

```cpp
#include <iostream>

// void means the function does not return a value to the caller
void printHi()
{
    std::cout << "Hi" << '\n';

    return; // tell compiler to return to the caller -- this is redundant since the return will happen at the end of the function anyway!
} // function will return to caller here

int main()
{
    printHi();

    return 0;
}
```

Best practice: don't put a return statement at the end of a void function

##### Void functions can’t be used in expression that require a value

You cannot do this because this void function does not return a value:

```cpp
#include <iostream>

// void means the function does not return a value to the caller
void printHi()
{
    std::cout << "Hi" << '\n';
}

int main()
{
    printHi(); // okay: function printHi() is called, no value is returned

    std::cout << printHi(); // compile error

    return 0;
}
```

##### Returning a value from a void function is a compile error

```cpp
void printHi() // This function is non-value returning
{
    std::cout << "In printHi()" << '\n';

    return 5; // compile error: we're trying to return a value
}
```


#### 2.4 Introduction to function parameters and arguments

##### Function parameters and arguments

function parameter: variables initialized with the value provided by caller of function
- variable used in the header of a function

examples:

```cpp
// This function takes no parameters
// It does not rely on the caller for anything
void doPrint()
{
    std::cout << "In doPrint()\n";
}

// This function takes one integer parameter named x
// The caller will supply the value of x
void printValue(int x)
{
    std::cout << x  << '\n';
}

// This function has two integer parameters, one named x, and one named y
// The caller will supply the value of both x and y
int add(int x, int y)
{
    return x + y;
}
```

argument: value passed from caller of function to function call

```cpp
doPrint(); // this call has no arguments
printValue(6); // 6 is the argument passed to function printValue()
add(2, 3); // 2 and 3 are the arguments passed to function add()
```

##### How parameters and arguments work together

what happens when a function is called:
1. parameters are created as variables
2. value of each argument is copied into the matching param (by way of copy initialization)
- process name: pass by value

##### Using return values as arguments

Updating our program from earlier, so that now our program uses function parameters:

```cpp
#include <iostream>

int getValueFromUser()
{
 	std::cout << "Enter an integer: ";
	int input{};
	std::cin >> input;

	return input;
}

void printDouble(int value)
{
	std::cout << value << " doubled is: " << value * 2 << '\n';
}

int main()
{
	printDouble(getValueFromUser());

	return 0;
}

```

```bash
cd projects
cd multiply_by_2

g++ -g -o my_executable source_code.cpp -pedantic-errors -Werror -std=c++17
my_executable.exe

```

##### More examples

```cpp
#include <iostream>

int add(int x, int y)
{
    return x + y;
}

int multiply(int z, int w)
{
    return z * w;
}

int main()
{
    std::cout << add(4, 5) << '\n'; // within add() x=4, y=5, so x+y=9
    std::cout << add(1 + 2, 3 * 4) << '\n'; // within add() x=3, y=12, so x+y=15

    int a{ 5 };
    std::cout << add(a, a) << '\n'; // evaluates (5 + 5)

    std::cout << add(1, multiply(2, 3)) << '\n'; // evaluates 1 + (2 * 3)
    std::cout << add(1, add(2, 3)) << '\n'; // evaluates 1 + (2 + 3)

    return 0;
}

```

```cpp
int a{ 5 };
std::cout << add(a, a) << '\n'; // evaluates (5 + 5)

```

##### Unreferenced parameters

unreferenced parameters: parameters not used in the body of a function

Example:

```cpp
void doSomething(int count) // warning: unreferenced parameter count
{
    // This function used to do something with count but it is not used any longer
}

int main()
{
    doSomething(4);

    return 0;
}

```

Insight: If you remove the unused function parameter, the existing calls to function will  break (the function call would be supplying more arguments than the function could accept)

Remedy: unnamed parameter

unnamed parameter: a parameter without a name

Example (Note: The Google C++ style guide recommends using a comment to document what the unnamed parameter was):

```cpp
void doSomething(int /*count*/)  // ok: unnamed parameter will not generate warning
{
}
{
}
```

Best practice: When a function parameter exists but is not used, do not give it a name

#### 2.5 Introduction to local scope

local variables: variables defined inside body of a function
- typically: the function parameters

##### Local variable timeline

when is an instantiated variable destroyed: in opposite order of creation
- at the end of the set of curly braces it is defined in
    - for a function parameter: at end of function

object lifetime: time between creation + destruction
- variable creation/destruction occurs at runtime, (not compile time)

For advanced readers: C++ specification gives compilers flexibility to determine when local variables are created/destroyed ie. object may be created/destroyed earlier or later for optimization purposes
- oftentimes: local variables are created when the function is entered, destroyed in opposite order of creation at exit of function

Example program showing the lifetime of a variable `x`:

```cpp
#include <iostream>

void doSomething()
{
    std::cout << "Hello!\n";
}

int main()
{
    int x{ 0 };    // x's lifetime begins here

    doSomething(); // x is still alive during this function call

    return 0;
} // x's lifetime ends here

```

##### Local scope

local variable scope: 
- begins: at point of variable definition
- stops: at end of set of curly braces it is defined in
    - ensures that variables cannot be used before definition

Example showing `x`'s scope:

```cpp
#include <iostream>

// x is not in scope anywhere in this function
void doSomething()
{
    std::cout << "Hello!\n";
}

int main()
{
    // x can not be used here because it's not in scope yet

    int x{ 0 }; // x enters scope here and can now be used within this function

    doSomething();

    return 0;
} // x goes out of scope here and can no longer be used

```

##### “Out of scope” vs “going out of scope”

"Out of scope": anytime an identifier cannot be accessed within code
- 

"going out of scope": when scope ends ie. end of function main
- usually: applies to objects, not identifiers

takeaway: local variable's lifetime ends when it goes out of scope

Note: not all types of variables are destroyed when they go out of scope (more on this in later lessons)

##### Another example

Reminder: lifetime is a runtime property, scope is compile-time property (they are enforced at different points)

```cpp
#include <iostream>

int add(int x, int y) // x and y are created and enter scope here
{
    // x and y are visible/usable within this function only
    return x + y;
} // y and x go out of scope and are destroyed here

int main()
{
    int a{ 5 }; // a is created, initialized, and enters scope here
    int b{ 6 }; // b is created, initialized, and enters scope here

    // a and b are usable within this function only
    std::cout << add(a, b) << '\n'; // calls function add() with x=5 and y=6

    return 0;
} // b and a go out of scope and are destroyed here

```

##### Functional separation

This is the same as before ie. it runs identically (it works because x/y are distinct to their own functions, they don't even know about each other)

```cpp
#include <iostream>

int add(int x, int y) // add's x and y are created and enter scope here
{
    // add's x and y are visible/usable within this function only
    return x + y;
} // add's y and x go out of scope and are destroyed here

int main()
{
    int x{ 5 }; // main's x is created, initialized, and enters scope here
    int y{ 6 }; // main's y is created, initialized, and enters scope here

    // main's x and y are usable within this function only
    std::cout << add(x, y) << '\n'; // calls function add() with x=5 and y=6

    return 0;
} // main's y and x go out of scope and are destroyed here

```

Key insight: names used for function parameters/variables declared in a function body are only visible within that function that declares them
- ie. local variables can be named without regard for names of variables in other functions (keeps function independent!)

##### Where to define local variables

Best practice in modern C++: local variables inside the function body should be defined close to their first use

#### 2.6 Why functions are useful, and how to use them effectively

##### Why use functions?

Can’t we just put all the code inside the main function?
- if simple program: sure
- is it a good idea? no

Why functions are good:
1. Organization
- as programs grow, having everything in main makes things very complicated

2. Reusability
- a function can be called multiple times
- DRY: don't repeat yourself

3. Extensibility
- functions help extend the program

4. Abstraction
- lowers the knowledge required to use somebody else's code
- all you need to know:
    - name
    - inputs/outputs
    - where it lives

##### Effectively using functions

Basic guidelines for writing functions:
- Groups of statements that appear 2+ times should be a function
- Code with well-defined inputs and outputs is a good candidate
- Function should perform exactly 1 task
    - If it gets too long/complicated, split it up into 2+ functions
        - refactoring! (more on this later)

##### Note: When learning C++, you will see lots of programs like this:
1. read input from user
2. calculate value from inputs
3. print the calculated value

Many make this mistake: Doing all of this is main

What you should do: 3 separate functions:

```cpp
int main()
{
    int inputValue = readInputFromUser();
    int calculatedValue = calculateValue(inputValue);
    printCalculatedValue(calculatedValue);
    

}
```

#### 2.7 Forward declarations and definitions

This sample program does not work:

```cpp
#include <iostream>

int main()
{
    std::cout << "The sum of 3 and 4 is: " << add(3, 4) << '\n';
    return 0;
}

int add(int x, int y)
{
    return x + y;
}

```

Expected: The sum of 3 and 4 is: 7

Error: add.cpp(5) : error C3861: 'add': identifier not found

The compiler does not know what add is! 2 common ways to address this:

1. Reorder the function definitions
- defining add() before main() lets you use add() in main()

```cpp
#include <iostream>

int add(int x, int y)
{
    return x + y;
}

int main()
{
    std::cout << "The sum of 3 and 4 is: " << add(3, 4) << '\n';
    return 0;
}
```

Beware: In a larger program, it can become tedious doing this ie. knowing which functions are called first

2. Use a forward declaration
- forward declaration: tells the compiler about the existence of another program (before actually defining the identifier)

What we need to write a function declaration/function protoype:
- return type
- name of function
- parameter types
- semicolon

Example:

```cpp
#include <iostream>

int add(int x, int y); // forward declaration of add() (using a function declaration)

int main()
{
    std::cout << "The sum of 3 and 4 is: " << add(3, 4) << '\n'; // this works because we forward declared add() above
    return 0;
}

int add(int x, int y) // even though the body of add() isn't defined until here
{
    return x + y;
}
```

Technically, you don't need the parameter names, so this could work:

```cpp
int add(int, int); // valid function declaration
```

Best practice: Keep the parameter names in your function declaration

##### Why use forward declarations?

Most often: forward declarations tell the compiler about the existence of a function in a DIFFERENT code file
- ie. re-ordering is not possible!
- rare but can occur: if functions call one another: cannot re-order
    - "circular dependencies"

What happens if you make a forward declaration and call the function, but the program never finds/defines the function:
- compile: works
- linkage: fails

##### Other types of forward declarations

Most ofen use: Functions

Other:
- variables
- types

(these have a different synatx, so we can go over it later)

##### Declarations vs. definitions

In C++: Declarations and definitions used interchangeably
- declaration: tells the compiler about the existence of an identifier + its associated type information
    - NOT all declarations are also definitions 
- definition: declaration that implements/instantiates the identifier
    - all definitions are also declarations

```cpp
// declarations
int add(int x, int y); // tells the compiler about a function named "add" that takes two int parameters and returns an int.  No body!
int x;                 // tells the compiler about an integer variable named x

// definitions
int add(int x, int y) // implements function add()
{
    int z{ x + y };   // instantiates variable z

    return z;
}

int x;                // instantiates variable x
```

Summary table of this info:

[Summary table](./figures/2-definition-declaration.png)

##### The one definition rule (ODR)

one definition rule: well known C++ rule with 3 parts
1. within a file, each function/type/variable can only have 1 definition
2. Within a program, each function/variable can only have 1 definition
3. Types/templates/inline functions/inline variables can have duplicate definitions in different files
- as long as each definition is identical

#### 2.8 Programs with multiple code files

##### Adding files to your project

as programs get larger, you usually split programs into multiple files (for reusability/organization)

Best practice: When adding new source code files, give them a .cpp extension

Doing this from the command line:

0. Create a directory:

```bash
cd projects
mkdir multi_file_project
cd multi_file_project

```

1. Create 2 new files

```bash
echo > main.cpp
echo > add.cpp

```

```cpp
// main.cpp
#include <iostream>

int add(int x, int y); // needed so main.cpp knows that add() is a function defined elsewhere

int main()
{
    std::cout << "The sum of 3 and 4 is: " << add(3, 4) << '\n'; // compile error
    return 0;
}

```

```cpp
// add.cpp
int add(int x, int y)
{
    return x + y;
}

```



2. Compile
- make sure to add all files you want to link/compile

```bash
g++ -g -o executable main.cpp add.cpp -pedantic-errors -Werror -std=c++17
executable.exe

```

Hopefully this worked for you, as it did for me :)

##### Summary

C++ is designed so that each source file can be compiled independently, with no knowledge of what is in other files. Therefore, the order in which files are actually compiled should not be relevant.

#### 2.9 Naming collisions and an introduction to namespaces

Real life example of a naming collision:
- A city having 2 of the same street

C++ requires all identifiers to be non-amibuous
- if the compiler/linker cannot tell 2 identifiers apart, it produces an error ie. naming collision/naming conflict

##### Example of a naming conflict

```cpp
// a.cpp
#include <iostream>

void myFcn(int x)
{
    std::cout << x;
}
```

```cpp
// main.cpp
#include <iostream>

void myFcn(int x)
{
    std::cout << 2 * x;
}

int main()
{
    return 0;
}
```

What happens:
- compiler compiles a.cpp and main.cpp with no problem
- linker executes
    - it discovers that conficts exist ie. both function have a myFcn(int x)
        - abort: error thrown (even if the function is never called!)

Most naming collisions happen in 2 cases:
1. 2+ identically named functions/global variables are brought into 2 files of the same program
- result: linker error
2. 2+ identically named functions/global variables are brought into the same file
- result: compiler error

As programs get larger: Probability of naming collision increases!
- local scope does not work for function names

##### What is a namespace?

namespace: a region that allows you to declare names inside of it
- scope region/namespace scope: any name declared inside the namespace won't be mistaken for identical names in other scopes
    - within a namespace: all names must be unique (otherwise, collision results)

##### Global namespace

global namespace: any name that is not defined inside of a class/function
- an implicitly defined namespace

why the example above did not work: 2 versions of myFcn() were defined in the global namespace

What can/cannot go in the namespace:
- can:
    - declarations
    - definitions
- cannot:
    - expression statements

This code chunk helps explain:

```cpp
#include <iostream> // handled by preprocessor

// All of the following statements are part of the global namespace
void foo();    // okay: function forward declaration in the global namespace
int x;         // compiles but strongly discouraged: uninitialized variable definition in the global namespace
int y { 5 };   // compiles but discouraged: variable definition with initializer in the global namespace
x = 5;         // compile error: executable statements are not allowed in the global namespace

int main()     // okay: function definition in the global namespace
{
    return 0;
}

void goo();    // okay: another function forward declaration in the global namespace
```

Key insight: Only declarations and definitions can appear in a namespace.

##### The std namespace

History lesson:
- When C++ was originally designed:
    - all identifiers (including std::cin and std::cout) were available to be used WITHOUT std:: prefix
        - they were part of the global name space
        - why this was bad:
            - identifiers in the standard library ie. cin/cout could conflict with your user-defined identifiers
            - code that was working could get naming conflicts all of a sudden if you #include a new file from standard library (due to naming conflict)
- Nowadays:
    - all functionality of the standard library is in a namespace named "std" ie. short for standard
        - if you use std::cout, it won't conflict with cout (or anything in the global namespace)
    - example: std::cout
        - namespace: std
        - identifier: cout

Key insight: when you use an identifier that is defined inside a namespace ie. std::, you have to tell the compiler that the identifier lives inside that name space

2 ways of doing this:
1. explicit namespace qualifier `std::`
2. Using namespace std (and why to avoid it)
- avoid this: highly discouraged!!! (`std::cout` could be confused with a user's `cout`)

Warning: Avoid using-directives (such as using namespace std;) at the top of your program or in header files
- they violate the reason why namespaces were added in the first place.

Best practice: use explicit namespace prefixes to access identifiers defined in a namespace

Example why we don't want to use it:

```cpp
#include <iostream> // imports the declaration of std::cout

using namespace std; // makes std::cout accessible as "cout"

int cout() // defines our own "cout" function in the global namespace
{
    return 5;
}

int main()
{
    cout << "Hello, world!"; // Compile error!  Which cout do we want here?  The one in the std namespace or the one we defined above?

    return 0;
}
```

Personal note: Think of in Python/R how you will use the full library name of a function, instead of importing


#### 2.10 Introduction to the preprocessor

When you compile: The compiler does NOT do what you think
- what you think it does: compile each code file as you've written it
- what it actually does: each .cpp file goes through a preprocessing phase

phase: 
1. preprocessor makes changes to the text of the code file (using temporary code files OR in-memory)
- example: taking out comments, ensure each code file ends in a newline

2. process the `#include` directives
- very important role!

3. spit out a result
- result: translation unit, which ends up being compiled by the compiler

Process of preprocessing, compiling, and linking: Translation


##### Preprocessor directives

When preprocessor runs: 
1. Scan through code file from top to bottom, looking for preprocessor directives
- directives: instructions that start with # and end with a newline
    - these directives tell the preprocessor to do certain text manipulation
    - example: #include statements ie. `#include <iostream>`
        - note: preprocessor does NOT know C++, but directives have their own syntax (which may/may not resemble C++)

As an aside: preprocessing directives: Using directives is NOT an example:
- ie. `Using namespace std;`

##### #Include

When you #include a file:
1. Preprocessor replaces `#include directive_name` with contents of that file
- contents are then preprocessed
2. Repeats recursively for all #include statements
3. Rest of file is preprocessed

Example:

```cpp
#include <iostream> // preprocessor will replace #include <iostream> with the contents of the file named “iostream”, then preprocess the included content and the rest of the file.

int main()
{
    std::cout << "Hello, world!\n";
    return 0;
}
```

After the preprocessor has finished processing the code file AND all #include content, the result is the translation unit
- this is what is sent to the compiler!

Key insight: A translation unit contains both the processed code from the code file + processed code from `#include` files

##### Macro defines

#define directive: can be used to create a macro

macro: a rule that defines how input text is converted into replacement output text

2 types of macros:
1. object-like macros
- optional: substitution text
    - identifier can use letters/numbers/underscores ie. same as normal identifier
    - should start Uppercase ie. MY_NAME
- does not end with semicolon
- 

```cpp
// Object-like macros can be defined in one of two ways:
#define identifier // has no substitution text
#define identifier substitution_text // has substitution text

```

2. function-like macros
- act like functions (serve similar purpose, can do almost anything a normal function can)
- are considered unsafe

##### Object-like macros with substitution text

```cpp
#include <iostream>

#define MY_NAME "Alex"

int main()
{
    std::cout << "My name is: " << MY_NAME << '\n';

    return 0;
}
```

Why we won't use this:
- object like macros were used in C to assign names to literals
    - no longer necessary: better methods available in C++!!

Recommendation: Avoid these kind of macros alltogether (More in section 5.1)

##### Object-like macros without substitution text

Object-like macros can also be defined without substitution text:

```cpp
#define USE_YEN
```

Seems useless, but..
- useless for: text substitution
- acceptable/good for: conditional compilation
    - object-like macros with substitution text, considered acceptable to use.

##### Conditional compilation

conditional compilation preprocessor directives: allow you to choose what will/will not compile

3 most commonly used:
1. `#ifdef`: check whether an identifier has been previously #defined
- if yes: code between #ifdef and #endif is compiled
- if no: code is ignored

2. `#ifndef`: check whether an identifier has NOT been previously #defined (opposite of #ifdef)

3. `#endif`: marks end of #ifdef OR #ifndef

Examples:

```cpp
#include <iostream>

#define PRINT_JOE

int main()
{
#ifdef PRINT_JOE
    std::cout << "Joe\n"; // will be compiled since PRINT_JOE is defined
#endif

#ifdef PRINT_BOB
    std::cout << "Bob\n"; // will be excluded since PRINT_BOB is not defined
#endif

    return 0;
}
```

```cpp
#include <iostream>

int main()
{
#ifndef PRINT_BOB
    std::cout << "Bob\n"; // This program prints “Bob”, because PRINT_BOB was never #defined.
#endif

    return 0;
}
```

Note: In place of #ifdef PRINT_BOB and #ifndef PRINT_BOB, you’ll also see #if defined(PRINT_BOB) and #if !defined(PRINT_BOB).
- These do the same, but use a slightly more C++-style syntax.

##### #if 0

#if 0: 1 more common use of conditional compilation
- excludes a block of code from being compiled (as if it were inside a comment block)

Example:

```cpp
#include <iostream>

int main()
{
    std::cout << "Joe\n";

#if 0 // Don't compile anything starting here
    std::cout << "Bob\n";
    std::cout << "Steve\n";
#endif // until this point

    return 0;
}
```

Reason to use: provides a convenient way to “comment out” code that contains multi-line comments (which can’t be commented out using another multi-line comment due to multi-line comments being non-nestable)

Note: To temporarily re-enable code that has been wrapped in an #if 0, you can change the #if 0 to #if 1

##### Object-like macros don’t affect other preprocessor directives

Example to illustrate:

```cpp
#define FOO 9 // Here's a macro substitution

#ifdef FOO // This FOO does not get replaced because it’s part of another preprocessor directive
    std::cout << FOO << '\n'; // This FOO gets replaced with 9 because it's part of the normal code
#endif
```

##### The scope of #defines

Directives are resolved before compilation, from top to bottom on a file-by-file basis.

Consider the following program:

```cpp
#include <iostream>

//void foo() THIS IS THE SAME EVEN WITH THIS CODE COMMENTED OUT!
//{
#define MY_NAME "Alex"
//}

int main()
{
	std::cout << "My name is: " << MY_NAME << '\n';

	return 0;
}
```

Best practice for readability: #define identifiers outside of functions
- preprocessor will not notice it was done inside of a function
    - it doesn't understand C++ concepts like functions

Once the preprocessor has finished: All definedd identifiers from that file are discarded
- what this means: directives are only valid from the point of definition to the end of the file
    - directives in one code file do not impact other code files (even if in the same project)

Consider this example:

```cpp
// function.cpp
#include <iostream>

void doSomething()
{
#ifdef PRINT
    std::cout << "Printing!\n";
#endif
#ifndef PRINT
    std::cout << "Not printing!\n";
#endif
}

// main.cpp
void doSomething(); // forward declaration for function doSomething()

#define PRINT

int main()
{
    doSomething();

    return 0;
}
```

Output: Not printing!
- Why: `#define PRINT` in main.cpp is ignored 
    - Even though PRINT was defined in main.cpp, that doesn’t have any impact on any of the code in function.cpp (PRINT is only #defined from the point of definition to the end of main.cpp).

#### 2.11 Header files

As programs grow larger/use more files, it becomes very tedious to have to forward declare every function

Remedy: Header files!

header files: propogates declarations to .cpp files
- not the files commonly seen in C++ programming
- .h/.hpp extensions

Key insight: Header files allow us to put declaration in 1 central location and import them whenever we need them
- this can save A LOT of typing! (in multi-file programs)

##### Using standard library header files

Let's look at a basic example:

```cpp
#include <iostream>

int main()
{
    std::cout << "Hello, world!";
    return 0;
}

```

How this works:
- `#include <iostream>` brings in forward declarations for std::cout from the file named `iostream`

if we did not have this line of code: we would have to manually type/copy all declarations related to `std::cout` at the top of the file
- why this is bad:
    - requires lots of knowledge
    - can break ie. prototype change means your code must change too

##### Using header files to propogate forward declarations

Going back to the example from earlier where we had `main.cpp` and `add.cpp`, let's re-visit this:
- initially: we used forward declaration
    - this is so main.cpp knows what add() is from add.cpp
- better way to do this:
    - make a header file ie. add.h
        - add header guard
        - write content of header file ie. forward declarations

Let's do this ourselves:

```bash
cd projects
mkdir first_header_project
cd first_header_project

echo > add.h
echo > add.cpp
echo > main.cpp

```

```cpp
// add.h
// 1) We really should have a header guard here, but will omit it for simplicity (we'll cover header guards in the next lesson)

// 2) This is the content of the .h file, which is where the declarations go
int add(int x, int y); // function prototype for add.h -- don't forget the semicolon!

```

```cpp
// add.cpp
#include "add.h" // Insert contents of add.h at this point.  Note use of double quotes here.

int add(int x, int y)
{
    return x + y;
}

```

```cpp
// main.cpp
#include "add.h" // Insert contents of add.h at this point.  Note use of double quotes here.
#include <iostream>

int main()
{
    std::cout << "The sum of 3 and 4 is " << add(3, 4) << '\n';
    return 0;
}

```

And now to compile:

```bash
g++ -g -o my_executable add.h add.cpp main.cpp -pedantic-errors -Werror -std=c++17
my_executable.exe

```



Best practice:
- use a .h suffix when naming your header files (longstanding convention for C++ header files)
- if a header file is paired with a code file, they should have the same base name
    - example: add.h, add.cpp

##### How including definitions in a header file results in a violation of the one-definition rule

Avoid: putting function or variable definitions in header files
- violates the one-definition rule ie. header file is included in more than 1 source file

Let's say your header file looks like this now:

```cpp
// add.h
// We really should have a header guard here, but will omit it for simplicity (we'll cover header guards in the next lesson)

// definition for add() in header file -- don't do this!
int add(int x, int y)
{
    return x + y;
}
```

Now, when main.cpp is compiled, the #include "add.h" will be replaced with the contents of add.h and then compiled. Therefore, the compiler will compile something that looks like this:

```cpp
// main.cpp (after preprocessing):
int add(int x, int y)
{
    return x + y;
}
include <iostream>

int main()
{
    std::cout << "The sum of 3 and 4 is " << add(3, 4) << '\n';

    return 0;
}
```

This will compile. but....

When the compiler compiles add.cpp, the #include "add.h" will be replaced with the contents of add.h and then compiled. Therefore, the compiler will compile something like this:

```cpp
// add.cpp (after preprocessing):
int add(int x, int y)
{
    return x + y;
}
```

The linker will run and fail because there are 2 defintions of add()
- 1 in main.cpp
- 1 in add.cpp

Best practice: Do not put function and variable definitions in your header files (for now!)
- it will likely result in a violation of the one-definition rule (ODR) if that header is then #included into more than one source (.cpp) file

Author's note: In future lessons, we will encounter additional kinds of definitions that can be safely defined in header files (because they are exempt from the ODR). This includes definitions for inline functions, inline variables, types, and templates. We’ll discuss this further when we introduce each of these.

##### Source files should include their paired header 

Best practice for code files to #include their paired header file (if one exists).

This example illustrates it why easily:

```cpp
// something.h
int something(int); // return type of forward declaration is int

```

```cpp
// something.cpp
#include "something.h"

void something(int) // error: wrong return type
{
}

```

Why this is good: The compiler notices that the function something() has mismatched return types, and gives us a compiler error
(we would rather have this than the linker finding out)

##### Do not #include .cpp files

Preprocessor will let you, but you should never do this.

Why not:
- naming collisions
- can be hard to avoid one definition rules (especially in large projects)
- any change to a .cpp file will cause both the .cpp file and any other .cpp file that includes it to recompile (slow)
    - headers change less than source files
- non-conventional

Best practice: Avoid #including .cpp files

Tip: if your project doesn't compile unless you #include .cpp files, that menas your .cpp files are not being compiled as part of the project

##### Angled brackets vs double quotes

Why do we use <> for iostream, but "" for add.h?
- it is possible that a header file with the same filename can exist in multiple directories
    - <>: header file we did NOT write ourselves
        - searches in directories specified by `include directories`
            - configured by your compiler/IDE, defaults to the directory that header files come in your OS/operating system

    - "": header file we did write ourselves
        - searches in header file of current directory
            - if it cannot find a match, then looks in the `include directories`

Rule:
- double quotes: you've written and/or they are in the current directory
- angled bracket: headers that come with compiler

##### Why doesn't iostream have a .h extension?

Why doesn't iostream have a .h extension?
- iostream.h is a different header file than iostream

Short history lesson to explain
- when C++ was created: all files in the standard library ended in a .h suffix
    - original versions of cout/cin were in iostream.h

- after C++ standardization by ANSI committee: they moved all names used in the standard library into the std namespace
    - this helped avoid conflicts with user-declared identifiers
    - problem: if they moved all names into std namespace, none of the old programs with iostream.h would work anymore
    - workaround: a new set of header files was introduced that lacked the .h extension
        - these new header files declare all names in the std namespace
            - best of both worlds!
                - old programs: can keep `#include iostream.h`
                - new programs: can `#include <iostream>`

Key insight:
- Header files with the .h extension declared their names in the global namespace, and may be declared in std namespace as well
- Header files without the .h extension will declare their names in the std namespace
    - unfortunately and stupidly: these header files may optionally declare those names in the global namespace as well

Best practice:
- when including header file from standard library: do NOT use .h extension
- when including user-defined header file: use a .h extension

##### Including header files from other directories

Another common question: how to include header files from other directories

Bad way: relative paths

```cpp
#include "headers/myHeader.h"
#include "../moreHeaders/myOtherHeader.h"
```

Why this is bad:
- requires you to reflect your directory structure code
    - if you update your directory structure, your code won't work

Better method: Tell your compiler/IDE that you have a bunch of header files in some other location
- it will look there when it cannot find them in the current directory

How to do this: `include path` or `search directory`

For command line/G++ users: Use the -I option to specify an alternative include directory:

```bash
g++ -g -o my_executable -I/source/includes add.h add.cpp main.cpp -pedantic-errors -Werror -std=c++17
my_executable.exe

```

this way, you will only have to change a single command line call instead of every code file!

Note: There is no space after the -I.

##### Headers may include other headers

common: header files will #include another header file 
- header file will need declaration/definition that lives in a different header file
- transitive includes: when your code file #includes the first header file, you'll get any other header files that the first header file #includes (and any others that one #includes, and so on)

Best practice: Each file should explicity #include all header files it needs to compile (Don't rely on transitive includes)
- implementation of header files changes over time, so don't rely on them to keep the same #includes
    - this can be tough because C++ does not give a way to tell if you are relying...

##### The #include order of header files

if your header files are written properly: the order of inclusion does not matter

Example:
- header A needs declarations from header B
- if we forget to #include header B:
    - if we include header B before header A: code compiles (because that header B code will already have been compiled)
    - if we include header A before header B: code does NOT compile (code A will be compiled before we see declarations from B)

Best practice: To maximize the chance that missing includes will be flagged by compiler, order your #includes this way:
1. The paired header file
2. Other headers from your project
3. 3rd party library headers
4. Standard library headers

Note: In each group, sort alphabetically (unless directed otherwise)

##### Header file best practices

A few more recommendations:
- always include header guards
- do not define variables and functions (for now)
- give a header file the same name as source code ie. a.cpp and a.h
- each header file should have 1 job ie. should be specific
- avoid inadvertent transitive includes
- header file should #include any other headers containing functionality it needs
    - it should compile successfully if #included in a .cpp file by itself
- only #include what you need for the program/file
- do not #include .cpp files
- prefer putting documenation on what something does in the head
    - more likely to be seen there, than in the source file!
    - documentation describing how something works goes in the source file

#### 2.12 Header guards

Common: a definition in a header file gets included more than once
- can happen when a header file #includes another header file

Let's look at this example (note that you wouldn't put a function in a header, this is just an example):

```cpp
// square.h
int getSquareSides()
{
    return 4;
}
```

```cpp
// wave.h
#include "square.h"
```

```cpp
// main.cpp
#include "square.h"
#include "wave.h"

int main()
{
    return 0;
}
```

Why doesn't this work?
1. main.cpp #includes square.h, which copies the definition for function getSquareSides into main.cpp
2. main.cpp #includes wave.h, which #includes square.h itself
- his copies contents of square.h (including the definition for function getSquareSides) into wave.h, which then gets copied into main.cpp

Ending file:

```cpp
// after preprocessing
int getSquareSides()  // from square.h
{
    return 4;
}

int getSquareSides() // from wave.h (via square.h)
{
    return 4;
}

int main()
{
    return 0;
}

```

The duplicate definitions cause a compile error. How do we resolve this issue?

##### Header guards

Header guard: conditional compilation directives
- aka: include guard

Header guards take the following form:

```cpp
#ifndef SOME_UNIQUE_NAME_HERE
#define SOME_UNIQUE_NAME_HERE

// your declarations (and certain types of definitions) here

#endif
```

How this works:
1. Preprocessor checks whether SOME_UNIQUE_NAME_HERE has been defined already
- if yes: it defines it 
- if no: ignores and moves on

Examples of header guards:

```cpp
// square.h
#ifndef SQUARE_H
#define SQUARE_H

int getSquareSides()
{
    return 4;
}

#endif
```

Even the standard library headers use header guards. If you were to take a look at the iostream header file from Visual Studio, you would see:

```cpp
// _IOSTREAM_
#ifndef _IOSTREAM_
#define _IOSTREAM_

// content here

#endif
```

Note for advanced readers:
-  it is possible to have two separate header files (from different directories) that end up having the same filename
    - e.g. directoryA\config.h and directoryB\config.h
    - if only the filename is used for the include guard (e.g. CONFIG_H), these two files may end up using the same guard name
        - if that happens, any file that includes (directly or indirectly) both config.h files will not receive the contents of the include file to be included second
            - result: compilation error.
- remedy: developers recommend a naming convention of PROJECT_PATH_FILE_H, FILE_LARGE-RANDOM-NUMBER_H, or FILE_CREATION-DATE_H

##### Updating our previous example with header guards

Let's update the example from before with header guards!

```cpp
// square.h
#ifndef SQUARE_H
#define SQUARE_H

int getSquareSides()
{
    return 4;
}
```

```cpp
// wave.h
#ifndef WAVE_H
#define WAVE_H

#include "square.h"
```

```cpp
// main.cpp
#include "square.h"
#include "wave.h"

int main()
{
    return 0;
}
```

Now, after preprocessing, we end up with this!

```cpp
// Square.h included from main.cpp
#ifndef SQUARE_H // square.h included from main.cpp
#define SQUARE_H // SQUARE_H gets defined here

// and all this content gets included
int getSquareSides()
{
    return 4;
}

#endif // SQUARE_H

#ifndef WAVE_H // wave.h included from main.cpp
#define WAVE_H
#ifndef SQUARE_H // square.h included from wave.h, SQUARE_H is already defined from above
#define SQUARE_H // so none of this content gets included

int getSquareSides()
{
    return 4;
}

#endif // SQUARE_H
#endif // WAVE_H

int main()
{
    return 0;
}
```

How does this evaluate:
1. preprocessor evaluates #ifndef SQUARE_H.
- SQUARE_H has not been defined yet, so the code from the #ifndef to the subsequent #endif is included for compilation.
    - this code defines SQUARE_H, and has the definition for the getSquareSides function

2. the next #ifndef SQUARE_H is evaluated
- because SQUARE_H got defined above, so the code from the #ifndef to the subsequent #endif is excluded

##### Header guards do not prevent a header from being included once into different code files

Note: the goal of header guards is to prevent a code file from receiving more than 1 copy of a guarded header
- by design: they do NOT prevent a header file from being included more than once in separate code files

This can cause unexpected problems, as seen below:

```cpp
// square.h
#ifndef SQUARE_H
#define SQUARE_H

int getSquareSides()
{
    return 4;
}

int getSquarePerimeter(int sideLength); // forward declaration for getSquarePerimeter

#endif
```

```cpp
// square.cpp
#include "square.h"  // square.h is included once here

int getSquarePerimeter(int sideLength)
{
    return sideLength * getSquareSides();
}
```

```cpp
// main.cpp
#include "square.h" // square.h is also included once here
#include <iostream>

int main()
{
    std::cout << "a square has " << getSquareSides() << " sides\n";
    std::cout << "a square of length 5 has perimeter length " << getSquarePerimeter(5) << '\n';

    return 0;
}

```

Notice: square.h is included from both main.cpp and square.cpp.
- the contents of square.h will be included once into square.cpp, once into main.cpp\

Let's examine in more detail:
1. when square.h is included in square.cpp, SQUARE_H is defined until end of square.cpp
- this define prevents square.h from being included into square.cpp a 2nd time
- however, once square.cpp is finished, SQUARE_H is no longer considered defined
2. 
- result: both square.cpp and main.cpp get a copy of getSquareSides
    - program compiles
    - linker complains/fails

Best workaround: Put the function definition in one of the .cpp files so that the header just has a forward declaration

```cpp
// square.h
#ifndef SQUARE_H
#define SQUARE_H

int getSquareSides(); // forward declaration for getSquareSides
int getSquarePerimeter(int sideLength); // forward declaration for getSquarePerimeter

#endif
```

```cpp
// square.cpp
#include "square.h"

int getSquareSides() // actual definition for getSquareSides
{
    return 4;
}

int getSquarePerimeter(int sideLength)
{
    return sideLength * getSquareSides();
}
```

```cpp
// main.cpp
#include "square.h" // square.h is also included once here
#include <iostream>

int main()
{
    std::cout << "a square has " << getSquareSides() << " sides\n";
    std::cout << "a square of length 5 has perimeter length " << getSquarePerimeter(5) << '\n';

    return 0;
}

```

##### Can’t we just avoid definitions in header files?

Generally told so far: Do not include function definitions in header files
- there are a few cases where it is necessary to put non-function definitions in a header file
    - example: C++ lets you create your own types, and these are usually defined in a header file (so that type definitions can be propogated to the code files that use them)
        - we need a header guard so that multiple identical copies do not end up in 1 code file

We don't necessarily NEED header guards yet, but we are practicing good habits!

##### #pragma once

Modern compilers support a simpler/alternative form of header guards: #pragma preprocessor directive

#pragma once: serves same purpose as header guards ie. avoid a header file from being included multiple times
- traditional header guards: developer is responsible for guarding the header by using #ifndef, #define, #endif
- with #pragma once: compiler guards the header

For advanced readers: The is 1 known case where #pragma once will fail
- if a header file is copied so that it exists in multiple places on the file system, #pragma once won't realize they are identical content 
    - header guards would successfully de-dupe the identical headers, though

For most projects: #pragma once works fine
- many developers prefer it
- some IDE's will auto-include #pragma once at the top of a new header file

Warning: the #pragma directive was designed for compiler implementers to use for whatever purposes they desire
- because of this: which pragmas are supported and what meaning those pragmas have is implementation-specific
- besides #pragma once, do not expect a pragma that works on 1 compiler to work on another!

Because #pragma once is not defined by the C++ standard, it is possible that some compilers may not implement it.
- For this reason, some development houses (such as Google) recommend traditional header guards.
- In this tutorial series, we will favor header guards.

##### Summary

Header guards: ensures that the contents of a header file are not copied more than once into any single file (to prevent duplicate definitions)
- duplicate declarations are fine
    - even if your header file is composed of all declarations (no definitions) it’s still a best practice to include header guards

Note: header guards do not prevent the contents of a header file from being copied (once) into separate project files. This is a good thing, because we often need to reference the contents of a given header from different project files.


#### 2.13 How to design your first programs

Most important thing to do: Design your program BEFORE you start coding
- programming = architecture
- "a little up-front planning will save you time/frustration in the long run"

##### Design step 1: Define your goal

Goal:
- 1-2 sentences
- useful to be a user-facing outcome

Examples:
- "allow the user to organize a list of names and associated phone numbers"
- "Generate a list of stock recommendations for stocks that have high dividends."

This steps seems obvious, but is highly important!

##### Design step 2: Define requirements

requirements: fancy word for constraints + capabilities
- focused on the "what", not the "how"

For example:
- Phone numbers should be saved, so they can be recalled later.
- The randomized dungeon should always contain a way to get from the entrance to an exit.
- The stock recommendations should leverage historical pricing data.
- The user should be able to enter the height of the tower.
- We need a testable version within 7 days.
- The program should produce results within 10 seconds of the user submitting their request.
- The program should crash in less than 0.1% of user sessions.

the solution is not until all requirements are fulfilled!

##### Design step 3: Define your tools, targets, and backup plan

When you are an experienced programmer, there are many other steps that typically would take place at this point, including:
- Defining what target architecture and/or OS your program will run on.
- Determining what set of tools you will be using.
- Determining whether you will write your program alone or as part of a team.
- Defining your testing/feedback/release strategy.
- Determining how you will back up your code.

However, as a new programmer, the answers to these questions are typically simple: You are writing a program for your own use, alone, on your own system, using an IDE you downloaded, and your code is probably not used by anybody but you. This makes things easy.

You should probably get a plan to backup your code, though!
- version control with github is your best option
    - Version control systems have the added advantage of not only being able to restore your files, but also to roll them back to a previous version.

Assuming that all of my data so far is in the following structure:
- root folder: cpp
    - subfolder: projects
        - hello
        - ...

    - subfolder: figures
        - ...

Create a repo on github.com, then run the following code in the command line:

```bash
cd learncpp

echo "# learncpp" >> README.md
  git init
  git add README.md
  git commit -m "first commit"
  git branch -M main
  git remote add origin https://github.com/MylesThomas/learncpp.git
  git push -u origin main

```

##### Design step 4: Break hard problems down into easy problems

Examples:
1. Clean the house:
- Vacuum the carpets
- Clean the bathrooms
    - Scrub the toilet (yuck!)
    - Wash the sink
- Clean the kitchen
    - Clear the countertops
    - Clean the countertops
    - Scrub the sink
    - Take out the trash

2. Go to work
- Initial list: 
    - Pick out clothes
    - Get dressed
    - Eat breakfast
    - Travel to work
    - Brush your teeth
    - Get out of bed
    - Prepare breakfast
    - Get on your bicycle
    - Take a shower

Note: Using the bottom up method, we can organize these into a hierarchy of items by looking for ways to group items with similarities together

Get from bed to work:
- Bedroom things
    - Turn off alarm
    - Get out of bed
    - Pick out clothes
- Bathroom things
    - Take a shower
    - Get dressed
    - Brush your teeth
- Breakfast things
    - Make coffee or tea
    - Eat cereal
- Transportation things
    - Get on your bicycle
    - Travel to work

Hierarchies are very useful in programming! (they can define the overall structure of your program)
- main: top level task ie. go to work
- function: next level task ie. make breakfast
    - can be split into sub-functions

##### Design step 5: Figure out the sequence of events

Example: Calculator
- Get first number from user
- Get mathematical operation from user
- Get second number from user
- Calculate result
- Print result 

##### Implementation Step 1: Outlining your main function

The above sequences / steps can be used to outline your program.

Here is an example (don't worry about inputs/outputs just yet!)

```cpp
int main()
{
    // Get first number from user
//    getUserInput();

    // Get mathematical operation from user
//    getMathematicalOperation();

    // Get second number from user
//    getUserInput();

    // Calculate result
//    calculateResult();

    // Print result
//    printResult();

    return 0;
}

```

Note: We comment out the functions because they have not been implemented yet

##### Implementation step 2: Implement each function

For each function, do the following:
1. define the function prototype ie. inputs/outputs
2. write the function
3. test the function

If your functions are granular enough, each should be simple/straightforward
- if not: break it down further!

Example: First function for calculator

```bash
cd projects
mkdir calculator
cd calculator
echo > main.cpp

```

```cpp
// main.cpp
#include <iostream>

// Full implementation of the getUserInput function
int getUserInput()
{
    std::cout << "Enter an integer: ";
    int input{};
    std::cin >> input;

    return input;
}

int main()
{
    // Get first number from user
    int value{ getUserInput() }; // Note we've included code here to test the return value!
    std::cout << value << '\n'; // debug code to ensure getUserInput() is working, we'll remove this later

    // Get mathematical operation from user
//    getMathematicalOperation();

    // Get second number from user
//    getUserInput();

    // Calculate result
//    calculateResult();

    // Print result
//    printResult();

    return 0;
}

```

Let's run this program to see if we get the expected output! (Trying different values is good pressure testing, too)

```bash
g++ -g -o my_executable -I/source/includes main.cpp -pedantic-errors -Werror -std=c++17
my_executable.exe

```

Remember: Don’t implement your entire program in one go
- work in steps
- test each step along the way 

##### Implementation step 3: Final testing

Once your program is “finished”, the last step is to test the whole program and ensure it works as intended.
- If it doesn’t work, fix it.

##### Words of advice when writing programs

KISS = Keep It Simple, Stupid!

Words of advice:
- keep your programs simple to start
    - good: I want to be able to display a 2-dimensional field on the screen
    - bad: I want to write a role-playing game with graphics and sound and random monsters and dungeons, with a town you can visit to sell the items that you find in the dungeon
- add features over time
- focus on one area at a time
- test each piece of code as you go
- don't invest in perfecting early code
    - first draft = rarely is good
- optimize for maintainability, not performance
    - "premature optimization is the root of all evil"

Ending quote: "A complex system that works is invariably found to have evolved from a simple system that worked" -John Gall

##### Conclusion

Many new programmers shortcut the design process (because it seems like a lot of work and/or it’s not as much fun as writing the code). However, for any non-trivial project, following these steps will save you a lot of time in the long run.
- A little planning up front saves a lot of debugging at the end.

Key insight: Spending a little time up front thinking about how to structure your program will lead to better code and less time spent finding and fixing errors.
- "I would say this is arguably the most important thing in programming and some of us, like me at first, took it for granted."


As you become more comfortable with these concepts and tips, they will start coming more naturally to you. Eventually you will get to the point where you can write entire functions (and short programs) with minimal pre-planning.


#### 2.x Chapter 2 summary and quiz

...

### Chapter 3: Debugging C++ Programs

#### 3.1 Syntax and semantic errors

#### 3.2 The debugging process

#### 3.3 A strategy for debugging

#### 3.4 Basic debugging tactics

#### 3.5 More debugging tactics

#### 3.6 Using an integrated debugger: Stepping

#### 3.7 Using an integrated debugger: Running and breakpoints

#### 3.8 Using an integrated debugger: Watching variables

#### 3.9 Using an integrated debugger: The call stack

#### 3.10 Finding issues before they become problems

#### 3.x Chapter 3 summary and quiz

#### 3.

#### 3.

#### 3.

#### 3.

#### 3.

#### 3.

#### 3.

#### 3.

#### 3.

### Chapter 4: Fundamental Data Types

#### 

### Chapter 5: Constants and Strings

#### 

### Chapter 6: Operators

#### 

### Chapter O: Bit Manipulation (optional chapter)

#### 

### Chapter 7: Scope, Duration, and Linkage

#### 

### Chapter 8: Control Flow and Error Handling

#### 

### Chapter 9: (Reserved for future splitting of chapter 8)

#### 

### Chapter 10: Type conversion and Function Overloading

#### 

### Chapter 11: (Reserved for future splitting of chapter 10)

#### 

### Chapter 12: Compound Types: References and Pointers

#### 

### Chapter 13: Compound Types: Enums and Structs

#### 

### Chapter 14: Introduction to Classes

#### 

### Chapter 15: More on Classes

#### 

### Chapter 16: Dynamic arrays: std::vector

#### 

### Chapter 17: Fixed-size arrays: std::array and C-style arrays

#### 

### Chapter 18: Iterators and Algorithms (under construction)

#### 

### Chapter 19: Dynamic Allocation (under construction)

#### 

### Chapter 20: Functions

#### 

### Chapter 21: Operator Overloading

#### 

### Chapter 22: Move Semantics and Smart Pointers

#### 

### Chapter 23: Object Relationships

#### 

### Chapter 24: Inheritance

#### 

### Chapter 25: Virtual Functions

#### 

### Chapter 26: Templates and Classes

#### 

### Chapter 27: Exceptions

#### 

### Chapter 28: Input and Output (I/O)

#### 

### Appendix A: Miscellaneous Subjects

#### A.1 Static and dynamic libraries

#### A.1 Using libraries with Visual Studio

#### A.1 Using libraries with Code::blocks

#### A.4 C++ FAQ

### Appendix B: C++ Updates

#### B.1 Introduction to C++11

#### B.2 Introduction to C++14

#### B.3 Introduction to C++17

#### B.4 Introduction to C++20

### Appendix C: The End

#### The end?

### Appendix D: Deprecated Articles (will be removed soon)