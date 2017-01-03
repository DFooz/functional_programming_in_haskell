**Problem:**

Пусть определены следующие функции:

```haskell
emptyOrSingleton :: Bool -> a -> [a]
emptyOrSingleton False _ = []
emptyOrSingleton True x = [x]

isEqual :: (Eq a, Eq b) => (a, b) -> (a, b) -> Bool
isEqual (a, b) (a', b') = a == a' && b == b'
```

Выберите варианты вызовов этих функций, при которых сопоставление с образцом будет осуществлено успешно.


**Answer:**

- [ ] isEqual undefined undefined

- [x] isEqual (undefined, undefined) (undefined, undefined)

- [x] emptyOrSingleton True undefined

- [ ] isEqual undefined (undefined, undefined)

- [x] emptyOrSingleton False undefined

- [ ] emptyOrSingleton undefined 5

- [ ] isEqual (undefined, undefined) undefined