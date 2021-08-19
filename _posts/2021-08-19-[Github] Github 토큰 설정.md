---
title: '[Github] Personal access token 설정하기 (MacOS)'
categories:
  - Github

comments: true 
---

> Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.

<a href="/assets/images/210819_github_1.png"><img src="/assets/images/210819_github_1.png"></a>

오랜만에 개인 깃헙에서 push를 하려고 하니까 요런 에러를 겪었다. <br>
급한 건 아니었지만 생각난 김에 후딱 정리해보려고 한다! <br>

Github에서는 이제 **ID/PW** 기반의 인증을 금지하고, <br>
**ID/Personal Access Token** 방식의 인증을 요구하고 있다. <br>
그렇기 때문에 access token을 발급받아야 기존에 해왔던 레포 관리를 할 수 있다.

## 시작

1. **Settings - Developer Settings**

    <a href="/assets/images/210819_github_2.png"><img src="/assets/images/210819_github_2.png"></a>
    <br/>

2. **Personal access tokens - Generate new token**

    <a href="/assets/images/210819_github_3.png"><img src="/assets/images/210819_github_3.png"></a>
    <br/>

3. **New Personal acess token 설정**

    ***Select scopes***에서는 repo 관리만 하기 때문에 **repo**만 선택해주었다. <br>
    자신이 사용할 범위를 선택해서 체크하면 된다.<br>

    <a href="/assets/images/210819_github_4.png"><img src="/assets/images/210819_github_4.png"></a>
    <br/>

4. **생성한 토큰 복사하기**

    생성된 토큰은 지금 화면 이후에 다시 볼 수 없기 때문에 **꼭!** 저장해두어야 한다.

    <a href="/assets/images/210819_github_5.png"><img src="/assets/images/210819_github_5.png"></a>
    <br/>

5. **Github 키체인 암호 변경**

    **키체인 접근 - 로그인 - github.com** 키체인 순서로 이동한다. <br>
    검색창에 github 키워드를 치면 빠르게 찾을 수 있다.

    <a href="/assets/images/210819_github_6.png"><img src="/assets/images/210819_github_6.png"></a>
    <br/>

    <a href="/assets/images/210819_github_7.png"><img src="/assets/images/210819_github_7.png"></a>
    <br/>

---

### 참고

**WindowOS** 
- <a href = "https://firstquarter.tistory.com/entry/Git-%ED%86%A0%ED%81%B0-%EC%9D%B8%EC%A6%9D-%EB%A1%9C%EA%B7%B8%EC%9D%B8-remote-Support-for-password-authentication-was-removed-on-August-13-2021-Please-use-a-personal-access-token-instead"> [Git] 토큰 인증 로그인 + 자격 증명 - remote: Support for password authentication was removed on August 13, 2021 </a>
<br/>
- <a href = "https://curryyou.tistory.com/344"> GitHub 토큰 인증 로그인: Personal Access Token 생성 및 사용 방법 </a>

**MacOS** 
- <a href = "https://velog.io/@yund_272/Mac%EC%97%90%EC%84%9C-Git-token-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0"> Mac에서 Git token 설정하기 </a>