# 언리얼 엔진 예제

Developed with Unreal Engine 4   

---
## 1. 스팀회사의 얼불춤 (A Dance of Fire and Ice)의 특징을 반영하여 구현한 시뮬레이션
[시연 동영상](https://youtu.be/osqCmpbZOio)   
- <얼불춤 개임 소개>   
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

---
## 3. 배그 비슷한 간단한 TPS 게임 구현
[시연 동영상](https://youtu.be/J2F54ePCnwE)
