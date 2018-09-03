---
title: "백준 온라인 저지 - 소트인사이드(1427)"
comments: true
categories:
  - Algorithm
tags:
  - 알고리즘 문제 풀이
---

## Baekjoon Problem #1427 - 내림차순 정렬하기

배열을 정렬하는 것은 쉽다. 수가 주어지면, 그 수의 각 자리수를 내림차순으로 정렬해보자.

> 입력
> : 첫째 줄에 정렬하고자하는 수 N이 주어진다. N은 1,000,000,000보다 작거나 같은 자연수이다.

> 출력
> : 첫째 줄에 자리수를 내림차순으로 정렬한 수를 출력한다.

***
예제 입력 1
```
2143
```

예제 출력 1
```
4321
```

***
### My Solution in Python :ok_hand:

```python
print(''.join(sorted(input(), reverse=True)))
```

> 파이썬의 내장함수인 sorted() 함수는 기본적으로 전달받은 데이터를 오름차순으로 정렬하여 그 결과를 반환합니다. 따라서 내림차순으로 결과값을 반환받고 싶다면, reverse 인수에 True를 전달해야 합니다.  
>
> 또한, 문자열의 join() 함수를 사용하여 리스트의 각 요소를 하나의 문자열로 결합할 수 있습니다.

***
백준 온라인 저지 [https://www.acmicpc.net/problem/1427](https://www.acmicpc.net/problem/1427)
