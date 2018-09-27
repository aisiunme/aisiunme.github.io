---
title: "백준 알고리즘 문제 풀이 - 소수 찾기(1978)"
comments: true
categories:
  - Algorithm
tags:
  - 알고리즘 문제 풀이
  - 에라토스테네스의 체
---

## Baekjoon Problem #1978 - 주어진 수 중에서 소수가 몇 개인지를 출력하는 문제

주어진 수 N개 중에서 소수가 몇 개인지 찾아서 출력하는 프로그램을 작성하시오.

> 입력
> : 첫 줄에 수의 개수 N이 주어진다. N은 100이하이다. 다음으로 N개의 수가 주어지는데 수는 1,000 이하의 자연수이다.

> 출력
> : 주어진 수들 중 소수의 개수를 출력한다.

***
예제 입력 1
```
4
1 3 5 7
```
예제 출력 1
```
3
```

***
### My Solution in Python :ok_hand:

```python
result = 0
for i in map(int,input().split()):
    if i == 1: result-=1
    for j in range(2, int(i**.5)+1):
        if i % j == 0:
            result-=1
            break
    result+=1
print(result)
```

> 이번 문제에서는 소수의 개수만 출력하면 되므로, 굳이 소수로 확인된 숫자들을 저장할 필요가 없습니다.  
> 따라서 우선 전달받은 숫자가 1이라면 소수가 아니므로 변수 result 값에서 1을 뺍니다.  
> 다음으로 소수인지 아닌지 여부를 검사하여 만약 소수가 아니라면 변수 result 값에서 1을 빼고, 소수라면 1을 더하면 소수의 총 개수를 확인할 수 있습니다.

***
백준 온라인 저지 [https://www.acmicpc.net/problem/1978](https://www.acmicpc.net/problem/1978)
