# 객체 지향의 특징 : 다형성 (2025-05-16)
## 상속 관계에서의 다형성
- `C#에서 다형성` = 자식 클래스 타입을 부모 클래스 타입으로 다룰 수 있게 한다.
- 상속이란? 부모 클래스를 기반으로 자식 클래스를 만드는 방법.
- 따라서, `자식 클래스`는 `부모 클래스`의 `필드(변수)`와 `메서드(함수)`를 가지고 있는다.
### 어떠한 자식 클래스든, 부모 클래스 타입으로 취급하고 사용할 수 있다.
---
``` C#
public class Monster : MonoBehaviour {
    public float damage = 100f;

    public void Attack() {
        Debug.Log("공격!");
        // 공격 메서드 문 실행
    }
}
public class Orc : Monster {
    public void WarCry() {
        Debug.Log("전투함성!");
        // 전투함성 처리...
    }
}
public class Dragon : Monster {
    public void Fly() {
        Debug.Log("날기!");
        // 날기 처리...
    }
}
```
- `Monster` 부모 클래스를 만들고, 그것을 상속한 `Orc` 클래스와 `Dragon` 클래스를 만들었다.
- `Orc와 Dragon 클래스` 모두 `Monster 클래스`의 `필드`와 `메서드`는 물론, 자신의 `고유한 필드와 메서드`도 함께 가진다.
- Orc와 Dragon은 Monster 클래스를 상속하므로, Monster 타입으로 취급할 수 있다.
---
- 다음은 씬에서 Orc 타입의 오브젝트를 찾아 Monster 타입의 변수에 할당하는 예시이다.
``` C#
Orc orc = FindFirstObjectByType<Orc>(); // 씬에서 오크를 찾음
Monster monster = orc; // 몬스터 타입 변수 monster에 orc 변수를 할당
monster.Attack(); // 실행 가능
 오류 발생-> monster.WarCry(); // 실행 불가능(오류 발생)`
```
- `Monster monster = orc;` 가 실행되면, `orc`에 할당된 Orc 타입의 오브젝트가 `Monster 타입으로 취급`된다.
- 실제로는 바뀌지는 않지만, 컴퓨터 상에서는 저렇게 취급된다.
- 따라서, `Monster` 클래스 속의 `Attack()` 메서드는 `실행 가능`하지만,
- `Orc` 클래스의 `WarCry()` 메서드는 `실행이 불가능`하다. -> Monster 클래스는 없는 메서드 이기 때문이다.

## 다형성을 사용한 패턴
- `다형성`을 사용하여, `다양한 자식 타입`을 `하나의 부모 타입`으로 다뤄 `코드를 쉽고 간결하게 만들 수 있다`.
- 다음 예시에서, Orc 클래스의 WarCry() 메서드는 주변 몬스터의 공격력을 증가시킨다.
- `다형성`을 이용하면, WarCry()를 구현할 때, 몬스터를 종류별로 찾을 필요가 없다.
``` C#
public void WarCry() {
    Debug.Log("전투함성!");

    // 모든 Monster 오브젝트를 찾아 공격력을 10 증가시킴
    Monster[] monsters = FindObjectsByType<Monster>();
    for (int i = 0; i < monster.Length; i++) {
        monsters[i].damage += 10;
    }
}
```
- `Monster[] monsters = FindObjectsByType<Monster>();` 를 실행하면, `씬에 있는 모든 Monster 타입의 오브젝트`가 `monsters[] 배열에 저장`된다.
- 이때, Orc와 Dragon 타입을 따로 검색하지 않고, `Monster 타입`으로 취급해버려 `FindObjectByType<Monster>();` 가 `Orc` 타입과 `Dragon` 타입의 `오브젝트`도 찾아낸다.
- 이후, `반복문`을 통해 `monsters 배열`에 저장된 `모든 오브젝트`의 `damage 변수에 접근`하여 `10`을 증가시킨다.

## 오버라이드
- `메서드(함수)`에도 `다형성을 적용`하여 `같은 이름`의 메서드가 `서로 다른 방식`으로 `동작`하게 만들 수 있다.
- `오버라이드` = `부모 클래스`에서 작성된 `메서드`를 `자식 클래스`에서 `재정의`하는 것
- 다음 코드는 `같은 이름의 Attack() 메서드`가 `자식 타입`에 따라서 `서로 다른 공격 대사를 출력`하는 예시이다.
``` C#
public class Monster : MonoBehaviour {
    public virtual void Attack() {
        Debug.Log("공격!");
        // 공격 처리...
    }
}
public class Orc : Monster {
    public override void Attack() {
        base.Attack();
        Debug.Log("우리는 노예가 되지 않는다!");
    }
}
public class Dragon : Monster {
    public override void Attack() {
        base.Attack();
        Debug.Log("모든 것이 불타오를 것이다!");
    }
}
```
- `virtual` 키워드로 지정된 메서드는 `가상 메서드`가 된다.
- `가상 메서드` = `자식 클래스`가 `오버라이딩` 할 수 있도록 `허용된 메서드`이다.
- `자식 클래스`는 `override` 키워드를 사용하여 -> `부모 클래스`의 `가상 메서드(virtual)`를 `재정의`할 수 있다.
---
- Orc 타입의 오브젝트를 Monster 타입의 변수에 저장하고 Attack() 메서드를 실행해보자.
``` C#
Orc orc = FindFirstObjectByType<Orc>();
Monster monster = orc;
monster.Attack(); // orc의 Attack()이 실행됨.
```
- `monster.Attack()`이 실행되면, `Orc` 클래스에서 `재정의`한 `Attack() 메서드`가 실행된다.
- 따라서 `공격!`, `우리는 노예가 되지 않는다!` 로그가 순서대로 출력된다
- 즉, `기존 메서드`를 `부모 타입으로 실행`해도, `실제`로는 `자식 타입`에서 `재정의한 메서드가 실행`된다.

## base
- `자식이 부모의 메서드를 오버라이드` 할 때, `부모 메서드의 원형을 유지`하면서, `확장`할 수도 있고, `완전히 처음부터 메서드를 다시 만들 수 있다`.
- 예시의 `Orc와 Dragon`은 `Monster의 Attack()` 메서드 구현을 `유지`하면서 `자신만의 대사를 추가`한다.
- Orc에서 재정의한 Attack() 메서드를 다시 보자.
``` C#
public class Orc : Monster {
    public override void Attack() {
        base.Attack(); // Monster의 Attack()이 실행된다.
        Debug.Log("우리는 노예가 되지 않는다!");
    }
}
```
- `base.Attack();` 은 `부모 클래스`인 `Monster`의 `Attack() 메서드를 실행`한다.
- `base` 키워드 = `부모 클래스를 지칭`
- `base`를 사용하여 오버라이드 되기 전의 `원형 메서드로 접근`할 수 있다.
- 만약? 저 예시에서 `base.Attack();`을 사용하지 않았다면, Orc에서 Monster의 Attack() 메서드를 확장하는 것이 아닌, `처음부터 다시 만들게 된다`.

## 오버라이드 활용
- `오버라이드`를 활용하면, 다양한 `자식 클래스` `타입이 같은 이름의 메서드`를 `실행`하되, `실제 처리는 각각 다르게 만들 수 있다`.
- 다음은 `Attack()` 메서드로, `여러 가지 타입의 몬스터가 동시에 공격을 실행`하되, `각자 공격 대사는 다르게 출력하는 예시`이다.
``` C#
Monster[] monsters = FindOjbectByType<Monster>();
for (int i = 0; i < monsters.Length; i++) {
    monsters[i].Attack();
}
```
- 위 코드에서 `monsters`에 할당된 오브젝트들은 `Orc` 타입이거나 `Dragon` 타입이다.
- `Attack()` 메서드는 `Monster` 타입으로 실행되지만, 실제로는 `Orc`와 `Dragon` 등 `자식 클래스`에서 `재정의`한 `Attack()` 메서드가 `실행`된다.
