**Problem:**

Допустим мы объявили тип

```haskell
data Shape = Circle Double | Rectangle Double Double
```

Что произойдет при объявлении такой функции:

```haskell
isRectangle :: Shape -> Bool
isRectangle Rectangle{} = True
isRectangle _ = False
```

**Answer:**

- ( ) Она не компилируется, так как объявление типа Shape не использует синтаксис записей

- ( ) Она не компилируется из-за синтаксической ошибки

- ( ) Она компилируется и всегда возвращает True

- ( ) Она компилируется и всегда возвращает False

- (x) Она компилируется и возвращает True, если на вход передается Rectangle, иначе она возвращает False