---
title: "백준 온라인 저지 - 문자열 반복(2675)"
comments: true
categories:
  - Algorithm
tags:
  - 알고리즘 문제 풀이
  - 문자열 처리
---

## Baekjoon Problem #2675 - 문자열의 각 문자를 반복하여 출력하는 문제

문자열 S를 입력받은 후에, 각 문자를 R번 반복해 새 문자열 T를 만든 후 출력하는 프로그램을 작성하시오.

다시 설명하자면, 첫 번째 문자를 R번 반복하고, 두 번째 문자를 R번 반복하는 식으로 T를 만들면 된다. S에는 QR Code "alphanumeric" 문자만 들어있다.

QR Code "alphanumeric" 문자는 0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ$%*+-./: 이다.

> 입력
> : 첫째 줄에 테스트 케이스의 개수 T(1 <= T <= 1,000)가 주어진다.  
> : 각 테스트 케이스는  반복 횟수 R(1 <= R <= 8), 문자열 S가 공백으로 구분되어 주어진다.  
> : S의 길이는 적어도 1이며, 20글자를 넘지 않는다. 

> 출력
> : 각 테스트 케이스에 대해 T를 출력한다.

***
예제 입력 1
```
2
3 ABC
5 /HTP
```

예제 출력 1
```
AAABBBCCC
/////HHHHHTTTTTPPPPP
```

***
### My Solution in Python :ok_hand:

```python
for _ in range(int(input())):
    r, d = input().split()
    print(''.join([s * int(r) for s in d]))
```

> 파이썬 문자열의 join() 함수는 순환할 수 있는 객체(iterable object)를 인수로 전달받아 해당 객체에 포함된 각 문자열 요소를 하나의 문자열로 이어 붙여 반환해 줍니다.  
> 
> 이때 순환할 수 있는 객체의 각 요소에는 문자열이나 bytes 객체만이 올 수 있습니다.
> 
> 그리고 닷(.) 연산자 앞에 위치한 문자열을 이용하면, 각 요소들을 이어 붙일 때 그 사이에 삽입할 문자열을 명시할 수 있습니다.
> ```python
> print('%'.join(['아름다운', '우리', '나라']))
> ```
> ```
> 아름다운%우리%나라
> ```

***
백준 온라인 저지 [https://www.acmicpc.net/problem/2675](https://www.acmicpc.net/problem/2675)
