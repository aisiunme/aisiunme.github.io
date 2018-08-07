---
title: "백준 온라인 저지 - 음계(2920)"
comments: true
categories:
  - Algorithm
tags:
  - 알고리즘 문제 풀이
  - 배열
---

## Baekjoon Problem #2920 - 음계

다장조는 c d e f g a b C, 총 8개 음으로 이루어져있다. 이 문제에서 8개 음은 다음과 같이 숫자로 바꾸어 표현한다. c는 1로, d는 2로, ..., C를 8로 바꾼다.

1부터 8까지 차례대로 연주한다면 ascending, 8부터 1까지 차례대로 연주한다면 descending, 둘 다 아니라면 mixed 이다.

연주한 순서가 주어졌을 때, 이것이 ascending인지, descending인지, 아니면 mixed인지 판별하는 프로그램을 작성하시오.

입력
: 첫째 줄에 8개 숫자가 주어진다. 이 숫자는 문제 설명에서 설명한 음이며, 1부터 8까지 숫자가 한 번씩 등장한다.

출력
: 첫째 줄에 ascending, descending, mixed 중 하나를 출력한다.

예제 입력 1
```
1 2 3 4 5 6 7 8
```

예제 출력 1
```
ascending
```

예제 입력 2
```
8 7 6 5 4 3 2 1
```

예제 출력 2
```
descending
```

예제 입력 3
```
8 1 7 2 6 3 5 4
```

예제 출력 3
```
mixed
```

***
### My Solution in Python :ok_hand:

```python
n = ''.join(input().split())
if n == '12345678': print('ascending')
elif n == '87654321': print('descending')
else: print('mixed')
```

### Short coding Solution in Python

```python
n = input()[0::2]
print({n: "mixed", "12345678": "ascending", "87654321": "descending"}[n])
```

> 파이썬 string 타입의 join() 함수는 리스트나 튜플, 문자열과 같이 순환할 수 있는 객체(iterable object)를 인수로 전달받아 객체에 포함된 모든 요소를 해당 문자열 뒤쪽에 이어 붙인 새로운 문자열을 생성하여 반환해 줍니다.
> 
> 숏코딩에서는 리스트의 슬라이싱을 이용하여 제가 join() 함수와 split() 함수를 사용하여 작업한 결과를 한 번에 해결하고 있습니다.  
> 리스트 슬라이싱에서는 세 번째 인덱스로 자르려는 인덱스 간의 간격을 명시할 수 있습니다.  
> 또한, 파이썬의 딕셔너리를 이용하여 결과를 출력하고 있는 것을 볼 수 있습니다.

***
백준 온라인 저지 [https://www.acmicpc.net/problem/2920](https://www.acmicpc.net/problem/2920)
