![SQL](images/sql-logo.png)

# [Codewars](https://www.codewars.com/) SQL Solutions

## Challenges

|  Kyu  | Questions                                 |
| :---: | :---------------------------------------- |
|   8   | [Even or Odd](#even-or-odd)               |
|   8   | [Keep Hydrated](#keep-hydrated)               |
|   8   | [Opposite Number](#opposite-number)       |
|   7   | [Sum of Odd Numbers](#sum-of-odd-numbers) |

---

## Even or Odd

You will be given a table, `numbers`, with one column `number`. Return a table with a column `is_even` containing "Even" or "Odd" depending on `number` column values.  
_numbers table schema_: number INT  
_output table schema_: is_even STRING

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

## Keep Hydrated!

Nathan loves cycling. Because Nathan knows it is important to stay hydrated, he drinks 0.5 liters of water per hour of cycling. You get given the time in hours and you need to return the number of liters Nathan will drink, rounded to the smallest value.

Examples:

```markdown
time = 3:     liters = 1
time = 6.7:   liters = 3
time = 11.8:  liters = 5
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

```markdown
1: -1
14: -14
-34: 34
```

<details><summary>Solution</summary>

```sql
SELECT -number AS res FROM opposite;
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

Calculate the row sums of this triangle from the row index (starting at index 1) e.g.:

```
For row index 1 -> Result: 1
For row index 2 -> Result: 8 (because 3 + 5 = 8)
For row index 3 -> Result: 27 (because 7 + 9 + 11 = 27)
```

The table `nums` contains the integer `n` (the input row index). Return your result in a column `res`.

<details><summary>Solution</summary>

```sql
SELECT n * n * n AS res FROM nums;
```
</details>

---

**[⬆ Back to Top](#challenges)**
