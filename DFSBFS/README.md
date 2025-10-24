그래프를 DFS로 탐색한 결과와 BFS로 탐색한 결과를 출력하는 프로그램을 작성하시오. 단, 방문할 수 있는 정점이 여러 개인 경우에는 정점 번호가 작은 것을 먼저 방문하고, 더 이상 방문할 수 있는 점이 없는 경우 종료한다. 정점 번호는 1번부터 N번까지이다.

첫째 줄에 정점의 개수 N(1 ≤ N ≤ 1,000), 간선의 개수 M(1 ≤ M ≤ 10,000), 탐색을 시작할 정점의 번호 V가 주어진다. 다음 M개의 줄에는 간선이 연결하는 두 정점의 번호가 주어진다. 어떤 두 정점 사이에 여러 개의 간선이 있을 수 있다. 입력으로 주어지는 간선은 양방향이다.

첫째 줄에 DFS를 수행한 결과를, 그 다음 줄에는 BFS를 수행한 결과를 출력한다. V부터 방문된 점을 순서대로 출력하면 된다.

 
```
import sys
from collections import deque  

def dfs(index):
    global visited
    visited[index] = True       
    print(index, end=' ')
    
    for next in range(1, N + 1):  
        if not visited[next] and graph[index][next]:
            dfs(next)
            
# dfs와 다르게 하나의 배열 q를 더 쓴다
def bfs():                         
    global visited, q
    while q:
        cur = q.popleft()          # q의 첫번째 원소를 빼준다 
        print(cur, end=' ')        # 시작정점을 빼서 출력 
        for next in range(1, N + 1):
            if not visited[next] and graph[cur][next]:
                visited[next] = True
                q.append(next)

input = sys.stdin.readline
N, M, V = map(int, input().split())

# 1. 노드/간선 정보 저장할 2차원 배열 graph와 방문 정보 저장할 배열 visited 선언하기
graph = [[False] * (N + 1) for _ in range(N + 1)]
visited = [False] * (N + 1)

# 2. 사용자에게 노드/간선 입력받아서 graph에 넣기
for _ in range(M):  # 간선의 수만큼 입력받는다
    A, B = map(int, input().split())
    graph[A][B] = True 
    graph[B][A] = True
    
dfs(V)
print()

visited = [False] * (N + 1)
q = deque([V])
visited[V] = True
bfs()
```
