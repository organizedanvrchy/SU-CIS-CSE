# Programming Verification and Testing
This repository focuses on rigorous methods to verify the correctness of computer systems and troubleshoot unwanted behaviors.

## Formal Verification
Formal verification involves systematically ensuring that a system satisfies its desired properties. Key components include:

- **Description Language**: <br> Used to model systems.
- **Specification Language**: <br> Used to describe the properties that need to be verified.
- **Verification Method**: <br> Determines whether the description satisfies the specification.

### Verification Approaches
1. **Proof- or Model-Based**: <br> Use mathematical proofs or models to verify correctness.
2. **Automatic or Semi-Automatic**: <br> Employ tools and techniques to automate verification processes partially or fully.
3. **Intended Domain**: <br> Tailor verification methods to specific application domains.
4. **Stage in Program Development**: <br> Apply verification techniques at different stages of the development lifecycle.

Formal verification ensures the reliability and correctness of systems, contributing to high-quality software and hardware development.

---

# Haskell Concepts
## Sorting in Haskell
Haskell provides powerful and expressive tools for sorting data collections, leveraging its functional nature:

- **Built-in Functions**: <br> The `Data.List` module includes functions like `sort` for ascending order sorting.
- **Custom Sorting**: <br> Use `sortBy` with custom comparison functions for more control.
- **Performance Consideration**: <br> Haskell's lazy evaluation ensures efficient sorting strategies when properly designed.

### Example
```haskell
import Data.List (sort)

main :: IO ()
main = print (sort [3, 1, 4, 1, 5, 9])
```

## Caesar Cipher in Haskell
A Caesar Cipher is a simple substitution cipher where each letter is shifted by a fixed number of positions in the alphabet.

### Implementation Steps
- Shift each character by a specified number.
- Handle wrapping around the alphabet for characters.
- Ignore non-alphabetic characters as needed.

```haskell
import Data.Char (chr, ord, isAlpha, isUpper)

caesarCipher :: Int -> String -> String
caesarCipher shift = map (shiftChar shift)

shiftChar :: Int -> Char -> Char
shiftChar shift c
  | isAlpha c = let base = if isUpper c then 'A' else 'a'
                in chr $ (ord c - ord base + shift) `mod` 26 + ord base
  | otherwise = c

main :: IO ()
main = putStrLn $ caesarCipher 3 "Hello, World!"
```

---

# Haskell: Data Declarations
## Overview
Data declarations in Haskell define custom data types, enabling developers to model complex concepts beyond primitive types.

## Key Features
- **Creating New Types**: The `data` keyword allows you to define new data types.
```haskell
data Color = Red | Green | Blue
```
- **Constructors**: Used to create values of the custom data type. In the example above, `Red`, `Green`, and `Blue` are constructors of the `Color` type.

- **Parameterized Types**: Custom types can take type parameters.
```haskell
data Maybe a = Nothing | Just a
```

- **Record Syntax**: Provides named fields for better readability and access.
```haskell
data Person = Person { name :: String, age :: Int }
```

- **Recursive Types**: Enable the creation of data structures like lists or trees.
```haskell
data List a = Empty | Cons a (List a)
```

---

# Haskell: Access Controls and Access Control Functions
## Access Controls
Haskell provides access control through its module system, enabling selective exposure of functions, types, and constructors:

- **Public and Private Access**:  
  - By default, all functions and types defined in a module are accessible within that module.
  - To control access, the module export list specifies which entities are exposed.

```haskell
  module MyModule (publicFunction) where

  publicFunction :: String
  publicFunction = "Accessible outside the module"

  privateFunction :: String
  privateFunction = "Accessible only within the module"
```
  - Selective Exporting: Restrict access by listing only the functions, types, or constructors to be exposed.

## Access Control Functions
These functions help manage access and enforce security or permission constraints in Haskell programs:

- Guard Functions: <br> Check for conditions and restrict execution paths based on access rules.
```haskell
accessCheck :: Bool -> String
accessCheck True  = "Access Granted"
accessCheck False = "Access Denied"
```

- Pattern Matching: <br> Ensure safe handling of different access levels by matching specific cases.
```haskell
handleAccess :: Maybe String -> String
handleAccess (Just name) = "Welcome, " ++ name
handleAccess Nothing     = "No access"
```

- Higher-Order Functions: <br> Abstract access control logic for reusable patterns.
```haskell
withAccess :: Bool -> (String -> String) -> String
withAccess hasAccess action = if hasAccess then action "User" else "Access Denied"
```

---
