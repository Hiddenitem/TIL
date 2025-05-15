# GetAxis() (2025-05-15)
## GetAxis()
``` C#
float Input.GetAxis(string axisName);
```
- Input.GetAxis() 메서드는, 어떤 축에 대한 입력값을 숫자로 반환하는 메서드이다.
- Input.GetAxis()는 축(Axis)의 이름을 받는다.
- 아래와 같이 사용할 수 있다.
``` C#
float xInput = Input.GetAxis("Horizontal");
float zInput = Input.GetAxis("Vertical");
```
```
- Horizontal 축
1. 왼쪽 방향키, A키 누를 시 = -1.0 반환
2. 오른쪽 방향키, D키 누를 시 = 1.0 반환
3. 아무것도 안누를 시 = 0 반환

- Vertical 축
1. 아래 방향키, S키 누를 시 = -1.0 반환
2. 윗 방향키, W키 누를 시 = 1.0 반환
3. 아무것도 안누를 시 = 0 반환
```
- 어떤 키보드 자판이 눌리냐에 따라, 값을 반환해서 `xInput, zInput에 값을 저장`하고, 이후 메서드들을 이용해서 `움직이는 기능을 구현`한다.
``` C#
float xInput = Input.GetAxis("Horizontal");
float zInput = Input.GetAxis("Vertical");

float xSpeed = xInput * speed; // 좌*우 이동
float zSpeed = zInput * speed; // 상*하 이동
```
