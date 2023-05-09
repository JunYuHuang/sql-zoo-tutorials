# 1 SELECT from WORLD

## 1. Introduction

Read the notes about this table.

**Observe the result of running this SQL command to show the name, continent and population of all countries.**

```SQL
SELECT name, continent, population FROM world;
```

## 2. Large Countries

How to use WHERE to filter records.

**Show the name for the countries that have a population of at least 200 million. 200 million is 200000000, there are eight zeros.**

```SQL
SELECT name FROM world
WHERE population >= 200000000
```

## 3. Per capita GDP

**Give the `name` and the per capita GDP for those countries with a `population` of at least 200 million.**

HELP:How to calculate per capita GDP

per capita GDP is the GDP divided by the population GDP/population

```SQL
SELECT name, gdp / population AS per_capita_GDP
FROM world
WHERE population >= 200000000;
```
