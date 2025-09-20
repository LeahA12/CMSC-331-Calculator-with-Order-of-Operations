## AUTHORING: 
* Leah Arfa
* UMBC, CMSC 331 (Programming Principles), Fall 2024
* October 20, 2024

## PURPOSE OF SOFTWARE: 
Lex and Yacc Program of a command-line calculator that processes infix mathematical expressions. The calculator accurately handles operator precedence and variable assignments.

## FILES: 
* ```calc.l```: The Lex source file that defines the lexical rules for the calculator. It recognizes tokens such as numbers, names for variables, and operators, passing them to the parser.
* ```calc.y```: The Yacc source file that defines the grammar rules and operator precedence and associativity for the calculator (ensures expressions like ```2 + 3 * 4``` is evaluated as ```2 + (3 * 4)```). It constructs the AST (abstract syntax tree) and handles the logic for mathematical operations and variable assignments.
* ```Makefile```: The build script file that automates the compilation process using the ```lex``` and ```yacc``` tools, linking the generated C files to produce the executable.
* ```correctInputAndOutputEx.txt```: The text file that contains example inputs prefaced by ```>>``` and their corresponding outputs, demonstrating the correct behavior of the calculator.

## BUILD/TESTING INSTRUCTIONS: 
1. **Compilation:** Use the provided ```Makefile``` to compile the program by typing:
    ```
    make
    ```
2. **Execution:** Run the generated executable from the terminal using the command:
    ```
    ./calc
    ```
3. **Output Verification:** The program will start with a prompt ``>>``. You can type in an expression and press enter to see the result. The output should match the examples provided in ```correctInputAndOutputEx.txt```.

## ADDITIONAL INFORMATION:
* The calculator utilizes a symbol table to handle variable assignments. When a variable name is encountered, the symbol table stores its corresponding value, allowing the program to recall and use it in subsequent calculations.
    Ex:
    ```
    >> x = 5 
    >> x + 2
    7
    ```
* The ```yyerror()``` function is implemented to provide basic error handling. If a syntax error is detected in the input, the program prints an error message to the console.
