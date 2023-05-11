# 9 Self join

### 1.

```SQL
SELECT COUNT(*) FROM stops;
```

### 2.

```SQL
SELECT id
FROM stops
WHERE name = 'Craiglockhart';
```

### 3.

```SQL
SELECT id, name
FROM stops
JOIN route ON stops.id = route.stop
WHERE num = '4'
AND company = 'LRT';
```

### 4.

```SQL
SELECT company, num, COUNT(*)
FROM route
WHERE stop = 149
OR stop = 53
GROUP BY company, num
HAVING COUNT(*) = 2;
```

### 5.

```SQL
SELECT a.company, a.num, a.stop, b.stop
FROM route a
JOIN route b
ON
(a.company = b.company AND
 a.num = b.num)
WHERE a.stop = 53
AND b.stop = 149;
```

### 6.

```SQL
SELECT a.company, a.num, stop_a.name, stop_b.name
FROM route a
JOIN route b
ON (a.company = b.company AND a.num = b.num)
JOIN stops stop_a ON (a.stop = stop_a.id)
JOIN stops stop_b ON (b.stop = stop_b.id)
WHERE stop_a.name = 'Craiglockhart'
AND stop_b.name = 'London Road';
```

### 7.

```SQL
SELECT DISTINCT a.company, a.num
FROM route a
JOIN route b
ON
(a.company = b.company AND
 a.num = b.num)
WHERE a.stop = 115
AND b.stop = 137
```

### 8.

```SQL
SELECT route_a.company, route_a.num
FROM route route_a
JOIN route route_b
ON
(route_a.company = route_b.company AND
 route_a.num = route_b.num)
JOIN stops stop_a ON (route_a.stop = stop_a.id)
JOIN stops stop_b ON (route_b.stop = stop_b.id)
WHERE stop_a.name = 'Craiglockhart'
AND stop_b.name = 'Tollcross';
```

### 9.

```SQL
SELECT stop_b.name, route_a.company, route_a.num
FROM route route_a
JOIN route route_b
ON
(route_a.company = route_b.company AND
 route_a.num = route_b.num)
JOIN stops stop_a ON (route_a.stop = stop_a.id)
JOIN stops stop_b ON (route_b.stop = stop_b.id)
WHERE stop_a.name = 'Craiglockhart'
AND route_a.company = 'LRT'
```

### 10.

```SQL
-- returns right rows but order is off
-- modified based on codyloyd's solution
-- https://github.com/codyloyd/sqlzoo-solutions/blob/master/SQLZOO_solutions.md#self-join
SELECT
route_a.num, route_a.company,
stop_b.name,
route_c.num, route_c.company
FROM route route_a
JOIN route route_b
ON
(route_a.company = route_b.company AND
 route_a.num = route_b.num)
JOIN
(route route_c JOIN route route_d ON
 (route_c.company = route_d.company AND
  route_c.num = route_d.num))
JOIN stops stop_a ON (route_a.stop = stop_a.id)
JOIN stops stop_b ON (route_b.stop = stop_b.id)
JOIN stops stop_c ON (route_c.stop = stop_c.id)
JOIN stops stop_d ON (route_d.stop = stop_d.id)
WHERE stop_a.name = 'Craiglockhart'
AND stop_d.name = 'Lochend'
AND stop_b.name = stop_c.name
-- ORDER BY
-- LENGTH(route_a.num), route_b.num,
-- stop_b.name,
-- LENGTH(route_c.num), route_d.num;
```
