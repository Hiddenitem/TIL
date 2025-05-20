# 실전 포트폴리오 제작해보기 1 (나혼자 다 못함 실패...) (2025-05-21)
# 시간 남을 때 싹다 지우고 다시 만들어보자.
## 전체 코드
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link href="Project1.css" rel="stylesheet">
    <!-- 반응형 웹사이트 준비 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- 아이콘 불러오기 링크 -->
    <link rel="stylesheet" 
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css" 
    integrity="sha512-1ycn6IcaQQ40/MKBW2W4Rhis/DbILU74C1vSrLJxCq57o941Ym01SwNsOMqvEBFlcgUa6xLiPY/NS5R+E6ztJQ==" 
    crossorigin="anonymous" referrerpolicy="no-referrer" />
</head>
<body>
    <div>
        <!-- header -->
        <div class="header-container">
            <div class="header-text">
                <h1>Landing Pages for Apps</h1>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nobis voluptatem, officiis, delectus obcaecati officia enim, odit vel totam necessitatibus exercitationem veniam cupiditate molestias nesciunt voluptates velit dolor laboriosam corporis a.</p>
                <button type="submit" class="btn-style">Show More</button>
            </div>
            <div class="header-img">
                <img src="iphone-1.png">
            </div>
        </div>
        <!-- show portfolio -->
        <div class="portfolio-container">
            <div>
                <h1>It is the perfect theme for your next Project</h1>
                <h3>Lorem Ipsum LaLaLaLALAL</h3>
                <button type="submit" class="btn-style" style="width : 12%">Show Portfolio</button>
            </div>
        </div>
        <!-- What we Offer -->
        <div class="offer-container">
            <div class="offer-text">
                <p>services</p>
                <h4>What We Offer</h4>
            </div>
            <div class="offer-icon">
                <div>
                    <i class="fas fa-mobile-alt fa-3x"></i>
                    <h4>Responsive</h4>
                    <p>lorem ipsum i love coding</p>
                </div>
                <div>
                    <i class="fas fa-flask fa-3x"></i>
                    <h4>Experiments</h4>
                    <p>lorem ipsum i love making game</p>
                </div>
                <div>
                    <i class="fas fa-bolt fa-3x"></i>
                    <h4>Quickness</h4>
                    <p>lorem ipsum i love backend</p>
                </div>
                <div>
                    <i class="fas fa-globe-asia fa-3x"></i>
                    <h4>Global Shipping</h4>
                    <p>lorem ipsum i love Stellive</p>
                </div>
            </div>
            <div style="float:none; clear:both;"></div>
        </div>
        <!-- What we can do -->
        <div class="WWCD-container">
            <div class="WWCD-text">
                <p>Portfolio</p>
                <h4>What we can Do</h4>
            </div>
            <div class="WWCD-img">
                <div class="main-image"  style="background-image: linear-gradient(rgba(0, 0, 0, 0.527), rgba(0, 0, 0, 0.5)), url(portfolio-1-1.jpg)">
                    <div class="overlay"></div>
                    <h1>Stationary</h1>
                    <p>Lorem ipsum dhozp djfudna</p>
                </div>
                <div class="main-image" style="background-image : url(portfolio-2.jpg)">
                    <div class="overlay"></div>
                    <h1>Stationary</h1>
                    <p>Lorem ipsum dhozp djfudna</p>
                </div>
                <div class="main-image" style="background-image : url(portfolio-3-1.jpg)">
                    <div class="overlay"></div>
                    <h1>Stationary</h1>
                    <p>Lorem ipsum dhozp djfudna</p>
                </div>
                <div class="main-image" style="background-image : url(portfolio-4-1.jpg)">
                    <div class="overlay"></div>
                    <h1>Stationary</h1>
                    <p>Lorem ipsum dhozp djfudna</p>
                </div>
                <div style="float:none; clear:both"></div>
            </div>
        </div>
        <!-- link-Icon -->
        <div>
            <div class="offer-icon link-icon">
                <div style="cursor:pointer" onclick="window.open('https://www.google.com/webhp?hl=ko&sa=X&ved=0ahUKEwj82by81LGNAxVdqFYBHSBcOKQQPAgI');">
                    <i class="fab fa-google fa-3x"></i>
                </div>
                <div style="cursor:pointer" onclick="window.open('https://x.com/home?lang=ko');">
                    <i class="fab fa-twitter fa-3x"></i>
                </div>
                <div style="cursor:pointer" onclick="window.open('https://www.instagram.com/');">
                    <i class="fab fa-instagram fa-3x"></i>
                </div>
            </div>
        </div>
        <!-- Copyright -->
        <div class="copyright">
            <p>@ Hidden_Item</p>
        </div>
    </div>
</body>
</html>
```
```CSS
body {
    margin : 0;
}

.header-container {
    background-image : linear-gradient(to bottom, #23affa, #0666d4);
    padding : 20px;
    padding-left : 50px;
    padding-bottom : 0px;
    margin-bottom: 0px;
    display:flex;
}

.header-text {
    width : 50%;
    color : white;
}

.header-img {
    width : 50%;
    padding : 10px;
    height : 50%;
    padding-bottom : 0;
}

.header-img img {
    height : 100%;
    width : 100%;
    display : block;
}

.btn-style {
    background-color : gray;
    color : white;
    padding : 10px;
    border : none;
    border-radius : 5px;
    font-size : 25px;
    width : 25%;
}

.portfolio-container {
    padding : 50px;
    margin-left:auto;
    margin-right : auto;
    text-align : center;
}

.offer-container {
    background-color : #5c80e4;
    text-align : center;
    padding : 50px;
    color : white;
}

.offer-text p {
    margin-bottom : 0;
}

.offer-text h4 {
    margin-top : 0;
}

.offer-icon {
    text-align : center;
    display : flex;
    justify-content : center;
    padding : 20px;
}

.offer-icon i {
    border-radius : 50%;
    background-color : white;
    width : 100px;
    height : 100px;
    padding-top : 25px;
    box-sizing : border-box;
    color : #5c80e4;
}

.offer-icon div {
    padding : 25px;
}

.WWCD-container {
    padding : 10px;
}

.WWCD-text {
    text-align : center;
}

.WWCD-text p {
    margin-bottom : 0px;
}

.WWCD-text h4 {
    margin-top : 0px;
    margin-bottom : 10px;
}

.WWCD-img {
    padding : 20px;
    margin-left : auto;
    margin-right : auto;
}

.main-image{ 
    background-image : url(portfolio-1-1.jpg);
    width : 50%;
    float:left;
    height : 450px;
    background-size : cover;
    color : white;
    position : relative;
}

.overlay {
    position : absolute;
    width : 100%;
    height : 100%;
    border : 0px solid white;
    z-index : 1;
    transition : all 1s;
}
.overlay:hover {
    box-shadow : 0 0 0 25px white inset;
}

.main-image h1 {
    padding : 30px;
}
.main-image p {
    padding-left : 30px;
}


.link-icon i {
    background-color: #5c80e4;
    color : white;
    
}

.copyright {
    padding : 40px;
    text-align : center;
}

/* 모바일 사이즈에서는 아래 스타일 적용*/
@media screen and (max-width : 992px) {
    .header-container {
        display : block;
    }
    .header-text {
        width : 100%;
        display : block;
        margin : auto;
        margin-top : 50px;
        text-align : center;
    }
    .header-img {
        width : 100%;
        display : block;
        margin : auto;
        margin-top : 42px;
    }
    .main-image {
        float:none;
        width : 100%;
    }
}
```
# 혼자할 때 실패한 부분
1. 맨 아래 포트폴리오 사진쪽에 이상한 틈이 생긴 것
> 선생님은 저 포트폴리오 사진들을 모두 background-image 스타일을 사용하여서 만들었다. <br>
> 나는 `<div>` 태그를 이용하여 구현하려고 했다가, 이상한 테두리가 나오는 것과 더불어, 반응형 애니메이션을 구현하는데 애를 먹었었다. `실패`. 
1. 맨 아래 포트폴리오 사진에 마우스 올렸을 때 테두리 나오게 하는 애니메이션
> `<div>`태그를 어떻게 transition 시켜야 되나 정말 고민했다가 봤다.<br>
> box-shadow 문법을 사용하여서, box 안쪽에 그림자를 만드는 것으로 구현하였다. `반쪽짜리` 성공
1. 반응형 레이아웃으로, 아이폰하고 맨 위에 글자가 세로로 정렬되게 나오게 하기/
> - 2번 문제는 간단하게 해결했다. 나는 맨 위에 글자와 아이폰을 display : flex 를 활용하여 정렬시켰다.<br>
> - 따라서, `media query` 문법 안에서 `.header-container` 클래스에서 `display : block` 을 사용하여, display : flex 스타일을 날린다.<br>
> - 이후, .header-text 와 .header-img 클래스들의 `width을 100% 로 지정`하여, 자동으로 줄바꿈이 일어나게 구현하였다.<br>
> - 선생님의 정답과는 다른 방식으로 성공하였지만, 아무래도 참고를 하였으니 `반쪽짜리 성공`이다.
