# 언리얼 엔진 예제

Developed with Unreal Engine 4   

---
## 1. 스팀회사의 얼불춤 (A Dance of Fire and Ice)의 특징을 반영하여 구현한 시뮬레이션
[시연 동영상](https://youtu.be/osqCmpbZOio)   
- <얼불춤 게임 소개>   
얼불춤 (A Dance of Fire and Ice) 이라는 게임은 스팀회사의 리듬게임으로   
박자에 맞게 키를 누르면 빨간색 공과 파란색 공이 번갈아서 회전의 주체가 됩니다.   
![image](https://user-images.githubusercontent.com/92451281/192106199-b8e2749a-a354-4b25-a8d7-3b3549e1ad8e.png)   
- <개발>   
  - 스페이스 바를 누르면 회전의 주체가 바뀌도록   
  - ex) 처음 빨간색 공 중심으로 파란색 공 회전 -> 스페이스 바 -> 파란색 공 중심으로 빨간색 공 회전   
  - 액터 블루프린트 클래스에서 두개의 static mesh -> sphere로 설정 (material 빨간색, 파란색 각각 추가)
  - 회전의 중심이 되는 scene component 추가하여 자식으로 attach   
![image](https://user-images.githubusercontent.com/92451281/192106538-3f3028b8-e85c-4120-a1bc-ce1f7a0ce105.png)
  - switch Boolean 변수 추가
  - scene의 z축 중심으로 회전 AttachToComponent, AddRelativeRotation(Yaw 회전)
![image](https://user-images.githubusercontent.com/92451281/192106849-1fc15f64-93ac-4e82-98c4-56fadcbcc0bd.png)
  - FlipFlop으로 스위치 처럼 제어 DetachFromComponent (타깃 바꿔줌)
![image](https://user-images.githubusercontent.com/92451281/192106882-13f5cc1e-5695-448d-a747-5601197a9c10.png)

---
## 2. 롤 캐릭터 오리아나 스킬 구현
[시연 동영상](https://youtu.be/awBJutd_Jyc)
- <개발>
  - Player는 큐브 길게
  - Player 주변으로 구체(Sphere) 생성
  - Player 주변으로 구체는 항상 돈다.
  - 마우스 왼쪽 키(Left Mouse Key)를 누르면 500만큼 앞으로
    - 누른 상태에서 스페이스바(Space Key)를 누르면 일정거리 주변 액터가 모이게
    - 누른 상태에서 구체 주변으로 가면 부딪힌 방향에서 부터 다시 구체 회전
    - 누른 상태에서 Arrow Component를 추가하여 플레이어 방향을 알려줌
    - 누른 상태에서 마우스 오른쪽 키(Right Mouse Key)를 누르면 나아갔던 곳으로 다시 되돌아 오록
    - 누른 상태에서 일정거리 멀어지면 구체가 점점 빨간색으로 변하면서 다시 구체 회전
  - 스페이스 바(Space Key) 누른 상태에서 (모인 상태)
    - 앞으로 가면 모인 액터 분사 후 다시 Player 주변으로 구체 회전(부딪힌 방향에서 부터 회전)
    - 일정 거리 멀어지면 모인 액터 분사 후 다시 Player 주변으로 구체 회전
    - 마우스 오른쪽 키(Right Mouse Key)를 누르면 모인 액터 분사 후 다시 Player 주변으로 구체 회전
---
## 3. 배그 비슷한 간단한 TPS 게임 구현
[시연 동영상](https://youtu.be/J2F54ePCnwE)   
- <스크린샷>
![image](https://user-images.githubusercontent.com/92451281/195362029-8c4c5d8a-3028-4941-8c8b-4b8aafeb1e7a.png)
![image](https://user-images.githubusercontent.com/92451281/195362074-aafe6eeb-f4ee-4097-a8d1-c38b85579db4.png)
- <개발>
  - 블렌드 스페이스로 직접 에임 오프셋 구현 (애니메이션)
  - widget 크로스헤어 구현
  - widget 체력바 구현
  - line trace 사용
  - camera shake 사용
  - 소켓을 이용하여 총 매기, 총 잡기 구현
  - 체력바 기능 구현
