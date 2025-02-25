# Higher-Order Functions in Haskell
Higher-order functions (HOFs) are functions that take other functions as parameters or return functions as results. They enable functional programming by allowing functions to be treated as data.

## Using Functions as Data / Parameters
In Haskell, functions can be passed as arguments to other functions. A common example is applying a function `twice`:

```haskell
twice :: (a -> a) -> a -> a
twice f x = f (f x)
```

### Example:
```haskell
addOne :: Int -> Int
addOne x = x + 1

main = print (twice addOne 5)  -- Output: 7
```

## Maps
`map` applies a function to every element in a list.

```haskell
map :: (a -> b) -> [a] -> [b]
map f xs = [f x | x <- xs]
```

### Example:
```haskell
square :: Int -> Int
square x = x * x

main = print (map square [1,2,3,4])  -- Output: [1,4,9,16]
```

## Filters
`filter` selects elements from a list that satisfy a predicate.

```haskell
filter :: (a -> Bool) -> [a] -> [a]
filter p xs = [x | x <- xs, p x]
```

### Example:
```haskell
evenNumbers :: Int -> Bool
evenNumbers x = x `mod` 2 == 0

main = print (filter evenNumbers [1,2,3,4,5,6])  -- Output: [2,4,6]
```

## Function Composition
Function composition allows combining functions into a single function using `(.)`.

```haskell
(.) :: (b -> c) -> (a -> b) -> a -> c
f . g = \x -> f (g x)
```

### Example:
```haskell
addOne :: Int -> Int
addOne x = x + 1

square :: Int -> Int
square x = x * x

main = print ((square . addOne) 3)  -- Output: 16
```

## Programming Patterns (Part I)
### Composition Operator
The composition operator `(.)` allows chaining functions together.

```haskell
odd :: Int -> Bool
odd = not . even

sumSqEven :: [Int] -> Int
sumSqEven = sum . map (^2) . filter even
```

We can also define a function that applies another function twice:

```haskell
twice :: (a -> a) -> a -> a
twice f = f . f
```

### Other Common Patterns

- **all** – Decides if every element of a list satisfies a given predicate.
- **any** – Checks if at least one element of a list satisfies a predicate.
- **takeWhile** – Selects elements from a list while a predicate is true.
- **dropWhile** – Removes elements while a predicate holds true.

### Example:
```haskell
main = do
  print (all even [2,4,6])       -- Output: True
  print (any odd [2,4,6])        -- Output: False
  print (takeWhile (< 5) [1..10]) -- Output: [1,2,3,4]
  print (dropWhile (< 5) [1..10]) -- Output: [5,6,7,8,9,10]
```

## Programming Patterns (Part II)
### Fold Right (`foldr`)
`foldr` (fold right) is a powerful recursion pattern that processes a list from right to left.

```haskell
foldr :: (a -> b -> b) -> b -> [a] -> b
foldr f v [] = v
foldr f v (x:xs) = f x (foldr f v xs)
```

### Example:
```haskell
sumList :: [Int] -> Int
sumList = foldr (+) 0

main = print (sumList [1,2,3])  -- Output: 6
```

We can also use `foldr` to reverse a list:

```haskell
reverseList :: [a] -> [a]
reverseList = foldr (\x xs -> xs ++ [x]) []

main = print (reverseList [1,2,3])  -- Output: [3,2,1]
```

### Fold Left (`foldl`)
`foldl` (fold left) is similar to `foldr`, but processes the list from left to right.

```haskell
foldl :: (b -> a -> b) -> b -> [a] -> b
foldl f v [] = v
foldl f v (x:xs) = foldl f (f v x) xs
```

### Example:
```haskell
sumListLeft :: [Int] -> Int
sumListLeft = foldl (+) 0

main = print (sumListLeft [1,2,3])  -- Output: 6
```

Unlike `foldr`, `foldl` processes elements iteratively from the beginning of the list, making it more efficient for some operations.

## Lambda Expressions
Lambda functions are anonymous functions that can be used in place of named functions.

```haskell
\x -> x * 2
```

### Example:
```haskell
main = print (map (\x -> x * 2) [1,2,3,4])  -- Output: [2,4,6,8]
```

## Unnamed Functions
Lambda functions can be used to simplify function definitions.

```haskell
odds :: Int -> [Int]
odds n = map f [0..n-1]
  where
    f x = x * 2 + 1
```

The above function can be rewritten using a lambda expression:

```haskell
odds :: Int -> [Int]
odds n = map (\x -> x * 2 + 1) [0..n-1]
```

### Example:
```haskell
main = print (odds 5)  -- Output: [1,3,5,7,9]
```

---

# Basic Access Control Concepts

Access control determines who should be granted what access to which objects under what circumstances. It is a fundamental security mechanism to regulate permissions and enforce security policies.

## 1. Access Request
An access request defines what is requested and by whom.

### Example:
```
Commander says (launch, missile)
```
In this case, the Commander is requesting to launch the missile.

## 2. Access Policy
The access policy defines who is authorized to perform certain actions.

### Example:
```
(Commander & Subcommander) controls (launch, missile)
```
This policy states that both the Commander and Subcommander have control over launching the missile.

## 3. Trust Assumption
Trust assumptions define who or what is considered trusted, including symbols or tokens of authority.

### Example:
```
KeyNCA => National Command Authority
```
Here, KeyNCA represents the National Command Authority, which is a trusted entity responsible for decision-making.

## 4. Reference Monitors
Reference monitors guard objects by ensuring that only authorized access requests are granted.

## 5. Tickets
Tickets serve as indicators of a principal’s right to access an object.

## 6. Access Control List (ACL)
An Access Control List is a list of principals who are granted access to an object.

## 7. Authentication
Authentication is the process of identifying a principal before granting access.

## 8. Derived Inference Rule
Derived inference rules help in deducing access rights based on existing policies.

### Ticket Rule
The Ticket Rule defines conditions under which a principal can obtain a ticket to access an object.

### Derive Ticket Rule
The Derive Ticket Rule specifies how tickets can be derived from existing access policies.

## Summary
Access control relies on several key components:
- **Access Request**: Specifies the action and the requester.
- **Access Policy**: Defines who is authorized to perform the action.
- **Trust Assumption**: Establishes trust and authority symbols in the system.
- **Reference Monitors**: Protect objects from unauthorized access.
- **Tickets**: Indicate access rights.
- **Access Control Lists (ACLs)**: Enumerate authorized principals.
- **Authentication**: Identifies principals before granting access.
- **Derived Inference Rules**: Define how access rights can be inferred.

By implementing clear access control mechanisms, organizations can enforce security and prevent unauthorized access.





