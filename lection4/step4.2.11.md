**Problem:**

Пусть определена следующая функция:

```haskell
foo :: Bool -> Int
foo ~True = 1
foo False = 0
```

Что произойдет при вызове `foo False`?


**Answer:**


- [ ] Поведение не определено

- [ ] Вычисление зависнет

- [ ] Будет брошено исключение

- [ ] Произойдет ошибка при сопоставлении с образцом

- [ ] Функция вернет 0

- [x] Функция вернет 1