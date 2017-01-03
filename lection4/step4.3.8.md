**Problem:**

Определить функцию `abbrFirstName`, которая сокращает имя до первой буквы с точкой, то есть, если имя было `"Ivan"`, то после применения этой функции оно превратится в `"I."`. Однако, если имя было короче двух символов, то оно не меняется.

**Answer:**

```haskell
data Person = Person { firstName :: String, lastName :: String, age :: Int }

abbrFirstName :: Person -> Person
abbrFirstName p @ Person{ firstName = (x:_:_) } = p { firstName = x : "." }
abbrFirstName p = p
```