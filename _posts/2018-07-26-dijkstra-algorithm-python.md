---
title: "다익스트라 알고리즘 - 최단경로 탐색"
comments: true
categories:
  - Algorithm
tags:
  - dijkstra
  - algorithm
---

## 다익스트라 알고리즘(Dijkstra algorithm)

그래프 자료구조에서 한 정점(vertex)에서 다른 정점까지의 최단 경로를 찾고자 할 때 깊이 우선 탐색(DFS)이나 너비 우선 탐색(BFS)를 사용하면 가장 적은 수의 간선(edge)을 지나는 최단 경로를 찾을 수 있습니다.

하지만 가중치를 가지는 방향 그래프에서는 더 많은 간선을 거치더라도 가중치의 합이 더 적은 경로(path)가 존재할 수 있습니다. 따라서 가중치까지 고려한 최단 경로를 찾기 위해서는 DFS나 BFS가 아닌 다른 알고리즘을 사용해야만 합니다.

이때 가장 손쉽게 사용할 수 있는 알고리즘이 바로 다익스트라 알고리즘입니다. 

다익스트라 알고리즘은 다음과 같이 간단한 단계를 거쳐 최단 경로를 찾습니다.

1. 시작 정점과 인접한 정점들 중 가중치가 가장 작은 정점을 찾습니다.
2. 해당 정점에서 인접한 정점들과 연결되는 간선의 가중치를 조사하여, 이를 통해 인접 정점까지의 최단 경로를 수정합니다.
3. 그래프의 모든 정점에 대하여 1과 2를 반복합니다.
4. 시작 정점에서 목표 정점까지의 최단 경로를 찾습니다.

위의 알고리즘을 파이썬으로 구현한 예제는 다음과 같습니다.
```python
import heapq
def dijkstra(graph, start):
    distances = {vertex: float('inf') for vertex in graph}
    distances[start] = 0

    queue = []
    for vertex, distance in distances.items():
        heapq.heappush(queue, [vertex, distance])
    
    while queue:
        current_vertex, current_distance = heapq.heappop(queue)

        for adjacent, weight in graph[current_vertex].items():
            distance = distances[current_vertex] + weight

            if distance < distances[adjacent]:
                distances[adjacent] = distance
    
    return distances

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