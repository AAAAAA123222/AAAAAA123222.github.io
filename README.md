# 사전캠프 시작

1. **내일배움캠프 Unity 트랙에 참여한 계기는 무엇인가요?**
    - *게임개발을 시도해보고 싶었고, 시도하더라도 후회 없을 정도로 노력해보고 싶었습니다.*
2. **본 코스 수료 후, 어떤 게임 개발자로 성장하고 싶나요?**
    - *아주 어려운 일이 되겠지만 독립적인 게임 개발자로 거듭나는 게 최종적인 목표입니다.*
    - *그걸 위해 많은 노력이 필요할 것이고 또 실무에서도 배워야 할 점이 끝없이 많을 것 같습니다*
3. **그 외에 Untiy 트랙에 기대하는 것이 있다면 자유롭게 작성해 주세요.**
    - *아직까지는 없는 것 같습니다*


# 1일차 개발자로서 시작하기

노션 슬랙에 가입하고 개발 블로그 (현재 github 블로그) 와 노션 멤버카드, 팀 노션에 참여했습니다.
팀 노션 생성 전 팀원분들을 기다리면서 C# 사전 문법을 살펴보긴 했지만, 역시 배워야 할 부분이 많은 것 같습니다.

# 2일차 팀원과 함께 Unity에 대해 알아가기

### Unity를 이용해 만든 프로젝트

|                **/** | **서비스 명** | **장르, 분류** | **제작사** |
| --- | --- | --- | --- |
| 첫 번째 프로젝트 | 데이브 더 다이버 | RPG, 경영 시뮬레이션 | 민트로켓 |
| 두 번째 프로젝트 | 이스케이프 프롬 타르코프 | FPS, 익스트랙션 슈터 | 배틀스테이트 게임즈 |
| 세 번째 프로젝트 | 폴 가이즈 | 플랫포머, 배틀 로얄 | 미디어토닉 |
| 네 번째 프로젝트 | 슬레이 더 스파이어 | 덱 빌딩, 로그라이크 | 메가 크릿 게임즈 |
| 다섯 번째 프로젝트 |  |  |  |

### 위 프로젝트들의 공통된 특징이 있나요?
독창적이고 참신한 게임플레이.

### 여러분이 생각하는 Unity의 강점은 뭐라고 생각하나요?
플러그인을 통한 개발 툴 자체의 폭 넓은 확장성과 편의성에 있다고 생각합니다.

### 여러분은 Unity를 이용해 어떤 게임을 만들어보고 싶으신가요?

- **장르** : 장르 불문하고 전부 좋아합니다. 그래도 한다면 타르코프나 델타포스같은 익스트랙션 슈터나 슬레이 더 스파이어와 비슷한 덱 빌딩 로그라이크 게임을 만들어보고 싶습니다. 
- **특징 :** 실력이든 장비든, 게임을 플레이하는 플레이어 자체가 성장했다고 느낄 수 있는 경험을 만들어주고 싶습니다.
- **그 이유는?** : 평소부터 오래 플레이해왔고 또 "이런 시스템이 추가된다면 어떨까" 하는 생각이 많았던 장르라서 그렇습니다.

### Unity 에셋 스토어 둘러보기
  ![image](https://github.com/user-attachments/assets/6bd49da3-4b2b-46db-b2ab-3e087fe6cf67)
  - Unity 에셋 스토어에서 모션 캡쳐 애니메이션을 구매했습니다.

### 게임 속 상호작용 분석 
- **게임 분석 템플릿
    1. **선택한 게임의 이름은 무엇인가요?**
    - 포켓몬스터 스칼렛•바이올렛
    1. **선택한 게임의 장르는 무엇인가요?**
        - 오픈 월드 RPG
    2. **선택한 게임의 어떤 시스템에 집중하셨나요?**
        - 포켓몬스터 스칼렛•바이올렛의 포획 시스템
    3. **해당 시스템이 동작하는 구조의 시작부터 과정을 자세하게 분석, 나열해봅시다.**
        - 필드에 포켓몬과 접촉하거나 볼을 던지면 인카운터 발생.
        - 인카운터가 발생하면 해당 포켓몬과 전투페이즈에 돌입.
        - 기본 포획 확률이 존재하고, 다양한 조건에 의해 볼을 던졌을 때 포켓몬의 포획 확률이 증가하며, 다양한 조건은 아래와 같다.
            1. 전투 초반에 사용하면 포획 확률이 늘어나거나(퀵 볼), 포켓몬이 무거울 수록 포획 확률이 늘어나는(헤비 볼) 등, 특정 조건에 따라 확률이 늘어나는 특수한 몬스터볼. 
            2. 포켓몬이 가진 상태이상에 따라 포획률이 늘어난다(독, 맹독, 화상, 마비, 얼음, 잠듦).
            3. 포켓몬별로 가진 포획률에 따라 포획확률이 달라진다(피카츄:190, 뮤츠:3).
            4. 특수한 경우에는 포획률이 100%가 된다(이벤트, 테라레이드 배틀).
            5. 포켓몬의 현재 체력이 낮을 수록 포획확률이 증가한다.
        - 포획을 시도할 때 볼이 흔들리는 연출이 존재한다. 볼을 던져서 포획을 시도했을때 상기된 조건에 의해 포획이 성공할 것인지 실패할 것인지 결정이 되고, 포획 성공 혹은 실패에 관한 연출이 재생이 된다. (볼이 몇번 흔들리고 잡히는 표시가 나오거나, 한번만 흔들리고 포획이 실패하여 포켓몬이 튀어나오거나, 혹은 한번만 흔들리고 포획이 성공하는 경우)
            - 포획한 포켓몬의 종류에 따라, 볼을 던진 횟수 그리고 특정 몬스터볼을 이용하여 던졌을 때 단 한번만 흔들리고 포획되는 “볼 크리티컬” 시스템이 존재한다.
        - 포획이 성공하고 난 뒤에는 먼저 플레이어의 포켓몬 엔트리에 들어갈 수 있는지 확인하고, 들어갈 수 있다면 포획한 포켓몬이 엔트리에 등록된다. 들어갈 수 없는 상태 (꽉 차거나 한 경우)라면 박스로 전송되어 등록된다.
    4. **직접 분석해본 내용 중 가장 핵심이 되는 구성 요소는 무엇이라 생각하나요?**
        - 포켓몬의 기본 포획률, 최대 체력과 현재 체력, 사용하는 볼의 종류, 포켓몬이 가진 상태 이상에 따라 달라지는 포획 확률.
            
            = 전투가 고조될수록 포획할 확률이 높아지는 시스템
