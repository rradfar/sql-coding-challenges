![SQL](images/sql-logo.png)

# [Codewars](https://www.codewars.com/) SQL Solutions

## Challenges

|  Kyu  | Questions                                 |
| :---: | :---------------------------------------- |
|   8   | [Even or Odd](#even-or-odd)               |
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
