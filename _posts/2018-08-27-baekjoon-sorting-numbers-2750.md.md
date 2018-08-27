---
title: "백준 온라인 저지 - 수 정렬하기(2750)"
comments: true
categories:
  - Algorithm
tags:
  - 알고리즘 문제 풀이
---

## Baekjoon Problem #2750 - 간단한 정렬 문제

N개의 수가 주어졌을 때, 이를 오름차순으로 정렬하는 프로그램을 작성하시오.

> 입력
> : 첫째 줄에 수의 개수 N(1 ≤ N ≤ 1,000)이 주어진다. 둘째 줄부터 N개의 줄에는 숫자가 주어진다. 이 수는 절대값이 1,000보다 작거나 같은 정수이다. 수는 중복되지 않는다.

> 출력
> : 첫째 줄부터 N개의 줄에 오름차순으로 정렬한 결과를 한 줄에 하나씩 출력한다.

***
예제 입력 1
```
5
5
2
3
4
1
```

예제 출력 1
```
1
2
3
4
5
```

***
### My Solution in Python :ok_hand:

```python
data = [int(input()) for _ in range(int(input()))]
for i in range(len(data)):  # 가장 간단한 선택 정렬
    min_index = data.index(min(data[i:]))  # 최솟값의 인덱스 찾기
    # 최솟값과 가장 맨 앞의 데이터를 서로 자리 바꿈 
    data[i], data[min_index] = data[min_index], data[i] 
[print(i) for i in data]
```

> 위의 파이썬 코드는 가장 간단한 정렬 알고리즘인 선택 정렬을 구현한 예제입니다.

```python
[print(i) for i in sorted([int(input()) for _ in range(int(input()))])]
```

> 하지만 내장함수인 sorted() 함수를 사용하면 데이터를 더욱 간단하게 정렬할 수 있습니다.

***
백준 온라인 저지 [https://www.acmicpc.net/problem/2750](https://www.acmicpc.net/problem/2750)
