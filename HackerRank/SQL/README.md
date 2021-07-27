
[Weather Observation Station 4](https://www.hackerrank.com/challenges/weather-observation-station-4/problem)
* Q. 총 카운트 - 도시 개수  
```sql
SELECT COUNT(CITY) - COUNT(DISTINCT CITY) FROM STATION;
```
---
[Weather Observation Station 6](https://www.hackerrank.com/challenges/weather-observation-station-6/problem)
* Q. 모음(aeiou)으로 시작하는 도시(정규식); MySQL  
```sql
SELECT DISTINCT city FROM station WHERE city REGEXP "^[aeiou].*";
```
---
[Weather Observation Station 7](https://www.hackerrank.com/challenges/weather-observation-station-7/problem)
* Q. 모음(aeiou)으로 끝나는 도시; MySQL  
```sql
SELECT DISTINCT CITY FROM STATION WHERE RIGHT(CITY,1) IN ('a','i','e','o','u');
```
---
[Weather Observation Station 8](https://www.hackerrank.com/challenges/weather-observation-station-8/problem)
* Q. 모음(aeiou)으로 시작하고 끝나는 도시(정규식); MySQL  
```sql
select DISTINCT CITY 
  from station 
 where city regexp '[aeiou]$' 
   and city in (SELECT CITY FROM STATION WHERE CITY REGEXP '^[aeiou]');

select distinct city from station 
where left(city,1) in ('a','e','i','o','u') 
and right(city, 1) in ('a','e','i','o','u');
```
---
[Draw The Triangle 1](https://www.hackerrank.com/challenges/draw-the-triangle-1/problem)
* 하나씩 줄어드는 * 그리기; Mysql 
```sql
set @number = 21;
select repeat('* ', @number := @number - 1) 
  from information_schema.tables;
```
---
[Draw The Triangle 2](https://www.hackerrank.com/challenges/draw-the-triangle-2/problem)
* 하나씩 줄어드는 * 그리기; Mysql 
```sql
set @row := 0;
select repeat('* ', @row := @row + 1) 
  from information_schema.tables 
 where @row < 20
```
---
[The Report](https://www.hackerrank.com/challenges/the-report/problem)
* IF로 DECODE; Mysql 
```sql
SELECT IF(GRADE < 8, NULL, NAME), GRADE, MARKS
  FROM STUDENTS JOIN GRADES
 WHERE MARKS BETWEEN MIN_MARK AND MAX_MARK
 ORDER BY GRADE DESC, NAME
```
---
[Occupations](https://www.hackerrank.com/challenges/occupations/problem)
* pivot; Mysql 
```sql
set @r1=0, @r2=0, @r3=0, @r4=0;
select min(Doctor), min(Professor), min(Singer), min(Actor)
from(
  select case when Occupation='Doctor' then (@r1:=@r1+1)
            when Occupation='Professor' then (@r2:=@r2+1)
            when Occupation='Singer' then (@r3:=@r3+1)
            when Occupation='Actor' then (@r4:=@r4+1) end as RowNumber,
    case when Occupation='Doctor' then Name end as Doctor,
    case when Occupation='Professor' then Name end as Professor,
    case when Occupation='Singer' then Name end as Singer,
    case when Occupation='Actor' then Name end as Actor
  from OCCUPATIONS
  order by Name
) Temp
group by RowNumber
```
---
[Binary Tree Nodes](https://www.hackerrank.com/challenges/binary-search-tree-1/problem)
* tree; Mysql 
```sql
SELECT CASE
	WHEN P IS NULL THEN CONCAT(N, ' Root')
	WHEN N IN (SELECT DISTINCT P FROM BST) THEN CONCAT(N, ' Inner')
	ELSE CONCAT(N, ' Leaf')
	END
FROM BST
ORDER BY N ASC
```

---
[SQL Project Planning](https://www.hackerrank.com/challenges/sql-projects/problem)
* 연속적 날짜 가지는 프로젝트를 기간이 가장 긴 순으로 나열; Mysql 
```sql
SET sql_mode = '';
SELECT Start_Date, End_Date
FROM 
    (SELECT Start_Date FROM Projects WHERE Start_Date NOT IN (SELECT End_Date FROM Projects)) a,
    (SELECT End_Date FROM Projects WHERE End_Date NOT IN (SELECT Start_Date FROM Projects)) b 
WHERE Start_Date < End_Date
GROUP BY Start_Date 
ORDER BY DATEDIFF(End_Date, Start_Date), Start_Date
```
```sql
SELECT Start_Date, MIN(End_Date)
FROM 
    (SELECT Start_Date FROM Projects WHERE Start_Date NOT IN (SELECT End_Date FROM Projects)) a,
    (SELECT end_date FROM PROJECTS WHERE end_date NOT IN (SELECT start_date FROM PROJECTS)) b
where start_date < end_date
GROUP BY start_date
ORDER BY datediff(start_date, MIN(end_date)) DESC, start_date
```