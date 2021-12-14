---
layout: post
title:  "Markdown"
date:   2021-12-14 22:40:41 +0900
categories: Tech
comments : true
---
<p align = "center">
    <img src= "https://user-images.githubusercontent.com/80762534/146047281-556d7190-3d1a-451c-9299-b0d5deac1431.png">
</p>

이 포스트에서는 마크다운과 간단한 마크다운 문법에 대해 소개해보고자 한다.

## **Makrdown**

마크다운은 일반적인 텍스트로 서식이 있는 문서를 작성하는데 사용된다. 문법이 간단한 반면 HTML과 리치 텍스트(RTF) 등 서식 문서로 쉽게 변환되기 때문에 README 파일이나 온라인 게시물 등에 많이 사용된다.

### **기본적인 문법**

- #, ##, ###... 으로 제목(Header) 작성. # 개수에 따라 크기가 달라진다.

    ex)

    `## Heading Level 2`

## ----> Heading Level 2

- `*...*` 또는 `_..._`로 기울임체(Italic) 작성
  
    ex) `*Hello*` => *Hello*

- `**...**` 또는 `__...__`로 강조체(Bold) 작성

  ex)
  `**Hello**` => **Hello**

- `~~...~~` 으로 취소선(strikethrough) 작성
  
  ex) `~~Hello~~` => ~~Hello~~

- `-...` 또는 `*...`으로 순서없는 리스트 (unordered list) 작성
  
  ex)
  ```md
  - Hello
  - World!
  ```

  - Hello
  - World!

- `1. ...` 으로 순서있는 리스트 (ordered list) 작성
  
  ex)
  ```md
  1. Hello
  2. World!
  ```
  1. Hello
  2. World!

- `` `...` `` 으로 코드(code) 작성
  
  ex)
  `` `print("hello")` ``  => `print("hello")`

- `  ``` ... ``` ` 으로 코드블럭(code block) 작성, ```뒤에 프로그래밍 언어를 지정할 수 있음
  ex)
  ````
  ```python
  i = int(input())
  print(i)
  ```
  ````

  ```python
  i = int(input())
  if i < 0 or i > 100 : print(i)
  ```
  
  ````
  ```java
  public class test {
    public static void main(String args[]){
        int i = 1;
        String s = "hello";
        System.out.println("hello world!");
    }
  }
  ```
  ````


  ```java
  public class test {
    public static void main(String args[]){
        int i = 1;
        String s = "hello";
        System.out.println("hello world!");
    }
  }
  ```

- `> ...` 으로 인용표기 작성
  
  ex) > Hello world
  > Hello world

더 자세한 내용은 [이곳](https://www.markdownguide.org/basic-syntax)에서 확인할 수 있다. (영어다)