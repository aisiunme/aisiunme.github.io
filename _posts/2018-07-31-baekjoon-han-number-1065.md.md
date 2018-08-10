---
title: "백준 온라인 저지 - 한수(1065)"
comments: true
categories:
  - Algorithm
tags:
  - 알고리즘 문제 풀이
  - 브루트 포스
  - 탐색
---

## Baekjoon Problem #1065 - 한수

어떤 양의 정수 X의 자리수가 등차수열을 이룬다면, 그 수를 한수라고 한다. 등차수열은 연속된 두 개의 수의 차이가 일정한 수열을 말한다. N이 주어졌을 때, 1보다 크거나 같고, N보다 작거나 같은 한수의 개수를 출력하는 프로그램을 작성하시오. 

> 입력
> : 첫째 줄에 1,000보다 작거나 같은 자연수 N이 주어진다.

> 출력
> : 첫째 줄에 1보다 크거나 같고, N보다 작거나 같은 한수의 개수를 출력한다.

***
예제 입력 1
```
110
```

예제 출력 1
```
99
```

***
### My Solution in Python :ok_hand:

```python
print(sum(i//100 - i//10%10 == i//10%10 - i%10 or i<100 for i in range(1, int(input())+1)))
```

> 파이썬에서 i//100은 백의 자리수, i//10%10은 십의 자리수, i%10은 일의 자리수를 각각 반환합니다.

***
백준 온라인 저지 [https://www.acmicpc.net/problem/1065](https://www.acmicpc.net/problem/1065)
