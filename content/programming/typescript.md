+++
title = "TypeScript"
[extra]
howtos = true
+++

TypeScript is a superset of JavaScript. It provides optional types annotations.

TypeScript can help avoid common bugs by type-checking the code. It can use the type system to help write code faster.

TypeScript allows to migrate from JavaScript gradually, i.e. on a file basis using the `--allowJs` flag. As of TypeScript 2.3, it is possible to check regular JavaScript files.

TypeScript's type system is complex. Its type-checking performance is a challenge.

TypeScript can parse JSDoc comments into type annotations.

TypeScript generates a corresponding .js file for every .ts file.

By default TypeScript generates ES3 JavaScript which should run in any browser.

TypeScript transpiles ES modules into the CommonJS format. Browsers cannot load the CommonJS modules, so a solution is to run the code through another tool, called a bundler. TypeScript compiler can bundle the code too, so there is no need for a bundler such as Webpack or Browserify.

TypeScript supporting bundling for only two of the five module formats, AMD and System. To create a bundle you specify the outFile parameter.

## Structural Types

TypeScript has structural types, in contrast with Java (which has nominal types): interfaces are assertions about the shape of an object, rather than things themselves.

## Configuration

-   `allowSyntheticDefaultImports` allows to use modules which don't define default exports

## How-Tos

## Notes

### [TypeScript's Built-In Type Declarations with the ~--lib~ Compiler Option](@/programming/typescript/built-in-type-declarations-lib-compiler-option.md)

