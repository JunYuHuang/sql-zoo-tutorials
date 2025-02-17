# 2 SELECT from WORLD

### 1.

```SQL
SELECT name, continent, population FROM world;
```

### 2.

```SQL
SELECT name FROM world
WHERE population >= 200000000;
```

### 3.

```SQL
SELECT name, gdp / population AS per_capita_GDP
FROM world
WHERE population >= 200000000;
```

### 4.

```SQL
SELECT name, population / 1000000
FROM world
WHERE continent = 'South America';
```

### 5.

```SQL
SELECT name, population
FROM world
WHERE name in ('France', 'Germany', 'Italy');
```

### 6.

```SQL
SELECT name
FROM world
WHERE name LIKE '%United%';
```

### 7.

```SQL
SELECT name, population, area
FROM world
WHERE area > 3000000
OR population > 250000000;
```

### 8.

```SQL
SELECT name, population, area
FROM world
WHERE (area > 3000000 and population <= 250000000)
OR (area <= 3000000 and population > 250000000);
```

### 9.

```SQL
SELECT name,
ROUND(population / 1000000, 2),
ROUND(gdp / 1000000000, 2)
FROM world
WHERE continent = 'South America';
```

### 10.

```SQL
SELECT name, ROUND(gdp / population, -3)
FROM world
WHERE gdp >= 1000000000000;
```

### 11.

```SQL
SELECT name, capital
FROM world
WHERE LENGTH(name) = LENGTH(capital);
```

### 12.

```SQL
SELECT name, capital
FROM world
WHERE LEFT(name, 1) = LEFT(capital, 1)
AND name <> capital;
```

### 13.

```SQL
SELECT name
FROM world
WHERE name LIKE '%a%'
AND name LIKE '%e%'
AND name LIKE '%i%'
AND name LIKE '%o%'
AND name LIKE '%u%'
AND name NOT LIKE '% %';
```
