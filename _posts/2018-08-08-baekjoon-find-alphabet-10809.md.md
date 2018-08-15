---
title: "백준 온라인 저지 - 알파벳 찾기(10809)"
comments: true
categories:
  - Algorithm
tags:
  - 알고리즘 문제 풀이
  - 문자열 처리
---

## Baekjoon Problem #10809 - 문자열 처리 문제

알파벳 소문자로만 이루어진 단어 S가 주어진다.  
각각의 알파벳에 대해서, 단어에 포함되어 있는 경우에는 처음 등장하는 위치를, 포함되어 있지 않은 경우에는 -1을 출력하는 프로그램을 작성하시오.

> 입력
> : 첫째 줄에 단어 S가 주어진다. 단어의 길이는 100을 넘지 않으며, 알파벳 소문자로만 이루어져 있다.

> 출력
> : 각각의 알파벳에 대해서, a가 처음 등장하는 위치, b가 처음 등장하는 위치, ... z가 처음 등장하는 위치를 공백으로 구분해서 출력한다.  
> : 만약, 어떤 알파벳이 단어에 포함되어 있지 않다면 -1을 출력한다.  
> : 단어의 첫 번째 글자는 0번째 위치이고, 두 번째 글자는 1번째 위치이다.

***
예제 입력 1
```
baekjoon
```

예제 출력 1
```
1 0 -1 -1 2 -1 -1 -1 -1 4 3 -1 -1 7 5 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1 -1
```

***
### My Solution in Python :ok_hand:

```python
s = input()
[print(s.find(chr(c)), end=' ') for c in range(97, 123)]
```

### Short coding Solution in Python

```python
print(*map(input().find, map(chr, range(97, 123))))
```

> 파이썬에서 asterisk를 이용한 언패킹과 map() 함수를 적절히 잘 사용하면 굉장히 심플한 코드를 작성할 수 있네요..  
> 얼른 저도 익숙해져야 할텐데..

***
백준 온라인 저지 [https://www.acmicpc.net/problem/10809](https://www.acmicpc.net/problem/10809)
