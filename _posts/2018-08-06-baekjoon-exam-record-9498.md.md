---
title: "백준 온라인 저지 - 시험 성적(9498)"
comments: true
categories:
  - Algorithm
tags:
  - 구현
---

## Baekjoon Problem #9498 - 시험 성적

시험 점수를 입력받아 90 ~ 100점은 A, 80 ~ 89점은 B, 70 ~ 79점은 C, 60 ~ 69점은 D, 나머지 점수는 F를 출력하는 프로그램을 작성하시오.

입력
: 첫째 줄에 시험 점수가 주어진다.  
: 시험 점수는 0보다 크거나 같고, 100보다 작거나 같은 자연수이다.

출력
: 시험 성적을 출력한다.

예제 입력 1
```
100
```

예제 출력 1
```
A
```

알고리즘 분류
: 구현

***
### My Solution in Python :ok_hand:

```python
s = int(input())

if s >= 90: print('A')
elif s >= 80: print('B')
elif s >= 70: print('C')
elif s >= 60: print('D')
else: print('F')
```

***
### Short coding Solution in Python

```python
print("FFFFFFDCBAA"[int(input())//10])
```

> 문자열에서 입력 받은 점수를 10으로 나눈 몫에 해당하는 문자를 출력하는 방식입니다.  
> 만약 65를 입력받으면 10으로 나눈 몫이 6이 되므로, 일곱 번째 문자인 D가 출력되네요.  
> 
> 파이썬의 숏코딩이란... 하지만, 숏코딩이 꼭 좋다고만은 할 수 없습니다.  
> 숏코딩은 위의 코드에 비해 코드의 길이는 확실히 줄어들지만, 가독성도 그만큼 같이 줄어든다는 사실!!  
>
> 언제나 유념하시길~ pythonic을 목표로!!

***
백준 온라인 저지 [https://www.acmicpc.net/problem/9498](https://www.acmicpc.net/problem/9498)
