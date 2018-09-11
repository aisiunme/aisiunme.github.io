---
title: "『파이썬 코딩의 기술』 : 시퀀스 자르기"
comments: true
categories:
  - (Book) Effective Python
tags:
  - 파이썬
---

## BETTER WAY 3 : 시퀀스를 슬라이스하는 방법을 알자

EFFECTIVE PYTHON: 59 SPECIFIC WAYS TO WRITE BETTER PYTHON
: 이 포스트는 『파이썬 코딩의 기술』 책을 공부하면서 새롭게 배운 내용들을 잊지 않기 위해 정리해 놓은 글입니다. 책에는 유용한 정보가 더 많이 수록되어 있으므로, 책을 구매해서 보시는 것도 좋은 공부가 될 것입니다!

파이썬에서는 list, tuple, range의 세 가지 기본 시퀀스(sequence) 타입을 제공합니다. 이러한 시퀀스 타입은 다음과 같은 연산을 공통적으로 사용할 수 있습니다.

1. x in s : s 의 항목 중 하나가 x 와 같으면 True, 그렇지 않으면 False
x not in s	s 의 항목 중 하나가 x 와 같으면 False, 그렇지 않으면 True
s + t	s 와 t 의 이어 붙이기
s * n 또는 n * s	s 를 그 자신에 n 번 더하는 것과 같습니다
s[i]	s 의 i 번째 항목, 0에서 시작합니다
s[i:j]	s 의 i 에서 j 까지의 슬라이스
s[i:j:k]	s 의 i 에서 j 까지 스텝 k 의 슬라이스
len(s)	s 의 길이	 
min(s)	s 의 가장 작은 항목	 
max(s)	s 의 가장 큰 항목	 
s.index(x[, i[, j]])	(인덱스 i 또는 그 이후에, 인덱스 j 전에 등장하는) s 의 첫 번째 x 의 인덱스
s.count(x)	s 등장하는 x 의 총수