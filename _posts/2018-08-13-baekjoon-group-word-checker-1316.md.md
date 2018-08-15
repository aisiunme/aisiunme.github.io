---
title: "백준 온라인 저지 - 그룹 단어 체커(1316)"
comments: true
categories:
  - Algorithm
tags:
  - 알고리즘 문제 풀이
  - 문자열 처리
  - 탐색
---

## Baekjoon Problem #1316 - 문자열 처리, 탐색 문제

그룹 단어란 단어에 존재하는 모든 문자에 대해서, 각 문자가 연속해서 나타나는 경우만을 말한다. 예를 들면, ccazzzzbb는 c, a, z, b가 모두 연속해서 나타나고, kin도 k, i, n이 연속해서 나타나기 때문에 그룹 단어이지만, aabbbccb는 b가 떨어져서 나타나기 때문에 그룹 단어가 아니다.

단어 N개를 입력으로 받아 그룹 단어의 개수를 출력하는 프로그램을 작성하시오.

> 입력
> : 첫째 줄에 단어의 개수 N이 들어온다. N은 100보다 작거나 같은 자연수이다.
> : 둘째줄부터 N개의 줄에 단어가 들어온다. 단어는 알파벳 소문자로만 되어있고 중복되지 않으며, 길이는 최대 100이다.

> 출력
> : 첫째 줄에 그룹 단어의 개수를 출력한다.

***
예제 입력 1
```
3
happy
new
year
```

예제 출력 1
```
3
```
***
예제 입력 2
```
4
aba
abab
abcabc
a
```

예제 출력 2
```
1
```

***
### My Solution in Python :ok_hand:

```python
result = int(input())
for _ in range(result):
    word = input()
    for i in range(1, len(word)):
        if word.find(word[i-1]) > word.find(word[i]):
            result -= 1
            break
print(result)
```

> `if word.find(word[i-1]) > word.find(word[i]):`  
> 단어에서 두 글자씩을 비교하여 앞 글자가 처음 등장하는 인덱스보다 뒷 글자가 처음 등장하는 인덱스가 더 작으면, 뒷 글자는 앞서 이미 등장한 글자가 됩니다.  
> 따라서 그룹 단어가 아니므로, 결과에서 1을 제외하고 다음 단어를 검사합니다.


### Short coding in Python

```python
result = 0
for i in range(int(input())):
    word = input()
    if list(word) == sorted(word, key=word.find):
        result += 1
print(result)
```

> `if list(word) == sorted(word, key=word.find):`  
> 파이썬의 내장 함수인 sorted() 함수는 key라는 인수로 함수를 전달받아, 해당 함수를 실행한 결과값을 기준으로 정렬을 진행하게 됩니다.  
> 따라서 만약 단어가 그룹 단어라면, 해당 단어의 각각의 문자를 그대로 리스트로 변환한 것과 find() 함수를 각각 적용한 후 그 결과값을 기준으로 정렬한 리스트가 같게 됩니다.  
>
> 제 코드는 그룹 단어가 아닌 것을 제외해 나가는 방식이며, 숏코딩의 코드는 그룹 단어인 것을 찾아가는 방식입니다.

***
백준 온라인 저지 [https://www.acmicpc.net/problem/1316](https://www.acmicpc.net/problem/1316)
