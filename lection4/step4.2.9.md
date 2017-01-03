**Problem:**

Целое число можно представить как список битов со знаком.

Реализуйте функции сложения и умножения для таких целых чисел, считая, что младшие биты идут в начале списка, а старшие — в конце. Можно считать, что на вход не будут подаваться числа с ведущими нулями.



**Answer:**

by [dstarcev](https://github.com/dstarcev/stepic-haskell/blob/master/src/Module4/Task10.hs):

```haskell
import Data.List (unfoldr)

data Bit = Zero | One
data Sign = Minus | Plus
data Z = Z Sign [Bit]

zToInt (Z Minus bits) = - zToInt (Z Plus bits)
zToInt (Z _ bits) = foldr (\x a -> a * 2 + toInt x) 0 bits where
  toInt One = 1
  toInt Zero = 0

intToZ x = (Z (sign x) (toBin $ abs x)) where
  sign n = if n < 0 then Minus else Plus
  toDigit 0 = Zero
  toDigit 1 = One
  toBin = unfoldr (\x -> if x > 0
                         then Just (toDigit $ rem x 2, div x 2)
                         else Nothing)

op f a b = intToZ $ f (zToInt a) (zToInt b)

add :: Z -> Z -> Z
add = op (+)

mul :: Z -> Z -> Z
mul = op (*)
```

**Description:**

[foldr](http://hackage.haskell.org/package/base-4.9.0.0/docs/Data-List.html#v:foldr)

```haskell
foldr :: Foldable t => (a -> b -> b) -> b -> t a -> b
```

Right-associative fold of a structure.

In the case of lists, foldr, when applied to a binary operator, a starting value (typically the right-identity of the operator), and a list, reduces the list using the binary operator, from right to left:

```haskell
foldr f z [x1, x2, ..., xn] == x1 `f` (x2 `f` ... (xn `f` z)...)
```

Note that, since the head of the resulting expression is produced by an application of the operator to the first element of the list, foldr can produce a terminating expression from an infinite list.

For a general Foldable structure this should be semantically identical to,

```haskell
foldr f z = foldr f z . toList
```


[unfoldr](http://hackage.haskell.org/package/base-4.9.0.0/docs/Data-List.html#v:unfoldr)

```haskell
unfoldr :: (b -> Maybe (a, b)) -> b -> [a]
```

The unfoldr function is a `dual' to foldr: while foldr reduces a list to a summary value, unfoldr builds a list from a seed value. The function takes the element and returns Nothing if it is done producing the list or returns Just (a,b), in which case, a is a prepended to the list and b is used as the next element in a recursive call. For example,

```haskell
iterate f == unfoldr (\x -> Just (x, f x))
```

In some cases, unfoldr can undo a foldr operation:

```haskell
unfoldr f' (foldr f z xs) == xs
```

if the following holds:

```haskell
f' (f x y) = Just (x,y)
f' z       = Nothing
```

A simple use of unfoldr:

```haskell
unfoldr (\b -> if b == 0 then Nothing else Just (b, b-1)) 10
 [10,9,8,7,6,5,4,3,2,1]
```