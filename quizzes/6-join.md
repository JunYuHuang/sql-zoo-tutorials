# 6 JOIN Quiz

### 1.

```SQL
game JOIN goal ON (id = matchid)
```

### 2.

```
matchid, teamid, player, gtime, id, teamname, coach
```

### 3.

```SQL
-- option 1
SELECT player, teamid, COUNT(*)
FROM game JOIN goal ON matchid = id
WHERE (team1 = "GRE" OR team2 = "GRE")
AND teamid != 'GRE'
GROUP BY player, teamid
```

### 4.

```
Table 1
```

### 5.

```SQL
SELECT DISTINCT player, teamid
FROM game JOIN goal ON matchid = id
WHERE stadium = 'National Stadium, Warsaw'
AND (team1 = 'POL' OR team2 = 'POL')
AND teamid != 'POL'
```

### 6.

```SQL
SELECT DISTINCT player, teamid, gtime
FROM game JOIN goal ON matchid = id
WHERE stadium = 'Stadion Miejski (Wroclaw)'
AND
(( teamid = team2 AND team1 != 'ITA') OR
 ( teamid = team1 AND team2 != 'ITA'))
```

### 7.

```
Table 2
```
