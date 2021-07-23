
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