**Problem:**

Определите представителя класса `Functor` для бинарного дерева, в каждом узле которого хранятся элементы типа Maybe:

```haskell
data Tree a = Leaf (Maybe a) | Branch (Tree a) (Maybe a) (Tree a) deriving Show
```
```
GHCi> words <$> Leaf Nothing
Leaf Nothing

GHCi> words <$> Leaf (Just "a b")
Leaf (Just ["a","b"])
```

**Answer:**

```haskell
instance Functor Tree where
    fmap f (Leaf x) = Leaf (fmap f x)
    fmap f (Branch l x r) = Branch (fmap f l) (fmap f x) (fmap f r)
```

**Description**

[words](http://hackage.haskell.org/package/base-4.9.0.0/docs/Prelude.html#v:words)

```haskell
words :: String -> [String]
```

words breaks a string up into a list of words, which were delimited by white space.
