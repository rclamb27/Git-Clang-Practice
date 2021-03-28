# CPSC 121
## Command Line Arguments

The objective of this exercise is to remember or learn how to read command line arguments in a C++ program using `int argc` and `char* argv[]` parameters of the main function.

This is a trivial exercise to explore how these two variables work in conjunction with one another.

The `main( )` function is the entry point into our C++ program. By convention, this is where our program starts. Name your function `main` and the compiler makes it the entry point.

Additionally, by convention, there are at least two parameters to the `main( )` function. The first is `int argc`. The variable `argc` tells the program how many arguments were passed to it when it was executed by the command shell. In our case, the command shell is the BASH shell you are using and you can specify as many arguments as your BASH shell supports. The program name is always counted as an argument and the count starts from zero.

The second variable is `char* argv[]`. This variable is an array of `char` pointers or in otherwords a list of C-strings. The zeroth location of this array is the name of the program and each subsequent element in the array is the following command line argument.

For example, let's image I have a program named `foo`. The program `foo` prints out `I am foo`. To execute or run `foo`, I type `foo` on the BASH command line.
```
bash$ foo
I am foo
bash$
```

If additional arguments are present, then let's imagine `foo` prints them out one line at a time. For example
```
bash$ foo 1 cat dog 4 "ice cream"
I am foo
1
cat
dog
4
ice cream
```

In the example given, `argc` is equal to 6 and `argv` can be visualized as:
```
argv[0] == "foo"
argv[1] == "1"
argv[2] == "cat"
argv[3] == "dog"
argv[4] == "4"
argv[5] == "ice cream"
```
Note that the values are C-strings regardless of if they represent a string or a numerical value.

Write a program that prints out the value of `argc` and then iterates through `argv` printing out each value.

Your program shall be in one file named argdemo.cpp. The name of the program shall be `argdemo`. The included `Makefile` includes the targets:
* all: builds the project
* clean: removes object and dependency files
* spotless: removes everything the clean target removes and all binaries
* format: outputs a [`diff`](https://en.wikipedia.org/wiki/Diff) showing where your formatting differes from the [Google C++ style guide](https://google.github.io/styleguide/cppguide.html)
* tidy: output of the linter to give you tips on how to improve your code

To build your program, use the command `make` or `make all`. 

## Example Output
To earn full credit, your submission must match the format of the example output. In other words, aside from the portions of user input, your program ought to prompt and output exactly as the example given.

```
$ make all
$ ./argdemo 
Argc is 1
argv[0] == "./argdemo"
$ ./argdemo sadf 
Argc is 2
argv[0] == "./argdemo"
argv[1] == "sadf"
$ ./argdemo 1 2 3 4
Argc is 5
argv[0] == "./argdemo"
argv[1] == "1"
argv[2] == "2"
argv[3] == "3"
argv[4] == "4"
$ ./argdemo a b c d
Argc is 5
argv[0] == "./argdemo"
argv[1] == "a"
argv[2] == "b"
argv[3] == "c"
argv[4] == "d"
$ ./argdemo cat 1 dog "lemon custard"
Argc is 5
argv[0] == "./argdemo"
argv[1] == "cat"
argv[2] == "1"
argv[3] == "dog"
argv[4] == "lemon custard"
```

## Submission
Use git to commit and push your changes back to your repository on GitHub. Remember that you are evaluated on the quality of your git log messages; please do not ignore them.
