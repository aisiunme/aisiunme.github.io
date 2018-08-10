---
title: "백준 온라인 저지 - OX퀴즈(8958)"
comments: true
categories:
  - Algorithm
tags:
  - 알고리즘 문제 풀이
---

## Baekjoon Problem #8958 - OX퀴즈

"OOXXOXXOOO"와 같은 OX퀴즈의 결과가 있다. O는 문제를 맞은 것이고, X는 문제를 틀린 것이다.  
문제를 맞은 경우 그 문제의 점수는 그 문제까지 연속된 O의 개수가 된다.  
예를 들어, 문제의 10번째 O의 점수는 3이 된다.

"OOXXOXXOOO"의 점수는 1+2+0+0+1+0+0+1+2+3 = 10점이다.

OX퀴즈의 결과가 주어졌을 때, 점수를 구하는 프로그램을 작성하시오.

> 입력
> : 첫째 줄에 테스트 케이스의 개수가 주어진다. 각 테스트 케이스는 한 줄로 이루어져 있고, 길이가 0보다 크고 80보다 작은 문자열이 주어진다. 문자열은 O와 X만으로 이루어져 있다.

> 출력
> : 각 테스트 케이스마다 점수를 출력한다.

***
예제 입력 1
```
5
OOXXOXXOOO
OOXXOOXXOO
OXOXOXOXOXOXOX
OOOOOOOOOO
OOOOXOOOOXOOOOX
```

예제 출력 1
```
10
9
7
55
30
```

***
### My Solution in Python :ok_hand:

```python
for _ in range(int(input())):
    print(sum([len(i) * (len(i)+1)//2 for i in input().split('X')]))
```

> 파이썬에서 언더스코어(_)는 다양한 용도로 사용됩니다.
> 
> 1. 반복문이나 언패킹 시 해당 값을 사용하지 않을 경우 값을 무시하기 위해 사용합니다.
> 2. 파이썬 인터프리터에서 마지막으로 실행된 명령문의 결과값이 자동으로 언더스코어(_)에 저장됩니다.

***
백준 온라인 저지 [https://www.acmicpc.net/problem/8958](https://www.acmicpc.net/problem/8958)
