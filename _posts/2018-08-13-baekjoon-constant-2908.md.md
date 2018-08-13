---
title: "백준 온라인 저지 - 상수(2908)"
comments: true
categories:
  - Algorithm
tags:
  - 알고리즘 문제 풀이
  - 문자열 처리
---

## Baekjoon Problem #2908 - 상수

상근이의 동생 상수는 수학을 정말 못한다. 상수는 숫자를 읽는데 문제가 있다. 이렇게 수학을 못하는 상수를 위해서 상근이는 수의 크기를 비교하는 문제를 내주었다. 상근이는 세 자리 숫자 두 개를 칠판에 써주었다. 그 다음에 크기가 큰 수를 말해보라고 했다.

상수는 수를 다른 사람과 다르게 거꾸로 읽는다. 예를 들어, 734과 893을 칠판에 적었다면, 상수는 이 수를 437과 398로 읽는다. 따라서, 상수는 두 수중 큰 수인 437을 큰 수라고 말할 것이다.

두 수가 주어졌을 때, 상수의 대답을 출력하는 프로그램을 작성하시오.

> 입력
> : 첫째 줄에 상근이가 칠판에 적은 두 수 A와 B가 주어진다. 두 수는 같지 않은 세 자리 수이며, 0이 포함되어 있지 않다.

> 출력
> : 첫째 줄에 상수의 대답을 출력한다.

***
예제 입력 1
```
734 893
```

예제 출력 1
```
437
```

***
### My Solution in Python :ok_hand:

```python
a, b = input().split()
ra = ''.join(reversed(a))
rb = ''.join(reversed(b))
print(ra) if int(ra) > int(rb) else print(rb)
```

> reversed () 함수의 반환값은 reversed 객체이므로, join() 함수를 사용하여 문자열로 변환하여 비교해야 합니다.


### Short coding in Python

```python
print(max(input()[::-1].split()))
```

> 리스트 슬라이싱에서 [::-1]은 역순의 리스트를 반환합니다.  
> 두 값의 비교를 조건문이 아닌 max() 함수를 사용하는 것도 숏코딩의 팁!!

***
백준 온라인 저지 [https://www.acmicpc.net/problem/2908](https://www.acmicpc.net/problem/2908)
