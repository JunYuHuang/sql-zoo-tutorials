# 5 SUM and COUNT

### World Country Profile: Aggregate functions

This tutorial is about aggregate functions such as `COUNT`, `SUM` and `AVG`. An aggregate function takes many values and delivers just one value. For example the function `SUM` would aggregate the values 2, 4 and 5 to deliver the single value 11.

### 1. Total world population

**Show the total population of the world.**

```
world(name, continent, area, population, gdp)
```

```SQL
SELECT SUM(population)
FROM world;
```

### 2. List of continents

**List all the continents - just once each.**

```SQL
SELECT DISTINCT continent
FROM world;
```

### 3. GDP of Africa

**Give the total GDP of Africa**

```SQL
SELECT SUM(gdp)
FROM world
WHERE continent = 'Africa';
```

### 4. Count the big countries

**How many countries have an area of at least 1000000**

```SQL
SELECT COUNT(name)
FROM world
WHERE area >= 1000000;
```

### 5. Baltic States population

**What is the total population of ('Estonia', 'Latvia', 'Lithuania')**

```SQL
SELECT SUM(population)
FROM world
WHERE name in ('Estonia', 'Latvia', 'Lithuania');
```

## Using `GROUP BY` and `HAVING`

You may want to look at these examples: Using GROUP BY and HAVING.

### 6. Counting the countries of each continent

**For each continent show the continent and number of countries.**

```SQL
SELECT continent, COUNT(name)
FROM world
GROUP BY continent;
```

### 7. Counting big countries in each continent

**For each continent show the continent and number of countries with populations of at least 10 million.**

```SQL
SELECT continent, COUNT(name)
FROM world
WHERE population >= 10000000
GROUP BY continent;
```

### 8. Counting big continents

**List the continents that have a total population of at least 100 million.**

```SQL
SELECT continent
FROM world
GROUP BY continent
HAVING SUM(population) >= 100000000;
```
