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

## Sum of Angles

Find the total sum of interior angles (in degrees) in an n-sided simple polygon. The formula for calculating the sum of interior angles of a polygon with `n` sides where `n > 2` is `(n − 2) × 180°`.

Examples:

```
n = 3 -> res = 180
n = 4 -> res = 360
```

```sql
SELECT /* your query given n */
AS res
FROM angle;
```

<details><summary>Solution</summary>

```sql
SELECT (n - 2) * 180
AS res
FROM angle;
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

```
people
------
id
name
age
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

## Best-Selling Books

You work at a book store. It's the end of the month, and you need to find out the top 5 bestselling books at your store. Use a select statement to list names, authors, and number of copies sold of the 5 books which were sold the most.

```
books
-----
name
author
copies_sold
```

<details><summary>Solution</summary>

```sql
SELECT * FROM books ORDER BY copies_sold DESC LIMIT 5;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## On the Canadian Border

You are a border guard sitting on the Canadian border. You were given a list of travelers who have arrived at your gate today. You know that American, Mexican, and Canadian citizens don't need visas, so they can just continue their trips. You don't need to check their passports for visas! You only need to check the passports of citizens of all other countries!

Select names, and countries of origin of all the travelers, excluding anyone from `Canada`, `Mexico`, or `USA`.

```
travelers
---------
name
country
```

<details><summary>Solution</summary>

```sql
SELECT * FROM travelers
WHERE country NOT IN ('Canada', 'Mexico', 'USA');
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Simple JOIN

For this challenge you need to return all columns from the `products` table, and join to the `companies` table so that you can retrieve the company name. Return all product fields as well as the company name as `company_name`.

```
products        companies
--------        ---------
id              id
name            name
isbn
company_id
price
```

<details><summary>Solution</summary>

```sql
SELECT products.*, companies.name AS company_name
FROM products JOIN companies
ON products.company_id = companies.id;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Simple DISTINCT

For this challenge you need to find all the unique ages from the `people` table.

```
people
------
id
name
age
```

<details><summary>Solution</summary>

```sql
SELECT DISTINCT age
FROM people;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Simple SUM

For this challenge you need to find the sum of all the ages from the `people` table. Return your result as `age_sum`.

```
people
------
id
name
age
```

<details><summary>Solution</summary>

```sql
SELECT SUM (age) AS age_sum
FROM people;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Collect Tuition

You are working for a local school, and you are responsible for collecting tuition from students. You have a list of all students, some of them have already paid tuition and some haven't. Write a select statement to get a list of all students who haven't paid their tuition yet. The list should include all the data available about these students.

```
students
--------
name
age
semester
mentor
tuition_received (boolean)
```

<details><summary>Solution</summary>

```sql
SELECT * FROM students WHERE tuition_received IS false;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Simple HAVING

For this challenge you need to count how many people have the same age and return the groups with 10 or more people who have that age. Return the `age` and your count as `total_people`.

```
people
------
id
name
age
```

<details><summary>Solution</summary>

```sql
SELECT age, count(*) AS total_people
FROM people
GROUP BY age
HAVING count(id) >= 10;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Simple MIN / MAX

For this challenge you need to return the minimum and maximum ages (`age_min` and `age_max`) out of all the people.

```
people
------
id
name
age
```

<details><summary>Solution</summary>

```sql
SELECT MIN(age) AS age_min, MAX(age) AS age_max
FROM people;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## Simple JOIN with COUNT

For this challenge you need to join the people table and the toys table and return all people fields as well as the count of toys for each person as `toy_count`.

```
people        toys
------        ----
id            id
name          name
              people_id
```

<details><summary>Solution</summary>

```sql
SELECT people.*, COUNT(*) as toy_count
FROM people JOIN toys
ON people.id = toys.people_id
GROUP BY people.id;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**
