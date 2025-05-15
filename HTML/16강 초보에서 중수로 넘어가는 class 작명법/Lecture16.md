# 도움이 되는 class 작명법 속성 (2025-05-14)
## 1. 초보자 class 설정의 문제점
```html
<!-- html 파일 내부 -->
    <button class="btn-red">더 알아보기</button>
    <button class="btn-blue">구매하기</button>
```
```css
/* css 파일 내부 */
.btn-red {
    padding : 15px;
    font-size : 20px;
    border : none;
    cursor : pointer;
    background:red;
}
.btn-blue {
    padding : 15px;
    font-size : 20px;
    border : none;
    cursor : pointer;
    background:blue;
}
```
- `빨간 버튼 더 알아보기`, 그리고 `파란 버튼 구매하기 버튼`을 `두 가지` 만들었다.
- 각 버튼에 대한 클래스를 두 개 만들었다.
- 다만! 이렇게 되면, `중복 스타일이 발생`하게 된다.
---
### 각각 스타일을 따로 만들면 안되나요?
- 기능상으로 문제가 되는 부분은 없다.
- 하지만, 만약에 `저런 버튼을 10개 만들어야 된다고 가정`해보자.
- css 파일에 버튼 10개에 대한 클래스를 각각 작성한다고 생각해보면... 벌써부터 어지럽다.
- 만든다고 하더라도 `스타일을 수정하기 위해 css 파일 속을 돌아보는 시간이 엄청 늘어날 것`이다.

## 2. 도움이 되는 class 작명법
### 깔끔한 모습을 만들고 싶다?
### `중복되는 기능`을 가지는 `뼈대 클래스`와,
### `각각 달라지는 스타일`을 가지는 `살점 클래스`로 구분하라!
```html
    <button class="main-btn bg-red">더 알아보기</button>
    <button class="main-btn bg-blue">구매하기</button>
```
``` css
/* 뼈대 클래스 */
.main-btn {
    padding : 15px;
    font-size : 20px;
    border : none;
    cursor : pointer;
}
/* 살점 클래스 */
.bg-red {
    background : red;
}

.bg-blue {
    background : blue;
}
```
- 이런식으로 코드를 구성할 시
1. 코드의 가독성 상승
2. 유지보수가 용이함
3. 기능 확장에 용이함
4. 중복된 스타일을 재사용함 -> 코드 작성 속도가 빨라짐
- 이런 장점들을 가질 수 있으니, 유념에 두고 작성하도록하자.
### 이런 코드 작성법은 OOCSS(Object Oriented CSS) 라고 불리는 작성 관습이다.

## 3. BEM 작명법으로 클래스명을 작명하자
- BEM(Block-Element-Modifier)이라고 하는 작명법이 있다.
``` html
<div>
  <img>
  <h4>이름</h4>
  <p>소개글</p>
  <button>빨간버튼</button>
  <button>파란버튼</button>
</div>
```
- 웹사이트 프로필 레이아웃이 대충 이렇게 생겼다고 가정해보자.
- 각각에 스타일을 주기 위해 클래스를 제작해야 한다고 하면
``` html
<div class="profile">
  <img class="profile__img">
  <h4 class="profile__name">이름</h4>
  <p class="profile__content">소개글</p>
  <button class="profile__button--red">빨간버튼</button>
  <button class="profile_button--blue">파란버튼</button>
</div>
```
1. 전체적인 클래스 명 profile을 작성.
2. 그 뒤에 `__` 언더바를 2개 작성하고 이 요소의 역할을 작성.
3. 만약 같은 태그들의 디자인을 변경해야 한다면 `--` 대쉬를 2개 작성하고 디자인 요소를 작성한다.
- 요즘은 쌩 html, css 개발 보다는 React나 vue를 사용한다고 하던데, 이러면 편하게 작성할 수 있다.
- 더 알아보고 싶다면 공부를 해보도록 하자.