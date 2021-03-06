
+++

+++
# Programming Terms

## Flutent Interface

a method for designing object-oriented APIs based on method chaining.

## Binding

Binding is a correspondence between a name and its value.

## Lexical Binding/Scope

Lexical binding refers to how variables are looked up by their names.

Lexical scope makes it easy to reason about closures.

Lexical binding is also known as static binding.

## Dynamic Binding/Scope

Variable names and their values store only in the global state.

Dynamic scope is easier for language authors to implement.

Dynamic scope makes it possible to do certain kinds of code re-use not possible with lexical scope. This code re-use is often called **macro**.

Unhygenic macros require dynamic scope while hygenic macros require a pre-processor and no access to the dynamic scope.

Dynamic scope leads to unexpected side-effects. It makes closures difficult to implement and is only useful for writing unhygenic macros (the least useful kinds of macros).

## Meta-Circular Evaluator

A Lisp interpreter written in Lisp.

The exercise of writing an interpreter in its own language - or alternatively writing a self-hosting compiler - teaches a great deal about how programs work.

Writing a Meta-Circular Evaluator is a way into building intuition towards Godel Numbering, Reductions and the Church-Turing thesis.

There is also Curry's Paradox and Russel's Paradox that come from self-reference.

