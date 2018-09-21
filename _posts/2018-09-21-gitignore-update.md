---
title: ".gitignore 설정 변경 후 git에 반영되지 않는 문제"
comments: true
categories:
  - Git
tags:
  - 깃(git)
---

## .gitignore 설정 변경 후 git 업데이트 방법

프로젝트가 진행됨에 따라 .gitignore 파일에 추가해야 할 폴더와 파일 등이 점차 늘어나게 됩니다.

하지만 .gitignore 파일에 정상적으로 추가하였다고 하더라도 이미 git에 push된 폴더나 파일들은 삭제되지 않습니다.

이럴 때는 해당 repository 폴더에서 git bash를 실행하여 다음과 같은 명령을 실행하면 됩니다. 이렇게 함으로써 .gitignore 파일의 내용을 git에 업데이트하여 이미 push된 폴더나 파일을 삭제할 수 있습니다.

```
$ git rm -r --cached .
$ git add .
$ git commit -m 'git cach removed!'
$ git push origin <brunch 이름>
```

push까지 완료해야 업데이트됩니다~ :two_hearts:
