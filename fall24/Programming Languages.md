---
id: Programming Languages
aliases: []
tags: []
Class: CSCI 3600
Created: 2024-09-02T13:02
---
## Evolution of Procedural Programming Languages

- First generation: Machine Languages
- Second generation: Assembly Languages
- **Third generation**: High-Level Languages

  

### Five (Pre-1965) High-Level Languages

- Fortran (1957) - John Backus (Computer Scientist)
    - Formula Translator
- Algol60 (1960)
- COBOL (1960)
- Basic (1964)
- PL/I (1964)

  

### Definitions

- **Syntax** - form
- **Semantics** - meaning

  

### **BNF**

_Backus-Naur Form_

> [!important]  
> BNF is widely used for specifying the syntax of programming languages and is particularly useful for describing context-free grammars.  

- **N** - Non-terminal symbols
    - placeholders (like variables)
- **T** - Terminal symbols
    - lexemes and tokens
- **S** - start symbol
- **P** - production rules

 **Type Coercion** - when the operands of an operator are different types, one of them will be converted to an "equivalent" value of the other operand's type. 
    ex:
        ```language
            boolean = false
            integer = 1
            boolean = integer
            # >> boolean = true
        ```
    This uses type conversion


### General Problem of Describing Syntax

- ==**Lexeme**== - the smallest syntactic unit of a program
    - Example: int x = 5; // This entire statement is a lexeme, while 'int', 'x', '=', '5', and ';' are individual lexemes
- ==**Token**== - the category of a _==lexeme==_
    - Example: In the statement 'int x = 5;', 'int' is a keyword token, 'x' is an identifier token, '=' is an operator token, '5' is a literal token, and ';' is a punctuation token

|_Lexemes_|_Tokens_|
|---|---|
|index|identifier|
|=|equal_sign|
|2|int_literal|
|*|mult_op|
|count|identifier|
|+|plus_op|
|17|int_literal|
|;|semicolon|

- **Language Recognizers vs. Language Generators**

  

### Formal Methods of Describing Syntax 1/3

- Development



















