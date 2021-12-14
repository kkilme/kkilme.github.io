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

## 1. **[Google Analytics](https://analytics.google.com/analytics/web/#/) 홈페이지에서 계정 생성**
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

  위 과정을 완료하면 위와 같이 데이터 스트림이 생성된다. 여기서 측정 ID를 복사한다. 복사한 측정 ID를 `_config.yml` 파일에 다음과 같이 추가한다.

  ```yml
  google_analytics_id: G-P71SWHVVE8
  ```

  이 부분은 사용하는 테마마다 다를 수 있지만, config파일을 찾아보면 google analytics 관련된 부분이 있을 것이다.

  ~~이제 적용이 완료됐다.~~

  ... 라고 생각했지만 생각대로 작동하지 않아서 수십분간의 구글링을 통해 해결책을 찾았다.

  `_config.yml`에 다음과 같은 코드를 추가했다.

  ```yml
  analytics:
  provider               : "google-gtag" 
                          # false (default), "google", "google-universal", "google-gtag", "custom"
  google:
    tracking_id          : "G-P71SWHVVE8" #내 측정 ID
    anonymize_ip         : # true, false (default)
  ```

  `head.html`에도 다음과 같은 코드를 추가했다.

  ```html
  <script async src="https://www.googletagmanager.com/gtag/js?id=G-P71SWHVVE8"></script>
  <script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());

    gtag('config', 'G-P71SWHVVE8');
  </script>
  ```

  Lanyon 테마가 `head.html`에서 기본적으로 제공한 다음 코드는 주석처리 했다.
  
  ```html
  {% if site.google_analytics_id %}
  <script>
    (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
    (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
    m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
    })(window,document,'script','//www.google-analytics.com/analytics.js','ga');
    ga('create', '{{ site.google_analytics_id }}', 'auto');
    ga('send', 'pageview');
  </script>
  {% endif %} 
  ```

## 4. 적용된 것 확인하기

수십분의 구글링 끝에 드디어 적용에 성공했다. 이제 내 블로그에 직접 한번 들어가면, 구글 애널리틱스 보고서의 수치가 변화하는 것을 확인할 수 있다. 감격이다.

<p align = "center">
    <img src= "https://user-images.githubusercontent.com/80762534/146068775-786a55f2-1baa-4bd7-aa06-eadc3b4f92d0.PNG">
</p>

다음과 같이 상세 정보도 볼 수 있다. 신기하다.

<p align = "center">
    <img src= "https://user-images.githubusercontent.com/80762534/146069518-e2859a19-1e7f-4636-8b20-c78f2958ab8e.PNG">
</p>