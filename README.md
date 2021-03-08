![SQL](images/sql-logo.jpg)

# [Codewars](https://www.codewars.com/) SQL Solutions

## Challenges

|  Kyu  | Questions                           | Easy  | Medium | Hard  |
| :---: | :---------------------------------- | :---: | :----: | :---: |
|   8   | [Even or Odd](#even-or-odd)         |   ⭐   |        |       |
|   8   | [Opposite Number](#opposite-number) |   ⭐   |        |       |

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
