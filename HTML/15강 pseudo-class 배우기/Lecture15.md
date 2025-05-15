# Table 레이아웃과 vertical-align 속성 (2025-05-14)
## 1. 상태에 따라서 스타일을 줄 수 있는 pseudo-class에 대하여
![](./제목%20없는%20동영상%20-%20Clipchamp로%20제작.gif)
```
1. 마우스 올리기 전
2. 마우스 올린 후
3. 마우스로 클릭하는 중
4. 마우스 클릭한 후
```
- 이런 상태에 따라서 스타일을 변화할 수 있게 도와주는 `pseudo-class`에 대해서 학습했다.
---
```html
<!-- html 파일 내부 -->
<div>
    <button class="btn">구매하기</button>
    <input class="input-test">
    <a href="#" class="custom-link">링크</a>
</div>
```
``` css
/* css 파일 내부 */ 
/* 버튼과 관련된 pseudo-class */
.btn:hover {
    background-color : chocolate; /* 마우스를 올려놓을 때 */
}
.btn:focus {
    background-color : grey;  /* 클릭 후 계속 지정되있는 포커스 상태일때 */
}
.btn:active {
    background-color : brown; /* 누르는 중 */
    border:2px solid black;
}

/* 입력 박스와 관련된 pseudo-class */
.input-test {
    font-size : 20px;
}
.input-test:focus { /* 클릭 후 계쏙 지정되있는 포커스 상태 */
    border : 2px solid red;
}

/* 링크 관련된 pseudo-class */
.custom-link {
    text-decoration : none;
}
.custom-link:link {
    color : aqua; /* 방문 전 글자 스타일 */
}
.custom-link:visited {
    color : red; /* 방문 후 글자 스타일 */
}
```
- 이외에도 다양한 `pseudo-class` 사용 예시가 있다.
- 필요한 것이 있다면 구글링을 통해 살펴보자.