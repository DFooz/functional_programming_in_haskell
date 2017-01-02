**Problem:**

Реализуйте функцию `nTimes`, которая возвращает список, состоящий из повторяющихся значений ее первого аргумента. Количество повторов определяется значением второго аргумента этой функции.

```haskell
GHCi> nTimes 42 3
[42,42,42]
GHCi> nTimes 'z' 5
"zzzzz"
```

**Answer:**

```haskell
nTimes:: a -> Int -> [a]
nTimes x n = take n $ repeat x
```

**Description:**

[repeat](http://hackage.haskell.org/package/base-4.9.0.0/docs/Prelude.html#v:repeat)

```haskell
repeat :: a -> [a]
```

repeat x is an infinite list, with x the value of every element.


[take](http://hackage.haskell.org/package/base-4.9.0.0/docs/Prelude.html#v:take)

```haskell
take :: Int -> [a] -> [a]
```

take n, applied to a list xs, returns the prefix of xs of length n, or xs itself if n > length xs:

```haskell
take 5 "Hello World!" == "Hello"
take 3 [1,2,3,4,5] == [1,2,3]
take 3 [1,2] == [1,2]
take 3 [] == []
take (-1) [1,2] == []
take 0 [1,2] == []
```

It is an instance of the more general `genericTake`, in which n may be of any integral type.


