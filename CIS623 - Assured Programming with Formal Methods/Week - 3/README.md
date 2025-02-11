# Types and Functions

## Basic Types
Haskell provides several fundamental data types:

<details>
  <summary>Bool</summary>
  
- **Bool**: Represents boolean values (`True` or `False`).
```haskell
exampleBool :: Bool
exampleBool = True
```

</details>

<details>
  <summary>Char</summary>
  
- **Char**: Represents a single character (`'a'`, `'z'`, etc.).
```haskell
exampleChar :: Char
exampleChar = 'H'
```

</details>

<details>
  <summary>String</summary>
  
- **String**: A list of characters (`"Hello, Haskell!"`).
```haskell
exampleString :: String
exampleString = "Hello, Haskell!"
```

</details>

<details>
  <summary>Int</summary>
  
- **Int**: Fixed-precision integer.
```haskell
exampleInt :: Int
exampleInt = 42
```
  
</details>

<details>
  <summary>Integer</summary>

- **Integer**: Arbitrary-precision integer.
```haskell
exampleInteger :: Integer
exampleInteger = 12345678901234567890
```

</details>

<details>
  <summary>Float</summary>
  
- **Float**: Single-precision floating-point number.
```haskell
exampleFloat :: Float
exampleFloat = 3.14
```

</details>

<details>
  <summary>Double</summary>
  
- **Double**: Double-precision floating-point number.
```haskell
exampleDouble :: Double
exampleDouble = 3.141592653589793
```
  
</details>

---

## Basic Classes
Haskell classes define common behaviors for types. Here are key classes and their related types:

<details>
  <summary>Numeric Types</summary>
  
**Num (Numeric Types)**  
Numeric operations are supported for:
```haskell
addNumbers :: Int -> Int -> Int
addNumbers x y = x + y
result = addNumbers 5 10  -- Result: 15
```
  - **Integral Types**: Whole numbers (`Int`, `Integer`)
  - **Fractional Types**: Numbers with decimal points (`Float`, `Double`)
    ```haskell
    divideNumbers :: Float -> Float -> Float
    divideNumbers x y = x / y
    resultFractional = divideNumbers 5.0 2.0  -- Result: 2.5
    ```

</details>

<details>
  <summary>Equality Types</summary>
  
**Eq (Equality Types)**  
Supports equality comparison (`==`, `/=`) for all basic types.
```haskell
isEqual :: Int -> Int -> Bool
isEqual x y = x == y

resultEq = isEqual 5 5  -- Result: True
```

</details>

<details>
  <summary>Ordered Types</summary>
  
**Ord (Ordered Types)**  
Supports ordering comparisons (`<`, `>`, `<=`, `>=`) for all basic types.
```haskell
compareNumbers :: Int -> Int -> Bool
compareNumbers x y = x > y

resultOrd = compareNumbers 10 5  -- Result: True
```

</details>

<details>
  <summary>Show Types</summary>
  
**Show (Show Types)**  
Allows converting types to human-readable strings (`show 42` yields `"42"`).
```haskell
showExample :: Int -> String
showExample x = show x

resultShow = showExample 42  -- Result: "42"
```

</details>

<details>
  <summary>Read Types</summary>

**Read (Readable Types)**  
Allows parsing strings into specific types (`read "42" :: Int`).
```haskell
readExample :: String -> Int
readExample x = read x

resultRead = readExample "42"  -- Result: 42
```

</details>

<details>
  <summary>Multi-Class Type</summary>
  
### Multi-Class Type Membership
Haskell types can belong to multiple classes simultaneously:

```haskell
combinedExample :: Int -> String
combinedExample x = "The value is: " ++ show x

resultCombined = combinedExample 10  -- Result: "The value is: 10"
```

</details>

---

## Basic Mechanisms
<details>
  <summary>Conditional Expressions</summary>
  
### Conditional Expressions
In Haskell, conditional expressions use `if-then-else` statements. The `else` part is mandatory.

```haskell
absoluteValue :: Int -> Int
absoluteValue x = if x >= 0 then x else -x

resultIf = absoluteValue (-5)  -- Result: 5
```

</details>

<details>
  <summary>Guarded Equations</summary>
  
### Guarded Equations
Guarded equations provide a more elegant and readable way to define conditional logic.

```haskell
f x 
  | condition1 = value1
  | condition2 = value2
  | otherwise  = defaultValue
```

**Example:**

```haskell
grade :: Int -> String
grade score
  | score >= 90 = "A"
  | score >= 80 = "B"
  | score >= 70 = "C"
  | score >= 60 = "D"
  | otherwise   = "F"

resultGuard = grade 85  -- Result: "B"
```

> [!NOTE]
> In this example, `otherwise` acts as a default case when none of the preceding conditions are true.

</details>

<details>
  <summary>List Patterns</summary>

### List Patterns
Haskell provides list pattern matching for efficient list processing. However the `:` operator constructs a list by prepending an element to an existing list.

Examples:
```haskell
listExample = 1 : [2, 3]         -- Result: [1, 2, 3]
listEquality = [1, 2, 3] == 1 : 2 : 3 : []  -- True
```

`head` and `tail`: Functions for extracting parts of a list
```haskell
listHead = head [1, 2, 3]        -- Result: 1
listTail = tail [1, 2, 3]        -- Result: [2, 3]
```

</details>

<details>
  <summary>Curried Functions</summary>
  
### Curried Functions
Functions in Haskell are curried, meaning they take their arguments one at a time. Function arrows `->` associate to the right.

  - Type Association:
  ```haskell
  mult :: Int -> (Int -> (Int -> Int))
  ```
>[!TIP]
> This is equivalent to:
> ```haskell
> mult :: Int -> Int -> Int -> Int
> ```

  - Function Application:
  Function definition associates to the left:
  ```haskell
  mult x y z = x * y * z
  resultMult = mult 2 3 4  -- Result: 24
  ```

</details>

<details>
  <summary>Polymorphic Functions</summary>
### Polymorphic Functions
A polymorphic function works with any type.

**Example:**
```haskell
lengthExample = length [1, 2, 3, 4]      -- Result: 4
```
**Type Signature:**
```haskell
length :: [a] -> Int
```

</details>

<details>
  <summary>Overloaded Functions</summary>
  
### Overloaded Functions
Overloaded functions can operate on different types using class constraints.

**Example:** The addition operator `+` works on all types in the `Num` class.
```haskell
additionExample = (5 :: Int) + (2 :: Int)  -- Result: 7
```
**Type Signature:**
```haskell
(+) :: Num a => a -> a -> a
```

</details>

<details>
  <summary>Lambda Functions</summary>
  
### Lambda Functions
Lambda functions are anonymous functions defined using \. They take arguments and define how to calculate the result. Lambda functions provide a concise and readable way to define simple, on-the-fly functions.

**Example:**
```haskell
odds :: Int -> [Int]
odds n = map (\x -> x * 2 + 1) [0..n-1]

resultLambda = odds 5  -- Result: [1, 3, 5, 7, 9]
```

>[!TIP]
> This is equivalent to:
> ```haskell
> odds :: Int -> [Int]
> odds n = map f [0..n-1]
> where f x = x * 2 + 1
> ```

</details>

---

## Recursion
**Recursion** in Haskell involves functions that call themselves. A recursive function typically includes:
1. **Base Case**: Stops the recursion when a certain condition is met.  
2. **Recursive Definition**: Defines the function in terms of itself.

**Example:** Factorial Function
The factorial of `n` (`n!`) is calculated as `n * (n - 1) * ... * 1`.

```haskell
fac :: Int -> Int
fac 0 = 1  -- Base case
fac n = n * fac (n - 1)  -- Recursive definition

resultFactorial = fac 5  -- Result: 120
```

### Five Steps for Designing Recursive Functions
1. Define the Type <br>
Specify the input and output types of the function.
```haskell
fac :: Int -> Int
```

2. Enumerate the Cases <br>
Identify the base case(s) and recursive case(s).
```haskell
fac 0 = 1  -- Base case
fac n = n * fac (n - 1)  -- Recursive case
```

3. Define the Simple Cases <br>
Handle base cases first to avoid infinite recursion.
```haskell
fac 0 = 1
```

4. Define the Other Cases <br>
Provide the recursive logic for other cases.
```haskell
fac n = n * fac (n - 1)
```
 
5. Generalize and Simplify <br>
Ensure the function handles a variety of inputs and simplify where possible.

**Example:**
```haskell
sumList :: [Int] -> Int
sumList [] = 0  -- Base case: empty list
sumList (x:xs) = x + sumList xs  -- Recursive case: add the head to the sum of the tail

resultSum = sumList [1, 2, 3, 4, 5]  -- Result: 15
```

---

## List Comprehension
**List comprehension** is a concise way to create new lists from existing lists by applying operations and conditions.

### Syntax:
```haskell
[expression | generators, filters]
```
Where: <br>
`Expression`: Defines how to transform elements. <br>
`Generators`: Produce values from existing lists. <br>
`Filters`: Apply guard conditions to filter out unwanted values. <br>

**Example:**
```haskell
squares :: [Int]
squares = [x * x | x <- [1..5]]

resultSquares = squares  -- Result: [1, 4, 9, 16, 25]
```

>[!TIP]
> **Multiple Generators** <br>
> Create pairs from two lists:
> ```haskell
> pairs :: [(Int, Int)]
> pairs = [(x, y) | x <- [1, 2], y <- [3, 4]]
> resultPairs = pairs  -- Result: [(1, 3), (1, 4), (2, 3), (2, 4)]
> ```


### Guard Conditions
Filter values produced by generators.

**Example:** Filter even numbers from a list.
```haskell
evenNumbers :: [Int]
evenNumbers = [x | x <- [1..10], x `mod` 2 == 0]

resultEven = evenNumbers  -- Result: [2, 4, 6, 8, 10]
```

**Example:** Guarded List Comprehension.
```haskell
divisibleBy2And3 :: [Int]
divisibleBy2And3 = [x | x <- [1..20], x `mod` 2 == 0, x `mod` 3 == 0]

resultDivisible = divisibleBy2And3  -- Result: [6, 12, 18]
```

