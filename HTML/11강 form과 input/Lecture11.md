# form과 input 배우기 (2025-05-13)
## 1. form과 input
![](./결과%20화면.png)
- 사진과 같이, 웹사이트에서 이용자가 입력할 공간을 만들어보자.
``` html
<!-- html 파일 내부 -->
<body>
    <form>
        <input> <br>
        <!-- 텍스트를 넣을 공간 -->
        <input type="text"> <br>

        <!-- 이메일 작성 -->
        <!-- css 파일에서 padding : 10px;를 적용시킴 -->
        <input type="email"> <br>

        <!-- 체크박스 만들기 -->
        <input type="checkbox"> <br>

        <!-- 날짜 선택 박스 만들기 -->
        <input type="date"> <br>

        <!-- 동그라미 선택 박스 만들기 -->
        <input type="radio"> <br>

        <!-- 미리 박스에 글씨를 채워넣음 -->
        <input type="text" value="aaaaaaaaa"> <br>
        <!-- 회색 글자로 배경 글자 만들어줌 -->
        <input type="text" placeholder="aaaaaaaaa"> <br>
        <!-- 서버 개발시 필요, 여기에 작성된 것은 age라는 이름으로 전달됨 -->
        <input type="text" name="age">

        <!-- 선택 할 수 있는 박스 만들기 -->
        <select>
            <option>오</option>
            <option>오잉?</option>
            <option>셀렉트 박스 만드는가 보내?</option>
        </select>

        <!-- 길게 작성하고, 오른쪽 아래를 잡고 드래그 하면서 크기를 변경할 수 있는 박스 만들기 -->
        <textarea>sdasdsd</textarea> <br>
        <!-- 처음 사이트에서 어떤 사이즈로 보이게 할까 -->
        <textarea rows="10px;"></textarea> <br>

        <!-- 전송 버튼 만들기 2가지 방법 -->
        <input type="submit">
        <button type="submit">전송</button> <br>

        <input type ="text" class="text-input">
    </form>
</body>
```
``` css
/* css 파일 내부 */
.text-input {
    padding : 10px;
    font-size : 20px;
    border : 1px solid red;
    border-radius : 5px;
}

/* input type="email" 인 input 박스에만 스타일 적용 */
input[type=email] {
    padding:10px;
}
```

## 2. 과제 해보기
![](./완성본(내꺼).png)
- 다음과 같은 레이아웃을 제작해보자.
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link href="CSS/practice2.css" rel="stylesheet">
</head>
<body>
    <div class="container">
        <div class="title">contact us</div>
        <div class="EMAIL">
            Your email <br>
            <font>
                <input type="email"; placeholder="email@example.com"; style="width:353px; height:30px; padding-left:20px; font-size : 15px;"; >
            </font>
        </div>

        <div class="FN">
            First name<br>
            <font>
                <input type="text" style="width:170px; height:30px;">
            </font>
        </div>
        <div class="LN">
            Last name <br>
            <font>
                <input type="text" style="width:170px; height:30px;">
            </font>
        </div>
        <div class="MSG">
            Message <br>
            <font>
                <input type="text" style="width:370px; height : 150px">
            </font>
        </div>
        <div class="CB">
            <input id="sub" type="checkbox">
            <label for="sub">Subscribe</label>
        </div>
        <div class="SB">
            <font>
                <button type="submit" style="width : 170px; height : 50px; color : white; background-color : orange; border-radius : 5px; font-size : 20px; border:0;">SEND
                </button>
            </font>
        </div>
    </div>
</body>
</html>
```
``` css
.container {
    width : 500px;
    height : 700px;
    padding : 50px;
    box-sizing : border-box;
}

.title {
    width : 400px;
    height : 50x;
    font-weight : bold;
    font-size : 30px;
    padding : 5px;
    box-sizing : border-box;
}

.EMAIL {
    width : 400px;
    height : 85px;
    font-size : 20px;
    padding : 5px;
    box-sizing : border-box;
}

.FN {
    width : 200px;
    height : 85px;
    float:left;
    padding : 5px;
    box-sizing: border-box;
    font-size : 20px;
}

.LN {
    float:right;
    width : 200px;
    height : 85px;
    padding : 5px;
    box-sizing: border-box;
    font-size : 20px;
}

.MSG {
    clear :both;
    width : 400px;
    height : 200px;
    padding : 5px;
    box-sizing : border-box;
    font-size : 20px;
}

.CB {
    float:left;
    width : 200px;
    height : 50px;
    padding : 5px;
}

.SB {
    float:right;
    padding-top : 5px;
    padding-right : 17px;
}
```
- 위 코드의 문제점
1. css 파일 속에 중복되는 스타일들이 너무 많음.
2. html 코드 속 `<font>` 들의 스타일들을 하나도 css 파일로 옮기지 않음
3. div 박스 속 글자에 `<p>` 태그를 달지 않음.
- 이런 여러 문제들을 다음 12강에서 없애고 새롭게 만들어보겠다.