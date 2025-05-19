# Table 레이아웃과 vertical-align 속성 (2025-05-13)
![](./오.png)<br>
- 위 같은 표를 만드는 코드를 작성해보자.
```html
<!-- html 파일 내부 -->
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link href="CSS/13강.css" rel="stylesheet">
</head>
<body>
    <div>
        <table>
            <!-- 제목 행은 <thead>안에 작성 -->
            <thead>
                <!-- tr(행) 먼저 만들고 그 다음에 td(열) 만들기 -->
                <tr>
                    <!-- th 사용시 글자가 굵어짐 -->
                    <th>
                        <p>dddd</p>
                        <p>aaaa</p>
                    </th>
                    <!-- vertical-align : 테이블 셀 내에서 상하정렬을 도와줌 -->
                    <td style="vertical-align:top">2222</td>
                    <td style="vertical-align:middle">3333</td>
                </tr>
            </thead>

            <!-- 일반 행은 <tbody>안에 작성 -->
            <tbody>
                <tr>
                    <!-- th 사용시 글자가 굵어짐 -->
                    <th>1</th>
                    <td>2</td>
                    <td>3</td>
                </tr>
            </tbody>
        </table>
    </div>
    <!-- text-align 사용해보기(정렬을 할 수 있다) -->
    <div> <img src="https://mdn.mozillademos.org/files/12245/frame_image.svg" width="32" height="32"> 
        <span style="vertical-align:top">image with a default alignment.</span></div>
</body>
</html>
```
``` css
/* css파일 내부 */
td, th {
    border:1px solid black;
}

table {
    /* 테이블에서 셀 간의 간격을 없애는 코드 */
    border-collapse : collapse;
}
```
- 코드를 보면서 짜보면 어렵지 않게 습득할 수 있다.
- `tr(row, 행)`을 먼저 작성하고 `td(column, 열)`에 해당하는 숫자를 입력해서 표를 제작한다.
- `vertical-align` 스타일을 사용하여 `셀내부`와 `<span>`같은 display-inline 요소들을 나란히 배치할 때 상하정렬을 도와주는 스타일이다.
- top, middle, bottom 말고도 super, sub, px와 같은 단위도 사용가능하지만, `테이블 내`에서는 무조건 `top, middle, bottom만 사용가능`하다.
---
```css
.box {
  display : table;
  display : table-row;
  display : table-cell;
}
```
- 가끔, div로 이루어진 요소들을 테이블화 시키고 싶을 수 있다.
- 그럴 때는 변하게 하고 싶은 요소에 `display:table`을 작성한 후
- `tr(행)로 만들 요소`에는 `table-row` / `td(열)`로 만들 요소에는 `table-cell`을 작성한다.

## 2. 과제 하기
![](./어렵다.png)<br>
```html
<!-- html 파일 내부 -->
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link href="CSS/practice3.css" rel="stylesheet">
</head>
<body>
    <div class="form-background">
        <h1 class="box font">Your shopping cart</h1>
        <div>
            <table class="box list">
                <thead>
                    <tr>
                        <th style="width : 50%; text-align :center;">ITEM</th>
                        <th style="text-align : center">AMOUNT</th>
                        <th style="text-align : center">PRICE</th>
                        <th style="text-align : center">TOTAL</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>
                            <img src="마크.png" style="width : 50%; height : 50%; margin-left : 10px; margin-top : 5px;">
                            <div style="float:right; width : 40%;">
                                <h3>SONY</h3>
                                <p>FE 70-200 mm F2.8 GM OSS</p>
                            </div>
                        </td>
                        <td style="text-align : right">1</td>
                        <td>1979.00</td>
                        <td>1979.00</td>
                    </tr>
                    <tr>
                        <td>
                            <img src="마크.png" style="width : 50%; height : 45%; margin-left : 10px; margin-top : 5px; object-fit : cover;">
                            <div style="float:right; width : 40%;">
                                <h3>SONY</h3>
                                <p>FE 70-200 mm F2.8 GM OSS</p>
                            </div>
                        </td>
                        <td style="text-align : right">1</td>
                        <td>989.00</td>
                        <td>989.00</td>
                    </tr>
                    <tr style="height : 40px">
                        <td colspan="3" style="border-bottom : none;"></td>
                        <td style="border-bottom : none;">2968.00</td>
                    </tr>
                </tbody>
            </table>
        </div>
        <div class="box">
            <div style="float:left;">
                <p class="font"><a href="#">Edit your shopping cart</a></p>
            </div>
            <div>
                <form>
                    <button type="submit;" class="Button">Choose payment method</button>
                </form>
            </div>
        </div>
    </div>
</body>
</html>
```
``` css
/* css파일 내부 */
body {
    margin : 0px;
}

div {
    box-sizing : border-box;
}

.form-background {
    width : 700px;
    height : 525px;
    background-color :lightblue;
    padding : 20px;
    margin : auto;

}

.box {
    margin-left : 30px;
}

td, th {
    border : 1px solid black;
    border-left : none;
    border-right : none;
    border-top : none;
}

table {
    border-collapse : collapse;
}

.Button {
    background-color : darkblue;
    border : 0px;
    border-radius : 5px;
    float:right;
    font-size : 20px;
    padding : 15px;
    color : white;
    margin-top : 20px;
    width : 270px;
    height : 60px;
}

.font {
    color : darkblue;
}

.list {
    width : 95%;
    background-color : white;
    border-radius : 15px;
}
```
- 해결 안된 부분들
1. 테이블 내부에 마크 이미지를 넣고, 이를 적용시키는 부분
2. 그 마크 이미지 옆에 글자에 대한 조절
3. 전체적으로 크기를 자유자재로 조작할 수 있는 코드를 만들어야 함
4. Price와 Total의 숫자들 앞에 가격표시를 어떻게 해야되는지 모르겠음.
- 다음 강에서 이에 대한 보강학습과 과제를 다시 해보도록 하자.