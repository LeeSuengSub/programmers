### 없어진 기록 찾기
---
```
SELECT 
  O.ANIMAL_ID, 
  O.name 
FROM 
  ANIMAL_INS AS i 
  right JOIN ANIMAL_OUTS AS O on i.ANIMAL_ID = O.ANIMAL_ID 
WHERE 
  i.ANIMAL_ID is null 
ORDER BY 
  i.ANIMAL_ID

```
### 있었는데요,없었습니다
---
```
SELECT 
  pl.ID, 
  pl.NAME, 
  p.HOST_ID 
FROM 
  (
    SELECT 
      HOST_ID, 
      count(*) AS cnt 
    FROM 
      PLACES 
    GROUP BY 
      HOST_ID 
    HAVING 
      count(*)>= 2
  ) as p 
  INNER JOIN PLACES as pl on p.HOST_ID = pl.HOST_ID 
ORDER BY 
  pl.ID

```
### 오랜 기간 보호한 동물(1)
---
```
SELECT 
  i.name, 
  i.datetime 
FROM 
  ANIMAL_INS AS i 
  left join ANIMAL_OUTS AS o on i.ANIMAL_ID = o.ANIMAL_ID 
WHERE 
  o.datetime is null 
ORDER BY 
  i.datetime asc 
limit 
  3

```
### 헤비 유저가 소유한 장소
---
```
SELECT 
  pl.ID, 
  pl.NAME, 
  p.HOST_ID 
FROM 
  (
    SELECT 
      HOST_ID, 
      count(*) AS cnt 
    FROM 
      PLACES 
    GROUP BY 
      HOST_ID 
    HAVING 
      count(*)>= 2
  ) as p 
  INNER JOIN PLACES as pl on p.HOST_ID = pl.HOST_ID 
ORDER BY 
  pl.ID

```