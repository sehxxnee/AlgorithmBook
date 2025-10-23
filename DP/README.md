
# Dynamic Programming : 기록하며 풀기

- 복잡한 문제를 여러 개의 작은 문제로 나누어 푸는 방법이다.  
- 특정 범위까지의 값을 구하기 위해 그보다 작은 범위의 값을 이용해 효율적으로 계산한다.  
- 즉, **Memoization**을 통해 큰 문제를 반복되는 작은 문제로 나누어 해결한다.


<br>


## Divide and Conquer와의 차이점

| 비교 항목 | Dynamic Programming | Divide and Conquer |
|------------|---------------------|--------------------|
| 문제 분할 방식 | 동일한 부분 문제가 반복됨 | 부분 문제가 서로 다름 |
| 핵심 아이디어 | 이전 계산 결과를 재활용 (Memoization) | 각 부분 문제를 독립적으로 해결 |
| 예시 | 피보나치 수열, 배낭 문제 | 병합 정렬, 퀵 정렬 |



<br>


## Memoization

> 동일한 계산을 반복해야 할 경우, 한 번 계산한 결과를 저장해 두었다가 재사용하는 방식

- 장점: 시간 복잡도를 줄일 수 있음  
- 단점: 공간(메모리) 사용량이 늘어남  
- 핵심 개념: 공간 비용을 이용하여 시간 비용을 절약한다.



<br>


## DP를 사용할 수 있는 조건

### 1. Overlapping Subproblems  
> 동일한 작은 문제가 반복되어 나타나는 경우

예: 피보나치 수열, 이항 계수

<img width="3252" height="800" alt="Fibonacci 예시" src="https://github.com/user-attachments/assets/90d23e2a-67fd-44b9-a649-fb3489e44457" />



### 2️. Optimal Substructure  
> 부분 문제의 최적해를 이용해 전체 문제의 최적해를 구할 수 있는 경우

예: 최단 경로, 배낭 문제 

<img width="1548" height="830" alt="Optimal Substructure 예시" src="https://github.com/user-attachments/assets/e9317ffc-cbf0-495d-bf9b-7b10f72fcc19" />



