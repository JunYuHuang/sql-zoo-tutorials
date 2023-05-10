# 8 Using NULL

### 1.

```SQL
SELECT name
FROM teacher
WHERE dept IS NULL;
```

### 2.

```SQL
SELECT teacher.name, dept.name
FROM teacher
INNER JOIN dept
ON (teacher.dept = dept.id);
```

### 3.

```SQL
SELECT teacher.name, dept.name
FROM teacher
LEFT JOIN dept
ON (teacher.dept = dept.id);
```

### 4.

```SQL
SELECT teacher.name, dept.name
FROM teacher
RIGHT JOIN dept
ON (teacher.dept = dept.id);
```

### 5.

```SQL
SELECT name, COALESCE(mobile, '07986 444 2266')
FROM teacher;
```

### 6.

```SQL
SELECT teacher.name, COALESCE(dept.name, 'None')
FROM teacher
LEFT JOIN dept ON teacher.dept = dept.id;
```

### 7.

```SQL
SELECT COUNT(name), COUNT(mobile)
FROM teacher;
```

### 8.

```SQL
SELECT dept.name, COUNT(teacher.name)
FROM teacher
RIGHT JOIN dept ON teacher.dept = dept.id
GROUP BY dept.name;
```

### 9.

```SQL
SELECT name,
CASE
  WHEN dept IN (1, 2) THEN 'Sci'
  ELSE 'Art'
END
FROM teacher;
```

### 10.

```SQL
SELECT name,
CASE
  WHEN dept IN (1, 2) THEN 'Sci'
  WHEN dept = 3 THEN 'Art'
  ELSE 'None'
END
FROM teacher;
```
