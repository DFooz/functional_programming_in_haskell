**Problem:**

Определите частичную (определенную на значениях от `'0'` до `'9'`) функцию `charToInt`.

```haskell
GHCi> charToInt '0'
0
GHCi> charToInt '9'
9
```

**Answer:**

```haskell
charToInt :: Char -> Int
charToInt '0' = 0
charToInt '1' = 1
charToInt '2' = 2
charToInt '3' = 3
charToInt '4' = 4
charToInt '5' = 5
charToInt '6' = 6
charToInt '7' = 7
charToInt '8' = 8
charToInt '9' = 9
```

или

```haskell
charToInt :: Char -> Int
charToInt x | x `elem` ['0'..'9'] = (fromEnum x) - 48
```