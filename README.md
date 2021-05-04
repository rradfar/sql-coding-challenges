![SQL](images/sql-logo.png)

# SQL Coding Challenges for Beginners

## 1. Opposite Number

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

## 2. Sum of Angles

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

## 3. Clock

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

## 4. Simple Group By

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

## 5. Century From Year

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

## 6. Even or Odd

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

## 7. Expressions Matter

Given three integers `a`, `b`, `c` where `1  ≤  a,  b,  c  ≤  10`, return the largest number obtained after inserting the following operators and brackets in any order: `+`, `*`, `()`. You can use the same operator more than once, and it is not necessary to use all the operators and brackets. However, you must use `a`, `b`, and `c` only once, and you may _not_ swap their order.

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

## 8. Is n Divisible by x and y?

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

## 9. Keep Hydrated!

Nathan loves cycling. Because Nathan knows it is important to stay hydrated, 
he drinks 0.5 liters of water per hour of cycling. You are given the time in hours, and you need to return the number of liters Nathan will drink, rounded to the smallest value.

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

## 10. Returning Strings

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

## 11. Sum of odd numbers

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

## 12. Maximum Multiple

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

## 13. Best-Selling Books

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
SELECT *
FROM books
ORDER BY copies_sold DESC
LIMIT 5;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 14. On the Canadian Border

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
SELECT *
FROM travelers
WHERE country NOT IN ('Canada', 'Mexico', 'USA');
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 15. Simple JOIN

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

## 16. Simple DISTINCT

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

## 17. Simple SUM

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

## 18. Collect Tuition

You are working for a local school, and you are responsible for collecting tuition from students. You have a list of all students, some of them have already paid tuition, and some haven't. Write a select statement to get a list of all students who haven't paid their tuition yet. The list should include all the data available about these students.

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
SELECT *
FROM students
WHERE tuition_received IS false;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 19. Simple HAVING

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

## 20. Simple MIN / MAX

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

## 21. Simple JOIN with COUNT

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

## 22. Register for the Party

You received an invitation to an amazing party. Now you need to write an insert statement to add yourself to the table of participants.

```
participants
------------
name (string)
age (integer)
attending (boolean)
```

<details><summary>Solution</summary>

```sql
INSERT INTO participants (name, age, attending)
VALUES ('John Doe', 35, true);
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 23. Ordering

Your task is to sort the information in the table `companies` by the number of employees (high to low).

```
companies
---------
id
ceo
motto
employees
```

<details><summary>Solution</summary>

```sql
SELECT *
FROM companies
ORDER BY employees DESC;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 24. Counting and Grouping

Given a demographics table, your task is to return a table that shows a count of each race represented in descending order.

```
demographics
------------
id
name
birthday
race
```

<details><summary>Solution</summary>

```sql
SELECT race, COUNT(*) AS count
FROM demographics
GROUP BY race
ORDER BY count DESC;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 25. Alphabetical Addition

Given a table `letters`, with a string column `letter`, return the sum of the 
letters in that column. Letters will always be lowercase. Letters can 
overflow (see second to last example of the description)
If no letters are given, the function should return `z`.

```
"a", "b" -> "c" -- Because a = 1, b = 2, and 1 + 2 = 3 which corresponds to the letter c
"a", "b", "c" -> "f"
"z", "a" -> "a"
"y", "c", "b" -> "d" -- notice the letters overflowing
"z" -> "z"
"" -> "z"
```

<details><summary>Solution</summary>

```sql
-- Note: CHR(97) -> "a"
-- Note: ASCII("a") -> 97

SELECT COALESCE(CHR(MOD(SUM(ASCII(letter) - 96) - 1, 26)::INT + 97),'z') AS letter
FROM letters;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 26. Simple IN

For this challenge, use the `IN` operator to check whether a department has had a sale with a price over 98 dollars.

```
departments       sales             result
-----------       -----             ------
id                id                id
name              department_id     name
                  name
                  price
                  card_name
                  card_number
                  transaction_date
```

<details><summary>Solution</summary>

```sql
SELECT *
FROM departments
WHERE id IN
  (SELECT department_id FROM sales WHERE price > 98);
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 27. Simple EXISTS

For this challenge, use the `EXISTS` operator to check whether a department has had a sale with a price over 98 dollars.

```
departments       sales             result
-----------       -----             ------
id                id                id
name              department_id     name
                  name
                  price
                  card_name
                  card_number
                  transaction_date
```

<details><summary>Solution</summary>

```sql
SELECT *
FROM departments
WHERE EXISTS
  (SELECT 1 FROM sales WHERE department_id = departments.id AND price > 98); 
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 28. LowerCase

Given a demographics table, your task is to return the same table where all letters are lowercase in the `race` column.

```
demographics
------------
id
name
birthday
race
```

<details><summary>Solution</summary>

```sql
SELECT id, name, birthday, LOWER(race) AS race
FROM demographics;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 29. Concatenating Columns

Given a names table, your task is to return a single column table containing the full title of the person (i.e. concatenate all columns together except the `id`). Don't forget to add spaces!

```
names        output
-----        ------
id           title
prefix
first
last
suffix
```

<details><summary>Solution</summary>

```sql
SELECT CONCAT_WS(' ', prefix, first, last, suffix)
AS title
FROM names;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 30. Simple UNION ALL

There are two tables `ussales` and `eusales` where the parent company tracks each sale at its respective location. Your task is to filter the sale price so it only returns rows with a sale greater than `50.00`. You have been tasked with combining that data for future analysis. Order by `location` (US before EU), then by `id`.

```
(us/eu)sales
------------
id
name
price
card_name
card_number
transaction_date

output
------
location (EU for eusales and US for ussales)
id
name
price (greater than 50.00)
card_name
card_number
transaction_date
```

<details><summary>Solution</summary>

```sql
SELECT 'US' as location, *
  FROM ussales
  WHERE price > 50
UNION ALL
SELECT 'EU' as location, *
  FROM eusales
  WHERE price > 50
ORDER BY location DESC, id;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 31. Growing Plant

Each day a plant is growing by `up_speed` meters. Each night that plant's height declines by `down_speed` meters due to the lack of sun heat. Initially, the plant is `0` meters tall. We plant the seed at the beginning of a day. We want to know the number of days that it will take for the plant to reach or pass a desired height (including the last day in the total count). For example,
- For `up_speed = 100`, `down_speed = 10` and `desired_height = 910`, the output should be `10` days.
- For `up_speed = 10`, `down_speed = 9` and `desired_height = 4`, the output should be `1` day, because the plant already reaches the desired height on the first day.

```
growing_plant        output
-------------        ------
id                   id
down_speed           num_days
up_speed
desired_height
```

<details><summary>Solution</summary>

```sql
SELECT
  id,
  CASE
    WHEN up_speed >= desired_height THEN 1
    ELSE CEIL((desired_height - up_speed)::decimal / (up_speed - down_speed))::int + 1 
  END
  AS num_days
FROM growing_plant;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 32. Second Highest Salary

Write a SQL query to get the second highest salary from the `Employee` table.

```
+----+--------+
| Id | Salary |
+----+--------+
| 1  | 100    |
| 2  | 200    |
| 3  | 300    |
+----+--------+
```

For example, given the above Employee table, the query should return `200` as the second highest salary. If there is no second highest salary, then the query should return `null`.

```
+---------------------+
| SecondHighestSalary |
+---------------------+
| 200                 |
+---------------------+
```

<details><summary>Solution</summary>

```sql
SELECT
  IFNULL(
    (
      SELECT DISTINCT Salary
      FROM Employee
      ORDER BY Salary DESC
      LIMIT 1 OFFSET 1
    ),
  NULL)
AS SecondHighestSalary;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 33. Combine Two Tables

Write a SQL query for a report that provides the following information for each person in the `Person` table, regardless if there is an address for each of those people:

```
Person        Address         Your output
------        -------         -----------
PersonId      AddressId       FirstName
FirstName     PersonId        LastName
LastName      City            City
              State           State
```

<details><summary>Solution</summary>

```sql
SELECT FirstName, LastName, City, State
FROM Person LEFT JOIN Address
ON Person.PersonId = Address.PersonId;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 34. Rounding Decimals

Given the following table `decimals`, return a table with two columns (`number1`, `number2`), where the value in `number1` is rounded down and the value in `number2` is rounded up.

```
decimals
--------
id
number1
number2
```

<details><summary>Solution</summary>

```sql
SELECT
  FLOOR(number1) AS number1,
  CEILING(number2) AS number2
FROM decimals;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 35. Employees Earning More Than Their Managers

The Employee table holds information for all employees including their managers. Every employee has an Id, and there is also a column for their manager Id.

```
+----+-------+--------+-----------+
| Id | Name  | Salary | ManagerId |
+----+-------+--------+-----------+
| 1  | Joe   | 70000  | 3         |
| 2  | Henry | 80000  | 4         |
| 3  | Sam   | 60000  | NULL      |
| 4  | Max   | 90000  | NULL      |
+----+-------+--------+-----------+
```

Given the Employee table, write a SQL query that finds out employees who earn more than their managers. For the above table, Joe is the only employee who earns more than his manager.

```
+----------+
| Employee |
+----------+
| Joe      |
+----------+
```

<details><summary>Solution</summary>

```sql
SELECT
  a.Name AS Employee
FROM
  Employee a JOIN Employee b
ON
  a.managerId = b.Id
WHERE
  a.Salary > b.Salary;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 36. Invalid Tweets

Given the table `Tweets`, write a SQL query to find the `tweet_id` of the invalid tweets. A tweet is invalid if the number of characters used in the content of the tweet is greater than 15.

```
Tweets
------
tweet_id
content
```

<details><summary>Solution</summary>

```sql
SELECT tweet_id
FROM Tweets
WHERE LENGTH(content) > 15;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 37. Daily Leads and Partners

The `DailySales` table contains the date and the name of products sold and the IDs of the leads and partners they were sold to. Write a SQL query that for each `date_id` and `make_name`, returns the number of distinct `lead_id`'s and distinct `partner_id`'s. Here is an example:

```
DailySales table:
+-----------+-----------+---------+------------+
| date_id   | make_name | lead_id | partner_id |
+-----------+-----------+---------+------------+
| 2020-12-8 | toyota    | 0       | 1          |
| 2020-12-8 | toyota    | 1       | 0          |
| 2020-12-8 | toyota    | 1       | 2          |
| 2020-12-7 | toyota    | 0       | 2          |
| 2020-12-7 | toyota    | 0       | 1          |
| 2020-12-8 | honda     | 1       | 2          |
| 2020-12-8 | honda     | 2       | 1          |
| 2020-12-7 | honda     | 0       | 1          |
| 2020-12-7 | honda     | 1       | 2          |
| 2020-12-7 | honda     | 2       | 1          |
+-----------+-----------+---------+------------+
```

```
Result table:
+-----------+-----------+--------------+-----------------+
| date_id   | make_name | unique_leads | unique_partners |
+-----------+-----------+--------------+-----------------+
| 2020-12-8 | toyota    | 2            | 3               |
| 2020-12-7 | toyota    | 1            | 2               |
| 2020-12-8 | honda     | 2            | 2               |
| 2020-12-7 | honda     | 3            | 2               |
+-----------+-----------+--------------+-----------------+
```

<details><summary>Solution</summary>

```sql
SELECT
  date_id,
  make_name,
  COUNT(DISTINCT(lead_id)) AS unique_leads,
  COUNT(DISTINCT(partner_id)) AS unique_partners
FROM DailySales
GROUP BY date_id, make_name;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 38. Find Total Time Spent by Each Employee

Write a SQL query to calculate the total time in minutes spent by each employee on each day at the office. Note that within one day, an employee can enter and leave the office more than once. The time spent in the office for a single entry is `out_time - in_time`. Return the result table in any order. Here is an example:

```
Employees table:
+--------+------------+---------+----------+
| emp_id | event_day  | in_time | out_time |
+--------+------------+---------+----------+
| 1      | 2020-11-28 | 4       | 32       |
| 1      | 2020-11-28 | 55      | 200      |
| 1      | 2020-12-03 | 1       | 42       |
| 2      | 2020-11-28 | 3       | 33       |
| 2      | 2020-12-09 | 47      | 74       |
+--------+------------+---------+----------+
```

```
Result table:
+------------+--------+------------+
| day        | emp_id | total_time |
+------------+--------+------------+
| 2020-11-28 | 1      | 173        |
| 2020-11-28 | 2      | 30         |
| 2020-12-03 | 1      | 41         |
| 2020-12-09 | 2      | 27         |
+------------+--------+------------+
```

<details><summary>Solution</summary>

```sql
Select
  event_day AS day,
  emp_id,
  SUM(out_time - in_time) AS total_time
FROM
  Employees
Group BY
  emp_id, event_day;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**

## 39. SQL Basics - Position

You have access to a table of `monsters`. In each row, the `characteristic` column has a single comma. Your task is to find its position. The `comma` column should contain the position of the comma within the characteristics string. Order the results by `comma`.

```
Monsters          output
--------          ------
id                id
name              name
legs              comma
arms
characteristics
```

<details><summary>Solution</summary>

```sql
SELECT
  id,
  name,
  POSITION(',' IN characteristics) AS comma
FROM
  monsters
ORDER BY
  comma;
```

</details>

---

**[⬆ Back to Top](#sql-coding-challenges-for-beginners)**
