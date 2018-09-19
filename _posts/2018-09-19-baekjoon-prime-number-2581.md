---
title: "백준 알고리즘 문제 풀이 - 소수(2581)"
comments: true
categories:
  - Algorithm
tags:
  - 알고리즘 문제 풀이
---

## Baekjoon Problem #2581 - 두 수 사이의 존재하는 소수를 구하는 문제

자연수 M과 N이 주어질 때 M이상 N이하의 자연수 중 소수인 것을 모두 골라 이들 소수의 합과 최솟값을 찾는 프로그램을 작성하시오.

예를 들어 M=60, N=100인 경우 60이상 100이하의 자연수 중 소수는 61, 67, 71, 73, 79, 83, 89, 97 총 8개가 있으므로, 이들 소수의 합은 620이고, 최솟값은 61이 된다.

> 입력
> : 입력의 첫째 줄에 M이, 둘째 줄에 N이 주어진다.  
> : M과 N은 10,000이하의 자연수이며, M은 N보다 작거나 같다.

> 출력
> : M이상 N이하의 자연수 중 소수인 것을 모두 찾아 첫째 줄에 그 합을, 둘째 줄에 그 중 최솟값을 출력한다.  
> : 단, M이상 N이하의 자연수 중 소수가 없을 경우는 첫째 줄에 -1을 출력한다.

***
예제 입력 1
```
60
100
```
예제 출력 1
```
620
61
```
***
예제 입력 2
```
64
65
```
예제 출력 2
```
-1
```

***
### My Solution in Python :ok_hand:

```python
def f(n):
    if n==1: return False
    for i in range(2, n):
        if n%i==0: return False
    return True

a=int(input())
b=int(input())
d=[i for i in range(a,b+1) if f(i)]
if len(d)==0:
    print(-1)
else:
    print(sum(d))
    print(min(d))
```

> 함수 f()는 전달받은 정수가 소수이면 True를 반환하고, 소수가 아니면 False를 반환하는 함수입니다.  
> 
> 이 함수의 성능을 높이기 위해서는 math 라이브러리에서 제곱근을 반환해 주는 sqrt() 함수를 사용하면 됩니다. 2부터 n까지가 아닌 sqrt(n)+1까지만 살펴보아도 해당 정수가 소수인지 아닌지를 판단할 수 있기 때문입니다.  
> ```python
> import math
> for i in range(2, int(math.sqrt(n))+1):
>    if n%i==0: return False
> ```
> 이때 sqrt() 함수는 실수를 반환하므로, range() 함수에 전달하기 위해서는 정수로 변환해 주어야 함에 유의해야 합니다.

***
백준 온라인 저지 [https://www.acmicpc.net/problem/2581](https://www.acmicpc.net/problem/2581)
