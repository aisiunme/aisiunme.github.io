---
title: "Jekyll - Github page 오류 해결 방법"
comments: true
categories:
  - Jekyll
tags:
  - jekyll
  - github page
---

## Jekyll을 이용한 Github page 생성시

### Jekyll 구동 오류 발생 :anger:
```
jekyll server
```
이 명령을 통해 jekyll이 내장하고 있는 서버를 동작시키고 이를 로컬 PC에서 확인할 수 있다. (localhost:4000)<br>
하지만 오류 발생! :boom:
```
WARN: Unresolved specs during Gem::Specification.reset:
      rouge (< 4, >= 1.7)
WARN: Clearing out unresolved specs.
Please report a bug if this causes problems.
C:/Programs/Ruby24-x64/lib/ruby/gems/2.4.0/gems/bundler-1.16.3/lib/bundler/runtime.rb:313:in `check_for_activated_spec!': You have already activated public_suffix 3.0.2, but your Gemfile requires public_suffix 2.0.5. Prepending `bundle exec` to your command may solve this. (Gem::LoadError)
        from C:/Programs/Ruby24-x64/lib/ruby/gems/2.4.0/gems/bundler-1.16.3/lib/bundler/runtime.rb:31:in `block in setup'
        from C:/Programs/Ruby24-x64/lib/ruby/2.4.0/forwardable.rb:229:in `each'
        from C:/Programs/Ruby24-x64/lib/ruby/2.4.0/forwardable.rb:229:in `each'
        from C:/Programs/Ruby24-x64/lib/ruby/gems/2.4.0/gems/bundler-1.16.3/lib/bundler/runtime.rb:26:in `map'
        from C:/Programs/Ruby24-x64/lib/ruby/gems/2.4.0/gems/bundler-1.16.3/lib/bundler/runtime.rb:26:in `setup'
        from C:/Programs/Ruby24-x64/lib/ruby/gems/2.4.0/gems/bundler-1.16.3/lib/bundler.rb:107:in `setup'
        from C:/Programs/Ruby24-x64/lib/ruby/gems/2.4.0/gems/jekyll-3.8.3/lib/jekyll/plugin_manager.rb:50:in `require_from_bundler'
        from C:/Programs/Ruby24-x64/lib/ruby/gems/2.4.0/gems/jekyll-3.8.3/exe/jekyll:11:in `<top (required)>'
        from C:/Programs/Ruby24-x64/bin/jekyll:23:in `load'
        from C:/Programs/Ruby24-x64/bin/jekyll:23:in `<main>'
```
---
```
bundle exec jekyll server
```
해결책 발견!!<br>
번들러는 Ruby에서 필요한 정확한 gem과 버전을 추적하고 설치하여 루비 프로젝트를 위한 일관된 환경을 제공합니다.<br>
번들러는 의존성 지옥에서 벗어나게 하고, 필요한 gem이 개발, 스테이징, 프로덕션에 있는지 확인해 줍니다.<br>
하지만 오류 발생! :boom:
```
Configuration file: D:/Work/Git/aisiunme.github.io/_config.yml
            Source: D:/Work/Git/aisiunme.github.io
       Destination: D:/Work/Git/aisiunme.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
      Remote Theme: Using theme mmistakes/minimal-mistakes
   GitHub Metadata: No GitHub API authentication could be found. Some fields may be missing or have incorrect data.
  Conversion error: Jekyll::Converters::Scss encountered an error while converting 'assets/css/main.scss':
                    Invalid CP949 character "\xE2" on line 54
jekyll 3.7.3 | Error:  Invalid CP949 character "\xE2" on line 54
```
---
### 해결 방안
윈도우에서의 Jekyll에 관한 이슈<br>
만약 UTF-8 인코딩을 사용한다면, 문서 안에 BOM 헤더를 사용하지 않아야 합니다.<br>
그렇지 않으면 Jekyll 에 아주, 아주 안 좋은 일이 벌어집니다.<br>
이는 특히, 윈도우즈에서 Jekyll을 사용하는 것에 연관된 문제입니다.<br>
그리고, 사이트 생성 단계에서 “Liquid Exception: Incompatible character encoding” 에러가 발생하는 경우엔,<br>
콘솔창의 코드 페이지를 UTF-8 로 바꿔야 할 수도 있습니다.<br>
콘솔창에 다음과 같이 입력하면 됩니다:
```
chcp 65001
```
콘솔창 화면이 Active code page: 65001로 넘어가면서 다시 jekyll을 구동시키면 정상적으로 동작함!<br>
http://jekyllrb-ko.github.io/docs/windows/
---
해결됨! :two_hearts:
