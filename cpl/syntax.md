# Concepts of Programming Languages

# Syntax and Semantics

## Introduction
- Syntax: the form or structure of the expressions, statements, and program units
- Semantics: the meaning of the expressions, statements, and programming units
- Syntax and semantics provide a language's definition
  - Users of a language definition


#### Syntax
- Syntax is the order or arrangement of words and phrases to form proper sentences.

#### Semantics
- A "sentence" is a group of words that express a specific thought: to capture it, we need to understand how words relate to other words. 

#### Syntax vs Semantics
- Syntax is the study of sentence structure and the rules of grammar.
- It also, helps common users of a language understand how to organize words so that they make the most sense.
- Semantics, on the other hand, is the study of the meaning of sentences.


## BNF and Context-Free Grammars
- Context-Free Grammars
  - Developed by Noam Chomsky in the mid-1950s.
  - Language generators, meant to describe the syntax of natural languages.
  - Define a class of languages called context-free languages.
- Backus-Naur Form (1959)
  - Invented by John Backus to describe the syntax of Algol 58.
  - In BNF, abstractions are used to represent classes of syntactic structures, They act like syntactic variables. 
  - A rule has a left-hand side and a right hand side.

### BNF Fundamentals
- Non-terminals are often enclosed in angle brackets.
- Grammar: a finite non-empty set of rules.
- A start symbol is a special element of the non-terminals of a grammar. 

#### BNF Rules 
- An abstraction can have more than one right hand side. 


#### Example 1 
- Java if-then else grammar
```
<if_stmt> -> if(<logic_expr>) <stmt> 
          | if(<logic_expr>) <stmt> else <stmt>
```


