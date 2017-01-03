**Problem:**

Тип `LogLevel` описывает различные уровни логирования.

```haskell
data LogLevel = Error | Warning | Info
```

Определите функцию cmp, сравнивающую элементы типа `LogLevel` так, чтобы было верно, что `Error > Warning > Info`.

```haskell
GHCi> cmp Error Warning
GT
GHCI> cmp Info Warning
LT
```

**Answer:**

```haskell
cmp :: LogLevel -> LogLevel -> Ordering
cmp a b = compare (i a) (i b) where
    i Error = 2
    i Warning = 1
    i Info = 0
```