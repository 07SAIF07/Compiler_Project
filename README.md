Compiler Project  

This project is a mini compiler implementation for a simple programming language defined by a given grammar. The compiler is divided into three main components: lexical analysis, syntactic analysis, and semantic analysis with code generation. The project is written in C and includes a test suite to validate the functionality of each component.

Project Structure
The project consists of the following files:

lexer.h and lexer.c:

These files implement the lexical analyzer (lexer), which reads the source code and breaks it into tokens (lexical units). The lexer recognizes keywords, identifiers, numbers, operators, and punctuation.

parser.h and parser.c:

These files implement the syntactic analyzer (parser), which checks if the sequence of tokens follows the grammar rules. The parser uses a recursive descent approach to parse the input.

semantic.h and semantic.c:

These files implement the semantic analyzer, which performs type checking and generates intermediate code for an abstract stack machine.

test.c:

This file contains test cases for the lexer, parser, and semantic analyzer. It ensures that each component works correctly by comparing the output with expected results.

main.c:

This is the entry point of the program. It reads a source file, performs lexical, syntactic, and semantic analysis, and reports any errors.

How It Works :
1. Lexical Analysis
The lexer reads the source code character by character and groups them into tokens. Each token has a type (e.g., keyword, identifier, number) and a lexeme (the actual string representing the token).

Supported Tokens:

Keywords: program, var, int, begin, end, writeln, readln, if, then, endif.

Identifiers: A letter followed by letters or digits (e.g., x, y1).

Numbers: Unsigned integers (e.g., 10, 123).

Operators: Arithmetic (+, *) and relational (==, <>, <, <=, >, >=).

Punctuation: ;, :, ,, ., (, ).

Example Input:

program test; var x, y: int; begin x := 10; end.

Output Tokens:

TOKEN_PROGRAM, TOKEN_ID (test), TOKEN_SEMICOLON, TOKEN_VAR, TOKEN_ID (x), TOKEN_COMMA, TOKEN_ID (y), TOKEN_COLON, TOKEN_INT, TOKEN_SEMICOLON, TOKEN_BEGIN, TOKEN_ID (x), TOKEN_ASSIGN, TOKEN_NB (10), TOKEN_SEMICOLON, TOKEN_END, TOKEN_DOT.

2. Syntactic Analysis
The parser checks if the sequence of tokens follows the grammar rules. It uses a recursive descent approach, where each non-terminal in the grammar is represented by a function.

Grammar Rules:

The grammar defines a simple programming language with declarations, assignments, and control structures (e.g., if statements).

Example Input:

program test; var x, y: int; begin x := 10; end.

Output:

The parser ensures that the input follows the grammar rules. If it does, the program is syntactically correct. Otherwise, it reports a syntax error.

3. Semantic Analysis
The semantic analyzer performs type checking and generates intermediate code for an abstract stack machine.

Type Checking:

Ensures that expressions are type-consistent (e.g., no adding a string to an integer).

Checks that variables are declared before use.

Intermediate Code Generation:

Generates code for an abstract stack machine. For example, the expression x + 5 might generate the following intermediate code:

push x
push 5
add

How to Run the Project :

1. Compile the Project
To compile the project, use the following command:

gcc lexer.c parser.c semantic.c main.c -o compiler

2. Run the Compiler
To run the compiler on a source file, use the following command:


./compiler <source_file>

For example:

./compiler test_input.txt

3. Run the Tests
To run the test suite, compile and run the test.c file:

gcc lexer.c parser.c semantic.c test.c -o test
./test

Example Input and Output
Input File (test_input.txt):

program test; var x, y: int; begin x := 10; y := x + 5; end.
Output:

Parsing completed successfully.

Key Features:

Lexical Analysis:

Recognizes keywords, identifiers, numbers, operators, and punctuation.

Skips whitespace and comments.

Syntactic Analysis:

Uses a recursive descent parser to validate the syntax of the input program.

Reports syntax errors with detailed messages.

Semantic Analysis:

Performs type checking and ensures variables are declared before use.

Generates intermediate code for an abstract stack machine.

Test Suite:

Includes test cases for the lexer, parser, and semantic analyzer.

Ensures that each component works correctly.

Future Improvements :
Error Recovery:

Implement error recovery in the parser to continue parsing after encountering an error.

Code Optimization:

Add optimizations to the intermediate code generation phase.

Support for More Features:

Extend the language to support more features, such as loops, functions, and arrays.

Conclusion :

This project provides a basic implementation of a compiler for a simple programming language. It covers the key phases of compilation: lexical analysis, syntactic analysis, and semantic analysis. The project is a great starting point for understanding how compilers work and can be extended to support more advanced features.
