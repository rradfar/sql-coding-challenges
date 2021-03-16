![SQL](images/sql-logo.png)

# [Codewars](https://www.codewars.com/) SQL Solutions

## Challenges

|  Kyu  | Questions                                 |
| :---: | :---------------------------------------- |
|   8   | [Beginner Series #2 Clock](#beginner-series-2-clock)               |
|   8   | [Century From Year](#century-from-year)               |
|   8   | [Even or Odd](#even-or-odd)               |
|   8   | [Is n Divisible by x and y?](#is-n-divisible-by-x-and-y)               |
|   8   | [Keep Hydrated](#keep-hydrated)               |
|   8   | [Opposite Number](#opposite-number)       |
|   8   | [Returning Strings](#returning-strings)       |
|   7   | [Sum of Odd Numbers](#sum-of-odd-numbers) |

---

## Beginner Series #2 Clock

The clock shows h hours (0 <= h <= 23), m minutes (0 <= m <= 59) and s seconds (0 <= s <= 59) after midnight. Given table `past` with columns `h`, `m`, and `s`, your task is to return column `res` which represents the time since midnight in milliseconds.

Examples:

```
h = 0, m = 0, s = 0 -> res = 0
h = 0, m = 1, s = 1 -> res = 61000
h = 1, m = 0, s = 1 -> res = 3601000
```

<details><summary>Solution</summary>

```sql
SELECT ((h * 60 * 60) + (m * 60) + s) * 1000 AS res FROM past;
```
</details>

---

**[⬆ Back to Top](#challenges)**

## Century From Year

The first century spans from the year 1 up to and including the year 100, The second - from the year 101 up to and including the year 200, etc.

You are given a table `years` with a column `yr` for the year. Return a table with a column `century` which is the century that the given year is in.

Examples:

```
yr = 1705 -> century = 18
yr = 1900 -> century = 19
yr = 1601 -> century = 17
yr = 2000 -> century = 20
```

<details><summary>Solution</summary>

```sql
SELECT CEILING(yr/100.00) AS century FROM years;
```
</details>

---

**[⬆ Back to Top](#challenges)**

## Even or Odd

You will be given a table `numbers` with one column `number`. Return a table with a column `is_even` containing "Even" or "Odd" depending on `number` column values.

Examples:

```
number = -1 -> is_even = 'Odd'
number = 0 -> is_even = 'Even'
number = 1 -> is_even = 'Odd'
number = 2 -> is_even = 'Even'
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

**[⬆ Back to Top](#challenges)**

## Is n Divisible by x and y?

You will be given a table `kata` with columns `n`, `x`, and `y`. Your task is to check if `n` is divisible by the two numbers `x` and `y`. Return the `id` and your result in a column named `res`. All inputs are positive, non-zero digits.

Examples:

```
n = 3, x = 1, y = 3 -> res = true (because 3 is divisible by 1 and 3)
n = 12, x = 2, y = 6 -> res = true (because 12 is divisible by 2 and 6)
n = 100, x = 5, y = 3 -> res = false (because 100 is not divisible by 3)
n = 12, x = 7, y = 5 -> res = false (because 12 is neither divisible by 7 nor 5)
```

<details><summary>Solution</summary>

```sql
SELECT id, n % x = 0 AND n % y = 0 AS res FROM kata;
```
</details>

---

**[⬆ Back to Top](#challenges)**

## Keep Hydrated!

Nathan loves cycling. Because Nathan knows it is important to stay hydrated, he drinks 0.5 liters of water per hour of cycling. You get given the time in hours and you need to return the number of liters Nathan will drink, rounded to the smallest value.

Examples:

```
time = 3 -> liters = 1
time = 6.7 -> liters = 3
time = 11.8 -> liters = 5
```

Given the table `cycling` which contains columns `id` and `hours`, you have to return 3 columns: `id`, `hours` and `liters`.

<details><summary>Solution</summary>

```sql
SELECT *, FLOOR(hours / 2) AS liters FROM cycling;
```
</details>

---

**[⬆ Back to Top](#challenges)**

## Opposite Number

You are given a table `opposite`, with a column `number`. Return a table with a column `res`.

Examples:

```
number = 1 -> res = -1
number = 14 -> res = -14
number = -34 -> res = 34
```

<details><summary>Solution</summary>

```sql
SELECT -number AS res FROM opposite;
```
</details>

---

**[⬆ Back to Top](#challenges)**

## Returning Strings

You are given a table `person` with a column `name`. Return a table with a column `greeting` that contains `Hello, <name> how are you doing today?`.

Example:

```
name = "John" -> greeting = "Hello, John how are you doing today?"
```

<details><summary>Solution</summary>

```sql
SELECT 'Hello, ' || name || ' how are you doing today?' AS greeting FROM person;
```
</details>

---

**[⬆ Back to Top](#challenges)**

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

Calculate the row sums of this triangle from the row index (starting at index 1). The table `nums` contains the integer `n` (the input row index). Return your result in a column `res`.

Examples:

```
n = 1 -> res = 1
n = 2 -> res = 8 (because 3 + 5 = 8)
n = 3 -> res = 27 (because 7 + 9 + 11 = 27)
```

<details><summary>Solution</summary>

```sql
SELECT n * n * n AS res FROM nums;
```
</details>

---

**[⬆ Back to Top](#challenges)**
