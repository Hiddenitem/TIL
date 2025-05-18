# 로렘입숨 (2025-05-)
## 1. GDScript 배우기
1. [Hello world](#hello-world-출력하기)<br>
2. [변수](#변수-알아보기)<br>
3. [열거형 enum](#열거형-enum) <br>
4. [배열](#배열-배우기) <br>
---
### Hello world 출력하기
```gd
extends Node


# Called when the node enters the scene tree for the first time.
func _ready() -> void: # 유니티의 Start
	pass # Replace with function body.


# Called every frame. 'delta' is the elapsed time since the previous frame.
func _process(delta: float) -> void: # 유니티의 Update
	pass
```
- 가장 기본적인 스크립트로
- `func`는 함수를 나타내며,
- _ready() 는 유니티의 Start / _process(delta:float) 는 유니티의 Update 메서드라 생각하자.

```
extends Node


# Called when the node enters the scene tree for the first time.
func _ready() -> void: # 유니티의 Start
	print("Hello world!")


# Called every frame. 'delta' is the elapsed time since the previous frame.
func _process(delta: float) -> void: # 유니티의 Update
	pass
```
- `_ready()` 메서드 속, `print("Hello world!")` 를 입력하고 스크립트를 메인 씬의 노드로서 저장하면, 출력 화면에 `Hello world` 가 재생된다.
> Hello world!
---
### 변수 알아보기
``` 
var number1 = 1 # 숫자 변수 선언
var number2 = 2

var result = number1 + number2

var my_name = "홍길동" # 문자열 저장 가능

var boxname = 123 

var am_i_hansome = true # 참 거짓의 bool 저장 가능

const yes_value = 1 # 상수 선언
```
- 여러 `변수`들을 여기서는 `var` 로 퉁쳐서 선언할 수 있다.
- `상수` 선언할 때는 `const` 로 선언할 수 있다.
---
### 열거형 enum
```
enum {ALLIANCE, ENEMY, UNKNOWN, }
enum Named {IDLE = 12, RUN, JUMP = 14 }
```
- 열거형 `enum` 은 `상수들을 묶어서 편하게 사용`할 수 있도록 만든 것이다.
- 일반적인 상수와는 달리, `숫자만` 담을 수 있다.
- 게임에서 발생한 상황이나 상태를 알아보기 쉽도록 숫자 대신 문자로 표현할 때 유용하다.
- 관행적으로, `열거형의 이름들은 알아보기 쉽게 대문자로 작성`한다.
```
enum {ALLIANCE, ENEMY, UNKNOWN, }
```
- 숫자들을 따로 작성하지 않는다면, `왼쪽부터 차례대로 0, 1, 2 ... 의 숫자`가 들어간다.
```
enum {ALLIANCE, ENEMY, UNKNOWN, }
enum Named {IDLE = 12, RUN, JUMP = 14 }

func _ready() -> void:
	print("Hello world!")
	print(ALLIANCE)
	print(ENEMY)
	print(UNKNOWN)
```
- 위 코드를 실행시켜보면, 

> Hello world!     <br>
> 0             <br>
> 1             <br>
> 2            <br>

- 위와 같은 출력 결과가 나타난다.
---
```
enum Named {IDLE = 12, RUN, JUMP = 14 }

func _ready() -> void:
    print(Named.RUN)
```
- 위와 같은 코드를 실행 시키면, `13` 이라는 값이 출력된다.
- enum 에서 처음에 숫자가 정해진다면(IDLE 에 12 값 들어감), 그 다음에 오는 상수는 다음 숫자가 대입된다.
- 따라서, RUN 이라는 상수는 13 값이 대입된다.
- 추가적으로, enum 자체에 이름을 붙여줄 수 있다.
```
enum Named {IDLE = 12, RUN, JUMP = 14}
```
- 이렇게 작성하면, `Named` 라는 이름의 `열거형 enum` 이 완성된다. 이를 `Named Enum` 이라고 한다.
- `이름있는 enum(Named Enum)` 을 사용할 때는, `.` 을 사용하여 출력해야 한다.
```
print(Named.RUN)
```
---
### 배열 배우기
- 배열은 여러 데이터를 한꺼번에 담는 상자로 이해하면 된다.
``` GDScript
var NAME =["a", "b", "c"] # NAME 이라는 이름의 3개의 요소를 가지는 배열 생성

func _ready() -> void:
	print(NAME)
	print(NAME[0])
	print(NAME[1])
	print(NAME[2])
```
> 출력결과<br>
> [a, b, c] <Br>
> a <Br>
> b <br>
> c <br>
---
### 함수(메서드)
- `함수` 는 다양한 `기능`들을 묶어서 편하게 사용하도록 만든 개념이다.
```
func TALK_function(my_input):
	print (my_input)
	print("라고 하겠습니다")
	
func 단호박_function() -> String:
	return "안됩니다"

func _ready() -> void:
	TALK_function("안녕하세요")
	TALK_function("반갑습니다")
	TALK_function(단호박_function())
```
### 출력결과
> 안녕하세요 <br>
> 라고 하겠습니다<br>
> 반갑습니다<br>
> 라고 하겠습니다<br>
> 안됩니다<br>
> 라고 하겠습니다<br>
- `함수(메서드)`를 선언할 때는 `func` 를 사용한다.
- 함수를 선언할 때, `func 함수의_이름(입력데이터를_받을_변수):` 형식으로 만든다.
- 입력받을 데이터가 없다면 `()` 만 적는다.
```
func 단호박_function() -> String:
    return "안됩니다"
```
- 위와 같이, 함수가 `어떤 값(안됩니다)` 을 `반환`하게 만들고 싶다면, `return` 문을 사용하여 반환할 값을 입력한다.
- 이때, 앞수 뒤쪽으로 `->` 와 반환할 값의 `반환형식(String)` 을 작성한다.
- 이제, `단호박_function()` 함수가 실행되면, `"안됩니다"` 라는 `문자열이 반환`된다.


