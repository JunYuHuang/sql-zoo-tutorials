# 9 Self join Quiz

### 1.

```SQL
-- option 3
SELECT DISTINCT a.name, b.name
FROM stops a
JOIN route z ON a.id = z.stop
JOIN route y ON y.num = z.num
JOIN stops b ON y.stop = b.id
WHERE a.name = 'Craiglockhart' AND b.name = 'Haymarket'
```

### 2.

```SQL
-- option 5
SELECT S2.id, S2.name, R2.company, R2.num
FROM stops S1, stops S2, route R1, route R2
WHERE S1.name = 'Haymarket' AND S1.id = R1.stop
AND R1.company = R2.company AND R1.num = R2.num
AND R2.stop = S2.id AND R2.num = '2A'
```

### 3.

```SQL
-- option 4
SELECT a.company, a.num, stopa.name, stopb.name
FROM route a
JOIN route b ON (a.company = b.company AND a.num = b.num)
JOIN stops stopa ON (a.stop = stopa.id)
JOIN stops stopb ON (b.stop = stopb.id)
WHERE stopa.name = 'Tollcross'
```
