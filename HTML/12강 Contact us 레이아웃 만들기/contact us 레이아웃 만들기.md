# 11강 과제 다시 제작하기 (2025-05-13)
![](./완성본(쌤꺼).png)
- 결과 화면을 보면 11강때의 과제와 비슷한데 더 이쁜걸 볼 수 있다.
- 코드는 어떤지 아래를 보고 확인해보자.
```html
<!-- html 파일 내부 -->
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link href="CSS/practice2.css" rel="stylesheet">
</head>
<body>
    <div class="form-background">
        <div class="form-white">
            <!-- form 태그가 여기 들어감 -->
            <form>
                <div class="w-100">
                    <h3>Contact Us</h3>
                    <p>Your Email</p>
                    <input class="form-input" type="email" placeholder="example@email.com">
                </div>

                <div class="w-50">
                    <p>First name</p>
                    <input class="form-input" type="text">
                </div>
                <div class="w-50">
                    <p>Last name</p>
                    <input class="form-input" type="text">
                </div>
                <!-- float 사용한 first name, last name 박스들 뒤로 clear:both를 적용 -->
                <div style="clear:both"></div>

                <div class="w-100">
                    <p>Message</p>
                    <textarea class="form-input"></textarea>
                </div>

                <div>
                    <input id="sub" type="checkbox">
                    <label for="sub">Subscribe</label>
                    <button class="SEND-button" type="submit">SEND</button> 
                </div>
            </form>
        </div>
    </div>
</body>
</html>
```
``` css
/* selector에서 , 를 사용해서 중복으로 조정 가능 */
div, input, textarea {
    box-sizing : border-box;
}

body {
    margin:0px;
}

/* css 파일과 html 파일을 보면, 클래스들을 재사용하는 것을 알 수 있다. */
/* 통일감, 시간 절약 등등 클래스는 재사용이 가능하게 짜는 걸 고민하는게 좋다 */

.form-background {
    background-color : black;
    padding : 30px;
}

.form-white {
    background-color : white;
    padding : 30px;
    /* 박스 크기 고정 */
    width : 80%;
    max-width : 600px;
    /* 박스 가운데 정렬 */
    margin:auto;
}

.form-input {
    /* 가로로 꽉 차게 만듬 */
    width:100%;
    font-size : 20px;
    border : 1px solid black;
    border-radius : 5px;
    padding : 10px;
}

/* 50% 사이즈를 가진 박스 디자인 */
.w-50 {
    width : 50%;
    float:left;
    padding : 10px;
}

.w-100 {
    width:100%;
    padding:10px;
}

.SEND-button {
    background-color : orange;
    border : 0px;
    border-radius : 5px;
    float:right;
    font-size : 20px;
    padding : 10px;
    color : white;
    width : 35%;
}
```
---
---
- 11강의 코드와 다른점
1. 클래스를 재활용하여, 코드 작성 시간이 현저히 줄어들었으며, 코드의 양도 줄어들음.
2. selector에서 여러 클래스를 한꺼번에 스타일을 지정하여 코드를 간결하게 만듬.
3. 모든 글자들에 다 태그가 달려있음.
- 분발하도록 하자...ㅜㅜ