# 8 Using NULL Quiz

### 1.

```SQL
SELECT teacher.name, dept.name
FROM teacher
LEFT OUTER JOIN dept ON (teacher.dept = dept.id)
```

### 2.

```SQL
SELECT dept.name
FROM teacher
JOIN dept ON (dept.id = teacher.dept)
WHERE teacher.name = 'Cutflower'
```

### 3.

```SQL
SELECT dept.name, COUNT(teacher.name)
FROM teacher
RIGHT JOIN dept ON dept.id = teacher.dept
GROUP BY dept.name
```

### 4.

```
display 0 in result column for all teachers without department
```

### 5.

```
'four' for Throd
```

### 6.

```
Table-A
```
