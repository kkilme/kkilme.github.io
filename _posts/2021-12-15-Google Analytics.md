---
layout: post
title:  "블로그에 Google Analytics 추가하기"
date:   2021-12-15 03:33:21 +0900
categories: Blog
comments : true
---
<p align = "center">
    <img src= "https://user-images.githubusercontent.com/80762534/146059498-ba3fd55a-4a9a-4352-adee-5e2699222d07.png" height = 200>
</p>

오늘은 github page로 만든 내 블로그에 google analytics를 추가하는 과정을 포스팅하고자 한다.

## 1. **[Google Anaytics](https://analytics.google.com/analytics/web/#/) 홈페이지에서 계정 생성**
 <p align = "center">
    <img src= "https://user-images.githubusercontent.com/80762534/146060015-1f505990-8046-4b7a-be23-f836003dd3ef.PNG">
</p>
  계정 설정, 속성 설정, 비즈니스 정보를 입력하여 계정을 생성해 준다.

## 2. **데이터 스트림 설정**
<p align = "center">
    <img src= "https://user-images.githubusercontent.com/80762534/146060428-fe7be335-6455-413f-b889-d5d88288b572.PNG">
</p>

  1번 과정을 마치고 나면 이런 창이 뜨는데, 웹을 선택해 준다. 그럼 아래와 같은 창이 뜬다.

<p align = "center">
    <img src= "https://user-images.githubusercontent.com/80762534/146060664-6d88b7d9-857f-4f59-acc8-42c2002aaf03.PNG">
</p>

  웹사이트 URL에 내 블로그 주소를 입력하고, 이름은 아무거나 적절히 입력한다. 그 후 스트림 만들기를 누른다. 


## 3. **측정 ID를 코드에 추가하기**

<p align = "center">
    <img src= "https://user-images.githubusercontent.com/80762534/146061502-363258ab-6009-4ab8-8681-e10eb494b04c.PNG">
</p>

  위 과정을 완료하면 위와 같이 데이터 스트림이 생성된다. 여기서 측정 ID를 복사한다. 복사한 측정 ID를 `config.yml` 파일에 다음과 같이 추가한다.

  ```yml
  google_analytics_id: G-P71SWHVVE8
  ```

  이 부분은 사용하는 테마마다 다를 수 있지만, config파일을 찾아보면 google analytics 관련된 부분이 있을 것이다.

## 4. 적용된 것 확인하기

이제 블로그에 한번 들어가면, 구글 애널리틱스 보고서의 수치가 변화하는 것을 확인할 수 있다.