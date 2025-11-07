파이썬으로 큐를 구현하는 방법은 대표적으로 두 가지가 있다. 
**`list`를 사용하는 방법**과 **`queue` 라이브러리를 사용하는 방법**이다.

### 1. `list`로 큐 구현하기

``` 
# 큐 초기화
queue = list()

# 요소 추가: append()
queue.append(0)
queue.append(1)
queue.append(2)

# 요소 삭제: del 키워드 또는 pop(0) 함수 사용
del queue[0]   # 요소 0 제거
queue.pop(0)   # 요소 1 제거

# 결과 출력
print(queue) # 출력: [2]
```
### 2. queue 라이브러리 사용하기
파이썬의 queue 라이브러리에는 Queue() (FIFO), LifoQueue() (LIFO), PriorityQueue() (우선순위)가 존재한다.

A. Queue() (선입선출, FIFO)
```

import queue

# 큐 초기화 (FIFO)
queue = queue.Queue()

# 요소 추가: put()
queue.put(0)
queue.put(1)
queue.put(2)

# 요소 제거: get()
removed_element = queue.get() # 가장 먼저 추가된 요소 0 제거

# 큐 크기 확인: qsize()
size = queue.qsize()

# 결과 출력
print(f"제거된 요소: {removed_element}") # 제거된 요소: 0
print(f"남은 요소 개수: {size}") # 남은 요소 개수: 2
설명: Queue()는 선입선출(FIFO) 구조이므로, get() 함수를 수행할 경우, 가장 먼저 추가된 요소 **0**이 제거된다.
```
B. LifoQueue() (후입선출, LIFO)
```

import queue

# 큐 초기화 (LIFO)
queue = queue.LifoQueue()

# 요소 추가: put()
queue.put(0)
queue.put(1)
queue.put(2)

# 요소 제거: get()
removed_element = queue.get() # 가장 마지막에 추가된 요소 2 제거

# 큐 크기 확인: qsize()
size = queue.qsize()

# 결과 출력
print(f"제거된 요소: {removed_element}") # 제거된 요소: 2
print(f"남은 요소 개수: {size}") # 남은 요소 개수: 2
```
설명: LifoQueue()는 후입선출(LIFO) 구조이므로, get() 함수를 수행할 경우, 가장 **마지막에 추가된 요소 2**가 제거된다. (스택처럼 동작)

C. PriorityQueue() (우선순위) 
```
import queue

# 큐 초기화 (우선순위)
queue = queue.PriorityQueue()

# 요소 추가: put((우선순위, 값))
queue.put((5, 0))
queue.put((10, 1))
queue.put((7, 2))

# 요소 제거: get()
removed_element = queue.get() # 우선순위가 가장 높은 (값이 가장 작은) 요소 제거

# 큐 크기 확인: qsize()
size = queue.qsize()

# 결과 출력
print(f"제거된 요소: {removed_element}") # 제거된 요소: (5, 0)
print(f"남은 요소 개수: {size}") # 남은 요소 개수: 2
```
