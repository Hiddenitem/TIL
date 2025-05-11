# 셀렉터를 이용해 CSS 코드 양 줄이기 (2025-05-11)
## 1. 셀렉터 사용해보기
- 6강에서 만든 레이아웃 맨 위에 네이버 바와 같은 화면을 만들어보자.
``` html
<!-- div와 동일한 기능을 하는 nav 이용 -->
<nav>
    <ul>
        <li>영화</li>
        <li>맛집</li>
        <li>IT</li>
        <li>컴퓨터</li>
    </ul>
</nav>
```
- 맨 위에 리스트로다가 블로그에서 탭을 누르는 내비게이션을 만들어보자.
- 사용된 `<nav>`는 `<div>`와 동일한 기능을 한다.
- 위의 코드처럼 작성하고, `<li>` 옆에다가 class를 만들고 막 스타일을 넣는 방법이 있긴 하지만, 이렇게 하면 class를 4개나 만들어야 하고, 이를 각각 관리해야 하는 불편함이 생기게 된다.
- 다음과 같이 셀렉터를 사용해보자.
```html
<!-- html 파일 내부 -->
<nav>
    <ul class="navbar">
        <li>영화</li>
        <li>맛집</li>
        <li>IT</li>
        <li>컴퓨터</li>
    </ul>
</nav>
```
```css
/* css 파일 내부 */
.navbar li{
    display : inline-block;
}
```
- 결과 화면을 보면
![](./오.png)
- 빨간 박스처럼 스타일이 적용된 것을 볼 수 있다.
- css 파일 내부에서
```
navbar 클래스 안에 있는 모든 li 태그는 이 스타일을 가져라
```
- 라는 편리한 기능을 적용시킨 것이다. 
---
---
```css
.navbar>li {}
```
- 위와 같이 사용하면 `li 태그`가 적힌 navbar 클래스 속 `직계 자식`들만 적용이 된다.
```html
<nav>
    <ul class="navbar">
        <li><p>영화</p></li>
    </ul>
</nav>
```
- 즉, `<li>` 태그에만 적용이 되며, `<p>`에는 적용이 되지 않는다.
---
- 반대로 `공백을 포함`하는 셀렉터라면?
``` css
.navbar li{
    display : inline-block;
}
```
```html
<nav>
    <ul class="navbar">
        <li><p>영화</p></li>
    </ul>
</nav>
```
- 이러면은 `<li>` 태그 속 `<p>` 태그들도 다 스타일이 적용된다.
---
- 편리한 셀렉터를 낭비하지는 말자.
``` css
.navbar>li>span>p>a {
    /* 생략 */
}
```
- 이렇게 사용하는 셀렉터는 코드 읽기에 굉장히 불편해진다.
- 깔끔하게 클래스 하나를 파서 바로 위 div나 nav 태그에 적용시키자.

## 2. 오늘 완성된 코드와 결과본
```html
<body>
    <!-- div와 동일한 기능을 하는 nav 이용 -->
    <nav>
        <ul class="navbar">
            <li><a href="#">영화</a></li>
            <li><a href="#">맛집</a></li>
            <li><a href="#">IT</a></li>
            <li><a href="#">컴퓨터</a></li>
            <li><a href="#">게임</a></li>
        </ul>
    </nav>
```
```css
.navbar li{
    display : inline-block;
    width: 100px;
    text-align:center;
    background : greenyellow;
    border : 2px solid black;
    border-radius : 20%;
    padding : 10px;
    border-radius:5px;
}

.navbar a{
    font-size : 20px;
    /* 링크된 글자의 밑줄 없애기 */
    text-decoration-line : none;
}

/* 방문한 링크 클릭 시 색깔 안바뀌게 하기 */
.navbar a:visited{
    color:blue;
}
/* 링크 위에 마우스 포인터 올릴 시 색깔 변하기 */
.navbar a:hover {
    color : blueviolet;
}
/* 링크를 누르고 있으면 색깔 변하게 하기 */
.navbar a:active {
    color : green;
}
```
![](./오이.png)