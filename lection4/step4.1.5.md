**Problem:**

Тип данных `Color` определен следующим образом

```haskell
data Color = Red | Green | Blue
```

Определите экземпляр класса Show для типа `Color`, сопоставляющий каждому из трех цветов его текстовое представление.

```haskell
GHCi> show Red
"Red"
```


**Answer:**

```haskell
instance Show Color where
    show Red = "Red"
    show Green = "Green"
    show Blue = "Blue"
```