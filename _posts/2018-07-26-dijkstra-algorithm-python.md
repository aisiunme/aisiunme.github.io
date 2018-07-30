---
title: "다익스트라 알고리즘 - 최단경로 탐색"
comments: true
categories:
  - 알고리즘
tags:
  - algorithm
  - 다익스트라(Dijkstra)
---

## 다익스트라 알고리즘(Dijkstra algorithm)

그래프 자료구조에서 하나의 정점(vertex)에서 다른 정점까지의 최단 경로를 찾고자 할 때는 깊이 우선 탐색(DFS)이나 너비 우선 탐색(BFS)를 사용할 수 있습니다. 하지만 DFS나 BFS는 가장 적은 수의 간선(edge)을 지나는 최단 경로만을 찾아줍니다.

가중치를 가지는 방향 그래프에서는 더 많은 간선을 거치더라도 가중치의 합이 더 적은 경로(path)가 존재할 수 있습니다. 따라서 가중치까지 고려한 최단 경로를 찾기 위해서는 DFS나 BFS가 아닌 다른 알고리즘을 사용해야만 합니다.

이때 가장 손쉽게 사용할 수 있는 알고리즘이 바로 다익스트라 알고리즘입니다. 

다익스트라 알고리즘은 다음과 같이 간단한 단계를 거쳐 최단 경로를 찾습니다.

1. 시작 정점과 인접한 정점들 중 가중치가 가장 작은 정점을 찾습니다.
2. 해당 정점에서 인접한 정점들과 연결되는 간선의 가중치를 조사하여, 이를 통해 인접 정점까지의 최단 경로를 수정합니다.
3. 그래프의 모든 정점에 대하여 1과 2를 반복합니다.
4. 시작 정점에서 목표 정점까지의 최단 경로를 찾습니다.

위의 알고리즘을 파이썬으로 구현한 예제는 다음과 같습니다.
```python
import heapq

# 탐색할 그래프와 시작 정점을 인수로 전달받습니다.
def dijkstra(graph, start):
    # 시작 정점에서 각 정점까지의 거리를 저장할 딕셔너리를 생성하고, 무한대로 초기화합니다.
    distances = {vertex: float('inf') for vertex in graph}
    distances[start] = 0
    
    # 모든 정점이 저장될 큐를 생성합니다.
    queue = []
    for vertex, distance in distances.items():
        # 파이썬의 heapq 모듈을 사용하여 큐를 우선순위 큐로 저장합니다.
        heapq.heappush(queue, [vertex, distance])
    
    # 큐의 저장된 모든 정점에 대해서
    while queue:
        
        # 큐에서 정점을 하나씩 꺼내 인접한 정점들의 가중치를 모두 확인하여 업데이트합니다.
        current_vertex, current_distance = heapq.heappop(queue)
        for adjacent, weight in graph[current_vertex].items():
            distance = distances[current_vertex] + weight
            # 만약 시작 정점에서 인접 정점으로 바로 가는 것보다 현재 정점을 통해 가는 것이 더 가까울 경우에는
            if distance < distances[adjacent]:
                # 거리를 업데이트합니다.
                distances[adjacent] = distance
    
    return distances

# 방향 그래프
mygraph = {
    'A': {'B': 8, 'C': 1, 'D': 2},
    'B': {},
    'C': {'B': 5, 'D': 2},
    'D': {'E': 3, 'F': 5},
    'E': {'F': 1},
    'F': {'A': 5}
}

print(dijkstra(mygraph, 'A'))
```
실행결과
```
{'A': 0, 'B': 6, 'C': 1, 'D': 2, 'E': 5, 'F': 6}
```

만약 음의 가중치를 가지는 정점이 하나라도 존재하면, 해당 그래프에 대해 다익스트라 알고리즘은 정확한 동작을 수행하지 못합니다.
따라서 그 경우에는 실행 속도는 다익스트라 알고리즘보다 느리지만, 음의 가중치까지 처리할 수 있는 벨먼-포드 알고리즘(Bellman-Ford algorithm)을 사용해야 합니다.