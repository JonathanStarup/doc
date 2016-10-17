# Parsing

The parser is based on the excellent [Parboiled2](https://github.com/sirthias/parboiled2) scala library. 
This is a [parsing expression grammar](https://en.wikipedia.org/wiki/Parsing_expression_grammar) (PEG) parser library. 
PEGs are great because they overcome the ambiguity problem by greedy choice. 

### Key Classes

- `Parser`, the class that implements the Flix grammar.
- `SourcePosition`, a class that represents a specific *point* in the source code, i.e. a line and column number.
- `SourceLocation`, a class that represents a specific *range* in the source code, i.e. a beginning line and column
   number and an ending line and column number. In every later stage of the compiler, every AST node is associated
   with a `SourceLocation`.

### Caveats 

The grammar is pretty straightforward, but there are a couple of things to be aware of:

- Compilation of the parser class is slow due to the use of macros in Parboiled. 
- The error messages produced by Parboiled, if there is an error in the grammar, are almost unusable.
- The PEG grammar is greedy. Make sure you understand what this means.
- The AST is constructed during parsing. However, you should avoid any costly work during AST construction since an AST
  fragment may be constructed only to be discarded later because of a parse mismatch.  
- Whitespace must be handled carefully: 
    - The production rule `WS` *requires* some whitespace, whereas 
    - The production rule `optWS` *allows* whitespace.
- Optional semicolons are matched by the `optSC` rule.
- Source locations are tracked by pushing a `SourcePosition` on the stack when a syntactic element begins and again
  when the element ends. For example, the rule `SP ~ "Foo" ~ SP` can be used to track when the element `"Foo"` begins
  and ends. `SourcePosition`s are later translated into proper `SourceLocation`s. 