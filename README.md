# RDFP

**WIP, idea only**.

The basic idea is to enpower semantic web with programming.

```turtle
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix rdfp: <http://xubai.wang/rdfp#> .

# `print` functions (without implementation)
<#display>    rdf:type rdfp:Function .
<#displayln>  rdf:type rdfp:Function .

# `main` function
# execute to `Hello, rdfp!`
<#main>
  rdf:type rdfp:MainFn;
  rdfp:fnBody (
    [
      rdf:type rdfp:FnApp;
      rdfp:appFn rdfp:display;
      rdfp:args (
        "Hello, "
      )
    ]
    [
      rdftype rdfp:FnApp;
      rdfp:appFn rdfp:displayln;
      rdfp:args (
        "rdfp!"
      )
    ]
  ) .

# metaprogramming should be first-class, e.g.
# syntax extensions
# "emulate" other lanuages

@syntax lisp
(display "Hello, ")
(displayln "rdfp!")
```
