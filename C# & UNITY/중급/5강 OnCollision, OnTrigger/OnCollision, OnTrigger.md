# OnCollision, OnTrigger (2025-05-15)
## 콜라이더를 가진 두 게임 오브젝트 간의 충돌
- `리지드바디가 충돌`할 때, 기능을 구현할 때는 두 가지 충돌 종류중 한 가지를 사용해서 구현한다.

## OnCollision : 일반 충돌
- `일반적인 콜라이더`를 가진 `두 게임 오브젝트가 충돌`할 때 자동으로 실행된다.
- `충돌한 두 콜라이더는 서로를 통과하지 않고 밀어낸다.`
```
- OnCollisionEnter(Collision collision) : 충돌한 순간
- OnCollisionStay(Collision collision) : 충돌하는 동안
- OnCollisionExit(Collision collision) : 충돌했다가 분리되는 순간
```
- `Collision` 타입 = `충돌 관련 정보`를 담아두는 단순한 `정보 컨테이너`이다.
- 입력으로 들어안 collision을 통해 `충돌한 상대방 게임 오브젝트`, `충돌 지점`, `충돌 표면의 방향` 등을 알 수 있다.

## OnTrigger : 트리거 충돌
- 충돌한 두 게임 오브젝트의 콜라이더 중 `최소 하나가 트리거 콜라이더`라면 `자동으로 실행`된다.
- `두 게임 오브젝트가 충돌할 때 서로 그대로 통과한다.`
```
- OnTriggerEnter(Collider other) : 충돌한 순간
- OnTriggerStay(Collider other) : 충돌하는 동안
- OnTriggerExit(Collider other) : 충돌했다가 분리되는 순간
```
- OnTriggerEnter 메서드가 실행 = 메서드 입력으로 충돌한 상대방 게임 오브젝트의 콜라이더 컴포넌트가 Collider 타입으로 들어온다.
- Collider 타입인 이유 = `트리거 충돌에는 상세한 충돌 정보가 필요 없다`.
- `OnTrigger 계열의 메서드`는 `자신이 트리거 콜라이더가 아니어도 실행`된다.

## 실제 예시 : 탄알이 플레이어에게 맞는다면
``` C#
void OnTriggerEnter(Collider other) {
    // 충돌한 상대방 게임 오브젝트가 Player 태그를 가진 경우
    if (other.tag == "Player") {
        // 상대방 게임 오브젝트에서 PlayerController 컴포넌트 가져오기
        PlayerController playerController = other.GetComponent<PlayerController>();

        // 상대방으로부터 PlayerController 컴포넌트를 가져오는 데 성공했다면
        if (playerController != null) {
            // 상대방 PlayerController 컴포넌트의 Die() 메서드 실행
            playerController.Die();
        }
    }
}
```
- 이후, 이 스크립트를, 오브젝트에 컴포넌트로 추가하면 된다.