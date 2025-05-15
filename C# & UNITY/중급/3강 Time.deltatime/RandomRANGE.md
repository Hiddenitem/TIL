# C# RandomRange() (2025-05-15)
## 랜덤한 숫자를 얻을 수 있는 방법
- Random.Range() 메서드 = 입력으로 최댓값과 최솟값을 순서대로 받고, 그 사이의 랜덤한 숫자를 출력해준다.
``` C#
Random.Range(0, 3); // 0, 1, 2 중에 하나가 int 값으로 출력됨
Random.Range(0f, 3f); // 0f부터 3f 사이의 float 값이 출력됨(EX 0.5f)
```