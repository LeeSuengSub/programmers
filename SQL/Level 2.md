### 고양이와 개는 몇 마리 있을까
---
```
SELECT 
  ANIMAL_TYPE, 
  count(*) 
from 
  ANIMAL_INS 
group by 
  ANIMAL_TYPE 
order by 
  count(*)
```
### 루시와 엘라 찾기
---
```
SELECT 
  ANIMAL_ID, 
  NAME, 
  SEX_UPON_INTAKE 
from 
  ANIMAL_INS 
where 
  name = "Lucy" 
  or name = "Ella" 
  or name = "Pickle" 
  or name = "Roger" 
  or name = "Sabrina" 
  or name = "Mitty"
```
### 최솟값 구하기
---
```
SELECT 
  min(datetime) 
from 
  ANIMAL_INS
```
### 동명 동물 수 찾기
---
```
SELECT 
  name, 
  count(name) 
from 
  ANIMAL_INS 
WHERE 
  name is not null 
group by 
  name 
having 
  count(name)>= 2 
order by 
  name
```
### 이름에 el이 들어가는 동물 찾기
---
```
SELECT 
  ANIMAL_ID, 
  NAME 
FROM 
  ANIMAL_INS 
WHERE 
  name like "%el%" 
  and ANIMAL_TYPE = "Dog" 
ORDER BY 
  NAME
```
### 동물 수 구하기
---
```
SELECT 
  count(*) 
FROM 
  ANIMAL_INS
```
### 입양 시각 구하기(1)
---
```
SELECT 
  date_format(DATETIME, "%H") as HOUR, 
  count(*) 
FROM 
  ANIMAL_OUTS 
WHERE 
  date_format(datetime, "%H") >= 9 
  and date_format(datetime, "%H") < 20 
group by 
  date_format(datetime, "%H") 
order by 
  HOUR asc
```
### NULL 처리하기
---
```
SELECT 
  ANIMAL_TYPE, 
  IFNULL(NAME, "No name"), 
  SEX_UPON_INTAKE 
FROM 
  ANIMAL_INS 
ORDER BY 
  ANIMAL_ID
```
### 중성화 여부 파악하기
---
```
SELECT 
  ANIMAL_ID, 
  NAME, 
  if(
    substring(SEX_UPON_INTAKE, 1, 2) in ('Ne', 'Sp'), 
    'O', 
    'X'
  ) 
FROM 
  ANIMAL_INS
```
### 중복 제거하기
---
```
SELECT
count(distinct(name))
FROM ANIMAL_INS
WHERE name is not null
```
### DATETIME에서 DATE로 형 변환
---
```
SELECT 
  ANIMAL_ID, 
  NAME, 
  date_format(datetime, "%Y-%m-%d") as 날짜 
FROM 
  ANIMAL_INS 
ORDER BY 
  ANIMAL_ID
```