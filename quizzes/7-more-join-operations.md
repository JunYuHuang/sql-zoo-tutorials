# 6 More JOIN Operations Quiz (JOIN Quiz 2)

### 1.

```SQL
SELECT name
FROM actor INNER JOIN movie ON actor.id = director
WHERE gross < budget
```

### 2.

```SQL
SELECT *
FROM actor
JOIN casting ON actor.id = actorid
JOIN movie ON movie.id = movieid
```

### 3.

```SQL
SELECT name, COUNT(movieid)
FROM casting
JOIN actor ON actorid=actor.id
WHERE name LIKE 'John %'
GROUP BY name
ORDER BY 2 DESC
```

### 4.

```
Table-B
```

### 5.

```SQL
SELECT name
FROM movie
JOIN casting ON movie.id = movieid
JOIN actor ON actor.id = actorid
WHERE ord = 1 AND director = 351
```

### 6.

```
* link the director column in movies with the primary key in actor
* connect the primary keys of movie and actor via the casting table
```

### 7.

```
Table-B
```
