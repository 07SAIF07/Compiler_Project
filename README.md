# 📘 Compiler_Project

This project is a mini compiler implementation for a simple programming language defined by a given grammar. The compiler is divided into three main components: **lexical analysis**, **syntactic analysis**, and **semantic analysis with code generation**. The project is written in **C** and includes a **test suite** to validate the functionality of each component.

---

## 📂 Project Structure

The project consists of the following files:

### `lexer.h` and `lexer.c`
These files implement the **lexical analyzer (lexer)**, which reads the source code and breaks it into tokens (lexical units). The lexer recognizes:
- Keywords
- Identifiers
- Numbers
- Operators
- Punctuation

### `parser.h` and `parser.c`
These files implement the **syntactic analyzer (parser)**, which checks if the sequence of tokens follows the grammar rules using a **recursive descent** approach.

### `semantic.h` and `semantic.c`
These files implement the **semantic analyzer**, which performs **type checking** and generates **intermediate code** for an abstract stack machine.

### `test.c`
Contains **test cases** for the lexer, parser, and semantic analyzer to ensure each component functions correctly.

### `main.c`
The **entry point** of the program. It reads a source file, performs lexical, syntactic, and semantic analysis, and reports errors.

---

## ⚙️ How It Works

### 1. Lexical Analysis
The lexer reads the source code character by character and groups them into tokens.

#### Supported Tokens:
- **Keywords**: `program`, `var`, `int`, `begin`, `end`, `writeln`, `readln`, `if`, `then`, `endif`
- **Identifiers**: e.g., `x`, `y1`
- **Numbers**: e.g., `10`, `123`
- **Operators**: `+`, `*`, `==`, `<>`, `<`, `<=`, `>`, `>=`
- **Punctuation**: `;`, `:`, `,`, `.`, `(`, `)`

#### Example Input:
```pascal
program test; var x, y: int; begin x := 10; end.
