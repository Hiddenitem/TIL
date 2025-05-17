# 태양계 간단하게 구현해보기 (2025-05-18)
![](./제목%20없는%20동영상%20-%20Clipchamp로%20제작%20(5).gif)
- 공이 공 주의를 자기 스스로 회전하면서 도는 것을 구현해보았다.

## 1. 태양 만들기
- 맨 가운데를 Sun 이라는 이름의 구 오브젝트를 만든다.
``` C#
using UnityEngine;

public class Rotateitself : MonoBehaviour
{
    // Update is called once per frame
    void Update()
    {
        transform.Rotate(0, 10f * Time.deltaTime, 0);
    }
}
```
- 간단히 `transform.Rotate`를 사용하여, `Y축` 방향으로 `10f * Time.deltaTime` 만큼 `회전`하게 구성하였다.

## 2. 주변에 회전하는 행성들 만들기
- 똑같이 여러 개의 구를 제작한다.
``` C#
using UnityEngine;

public class Rotate : MonoBehaviour
{
    // 가운데 기준으로 돌 오브젝트를 가져옴
    public GameObject Sun;
    // 원하는 속도를 인스펙터 창에서 입력할 수 있게 선언
    public float speed;

    // Update is called once per frame
    void Update()
    {
        // Sun 오브젝트의 위치를 기준으로 돌게 선언
        transform.RotateAround(Sun.transform.position, new Vector3(0, speed * Time.deltaTime, 0), speed * Time.deltaTime);
        // speed 만큼 자전하게 선언
        transform.Rotate(0, speed * Time.deltaTime, 0);
    }
}
```
- 주위를 도는 행성들의 코드는 다음과 같다.
- 태양을 중심으로 돌 예정이기에, `Sun` 이라는 게임 오브젝트를 가져올 수 있게 `public GameObject Sun;` 을 통해, `Sun` 변수에 `GameObject` 를 대입할 수 있게 만듬.
- `public float speed;` 를 통해, 사용자가 speed 값을 인스펙터 창에서 직접 입력하게 만들어, 각 행성들마다 속도를 다르게 줄 수 있게 만듬
- Update() 메서드 속에서, 저렇게 코드를 작성한다.
- `transform.RotateAround` 를 사용하여, `자신의 위치`를 `Sun.transform.position 을 기준`으로 `new Vector3(0, speed * Time.deltaTime, 0) 축`을 기준으로 `speed * Time.deltaTime 속도`만큼 돌게 만든다.
- `transform.Rotate(0, speed * Time.deltaTime, 0);` 을 사용하여, 행성을 자전시킨다.
