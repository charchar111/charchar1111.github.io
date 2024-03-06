# Kakao-talk-clone

## Link

[https://charchar111.github.io/kakao-talk-clone-html-css-practice-/](https://charchar111.github.io/kakao-talk-clone_html-css/)

## 컨셉

이 프로젝트는 카카오톡의 UI를 소재로 아래 주제에 대해 연구했다.

- [재사용에 적합한 컴포넌트 디자인](#컴포넌트-디자인)
- [BEM을 통한 가독성 및 유지보수-확장성](#BEM)
- [반응형 디자인과 적응형 디자인](#반응형-디자인)

## 기능
- 카카오톡 앱과 유사한 UI의 페이지
    - 로그인(index.html)
    - 친구 리스트(friends.html)
    - 채팅 리스트(chats.html)
    - 채팅창(chat.html)
    - 컨텐츠 더보기(find.html)
    - 기타 컨텐츠(more.html)
    - 세팅(settings.html)

 - 주요 컴포넌트의 상호작용 애니메이션
   - ex: 버튼 클릭 

## 기술 스택

- HTML5
- CSS3

## 세부 사항

### 컴포넌트 디자인

### BEM
### 반응형 디자인



## 이슈-해결방안
### 공용 컴포넌트를 만들면 커스터마이징이 어려워지는 문제
#### 문제
재사용을 위한 컴포넌트는 레이아웃에 따라 일부 스타일 값을 커스터마이징해야할 때가 있다.
이를 위해서 BEM의 수정자에 따라 새로운 속성을 추가하는 방식을 사용했다.

ex)

```html
<div class="page">
    <div class="nomal-component"></div>
   div class="nomal-component nomal-component--custom1"></div>
</div>
```

- 위 nomal-component는 nomal-component--custom1으로 새로운 속성을 추가했다.


#### 해결방안

### 애니메이션 성능 최적화
#### 문제
유저와의 상호작용에서 일어나는 일부 애니메이션이 느려지는 성능 문제가 발생했다.

- 요소의 호버링이나 클릭, 포커스에 대한 애니메이션

이 문제는 브라우저의 렌더링 동작과정을 모르는 데에서 발생했다. 브라우저는 html, css 파일을 파싱하여 렌더트리 형성, 레이아웃(리플로우), 페인팅(리페인팅), 컴포지트의 절차를 통해 화면을 보여준다.
그런데, 내가 사용한 애니메이션 속성(padding, background-color)이 리플로우와 리페인팅을 일으켜 문제가 생긴 것이었다.
  
#### 해결방안
- transform과 opacity 등의 속성을 사용, 이 속성들은 GPU 가속을 이용하며 레이아웃과 리페인팅을 발생시키지 않아 성능을 향상시켰다.


## 배운 점
