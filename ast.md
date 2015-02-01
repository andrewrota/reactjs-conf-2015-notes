Static analysis: analysis of computer software without actually executing it.

In the past, this has often been difficult.  DOM can be mutated anywhere, at any time.  Output is not a pure function of its input.  Template is pulled in externally and you can't determine what the end visual structure is.

React makes this easier because everything you need to know about the component is in the same file.  React components visual representation is effectivly a function of internal state and props.

You are probably already doing some kind of static analysis.  Higher level transformations with knowledge of React's API.

* Instrumentation
* Component Catalog
* Documentation

**Instrumenting**

http://blog.circleci.com/local-state-global-concerns

Generalize the transform.

Compiler takes a higher level source lanaguge and produces a lower level source output.

Use exprima to parse input source into an AST (abstract syntax tree).  `esprima.parse()`

Generate code.  `escodegen.generate()`

estraverse exposes enter and exit methods to traverse the tree.  Enter is called on the way down, exit is called on the way up.

esquery uses a query selector syntax.

ast-types can incrementally build up AST using a builder API.

Templtes (estemplate) allows you to use a string with delimiters with data for the resulting AST.

Object literals can be used too.

