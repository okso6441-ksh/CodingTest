# CodingTest
> 이직을 위한 코딩 테스트 준비  
---
## [이코테](https://www.youtube.com/watch?v=m-9pAwq1o3w&list=PLRx0vPvlEmdAghTr5mXQxGpHjWqSz0dgC)  
* [도서] 이것이 취업을 위한 코딩 테스트다 with 파이썬  
## [CodeUp](https://codeup.kr/index.php)    
## [HackerRank](https://www.hackerrank.com/interview/interview-preparation-kit)   
---
## 그리디
* 탐욕: 현 상황 당장 좋은 것만 고르는 방법  
  * 정당성 분석  
> 거스름 돈, 1이 될 때까지, 곱하기 혹은 더하기, 모험가 길드    
## 구현/시뮬레이션/완전 탐색
* 소스코드로 옮기기 어려운 문제  
  * 코드가 지나치게 길때, 적절한 라이브러리를 찾아서 사용해야 할 때  
* 2차원 공간 방향 벡터  
  * dx = [0, -1, 0, 1]  
  * dy = [1, 0, -1, 0]  
> 상하좌우, 시각, 왕실의 나이트, 문자의 재정렬     
## 재귀  
* 종료조건  
  * stack  
> 팩토리얼, 최대공약수(유클리드 호제법)  
## DFS - 그래프 탐색  
* 깊이 우선 탐색  
  * 스택ㄷ/재귀 함수  
> 음료수 얼려 먹기   
## BFS - 그래프 탐색  
* 너비 우선 탐색  
  * 큐=  
> 음료수 얼려 먹기, 미로 탈출   
## 정렬
* 선택, 삽입(거의 정렬), 퀵, 계수(범위 제한, 중복 많을 때)  
## 이진 탐색
* 정렬  
* bisect_left/right   
> 특정 범위 속하는 데이터 개수  
### 파라메트릭 서치: 최적화 문제를 결정(yes/no)로 바꾸어 해결하는 기법  
> 떡볶이 떡 만들기, 정렬된 배열에서 특정 수의 개수 구하기    
## 다이나믹 프로그래밍/동적 계획법  
* 메모리 사용 수행 시간 향상  
  * 이미 계산된 결과(작은 문제) 별도의 메모리 영역에 저장하여 다시 계산하지 않음  
  * 탑 다운(하향식)-재귀적/ 보텀 업(상향식)-반복문    
* 조건: 최적 부분 구조 + 중복되는 부분 문제  
* 점화식, 메모리제이션(한번 계산된 결과를 기록해서 다시 호출되면 사용=캐싱)=> DP 테이블    
> 피보나치 수열, 개미 전사, 1로 만들기, 효율적인 화폐 구성, 금광, 병사 배치하기(LIS: 가장 긴 증가하는 수열)        
## 최단 경로
* 다익스트라: 특정 노드에서 모든 노드로의 최단 경로 계산  
  * 음의 간선 없을 때, 그리디   
  * 출발 노드 설정> 최단 거리 테이블 초기화(무한)> **방문 X 노드 중 가장 짧은 노드 선택> 최단 거리 테이블 갱신> 반복  
    * **우선순위 큐(우선순위 높으면 먼저 삭제)- 최소 힙/최대 힙(->-)    
* 플로이드 워셜: 모든 노드에서 모든 노드까지 최단 경로 모두 계산  
  * 2차원 테이블에 최단 거리 저장, 점화식  
## 그래프 이론
* 서로소 집합: 공통 원소가 없는 두 집합  
  * 합치기 찾기(Union Find), 연결성> 경로 압축(재귀 호출 부모 값 바로 갱신)    
* 사이클 판별: 같은 집합에 속하면 사이클 ㅇ, 속하지 않으면 X   
  * 무방향: 서로소 집합  
  * 유방향: DFS    
* 신장 트리: 그래프에서 모든 노드 포함하면서 사이클 존재하지 않는 부분 그래프(트리 조건)  
  * 최소 신장 트리: 그리디  
    * 크루스칼  
      * 오름차순 정렬  
      * 사이클 발생 확인    
        * 발생 ㅇ: 최소 신장 트리 포함 ㅇ  
        * 발생 X: 최소 신장 트리 포함 X  
      * 반복  
* 위상 정렬: 사이클 없는 방향 그래프(DAG) 모든 노드를 방향성 거스르지 않는 순서대로 나열        
  * 진입 차수(Indegree)/진출차수(Outdegree)  
  * 큐/DFS  
---
