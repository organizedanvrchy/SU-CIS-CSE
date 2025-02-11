# Haskell Programming Language Overview

## Introduction
Haskell is a **purely functional programming language** that emphasizes immutability, first-class functions, and strong static typing. It is widely recognized for its use in academic and research environments but has also seen practical application in various industries such as finance, web development, and software engineering.

<details>
   <summary>Key Features</summary>
   
### Key Features
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

</details>

---

# Haskell Types
Haskell has a **strong and static type system** that ensures safety and reliability in programs. Types are strictly enforced, and `:type <name>` can be used in GHCi to inspect the type of any expression.

<details>
   <summary>Common Data Types</summary>
   
## Common Types in Haskell
### Bool  
  Represents logical values. Possible values are `True` or `False`.  
  Example:  
```haskell
isEven :: Int -> Bool
isEven n = n `mod` 2 == 0
```

### Char
Represents a single character, enclosed in single quotes ('). <br>
Example: 'a', '1'.

### String
Represents a sequence of characters, essentially a list of Char. Enclosed in double quotes ("). <br>
Example: "Hello, Haskell!".

### Int
Fixed-precision integer type. Efficient but has size limits (e.g., 32-bit or 64-bit depending on the system). <br>
Example: 42.

### Integer
Arbitrary-precision integer type. Can handle very large numbers but may be less efficient than Int. <br>
Example: 12345678901234567890.

### Float
Represents a floating-point number with single precision. <br>
Example: 3.14.

</details>

<details>
   <summary>Common Data Structures</summary>

## Haskell Data Structures
Haskell offers a variety of immutable data structures to efficiently model and manipulate data.

- **Lists**: <br>
Ordered collections of elements, e.g., `[1, 2, 3]`. Commonly used for iteration and recursion.
- **Tuples**: <br>
Fixed-size collections of heterogeneous elements, e.g., `(1, "hello", True)`.
- **Maybe**: <br>
Represents optional values, either `Just value` or `Nothing`.
- **Either**: <br>
Encodes a value of one of two types, `Left error` or `Right value`, often used for error handling.
- **Maps and Sets**: <br>
From the `Data.Map` and `Data.Set` modules, for efficient key-value storage and unique collections.
- **Custom Data Types**: <br>
Define your own structures using `data`, e.g.:
  
```haskell
data Person = Person { name :: String, age :: Int }
```

</details>

<details>
   <summary>Common Functions</summary>
   
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

### Haskell Functions: `head` and `last`
Haskell provides built-in functions to work with lists. Two commonly used functions are `head` and `last`, which extract specific elements from a list.

#### head
- **Type**: `head :: [a] -> a`  
  The `head` function returns the first element of a non-empty list.

- **Definition**:  
```haskell
head (x:_) = x
```

- Pattern matching is used to extract the first element (x) of the list.

- The rest of the list (_) is ignored.

Example: <br>
```haskell
head [1, 2, 3]   -- Output: 1
head "Haskell"   -- Output: 'H'
```

> [!NOTE]
> Calling `head` on an empty list will throw a runtime error. Always ensure the list is non-empty before using `head`.

#### last
- **Type**: `last :: [a] -> a`  
  The `last` function returns the last element of a non-empty list.

- **Definition**:  
```haskell
last [x] = x          -- If the list has one element, return it.
last (_:xs) = last xs -- Otherwise, recursively find the last element.
```

- Pattern matching distinguishes between a single-element list and a list with more elements.

Example: <br>
```haskell
last [1, 2, 3]   -- Output: 3
last "Haskell"   -- Output: 'l'
```

> Like `head`, calling `last` on an empty list will result in a runtime error. Ensure the list is non-empty before using `last`.

</details>
   
---

# Haskell Syntax

<details>
   <summary>Function Definition</summary>
   
## Function Definition:
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

</details>

<details>
   <summary>Advanced Concepts</summary>
   
## Advanced Concepts
### Monads:
- Monads are a powerful abstraction in Haskell for handling side effects, such as I/O operations or state changes, in a pure functional way. <br>
- Common monads include Maybe, IO, and Either.

### Lazy Evaluation:
- Haskell’s lazy evaluation allows for the creation of infinite data structures like streams or lazy lists that can be evaluated as needed.

### Type Inference:
- Haskell’s type system is powerful enough to allow for the automatic inference of types, reducing the need for explicit type annotations in many cases.

</details>

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

---

# Propositional Logic Overview
Propositional logic is a formal system in mathematics and computer science used to represent and reason about logical statements. Below are key concepts.

## Atomic Symbols
- **Atomic Symbols** represent basic, indivisible propositions. These are often denoted as `P`, `Q`, `R`, etc.  
  Example:  
  - `P`: "It is raining."
  - `Q`: "I have an umbrella."

### Logical Connectives
Logical connectives combine atomic symbols to create more complex propositions:

- **Not (¬)**: Negation of a statement.  
  Example: ¬P ("It is not raining").

- **And (∧)**: Conjunction of two statements.  
  Example: P ∧ Q ("It is raining, and I have an umbrella").

- **Or (∨)**: Disjunction of two statements.  
  Example: P ∨ Q ("It is raining, or I have an umbrella").

- **If-Then (→)**: Implication.  
  Example: P → Q ("If it is raining, then I have an umbrella").

## Syntax of Propositional Logic
The syntax defines valid statements in propositional logic. It is composed of a **base case** and **recursive rules**.

### Base Case
- Atomic symbols (e.g., `P`, `Q`) are valid propositions.

### Recursive Rules
- If `P` and `Q` are valid propositions, the following are also valid:
  - ¬P (Negation)
  - P ∧ Q (Conjunction)
  - P ∨ Q (Disjunction)
  - P → Q (Implication)

### Example
Using the base case and recursive rules:
1. `P` (Base case: Atomic symbol)
2. `¬P` (Negation of `P`)
3. `P ∧ Q` (Conjunction of two atomic symbols)
4. `(P ∧ Q) → ¬R` (Combination of rules)

## Applications
Propositional logic is foundational for:
- Formal reasoning in mathematics.
- Logic programming and artificial intelligence.
- Verifying correctness in computer science (e.g., circuits, algorithms).

---

# Access Control Language in Haskell
Access Control Language (ACL) in Haskell is used to define and enforce access control policies precisely. It enables reasoning about who has access to resources and under what conditions.

## Core Principles
1. **Specified Exactly**:  
   ACL ensures that access control policies are described unambiguously to precisely capture their intended meanings.

2. **Access Control Statements**:  
   These are logical constructs used to express permissions, responsibilities, and delegations of authority.

### Access Control Statements
1. **`P says (ϕ)`**  
   - **Meaning**: Principal `P` asserts or endorses the formula `ϕ`.  
   - Example:  
     If `Admin` says `"Alice can access the system"`, it means the statement is authorized by `Admin`.

2. **`P controls (ϕ)`**  
   - **Meaning**: Principal `P` has control over the truth of formula `ϕ`.  
   - Example:  
     If `Manager controls (AccessPolicy)`, only the `Manager` can modify or dictate the `AccessPolicy`.

3. **`P ⇒ Q` (P speaks for Q)**  
   - **Meaning**: Principal `P` can act on behalf of `Q`, or statements made by `P` are trusted as if they came from `Q`.  
   - Example:  
     If `ITAdmin ⇒ SystemAdmin`, it implies `ITAdmin` has the authority to act as `SystemAdmin`.

## Backus-Naur Form (BNF) Notation
### What is BNF?
- **BNF Notation** is a formal way to describe the syntax of a language or system.  
- In ACL, it defines all rules and structures necessary to construct valid access control statements.  
- This ensures that every statement adheres to the defined grammar.

### Example of BNF for ACL

```bnf
<Statement> ::= <Principal> "says" <Formula>
              | <Principal> "controls" <Formula>
              | <Principal> "=>" <Principal>
<Principal> ::= "P" | "Q" | "Admin" | "Manager"
<Formula>   ::= <Statement> | "AccessGranted" | "AccessDenied"
```

### Explanation:
- `Principal` represents entities in the system, such as users or roles.
- `Formula` represents logical statements regarding access.
- `Statement` defines how principals interact with access control policies.

## Why Use ACL in Haskell?
- **Precision**: <br>
Avoids ambiguity by using logical structures to clearly define access policies.
- **Expressiveness**: <br>
Easily represents complex relationships like delegation (P ⇒ Q) or authority (P controls (ϕ)).
- **Formal Verification**: <br>
Ensures correctness and security by verifying policies with logic-based tools.

---

# Set Notation: Composition of Relations
Set composition in mathematics deals with combining two relations to create a new relation. It is fundamental in formal reasoning and relational algebra.

## Composition of Relations

### Definition
- **Given**:  
  - Sets `A`, `B`, `C`  
  - Relations `R1 ⊆ A × B` and `R2 ⊆ B × C`  
- **Composition**:  
  The composition of `R1` and `R2`, denoted as `R1 ∘ R2`, is a subset of `A × C` defined by:  
```text
R1 ∘ R2 = {(x, z) | there exists y such that (x, y) ∈ R1 and (y, z) ∈ R2}.
```

- **Result**: <br>
  R1 ∘ R2 relates elements of A to elements of C by "bridging" through B.

#### Example
Sets and Relations: <br>
A = {(1, 2), (3, 2), (1, 4)} <br>
B = {(2, 3), (2, 4), (1, 4)} <br>

- Step 1: Compute A ∘ B:
   For each pair (x, y) ∈ A and (y, z) ∈ B, find (x, z). <br>
   
   `A = {(1, 2), (3, 2), (1, 4)}` <br>
   `B = {(2, 3), (2, 4), (1, 4)}` <br>
   - From (1, 2) ∈ A and (2, 3) ∈ B, (1, 3) ∈ A ∘ B. <br>
   - From (1, 2) ∈ A and (2, 4) ∈ B, (1, 4) ∈ A ∘ B. <br>
   - From (3, 2) ∈ A and (2, 3) ∈ B, (3, 3) ∈ A ∘ B. <br>
   - From (3, 2) ∈ A and (2, 4) ∈ B, (3, 4) ∈ A ∘ B. <br>
   - (1, 4) ∈ A has no match in B (since no pair starts with 4). <br>

   - Result: <br>
     `A ∘ B = {(1, 3), (1, 4), (3, 3), (3, 4)}`

- Step 2: Compute B ∘ A:
   Reverse the roles of A and B.

   `B = {(2, 3), (2, 4), (1, 4)}` <br>
   `A = {(1, 2), (3, 2), (1, 4)}` <br>
   - From (2, 3) ∈ B and (1, 2) ∈ A, (1, 3) ∈ B ∘ A. <br>
   - From (2, 4) ∈ B and (3, 2) ∈ A, (3, 4) ∈ B ∘ A. <br>
   - (1, 4) ∈ B has no match in A (since no pair starts with 4). <br>

  - Result: <br>
   `B ∘ A = {(1, 3), (3, 4)}`
- Final Results 
`A ∘ B = {(1, 3), (1, 4), (3, 3), (3, 4)}`
`B ∘ A = {(1, 3), (3, 4)}`

> [!NOTE]
> Composition is not commutative, i.e., A ∘ B ≠ B ∘ A in general.
