**Problem:**


Исследуйте тип функции

```haskell
sndHead = snd . head
```

и разберитесь, каково ее поведение. Эту функцию можно реализовать, используя сопоставление с образцом

```haskell
sndHead некоторый_образец = x
```

Отметьте те образцы, которые подходят для этой цели.


**Answer:**

```haskell

- [ ] ((,) ((:) _ _) x)

- [x] ((:) ((,) _ x) y)

- [ ] ((,) x y : z)

- [x] ((_, x) : _)

- [ ] ((,) y z : x)

- [x] ((,) y x : z)

```
