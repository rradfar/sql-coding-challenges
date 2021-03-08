![SQL](images/sql-logo.png)

# [Codewars](https://www.codewars.com/) SQL Solutions

## Challenges

|  Kyu  | Questions                   | Easy  | Medium | Hard  |
| :---: | :-------------------------- | :---: | :----: | :---: |
|   8   | [Even or Odd](#even-or-odd) |   ⭐   |        |       |

---

## Even or Odd

You will be given a table, `numbers`, with one column `number`. Return a table with a column `is_even` containing "Even" or "Odd" depending on `number` column values.  
numbers table schema: number INT  
output table schema: is_even STRING

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
