---
title: "『파이썬 코딩의 기술』 : 파이썬 코딩 컨벤션"
comments: true
categories:
  - (Book) Effective Python
tags:
  - 파이썬
---

## BETTER WAY 2 : PEP 8 스타일 가이드를 따르자

EFFECTIVE PYTHON: 59 SPECIFIC WAYS TO WRITE BETTER PYTHON
: 이 포스트는 『파이썬 코딩의 기술』 책을 공부하면서 새롭게 배운 내용들을 잊지 않기 위해 정리해 놓은 글입니다.

---

코딩 컨벤션(Coding conventions)이란 코드를 읽기 편하고 관리하기 쉽도록 작성하기 위해 지켜야 할 일종의 코딩 스타일이라고 할 수 있습니다.

이러한 코딩 컨벤션은 프로그래밍 언어의 문법(syntax)과 같이 반드시 지켜야 하는 것은 아닙니다. 코드를 작성할 때 해당 프로그래밍 언어에서 사용하는 문법에만 맞는다면, 코딩 컨벤션과는 전혀 다르게 코드를 작성하여도 프로그램은 정상적으로 동작할 것입니다.

하지만 코딩 컨벤션에 명시된 스타일을 잘 지켜가며 코드를 작성함으로써 프로그램의 가독성 및 유지보수의 난이도는 크게 낮아지는 이점을 얻을 수 있으며, 특히 여러 사람이 함께 작업하는 협업에서는 코딩 컨벤션을 지킴으로써 코딩 스타일에 따른 서로간의 혼란을 줄이고 작업의 능률도 높일 수 있습니다.

따라서 프로그래밍 언어뿐만 아니라 각 기업이나 프로젝트에서도 각각의 개발 환경 및 목적에 맞는 고유의 코딩 컨벤션을 만들어 사용하는 경우도 어렵지않게 찾아볼 수 있습니다.

파이썬에서는 이러한 코딩 컨벤션을 PEP 8(Python Enhancement Proposal #8)이라는 문서를 통해 제공하며, 이 문서에서는 어떻게 하면 파이썬 코드를 명확하고 읽기 쉽게 작성할 수 있는지에 대한 여러 규칙들을 제안하고 있습니다.

1. 들여쓰기(indentation)는 탭(tab)이 아닌 4개의 스페이스(space)를 사용합니다.  
2. 코드의 한 라인은 79자 이하로 유지합니다.  
3. 클래스와 함수는 2개의 빈 줄(blank line)로 구분합니다.  
4. 클래스에서 메소드는 1개의 빈 줄로 구분합니다.  
5. 주석은 가급적 별도의 라인으로 작성합니다.  

6. 클래스와 예외의 이름은 CapWords 방식을 사용합니다.  
```
BinarySearchTree, IndexError, ...
```
7. 함수(메소드)와 변수의 이름은 lowercase_underscores 방식을 사용합니다.  
```
find_leaf_node(), root_node, ...
```
8. 상수의 이름은 UPPERCASE_UNDERSCORES 방식을 사용합니다.  
```
NUMBER_OF_CHILD_NODES, LENGHT_OF_TREE, ...
```

9. import 문은 항상 파일의 가장 처음에 위치합니다.  
10. not ... is과 같은 긍정의 부정 표현보다는 is not과 같은 부정의 표현을 사용합니다.  
```
if foo is not None: (○), if not foo is None: (×)
```
11. 시퀀스 타입의 문자열과 리스트, 튜플의 경우 빈 값을 길이가 아닌 False로 확인합니다.  
```
if not seq: (○), if len(seq): (×)
```
12. 불리언 값을 비교 연산자(==)를 사용하여 True 또는 False와 직접 비교하지 않습니다.  
```
if greeting: (○), if greeting == True: (×), if greeting is True: (××)
```

위와 같은 규칙 외에도 파이썬 코드를 작성할 때 유의해야 할 더 많은 규칙들이 PEP 8 문서에 명시되어 있습니다. PEP 8 문서는 파이썬 커뮤니티에 의해 계속해서 업데이트되고 있습니다.

[PEP 8 문서](https://www.python.org/dev/peps/pep-0008/)
