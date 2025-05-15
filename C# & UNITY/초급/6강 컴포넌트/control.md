# C# 문법 : 스크립트로 컴포넌트 사용하기 (2025-05-15)
## 1. 분기를 결정하는 조건문 if문
``` C#
public class Jumper : MonoBehaviour {
    public Rigidbody myRigidbody;

    void Start() {
        myRigidbody.AddForce(0, 500, 0);
    }
}
```
- `public Rigidbody myRigidbody;`를 통해, `Rigidbody 타입의 변수 myRigidbody를 선언`하였고, `public` 접근 제한자로 인해 `클래스 외부에서 접근이 가능`하다.
- 코드 편집 창을 닫고, `GameObject에 Jumper 스크립트를 추가`하면, 해당 `GameObject의 컴포넌트에 Jumper 스크립트가 추가`된다.
- GameObject 컴포넌트의 Jumper 스크립트에 `My Rigidbody 필드`가 생성되는걸 볼 수 있는데, 이는, `myRigidbody 변수가 인스펙터 창에 표시`된 모습이다.
- 이 필드에 `Rigidbody` 타입의 오브젝트를 넣으면 게임 실행 시, Rigidbody 타입의 오브젝트에 `AddForce(0, 500, 0) 메서드`가 실행된다.
- 이런 식으로, `스크립트를 통해 게임 오브젝트들을 사용`할 수 있다.