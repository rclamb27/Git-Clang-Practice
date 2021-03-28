# CPSC 121
## Quadratic Formula
In this exercise write a program that takes the coefficients from one side of the equal sign and the solution from the other side of the equal sign to solve a quadratic equation. 

Students are encouraged to read the Wikipedia articles on [the quadratic formula](https://en.wikipedia.org/wiki/Quadratic_formula) which reviews the definition of a quadratic equation and how to solve it for its zero or more roots using the quadratic formula.

## Review
Remember that a quadratic equation is written in the form:
![ax^2 + bx + c = d](https://render.githubusercontent.com/render/math?math=ax%5E2%20%2B%20bx%20%2B%20c%20%3D%20d&mode=inline)

The coefficients of the equation are a, b, and c. The value or expression on the right hand side of the equal sign is the solution to the equation given an appropriate value for x. Let's call the solution to the equation d. In many textbooks and examples, d is always 0 (zero) yet it does not have to be.

The quadratic formula is:
![x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}](https://render.githubusercontent.com/render/math?math=x%20%3D%20%5Cfrac%7B-b%20%5Cpm%20%5Csqrt%7Bb%5E2%20-%204ac%7D%7D%7B2a%7D&mode=inline)

If the solution, d, is non-zero, subtract it from both sides of the equal sign which will leave one side as zero and the other side with (c-d). We can rewrite the quadratic formula replacing c with (c-d).

![x = \frac{-b \pm \sqrt{b^2 - 4a(c-d)}}{2a}](https://render.githubusercontent.com/render/math?math=x%20%3D%20%5Cfrac%7B-b%20%5Cpm%20%5Csqrt%7Bb%5E2%20-%204a%28c-d%29%7D%7D%7B2a%7D&mode=inline)

Using this re-written equation you may use the quadratic formula to find the roots for the equation. The roots are the values of x that are true/valid for the equation.

Please remember that there can be zero, one, or at most two solutions to every quadratic equation. 

## Program requirements
Your program must be named `quadsolver`. It will understand the following positional command line arguments:
1. The coefficient a
1. The coefficient b
1. The coefficient c
1. The coefficient d

Convert each command line argument to a float type for use in the program.

Furthermore, you are required to have at least one function in the program that calculates the roots of the given quadratic equation. The name of the function must be `QuadraticFormula`. The function must return an int type and take as parameters the coefficient a, b, c, and d by value and return by reference the roots of the equation. Use float pointer types for the roots.

```
int quadratic_formula(float a, float b, float c, float d, float* root_one, float* root_two);
```

The return value of the function is how many roots exist for the given equation. The returned value may be 0, 1, or 2 given the calculation of the quadratic formula for zero roots, one root, or two roots.

The roots are returned as references back to the caller by reference as `root_one` and `root_two`.


Your program shall be in one file named quadsolver.cpp. The name of the program shall be `quadsolver`. The included `Makefile` includes the targets:
* all: builds the project
* clean: removes object and dependency files
* spotless: removes everything the clean target removes and all binaries
* format: outputs a [`diff`](https://en.wikipedia.org/wiki/Diff) showing where your formatting differes from the [Google C++ style guide](https://google.github.io/styleguide/cppguide.html)
* tidy: output of the linter to give you tips on how to improve your code

To build your program, use the command `make` or `make all`. 

# Output
To earn full credit, your submission must match the format of the example output. In other words, aside from the portions of user input, your program ought to prompt and output exactly as the example given.

```
$ make all
$ quadsolver 6 11 -35 0
There are 2 solutions to 6x^2 + 11 - 35 = 0.
They are:
x = 1.66
x = -3.50
$ quadsolver 9 12 0 -4
There are 1 solutions to 9x^2 + 12 + 0 = -4.
They are:
x = -0.66
```

Your calculations may be off by 0.01 given that you are using floating point math.

## Submission
Use git to commit and push your changes back to your repository on GitHub. Remember that you are evaluated on the quality of your git log messages; please do not ignore them.
