![SQL](images/sql-logo.png)

# SQL Coding Challenges for Beginners

## Opposite Number

Your task is to return the opposite of a given number.

Examples:

```
number = 1 -> res = -1
number = 14 -> res = -14
number = -34 -> res = 34
```

```sql
SELECT /* your query given number */
AS res
FROM opposite;
```

<details><summary>Solution</summary>

```sql
SELECT -number
AS res
FROM opposite;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Clock

The clock shows `h` hours (`0 <= h <= 23`), `m` minutes (`0 <= m <= 59`) and `s` seconds (`**0 <= s <= 59**`) after midnight. Your task is to return the time since midnight in milliseconds.

Examples:

```
h = 0, m = 0, s = 0 -> res = 0
h = 0, m = 1, s = 1 -> res = 61000
h = 1, m = 0, s = 1 -> res = 3601000
```

```sql
SELECT /* your query given h, m, s */
AS res
FROM past;
```

<details><summary>Solution</summary>

```sql
SELECT ((h * 60 * 60) + (m * 60) + s) * 1000
AS res
FROM past;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Simple Group By

Given the table `people` which contains a list of people and their ages, your task is to group all the people by their age and count the people who have the same age.

```sql
SELECT /* your query given id, name, age */
```

<details><summary>Solution</summary>

```sql
SELECT age, COUNT(*) AS people_count
FROM people
GROUP BY age;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Century From Year

The first century spans from the year 1 up to and including the year 100, The second - from the year 101 up to and including the year 200, etc. Your task is to return the century that a given year is in.

Examples:

```
yr = 1705 -> century = 18
yr = 1900 -> century = 19
yr = 1601 -> century = 17
yr = 2000 -> century = 20
```

```sql
SELECT /* your query given yr */
AS century
FROM years;
```

<details><summary>Solution</summary>

```sql
SELECT CEILING(yr/100.00)
AS century
FROM years;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Even or Odd

Given a number, return whether the number is even or odd.

Examples:

```
number = -1 -> is_even = 'Odd'
number = 0 -> is_even = 'Even'
number = 1 -> is_even = 'Odd'
number = 2 -> is_even = 'Even'
```

```sql
SELECT /* your query given number */
AS is_even
FROM numbers;
```

<details><summary>Solution</summary>

```sql
SELECT
  CASE
    WHEN number % 2 = 0 THEN 'Even'
    ELSE 'Odd'
  END
AS is_even
FROM numbers;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Expressions Matter

Given three integers `a`, `b`, `c` where `1  ≤  a,  b,  c  ≤  10`, return the largest number obtained after inserting the following operators and brackets in any order: `+`, `*`, `()`. You can use the same operator more than once and it is not necessary to use all the operators and brackets. However, you must use `a`, `b`, and `c` only once, and you may _not_ swap their order.

Example:

```
Given a = 1, b = 2, c = 3:
1 * (2 + 3) = 5
1 * 2 * 3 = 6
1 + 2 * 3 = 7
(1 + 2) * 3 = 9
So the maximum value that you can obtain is 9.
```

```sql
SELECT /* your query given a, b, c */
AS res
FROM expression_matter;
```

<details><summary>Solution</summary>

```sql
SELECT GREATEST(a * b * c, a + b + c, a * (b + c), (a + b) * c)
AS res
FROM expression_matter;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Is n Divisible by x and y?

You will be given a table with columns `n`, `x`, and `y`. Your task is to check if `n` is divisible by the two numbers `x` and `y`. All inputs are positive, non-zero digits.

Examples:

```
n = 3, x = 1, y = 3 -> res = true (because 3 is divisible by 1 and 3)
n = 12, x = 2, y = 6 -> res = true (because 12 is divisible by 2 and 6)
n = 100, x = 5, y = 3 -> res = false (because 100 is not divisible by 3)
n = 12, x = 7, y = 5 -> res = false (because 12 is neither divisible by 7 nor 5)
```

```sql
SELECT id, /* your query given n, x, y */
AS res
FROM kata;
```

<details><summary>Solution</summary>

```sql
SELECT id, n % x = 0 AND n % y = 0
AS res
FROM kata;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Keep Hydrated!

Nathan loves cycling. Because Nathan knows it is important to stay hydrated, he drinks 0.5 liters of water per hour of cycling. You are given the time in hours and you need to return the number of liters Nathan will drink, rounded to the smallest value.

Examples:

```
time = 3 -> liters = 1
time = 6.7 -> liters = 3
time = 11.8 -> liters = 5
```

Given the table `cycling` which contains columns `id` and `hours`, you have to return 3 columns: `id`, `hours` and `liters`.

```sql
SELECT *, /* your query */
AS liters
FROM cycling;
```

<details><summary>Solution</summary>

```sql
SELECT *, FLOOR(hours / 2)
AS liters
FROM cycling;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Returning Strings

You are given a table `person` with a column `name`. Return a table with a column `greeting` that contains `Hello, <name> how are you doing today?`.

Example:

```
name = "John" -> greeting = "Hello, John how are you doing today?"
```

```sql
SELECT /* your query given name */
AS greeting
FROM person;
```

<details><summary>Solution</summary>

```sql
SELECT 'Hello, ' || name || ' how are you doing today?'
AS greeting
FROM person;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Sum of odd numbers

Given the triangle of consecutive odd numbers:

```
             1
          3     5
       7     9    11
   13    15    17    19
21    23    25    27    29
...
```

Calculate the row sums of this triangle from the row index (starting at index 1). The table `nums` contains the integer `n` (the input row index).

Examples:

```
n = 1 -> res = 1
n = 2 -> res = 8 (because 3 + 5 = 8)
n = 3 -> res = 27 (because 7 + 9 + 11 = 27)
```

```sql
SELECT /* your query given n */
AS res
FROM nums;
```

<details><summary>Solution</summary>

```sql
SELECT n * n * n
AS res
FROM nums;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Maximum Multiple

Given a divisor and a bound, find the largest integer `N` where `0 < N <= bound`, such that N is divisible by the divisor. Can you solve this challenge without using a loop?

Examples:

```
divisor = 2, bound = 7 -> N = 6
divisor = 3, bound = 10 -> N = 9
divisor = 7, bound = 17 -> N = 14
divisor = 7, bound = 100 -> N = 98
divisor = 10, bound = 50 -> N = 50
divisor = 37, bound = 200 -> N = 185
```

```sql
SELECT /* your query given divisor & bound */
AS res
FROM max_multiple;
```

<details><summary>Solution</summary>

```sql
SELECT bound - (bound % divisor)
AS res
FROM max_multiple;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**
