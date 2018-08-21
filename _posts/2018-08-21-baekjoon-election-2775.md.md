---
title: "백준 온라인 저지 - 부녀회장이 될테야(2775)"
comments: true
categories:
  - Algorithm
tags:
  - 알고리즘 문제 풀이
---

## Baekjoon Problem #2775 - 아파트에서 규칙에 따라 각 호실의 거주자를 구하는 문제

평소 반상회에 참석하는 것을 좋아하는 주희는 이번 기회에 부녀회장이 되고 싶어 각 층의 사람들을 불러 모아 반상회를 주최하려고 한다.

이 아파트에 거주를 하려면 조건이 있는데, “a층의 b호에 살려면 자신의 아래(a-1)층에 1호부터 b호까지 사람들의 수의 합만큼 사람들을 데려와 살아야한다” 는 계약 조항을 꼭 지키고 들어와야 한다.

아파트에 비어있는 집은 없고 모든 거주민들이 이 계약 조건을 지키고 왔다고 가정했을 때, 주어지는 양의 정수 k와 n에 대해 k층에 n호에는 몇 명이 살고 있나를 출력하라. 단, 아파트에는 0층부터 있고 각층에는 1호부터 있으며, 0층에 i호에는 i명이 산다.

> 입력
> : 첫 번째 줄에 Test case의 수 T가 주어진다. 그리고 각각의 케이스마다 입력으로 첫 번째 줄에 정수 k, 두 번째 줄에 정수 n이 주어진다. (1 <= k <= 14, 1 <= n <= 14)

> 출력
> : 각각의 Test case에 대해서 해당 집에 거주민 수를 출력하라.

***
예제 입력 1
```
2
1
3
2
3
```

예제 출력 1
```
6
10
```

***
### My Solution in Python :ok_hand:

```python
for _ in range(int(input())):
    k, n = int(input()), int(input())
    
    r =[[i for i in range(1, n+1)]]  # [[0, 1, 2, ..., n]] : 0층의 입주자 수
    for i in range(1, k+1):  # 1층부터 k층까지
        for j in range(1, n+1):  # 1호부터 n호까지
            if j==1: r.append([1])  # 1호에는 무조건 1명만 입주함.
            # k층 n호에는 k-1층 1호부터 n호까지 입주자를 합한 수가 입주함.
            else: r[i].append(sum(r[i-1][:j]))
    print(r[k][n-1])
```

***
백준 온라인 저지 [https://www.acmicpc.net/problem/2775](https://www.acmicpc.net/problem/2775)
