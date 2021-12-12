# kkilme's playground!
**My first blog w/ GitHub page**

## **Contents**

  - [**Start**](#start)
  - [**Theme**](#theme_lanyon)
  - [**Font**](#font)
  - [**Additional_Functions**](#additional_functions)
    - [**Comment**](#comment)

## **Start**
- **Github Page 사용**
  - kkilme.github.io Repository 생성 및 사용
- **Jekyll 사용**
  1. 공식 홈페이지에서 Jekyll 설치
  2. 터미널 창 (윈도우 - CMD 창) 에서 kkilme.github.io Repo의 로컬 저장소 위치로 이동 후 `jekyll new . --force` 명령어 실행
  3. 기본 테마의 jekyll 파일들이 해당 위치에 설치됨
  4. 해당 파일들을 수정하거나 새로운 파일들을 추가하여 블로그 관리
   

## **Theme_Lanyon**
- 무료 테마를 볼 수 있는 <https://jekyllthemes.io/free> 및 <http://jekyllthemes.org/> 에서 다양한 테마를 둘러봄
- 하지만 교수님께서 예시로 사용하신 **Lanyon 테마가 가장 깔끔하고 사이드바(sidebar)도 마음에 들어** 사용하게 됨.

- ### Lanyon 설치 과정
  1. [Lanyon Repository](https://github.com/poole/lanyon) 를 git clone을 활용해 로컬 저장소로 받아오기
  2. 받아온 파일들을 kkilme.github.io 로컬 저장소에 덮어쓰기

## **Font**
- 영어 폰트는 Lanyon 테마가 기본적으로 제공하는 폰트 사용
- 하지만 **한국어 폰트는 지정된 것이 없어** 글씨가 지저분해 보였음 **-> 한국어 폰트 추가 필요**
- 폰트 추가 과정
  1. [Google Fonts](https://fonts.google.com/)에서 원하는 한국어 폰트 찾기, [Noto Sans Korean](https://fonts.google.com/noto/specimen/Noto+Sans+KR)을 사용하기로 함
  2. 폰트 스타일 선택 후 @import 구문 복사
   <p align = "center">
    <img src= "https://user-images.githubusercontent.com/80762534/145720005-5c11c310-a6b5-4ae3-9deb-81078174e9aa.PNG">
   </p>

   ```css
   @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300&display=swap');
   ```
  3. `lanyon.css` 파일에 위 구문 붙여넣기
  4. 같은 파일의 font-family에 Noto Sans KR 폰트 추가  

   ```css
   font-family: "PT Serif", Georgia, "Times New Roman", 'Noto Sans KR', serif;
   ```

## **Additional_Functions**

### **Comment**
![Comment](https://user-images.githubusercontent.com/80762534/145720820-ec3c4842-bb85-48e7-b5f3-b1c1ca21d68d.PNG)
- **댓글 기능 - Disqus 활용**
- 설치 과정
  1. Disqus 가입 후 Website URL 등 기본 세팅
  2. `config.yml`에 다음과 같은 코드 추가
   ```yml
    comment : 
        provider :         "disqus"
        disqus :
            shortname :    "kkil-blog"
    ```
  3. disqus 홈페이지에서 Universal Code 복사 후 적절히 수정하여 `post.html`에 반영
    ```html
    {% if page.comments %}
    <h2>Comments</h2>
    <div id="disqus_thread"></div>
    <script>
        let PAGE_URL = "{{site.url}}{{page.url}}"
        let PAGE_IDENTIFIER = "{{page.url}}"
        var disqus_config = function () {
        this.page.url = PAGE_URL;  
        this.page.identifier = PAGE_IDENTIFIER; 
        };
        
        (function() {
        var d = document, s = d.createElement('script');
        s.src = 'https://kkil-blog.disqus.com/embed.js';
        s.setAttribute('data-timestamp', +new Date());
        (d.head || d.body).appendChild(s);
        })();
    </script>
    <noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
    {% endif %}
    ```
