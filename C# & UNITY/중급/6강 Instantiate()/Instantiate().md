# Instantiate() (2025-05-15)
## 실시간 오브젝트 생성
- Instantiate() = 게임 도중에 실시간으로 오브젝트를 생성하는 메서드
- 탄알을 복제 생성하는 것 처럼 사용한다.
``` C#
Instantiate(원본);
Instantiate(bulletPrefab);
```
- 위 코드는 기본형이고, 아래 코드를 위주로 사용한다.
``` C#
Instantiate(원본, 위치, 회전);
Instantiate(bulletPrefab, transform.position, transform.rotation);
```
- 다음과 같이 사용한다.