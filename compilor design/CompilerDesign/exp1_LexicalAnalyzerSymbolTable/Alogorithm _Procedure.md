ALGORITHM:
Start the program by including the necessary headers within the FLEX definitions section (%{ ... %}).
Define regular expressions for:
o Identifiers: [a-zA-Z_][a-zA-Z0-9_]*
o Constants: [0-9]+
o Comments: //.* and /* ... */
o Operators: + - * / = &lt; &gt;
Declare a symbol table array (structure with name and type fields) in the definitions section.
Write rules in the rules section of the FLEX (.l) file:
o When an identifier is recognized, call insert() to add it to the symbol table if not already present.
o Print or categorize constants, operators, and comments as they are matched.
Use yylex() actions to print matched tokens and perform symbol table insertion.
In main(), open the input file, call yylex(), then print the symbol table.
Compile the FLEX file using flex and gcc.
Execute the program with a sample C code input file.
Stop.
PROCEDURE:
Open a terminal and create a new FLEX file, symtab.l.
In the definitions section, include headers and declare the symbol table array along with insert()/lookup() helper
functions.
In the rules section, define patterns for identifiers, constants, comments, and operators.
Use { printf(...) } actions to print the recognized tokens and call insert() for identifiers.
Save and compile the file using:
flex symtab.l
gcc lex.yy.c -o symtab -lfl
Run the executable:
./symtab input.c
Observe the output and verify the tokens and symbol table entries.
