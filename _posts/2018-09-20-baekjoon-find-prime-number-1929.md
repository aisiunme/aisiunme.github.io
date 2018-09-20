---
title: "백준 알고리즘 문제 풀이 - 소수 구하기(1929)"
comments: true
categories:
  - Algorithm
tags:
  - 알고리즘 문제 풀이
  - 에라토스테네스의 체
---

## Baekjoon Problem #1929 - 두 수 사이의 존재하는 소수를 에라토스테네스의 체를 사용하여 구하는 문제

M이상 N이하의 소수를 모두 출력하는 프로그램을 작성하시오.

> 입력
> : 첫째 줄에 자연수 M과 N이 빈 칸을 사이에 두고 주어진다. (1≤M≤N≤1,000,000)

> 출력
> : 한 줄에 하나씩, 증가하는 순서대로 소수를 출력한다.

***
예제 입력 1
```
3 16
```
예제 출력 1
```
3
5
7
11
13
```

***
### My Solution in Python :ok_hand:

```python
m, n = map(int, input().split())
s = [False, False] + [True]*(n-1)
for i in range(2, int(n**0.5)+1):
    for j in range(i+i, n+1, i):
        if s[i]:
            s[j] = False
[print(i) for i in range(m, n+1) if s[i]]
```

> 위의 코드에서 변수 s에는 소수 여부를 불리언 값으로 저장합니다. 0과 1은 소수가 아니므로 False로 초기화하고 나머지는 우선 True로 초기화합니다.  
>
> 소수를 구할 때는 첫 번째 for 문처럼 2부터 (√n)+1 까지만 소수 여부를 검사하면 됩니다.
또한, 두 번째 for 문처럼 검사한 수의 배수를 모두 False로 설정해 주면 소수만이 True 값을 가지게 됩니다.

***
백준 온라인 저지 [https://www.acmicpc.net/problem/1929](https://www.acmicpc.net/problem/1929)
