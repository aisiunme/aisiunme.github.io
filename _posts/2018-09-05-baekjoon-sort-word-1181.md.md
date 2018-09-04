---
title: "백준 온라인 저지 -단어 정렬(1181)"
comments: true
categories:
  - Algorithm
tags:
  - 알고리즘 문제 풀이
---

## Baekjoon Problem #1427 - 단어를 길이와 사전순으로 정렬하는 문제

알파벳 소문자로 이루어진 N개의 단어가 들어오면 아래와 같은 조건에 따라 정렬하는 프로그램을 작성하시오.

1. 길이가 짧은 것부터  
2. 길이가 같으면 사전 순으로

> 입력
> : 첫째 줄에 단어의 개수 N이 주어진다. (1≤N≤20,000) 둘째 줄부터 N개의 줄에 걸쳐 알파벳 소문자로 이루어진 단어가 한 줄에 하나씩 주어진다. 주어지는 문자열의 길이는 50을 넘지 않는다.

> 출력
> : 조건에 따라 정렬하여 단어들을 출력한다. 단, 같은 단어가 여러 번 입력된 경우에는 한 번씩만 출력한다.

***
예제 입력 1
```
13
but
i
wont
hesitate
no
more
no
more
it
cannot
wait
im
yours
```

예제 출력 1
```
i
im
it
no
but
more
wait
wont
yours
cannot
hesitate
```

***
### My Solution in Python :ok_hand:

```python
print(*sorted(sorted(set(input() for _ in range(int(input())))),key=len))
```

> 문제에서 우선 단어들을 길이 순으로 정렬하고 같은 길이일 때는 사전순으로 정렬하라고 합니다. 하지만 이 순서를 꼭 지킬 필요는 없습니다. 즉, 먼저 단어들을 사전순으로 정렬하고나서 그 다음에 길이순으로 정렬해도 그 결과는 같습니다.
> 
> 파이썬의 내장 함수인 sorted() 함수는 기본적으로 문자열을 사전순으로 정렬시켜주며, key 인수를 사용하면 전달받은 함수에 각 단어들을 전달하여 호출한 결과에 따라 정렬시켜줍니다.
> 따라서 안쪽 sorted() 함수는 단어들을 사전순으로 정렬해주며, 바깥쪽 sorted() 함수는 key 인수에 len() 함수를 전달하였기에 단어들을 길이순으로 정렬하고 있습니다.
>
> 단, 예제의 출력 결과를 살펴보면 중복된 단어는 출력하지 않으므로, set() 함수를 사용하여 중복된 요소를 제거하고 있음에 유의해야 합니다.

***
백준 온라인 저지 [https://www.acmicpc.net/problem/1181](https://www.acmicpc.net/problem/1181)
