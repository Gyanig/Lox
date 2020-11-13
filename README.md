<<<<<<< HEAD
# Lox
Interpreter to complete
=======
# Learning to implement my C/C++ knowledge 

### building an interpreter

- application scripting languages, 
- template engines, 
- markup formats, and 
- configuration files

like Make,XSLT,Inform, YAML,ANTLR,CFML,SWIG, IDL,EMacs Lisp, Jinja, cpp, INI, JSON, Vim script,lex,Sed,Bash,yacc,Mustache,AWK,CSS,HTML,Scsh,XML,Batch,SQL,Tcl,bison, Guile, XAML

Topics:
- Recursion
- Dynamic Arrays,
- Trees
- Graphs
- Hash tables

### Dragon Book- Compilers Principles, Techniques & com.company.Lox.tools
### Wizard Book - Structure and interpretation of Computer Programs
- https://mitpress.mit.edu/sites/default/files/sicp/index.html

### LOX
- Other com.company.Lox.tools - Lex, Yacc

- Yacc is a tool that takes in a grammar file and produces a source file for a compiler, so it’s sort of like a “compiler” that outputs a compiler, which is where we get the term “compiler-compiler”.
Yacc wasn’t the first of its ilk, which is why it’s named “Yacc”—Yet Another Compiler-Compiler. A later similar tool is Bison, named as a pun on the pronunciation of Yacc like “yak”.

### jlox - a java interpreter
- A compiler reads in files in one language and translates them to files in another language. You can implement a compiler in any language, including the same language it compiles, a process called “self-hosting" else you go for a "Bootstrapping" process which leads from one to another language accordingly compiling. 

## Name of the interperter : parz 
- Language implementations C: Lua,CPython, Ruby's MRI(Matz’ Ruby Interpreter)

Source code -> scanning -> tokens -> parsing -> syntax tree -> analysis -> optimizing 
optimizing -> Transpiling -> High level language
optimizing -> bytecode 
optimizing -> machine code


### First Step : Scanning (aka Lexing / Lexical Analysis)

- Scanner/lexer 
    - takes in a linear stream of characters and chucks them together into a series of something more akin to words. 
- these words are called tokens in programming languages 


### Parsing 
- This is where our syntax gets the *grammer*
  - the ability to compise larger expression and statement out of smaller parts  
  - A parser takes the flat sequence if the tokens and builds a tree structure that mirror ths nested nature of the grammer 
      - these tree have a couple if differen names : parse tree and abstract syntax trees : dependin on how ckise the bare syntatic structure of the source of the language they are. 
              - laguage hackers call them Syntax trees / AST / trees
    - A parser also shows syntax errors
  
  - Static analysis :
    - starting starts with binding / resolution 
        - for each identifers we find our where that name is defined and wire the two together
        - scope is important as we have to knwonthe region of the source code where a certain name can be used to refer to a certain declaration
        - if language is statically typed, we type check during declaration  

    - few things i know:
      - attributes, literals , symbol table(refers to the ASCII mapping or the utf-08 )
      - i have to learn how to implement few tree structures, 

    - Three stages of the compiler: 
          - front end
          - backend
          - middle end - optimizer level 
                  - inline, dead code, constant loop, auto 
                  - https://en.wikipedia.org/wiki/Compiler#Middle_end

    - IR : intermediate representations : interface between two languages 
    (middle-end) 
        - control flow graph”, 
        - “static single-assignment”, - compiler designs 
          - https://en.wikipedia.org/wiki/Static_single_assignment_form
        - “continuation-passing style” - functional programming
            - https://en.wikipedia.org/wiki/Continuation-passing_style 
        - “three-address code”
          - geeksforgeeks.org/three-address-code-compiler/
    - GIMPLE- three address code from GENERIC 
          - https://gcc.gnu.org/onlinedocs/gccint/GIMPLE.html
    - GENERIC - The purpose of GENERIC is simply to provide a language-independent\
     way of representing an entire function in trees.
    - GCC - compiler
    - single complier design in the future. 
    - RTL- register level language 
    - Optimizing :
        - constant propagation”, “common subexpression elimination”, “loop invariant code motion”, “global value numbering”, “strength reduction”, “scalar replacement of aggregates”, “dead code elimination”, and “loop unrolling”

- Code generation - last step
    - We have a decision to make. Do we generate instructions for a real CPU or a virtual one? If we generate real machine code, we get an executable that the OS can load directly onto the chip. Native code is lightning fast, but generating it is a lot of work. Today’s architectures have piles of instructions, complex pipelines, and enough historical baggage to fill a 747

- Understand Runtime/ VM : OS notes go through 
- Extra thinking : 
    - Single-pass compliers 
    - Tree-Walk interpreters 
    - Web Assembly
    - just in time compilation
-http://www.craftinginterpreters.com/image/a-map-of-the-territory/venn.png

CHALLENGES
- Pick an open source implementation of a language you like. Download the source code and poke around in it. Try to find the code that implements the scanner and parser. Are they hand-written, or generated using com.company.Lox.tools like Lex and Yacc? (.l or .y files usually imply the latter.)
      - https://github.com/grpc/grpc
      - https://github.com/emscripten-core/emscripten

- Just-in-time compilation tends to be the fastest way to implement a dynamically-typed language, but not all of them use it. What reasons are there to not JIT?
  - Adding compilation time with excution time is a headache

- Most Lisp implementations that compile to C also contain an interpreter that lets them execute Lisp code on the fly as well. Why?
  - idk will look into.

## LOX
- few things to be included
  - Dynamic typing (easier)
      - static type system is a ton of work to learn and implement(difficult)
  - Automatic memory collection
        - reference counting (easier)
        - tracing garbage collection
  - Data types
        - booleans
        - numbers
        - strings
        - nil/null
  - Expressions
        - arithmetic
          - polish notations
          - mixfix
          - conditional/tertiary
        - comparisions and equality
        - logical operators 
        - precedence and grouping 
  - Statements
        - blocks
  - Variables 
  - Control flow
  - Functions
      - arguements and parameters 
      - closures - nesting 
  - Classes
    - objects/prototypes ~ INHERITANCE 
  - build my own library functions 

- Indian twist - hinglish library fucntions
    - CLASS TYPE :
     - instances and classes 
    - Prototype TYPE :
     - state and methods 


### CHALLENGES
Q. Write some sample Lox programs and run them (you can use the implementations of Lox in my repository). Try to come up with edge case behavior I didn’t specify here. Does it do what you expect? Why or why not?
- done
This informal introduction leaves a lot unspecified. List several open questions you have about the language’s syntax and semantics. What do you think the answers should be?

Lox is a pretty tiny language. What features do you think it is missing that would make it annoying to use for real programs? (Aside from the standard library, of course.)

interpreter - parz_hinglish

Scanning section
cmd run issues :
( Exit code is based on this : https://www.freebsd.org/cgi/man.cgi?query=sysexits&apropos=0&sektion=0&manpath=FreeBSD+4.3-RELEASE&format=html )
  - 0 when execution went fine;
  1, -1, whatever != 0 when some error occurred, you can use different values for different kind of errors.
  - If I'm correct exit codes used to be just positive numbers (I mean in UNIX) and according to range:
    - 1-127 are user defined codes (so generated by calling exit(n))
    - 128-255 are codes generated by termination due to different unix signals like SIGSEGV or SIGTERM

REPL- interactive prompt :  Read a line of input, Evaluate it, Print the result, then Loop and do it all over again.

### CHALLENGES
- The lexical grammars of Python and Haskell are not regular. 
    What does that mean, and why aren’t they?
    - lexical grammer is subject : Theory of computation : Grammers : basic syntax format of possiblity
        basically they use called indent tokens and lexer part is more powerful than the parser
        
- Aside from separating tokens—distinguishing print foo from print 
    foo—spaces aren’t used for much in most languages. 
    However, in a couple of dark corners, a space does affect 
    how code is parsed in CoffeeScript, Ruby, and the C preprocessor. 
    Where and what effect does it have in each of those languages?
    - no idea coz, coffeescript is written like JS and its parser uses Whitespace for so many purposes
    - Ruby, havent explored, maybe after completing the course i will do one from the projet list on ruby
    - In C preprocessor - whitespace is not considered by the parser, it might have role of assigning reasons
      
       
- Our scanner here, like most, discards comments and whitespace since 
those aren’t needed by the parser. Why might you want to write a scanner 
that does not discard those? What would it be useful for?
    - maybe keep things case-sensitive. in case of command line arguements, it is useful
    - markup languages
    - i would agree of discarding comments coz it helps the programmer to imply the process to a fellow programmer
        as well understand his own cod
        
- Add support to Lox’s scanner for C-style /* ... */ block comments.
 Make sure to handle newlines in them. Consider allowing them to nest. 
 Is adding support for nesting more work than you expected? Why?
 - i did not understand where to make changes for the simplest way to work. i left it like this and moved forward
 
 ## Representing Code 
 
 - How to evaluate the expressions like using Syntax trees 
    - Using Syntax Tree : 
        - expression representation 
        - traversal techniques : post-order
         
 - Context free Grammer : toolbox for formal grammer 
 - Rules for Grammer :
    - derivations : string
    - productions : rules
        - we use productions to create strings or infact derivations
    - letter from the grammar’s alphabet : terminals 
        - vs non-terminals
    - from the breakfast examples 
    - using simple tokens and extending ther meaning of it 
    
    metaSyntax
    - protein "with" breakfast "on the side"
       - breakfast  → protein ;
       - breakfast  → bread ;         
       - protein    → crispiness "crispy" "bacon" ;
       - protein    → "sausage" ;
       - protein    → cooked "eggs" ;
       - crispiness → "really" ;
       - crispiness → "really" crispiness ;
       - cooked     → "scrambled" ;
       - cooked     → "poached" ;
       - cooked     → "fried" ;
       - bread      → "toast" ;
       - bread      → "biscuits" ;
       - bread      → "English muffin" ;
    - expression tree grammer
        - expression     → literal
                        | unary
                        | binary
                        | grouping ;
        - literal        → NUMBER | STRING | "true" | "false" | "nil" ;
        - grouping       → "(" expression ")" ;
        - unary          → ( "-" | "!" ) expression ;
        - binary         → expression operator expression ;
        - operator       → "==" | "!=" | "<" | "<=" | ">" | ">="
                        | "+"  | "-"  | "*" | "/" ;   
 ### implementing Syntax Tree    
   - In particular, we’re defining an abstract syntax tree (AST). 
        In a parse tree, every single grammar production becomes a node 
        in the tree. An AST elides productions that aren’t needed by later 
        phases.
   - Expression problem :  interpret(), resolve() , analyze()
   - pattern matching for functions 
   - problem statement :A bunch of smart language nerds noticed that neither 
        style made it easy to add both rows and columns to the table. They called 
        this difficulty the “expression problem” because—like we are now—they first 
        ran into it when they were trying to figure out the 
        best way to model expression syntax tree nodes in a compiler.
        Languages with multimethods, like Common Lisp’s CLOS, Dylan, and Julia do
        support adding both new types and operations easily. What they typically
        sacrifice is either static type checking, or separate compilation.
        People have thrown all sorts of language features,
        design patterns and programming tricks to try to knock 
        that problem down but no perfect language has finished 
        it off yet. In the meantime, the best we can do is try 
        to pick a language whose orientation matches the 
        natural architectural seams in the program we’re writing.  
        
   - Study about Visitor pattern     
   - some bugs are there with the Ast printer class 
   
   ## Challenges
   1.  Earlier, I said that the |, *, and + forms we added to our grammar 
       metasyntax were just syntactic sugar. Given this grammar:
       expr → expr ( "(" ( expr ( "," expr )* )? ")" | "." IDENTIFIER )+
            | IDENTIFIER
            | NUMBER
       Produce a grammar that matches the same language but does not use any of 
       that notational sugar.
       Bonus: What kind of expression does this bit of grammar encode?
   -   
   
   2.  The Visitor pattern lets you emulate the functional style in an object-
       oriented language. Devise a complementary pattern for a functional language. 
       It should let you bundle all of the operations on one type together and let 
       you define new types easily.
       
       (SML or Haskell would be ideal for this exercise, but Scheme or another 
       Lisp works as well.)
   
   3.  In Reverse Polish Notation (RPN), the operands to an arithmetic 
       operator are both placed before the operator, so 1 + 2 becomes 1 2 +. 
       Evaluation proceeds from left to right. Numbers are pushed onto an 
       implicit stack. An arithmetic operator pops the top two numbers, 
       performs the operation, and pushes the result. Thus, this:
       
       (1 + 2) * (4 - 3)
       in RPN becomes:
       
       1 2 + 4 3 - *
       Define a visitor class for our syntax tree classes that takes an 
       expression, converts it to RPN, and returns the resulting string.
   
     
<<<<<<< HEAD
>>>>>>> 495c8fc... Updating Interpreter file
=======
>>>>>>> 495c8fc99a8b948a46540051493a3562e3fb2935
>>>>>>> ca0bc71cfcd00e7219619a5a3e41eee71a5653c4
