# 5 SUM and COUNT Quiz

### 1.

```SQL
SELECT SUM(population) FROM bbc
WHERE region = 'Europe'
```

### 2.

```SQL
SELECT COUNT(name) FROM bbc
WHERE population < 150000
```

### 3. (Core SQL aggregate functions)

```
AVG(), COUNT(), MAX(), MIN(), SUM()
```

### 4.

```
No result due to invalid use of the WHERE function
```

### 5.

```SQL
SELECT AVG(population) FROM bbc
WHERE name IN ('Poland', 'Germany', 'Denmark')
```

### 6.

```SQL
SELECT region,
SUM(population) / SUM(area) AS density
FROM bbc GROUP BY region
```

### 7.

```SQL
SELECT name, population/area AS density FROM bbc
WHERE population = (SELECT MAX(population) FROM bbc)
```

### 8.

```
Table-D
```
