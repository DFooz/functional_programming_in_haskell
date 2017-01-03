**Problem:**

Определите функцию `updateLastName person1 person2`, которая меняет фамилию `person2` на фамилию `person1`.

**Answer:**

```haskell
data Person = Person { firstName :: String, lastName :: String, age :: Int }

updateLastName :: Person -> Person -> Person
updateLastName per1 per2 = per2 {lastName = (lastName per1)}
```