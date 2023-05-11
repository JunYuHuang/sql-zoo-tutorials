# 7 More JOIN operations

### 1.

```SQL
SELECT id, title
FROM movie
WHERE yr = 1962;
```

### 2.

```SQL
SELECT yr
FROM movie
WHERE title = 'Citizen Kane';
```

### 3.

```SQL
SELECT id, title, yr
FROM movie
WHERE title LIKE '%Star%Trek%'
ORDER BY yr;
```

### 4.

```SQL
SELECT id
FROM actor
WHERE name = 'Glenn Close';
```

### 5.

```SQL
SELECT id
FROM movie
WHERE title = 'Casablanca';
```

### 6.

```SQL
SELECT name
FROM actor JOIN casting ON casting.actorid = actor.id
WHERE movieid =
(SELECT id
 FROM movie
 WHERE title = 'Casablanca');
```

### 7.

```SQL
SELECT name
FROM actor JOIN casting ON casting.actorid = actor.id
WHERE movieid =
(SELECT id
 FROM movie
 WHERE title = 'Alien');
```

### 8.

```SQL
SELECT title
FROM movie JOIN casting ON movie.id = casting.movieid
WHERE casting.actorid =
(SELECT id
 FROM actor
 WHERE name = 'Harrison Ford');
```

### 9.

```SQL
SELECT title
FROM movie JOIN casting ON movie.id = casting.movieid
WHERE casting.actorid =
(SELECT id
 FROM actor
 WHERE name = 'Harrison Ford')
AND casting.ord != 1;
```

### 10.

```SQL
SELECT title, name
FROM movie
JOIN casting ON movie.id = casting.movieid
JOIN actor ON actor.id = casting.actorid
WHERE movie.yr = 1962
AND casting.ord = 1;
```

### 11.

```SQL
SELECT yr, COUNT(title)
FROM movie
JOIN casting ON movie.id = casting.movieid
JOIN actor ON casting.actorid = actor.id
WHERE name = 'Rock Hudson'
GROUP BY yr
HAVING COUNT(title) > 2;
```

<!-- TODO - stuck on 12. -->

### 12.

```SQL
-- failing query
SELECT title, name
FROM movie
JOIN casting ON movie.id = casting.movieid
JOIN actor ON casting.actorid = actor.id
WHERE name = 'Julie Andrews'
```

### 13.

```SQL
SELECT name
FROM actor
JOIN casting on actor.id = casting.actorid
WHERE casting.ord = 1
GROUP BY name
HAVING COUNT(name) >= 15
ORDER BY name;
```

### 14.

```SQL
SELECT title, COUNT(actorid)
FROM movie
JOIN casting ON movie.id = casting.movieid
WHERE yr = 1978
GROUP BY title
ORDER BY
COUNT(actorid) DESC,
title ASC;
```

<!-- TODO - stuck on 15. -->

### 15.

```SQL
-- failing query
SELECT name
FROM actor
JOIN casting ON actor.id = casting.actorid
JOIN movie ON casting.movieid = movie.id
WHERE actorid =
(SELECT id
 FROM actor
 WHERE name = 'Art Garfunkel')
```
