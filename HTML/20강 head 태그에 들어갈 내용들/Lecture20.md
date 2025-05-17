# HTML 코드 속 `head` 태그에 들어갈 내용들 (2025-05-17)
- 전 19강에서 배운 `놀라운 기능`으로 `새로운 HTML 문서`를 하나 만들자.
![](./제목%20없는%20동영상%20-%20Clipchamp로%20제작%20(3).gif)
- 이제 시작해봅시다.

## 1. `head` 태그?
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```
- html 웹 문서의 기본 탬플릿을 가져왔다.
- `html` 웹문서는 꼭 `<head>`와 `<body>`를 포함해야 한다.
- `<head>` 에는 사이트 내의 중요한 정보들이 들어가는데, 여기에 들어가는 중요한 태그들을 몇 개 알아보도록 하자.
---
### 1-1. 각종 CSS 파일들
```html
<head>
    <link href="주소~~~" rel="stylesheet">
</head>
```
- 우리가 이전부터 했었던, `CSS` 파일들을 첨부할 때, `링크 태그`들을 집어넣는 걸 여기에다 사용한다.
```
1. css/main.css // 상대 경로 
2. /css/main.css // 절대 경로
```
- 참고로, 이 두개는 서로 다른 경로를 의미한다.
- 1번은 현재 `HTML 파일과 같은 경로`에 있는 `css 폴더` 내의 `main.css` 파일을 의미한다.
- 2번은 `현재 사이트의 메인경로부터 시작`해서 `(메인경로)/css/main.css` 파일을 `첨부`하라 라는 의미를 가진다.
- `/` 기호가 처음부터 있다면, `사이트 메인 경로`부터 `참조`하라는 의미를 가진다.
---
### 1-2. 스타일`<style>` 태그
```html
<head>
  <style>
    .button {
      color : red;
    }
  </style>
</head>
```
- "CSS 파일 만들고 언제 링크하고 으아아악.."
- 하는 사람들을 위해, `<style>` 태그를 그냥 `<head>` 에 첨부해버려 작동시킨다.
---
### 1-3. 사이트 제목
```html
<head>
  <title>우왕신기방기</title>
</head>
```
- `브라우저 탭`에 띄어지는 사이트의 `이름`을 작성한다.
---
### 1-4. 여러가지 meta 태그들
``` html
<head>
  <meta charset="UTF-8">
  <meta name="description" content="갓딩애플 상시 숭배중.">
  <meta name="keywords" content="HTML,CSS,JavaScript,자바스크립트,코딩">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
```
1. 사이트 `인코딩 형식`을 지정할 때, `charset="UTF-8"` 로 `속성`을 지정할 수 있다.
2. 사이트의 `검색 결과 화면`에 띄워지는 `글귀`를 `수정`한다. `name="description" content="원하는거~"` 로 사용한다. 
3. `description`은 구글 `검색` 시 `파란 제목`으로 띄어지는 글귀, `keywords`는 검색에 도움을 주는 키워드이다.
4. 사이트 `초기 zoom 레벨`이나 `폭을 지정`해주려면, `name="viewport"` 속성을 부여하라. `width=device-width`는 모바일 기기의 `실제폭으로 로딩`해달라는 의미이다. `initial-scale = 1.0f` 이 부분이 `접속시의 화면 줌 레벨`이다.

반응형 웹사이트를 만들 때 4번 기능이 유용하다.
--
### 1-5. open graph
```html
<head>
  <meta property="og:image" content="/이미지경로.jpg">
  <meta property="og:description" content="사이트설명">
  <meta property="og:title" content="사이트제목">
</head>
```
- facebook이 제작한 `og` 라는 메타 태그가 있다.
![](./4.png)
- 가끔, 다른사람 카톡이나 블로그에서 글을 작성할 때 `링크`를 걸었을 때 이렇게 깔끔하게 보이게 만들고 싶다면
- 위에 있는 저 태그들을 사용해서 만들면 된다.
---
### 1-6. favicon
```html
<head>
  <link rel="icon" href="아이콘경로.ico" type="image/x-icon">
</head> 
```
- 웹사이트 제목 옆에 뜨는 아이콘을 커스텀할러면
- 이렇게 `link` 를 사용하여 제작하면 된다.
![](./갓딩애플%20상시숭배.png)
_좋은 자료 감사합니다. 갓딩애플_
- 이런식으로 아이콘이 생기게 된다.
