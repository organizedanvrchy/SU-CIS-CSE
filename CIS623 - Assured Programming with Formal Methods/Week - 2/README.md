# Haskell Programming Language Overview

## Introduction
Haskell is a **purely functional programming language** that emphasizes immutability, first-class functions, and strong static typing. It is widely recognized for its use in academic and research environments but has also seen practical application in various industries such as finance, web development, and software engineering.

## Key Features
1. **Pure Functional Programming:**
   - Haskell is a purely functional language, meaning that functions have no side effects and every expression is a value.
   - Functions are first-class citizens, meaning they can be passed as arguments, returned from other functions, and assigned to variables.

2. **Strong Static Typing:**
   - Haskell features a **strongly typed** system with **type inference**, meaning the compiler can automatically deduce the types of expressions without requiring explicit type declarations.
   - **Polymorphic types** and **type classes** enable powerful abstractions in Haskell.

3. **Lazy Evaluation:**
   - Haskell uses **lazy evaluation**, which means expressions are not evaluated until their values are actually needed. This allows for infinite data structures and greater control over performance optimization.

4. **Immutability:**
   - All data in Haskell is immutable by default. This means that once a value is assigned to a variable, it cannot be changed. This property leads to fewer bugs and more predictable programs.

5. **Higher-Order Functions:**
   - Functions in Haskell can accept other functions as arguments and can return functions as results, enabling powerful abstractions and compositionality.

6. **Concurrent Programming:**
   - Haskell provides tools for **concurrent and parallel programming**, such as lightweight threads, software transactional memory (STM), and the `async` package, making it well-suited for scalable applications.

## Syntax and Example
### Function Definition:
A basic function in Haskell is defined as follows:
```haskell
double :: Int -> Int
double x = x * 2
```
- **double** takes an Int as an input and returns another Int. The :: syntax denotes the function's type

Lists are a fundamental data structure in Haskell.
```haskell
sumList :: [Int] -> Int
sumList [] = 0
sumList (x:xs) = x + sumList xs
```
- This function recursively calculates the sum of a list of integers.

Haskell’s type classes allow for generic programming. For example, the Eq type class enables equality checking:
```
data Point = Point Int Int

instance Eq Point where
    (Point x1 y1) == (Point x2 y2) = (x1 == x2) && (y1 == y2)
```
- **Eq** defines how two **Point** values can be compared for equality

## Advanced Concepts
### Monads:
- Monads are a powerful abstraction in Haskell for handling side effects, such as I/O operations or state changes, in a pure functional way. <br>
- Common monads include Maybe, IO, and Either.

### Lazy Evaluation:
- Haskell’s lazy evaluation allows for the creation of infinite data structures like streams or lazy lists that can be evaluated as needed.

### Type Inference:
- Haskell’s type system is powerful enough to allow for the automatic inference of types, reducing the need for explicit type annotations in many cases.

## Haskell Data Structures
Haskell offers a variety of immutable data structures to efficiently model and manipulate data.

- **Lists**: Ordered collections of elements, e.g., `[1, 2, 3]`. Commonly used for iteration and recursion.
- **Tuples**: Fixed-size collections of heterogeneous elements, e.g., `(1, "hello", True)`.
- **Maybe**: Represents optional values, either `Just value` or `Nothing`.
- **Either**: Encodes a value of one of two types, `Left error` or `Right value`, often used for error handling.
- **Maps and Sets**: From the `Data.Map` and `Data.Set` modules, for efficient key-value storage and unique collections.
- **Custom Data Types**: Define your own structures using `data`, e.g.:
  
```haskell
data Person = Person { name :: String, age :: Int }
```
  
## Haskell Functions
Functions are first-class citizens in Haskell, allowing for concise and expressive programming.

- Pure Functions: <br>
Always produce the same output for the same input, with no side effects.
- Higher-Order Functions:<br>
Functions that take other functions as arguments or return them, e.g., map, filter.
- Pattern Matching: <br>
Simplifies function definitions by matching specific input patterns:

```haskell
factorial 0 = 1
factorial n = n * factorial (n - 1)
```

- Recursion: <br>
The primary mechanism for iteration in Haskell.
- Lambda Functions: <br>
Anonymous functions defined inline, e.g., \x -> x + 1.
- Currying: <br>
Functions automatically take arguments one at a time, enabling partial application.

---

# Literate Programming in Haskell
Literate programming enables better documentation and understanding of your Haskell programs. It is a programming paradigm that intertwines code and documentation, and focuses on readability and explaining why the code exists alongside what it does.

## File Extensions:
- .hs: Standard Haskell scripts.
- .lhs: Literate Haskell scripts, where documentation and code coexist.

## Structure:
In .lhs files, lines starting with > are treated as code, while other lines are treated as comments or documentation. Example:

```haskell
This is a literate Haskell file explaining Fibonacci:

> fib 0 = 0
> fib 1 = 1
> fib n = fib (n - 1) + fib (n - 2)
```

## Benefits:
- Improved code clarity.
- Seamless integration of documentation into the development process.
- Facilitates collaboration and knowledge sharing.
