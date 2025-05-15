# HTML 레이아웃 만들어보기 (2025-05-10)
## 1. 레이아웃 만들어보기
- 이런 레이아웃을 만들어보자
![](./예제%201.png)
```html
<!-- layout1.html 내부--> 
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>Document</title>
        <link href="css/main.css" rel="stylesheet">
    </head>
    <body>
        <div class="container">
            <div class="header"></div>
            <div class="left_menu"></div><!--1
            --><div class="right"></div>
            <div class="footer"></div>
        </div>
    </body>
</html>
```
``` css
/* main.css 파일 내부 */
.container {
    width : 800px;
}

.header {
    width: 100%; /* 부모 태그의 width의 100%로 설정 */
    height : 100px;
    background : aquamarine;
}

.left_menu {
    width: 20%; /* 부모 태그의 20% */
    height : 400px;
    background : cornflowerblue;
    /* 기본적으로 <div>는 display:block 을 가지고 있어 아래와 같은 코드를 입력해야 한다. */
    /* float:left; */ /* 요소를 붕 띄워서 왼쪽 정렬 */
    display: inline-block; /* 내 크기 만큼 차지, 단 html 코드에서 공백이 없어야 함. */
}

.right {
    width : 80%;
    height : 400px;
    background:coral;
    /* float:right; */
    display: inline-block;
}

.footer {
    width : 100%;
    height : 100px;
    background-color: grey;
    /* clear :both; */ /* float 다음에 오는 요소에게 작성해야함 */
}
```
- 이런 `레이아웃을 만들 때`는, `기본적으로 div 박스들의 조합으로 만든다고 생각하라.`
- `<div>` 태그로 박스를 만들 때 그냥 div만 사용하면서 html 코드를 입력하면, 박스가 차곡차곡 쌓이지 않는다.
- 그 이유는 `<div>` 박스는 태그 속에 `display : block` 이라는 코드를 가지고 있기 때문이다.
- `display : block` 은 항목이 가로행을 전부 차지하게 된다.
- 따라서, 만약 가로행을 전부 차지하지 않고 박스 옆에 박스를 만들고 싶다면은
1. `float` 사용 (float 사용 이후 `<div>` 박스에는 `clear :both` 사용해야 함)
2. `display : inline-block` (html 코드에서 두 `<div>` 박스 사이에 `공백이 없어야 함`.)
- 두 개의 방법 중 하나를 선택하면 된다.
- 두 개의 방법 중, `inline-block`을 사용한 예시가 위의 `html` 코드에 있다.
- `float`을 사용한 예시는 `/* */` 주석 처리되어 있다.

## 2. 숙제로 레이아웃 만들기
![](./완성본.png)
- 위와 같은 레이아웃을 제작하였다.
``` html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>Document</title>
        <link href="CSS/practkce1.css" rel="stylesheet">
    </head>
    <body>
        <!-- 전체 내용이 들어갈 박스 공간 -->
        <div class="container">
            <!-- 내용 들어가는 공간 -->
            <div class="content">
                <!-- 제목 공간 -->
                <div class="title">
                    <img src="sample.png" class="sample">
                    <div class="title_title">
                        <p class="title_title_style">히든아이템</p>
                    </div>
                    <div class="title_sub_title">
                        <p class="title_sub_title_style">백엔드 개발자, 게임 개발자</p>
                    </div>
                    <div></div>
                </div>
                <!-- 본문 -->
                <div class="TEXT">
                    <div class="TEXT_title">
                        <p class="TEXT_title_style">개발자 히든아이템입니다!</p>
                    </div>
                    <div class="TEXT_text">
                        개발자 히든아이템입니다! 
                        저는 웹 사이트의 백엔드 개발과 게임 개발에 큰 관심을 가지고 있습니다! 
                        제가 사용할 수 있는 언어는 C, C++, JAVA, JS가 있고, 
                        제가 사용하는 프레임 워크는 Node.js, Spring이 있습니다!
                    </div>
                </div>
            </div>
            <!-- 이미지 들어가는 공간 -->
            <div class="img">
                <img src="sample.png" class="profile">
            </div>
        </div>
    </body>
</html>
```
``` css
/* 전체 박스 */
.container {
    width:800px;
    height:300px;
    /* 전체 박스에 가운데 정렬을 해놓으면, 아래 모든 것들 다 가운데 정렬됨 */ 
    /* 즉, 사이트 창 가운데로 보이게 됨 */
    margin-left:auto;
    margin-right:auto;
}

/* 내용 들어갈 전체 박스 */
.content {
    width: 70%;
    height : 300px;
    float:left;
}

/* 제목 */
.title {
    clear:both;
    height : 30%;
}

/* 내용 제목 박스 에 들어갈 썸네일*/ 
.sample {
    width:20%;
    height: 100%;
    border-radius:50%;
    float:left;
}

/* 내용 제목 글자 박스 */
.title_title {
    width:80%;
    height: 50%;
    float:left;
}

/* 내용 제목 글자 서식 */
.title_title_style {
    margin-top : 25px;
    font-size:20px;
    font-weight : bold;
}

/* 내용 부제목 글자 박스 */
.title_sub_title {
    width:80%;
    height : 50%;
    float:left;
}

/* 내용 부제목 글자 서식 */
.title_sub_title_style {
    margin-top : 10px;
    font-size : 15px;
    color : gray;
}

/* 본문 들어갈 박스 */
.TEXT {
    height : 70%;
}

/* 본문 제목 박스 */
.TEXT_title {
    width:100%;
    height : 30%;
    float:left;
}
/* 본문 제목 글자 서식 */
.TEXT_title_style {
    margin-top : 10px;
    font-size : 30px;
    font-weight : bold;
}

/* 본문 내용 박스 */
.TEXT_text {
    width : 100%;
    height : 70%;
    color : gray;
    float:left;
}

/* 프로필 */
.profile {
    width: 100%; 
    height : 200px;
    margin-left : auto; 
    margin-right : auto;
    margin-top : 10px;
    margin-bottom: auto;
    border-radius : 10%;
}

/* 이미지 담을 박스 */
.img {
    width : 30%;
    height : 300px;
    float :left;
}
```
- 박스를 만들고 나누면서 진행하면, 어렵지 않게 제작할 수 있다.