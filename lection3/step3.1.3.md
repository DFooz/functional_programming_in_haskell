**Problem:**

Реализуйте функцию `addTwoElements`, которая бы добавляла два переданных ей значения в голову переданного списка.
```haskell
GHCi> addTwoElements 2 12 [85,0,6]
[2,12,85,0,6]
```

**Answer:**

```haskell
addTwoElements :: a -> a -> [a] -> [a]
addTwoElements x y z = x:(y:z)
```
