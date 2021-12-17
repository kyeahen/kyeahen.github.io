---
title: '[blog] Github 블로그 폰트 변경하기 (Minimal Mistakes)'
categories:
  - Github blog

comments: true 
---

블로그 운영의 묘미는 블로그 꾸미기! <br/>

올 하반기에는 포스팅을 안하고 꾸미기만 하고 있다..(반성해..) <br/>
폰트 바꾸러 왔다가 글이라도 하나 남겨보려고 한다. <br/>
블로그 꾸미기에 도움이 되길! <br/>

---

# 시작
> **Minimal Mistakes** 템플릿 기준으로 설명한다.

## 1. 마음에 드는 폰트 고르기!

<a href="/assets/images/211217_blog1.png"><img src="/assets/images/211217_blog1.png"></a>
<br/>
> 눈누 : <a href = "https://noonnu.cc/"> https://noonnu.cc/ </a>

폰트 파일을 따로 추가할 필요 없이 웹폰트로 간단하게 적용할 수 있다. <br/>
위의 사이트로 가면 다양한 폰트들이 있는데 마음에 드는 폰트를 고르고 <br/>
해당 **웹폰트 코드**를 복사해준다. <br/>

## 2. 웹폰트 코드 추가하기

<a href="/assets/images/211217_blog2.png"><img src="/assets/images/211217_blog2.png"></a>
<br/>

> 파일 경로 : **assets/css/main.scss**

눈누 사이트에서 복사한 웹폰트 코드를 그대로 해당 파일 하단에 복사해준다.

## 3. 폰트 이름(font-family) 추가하기

<a href="/assets/images/211217_blog3.png"><img src="/assets/images/211217_blog3.png"></a>
<br/>

> 파일 경로 : **_sass/minimal-mistakes/_variables.scss**

웹폰트 코드에 있는 **font-family** 이름을 그대로 추가해주면 된다.
