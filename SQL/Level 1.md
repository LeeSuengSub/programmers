### 모든 레코드 조회하기
---
```
SELECT 
  * 
from 
  ANIMAL_INS
```
### 최댓값 구하기
---
```
SELECT 
  max(DATETIME) 
from 
  ANIMAL_INS
```
### 이름이 없는 동물의 아이디
---
```
SELECT 
  ANIMAL_ID 
from 
  ANIMAL_INS 
where 
  NAME is null
```
### 역순 정렬하기
---
```
SELECT 
  NAME, 
  DATETIME 
from 
  ANIMAL_INS 
order by 
  ANIMAL_ID desc
```
### 이름이 있는 동물의 아이디
---
```
SELECT 
  ANIMAL_ID 
from 
  ANIMAL_INS 
where 
  NAME is not null 
order by 
  ANIMAL_ID asc
```
### 아픈 동물 찾기
---
```
SELECT 
  ANIMAL_ID, 
  NAME 
from 
  ANIMAL_INS 
where 
  INTAKE_CONDITION = "Sick";
```
### 어린 동물 찾기
---
```
SELECT 
  ANIMAL_ID, 
  NAME 
from 
  ANIMAL_INS 
where 
  INTAKE_CONDITION != "Aged" 
order by 
  ANIMAL_ID
```
### 동물의 아이디와 이름
---
```
SELECT 
  ANIMAL_ID, 
  NAME 
from 
  ANIMAL_INS 
order by 
  ANIMAL_ID
```
### 여러 기준으로 정렬하기
---
```
SELECT 
  ANIMAL_ID, 
  NAME, 
  DATETIME 
from 
  ANIMAL_INS 
order by 
  NAME, 
  DATETIME desc
```
### 상위 n개 레코드
---
```
SELECT 
  NAME 
FROM 
  ANIMAL_INS 
order by 
  datetime 
limit 
  1
```