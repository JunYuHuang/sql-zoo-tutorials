# 3 SELECT from nobel Quiz (Nobel Quiz)

### 1.

```SQL
SELECT winner FROM nobel
WHERE winner LIKE 'C%' AND winner LIKE '%n'
```

### 2.

```SQL
SELECT COUNT(subject) FROM nobel
WHERE subject = 'Chemistry'
AND yr BETWEEN 1950 and 1960
```

### 3.

```SQL
SELECT COUNT(DISTINCT yr) FROM nobel
WHERE yr NOT IN
(SELECT DISTINCT yr FROM nobel WHERE subject = 'Medicine')
```

### 4.

```
Table
```

### 5.

```SQL
SELECT yr FROM nobel
WHERE yr NOT IN
(SELECT yr FROM nobel
 WHERE subject IN ('Chemistry','Physics'))
```

### 6.

```SQL
SELECT DISTINCT yr
FROM nobel
WHERE subject='Medicine'
AND yr NOT IN
(SELECT yr FROM nobel
 WHERE subject='Literature')
AND yr NOT IN
(SELECT yr FROM nobel
WHERE subject='Peace')
```

### 7.

```
Table 3
```
