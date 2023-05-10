# 3 SELECT from Nobel

## `nobel` Nobel Laureates

We continue practicing simple SQL queries on a single table.

This tutorial is concerned with a table of Nobel prize winners:

```
nobel(yr, subject, winner)
```

Using the `SELECT` statement.

### 1. Winners from 1950

**Change the query shown so that it displays Nobel prizes for 1950.**

```SQL
SELECT yr, subject, winner
FROM nobel
WHERE yr = 1950;
```

### 2. 1962 Literature

**Show who won the 1962 prize for literature.**

```SQL
SELECT winner
FROM nobel
WHERE yr = 1962 AND subject = 'literature';
```

### 3. Albert Einstein

**Show the year and subject that won `Albert Einstein` his prize.**

```SQL
SELECT yr, subject
FROM nobel
WHERE winner = 'Albert Einstein';
```

### 4. Recent Peace Prizes

**Give the name of the `peace` winners since the year 2000, including 2000.**

```SQL
SELECT winner
FROM nobel
WHERE yr >= 2000 AND subject = 'Peace';
```

### 5. Literature in the 1980's

**Show all details (`yr`, `subject`, `winner`) of the literature prize winners for 1980 to 1989 inclusive.**

```SQL
SELECT *
FROM nobel
WHERE subject = 'Literature' AND yr BETWEEN 1980 and 1989;
```

### 6. Only Presidents

**Show all details of the presidential winners:**
* Theodore Roosevelt
* Thomas Woodrow Wilson
* Jimmy Carter
* Barack Obama

```SQL
SELECT *
FROM nobel
WHERE winner IN ('Theodore Roosevelt', 'Woodrow Wilson', 'Jimmy Carter', 'Barack Obama');
```

### 7. John

**Show the winners with first name `John`**

```SQL
SELECT winner
FROM nobel
WHERE winner LIKE 'John_%';
```

### 8. Chemistry and Physics from different years

**Show the year, subject, and name of physics winners for 1980 together with the chemistry winners for 1984.**

```SQL
SELECT *
FROM nobel
WHERE (subject = 'Physics' AND yr = 1980)
OR (subject = 'Chemistry' AND yr = 1984);
```

### 9. Exclude Chemists and Medics

**Show the year, subject, and name of winners for 1980 excluding chemistry and medicine**

```SQL
SELECT *
FROM nobel
WHERE yr = 1980
AND subject NOT IN ('chemistry', 'medicine');
```

### 10. Early Medicine, Late Literature

**Show year, subject, and name of people who won a 'Medicine' prize in an early year (before 1910, not including 1910) together with winners of a 'Literature' prize in a later year (after 2004, including 2004)**

```SQL
SELECT *
FROM nobel
WHERE (subject = 'Medicine' AND yr < 1910)
OR (subject = 'Literature' AND yr >= 2004);
```

## Harder Questions

### 11. Umlaut

**Find all details of the prize won by PETER GRÜNBERG**

*Non-ASCII characters*

The u in his name has an `umlaut`. You may find this link useful https://en.wikipedia.org/wiki/%C3%9C#Keyboarding

```SQL
SELECT *
FROM nobel
WHERE winner = 'PETER GRÜNBERG';
```

### 12. Apostrophe

**Find all details of the prize won by EUGENE O'NEILL**

*Escaping single quotes*

You can't put a single quote in a quote string directly. You can use two single quotes within a quoted string.

```SQL
SELECT *
FROM nobel
WHERE winner = 'Eugene O\'Neill';
```

### 13. Knights of the realm

Knights in order

**List the winners, year and subject where the winner starts with `Sir`. Show the the most recent first, then by name order.**

```SQL
SELECT winner, yr, subject
FROM nobel
WHERE winner LIKE 'Sir_%'
ORDER BY yr DESC, winner ASC;
```

### 14. Chemistry and Physics last

The expression `subject IN ('chemistry','physics')` can be used as a value - it will be `0` or `1`.

**Show the 1984 winners and subject ordered by subject and winner name; but list chemistry and physics last.**

```SQL
SELECT winner, subject
FROM nobel
WHERE yr = 1984
ORDER BY subject IN ('physics','chemistry') ASC, subject, winner;
```
