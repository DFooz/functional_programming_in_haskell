**Problem:**

Определите (частичную) функцию stringToColor, которая по строковому представлению цвета как в прошлой задаче возвращает исходный цвет.

```haskell
GHCi> stringToColor "Red"
Red
```

**Answer:**

```haskell
data Color = Red | Green | Blue deriving (Show, Read)

stringToColor :: String -> Color
stringToColor = read
```