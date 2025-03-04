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
  Unity 프로젝트를 분석하고, 에셋 스토어를 둘러보면서 무료 에셋도 받아보고 게임 내 상호작용에 대해 팀원분들과 분석했습니다.

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
- 게임 분석 템플릿
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

# 3일차 C# 사전 문법 기초 / 데이터 다루기 실습
오늘은 무엇을 배울지에 대한 스크럼을 짧게 진행한 뒤 바로 사전 문법 기초를 진행했습니다.
아래는 데이터 다루기 실습을 진행했던 연습문제들이었습니다.

1. 데이터 다루기 실습

{

    int level = 10;
    int count = 5;

    float percentage = 0.1f;
    float speed = 4.5f;

    string nickname = "김도훈";
    string description = "학생입니다";

}

{

    int iten = 10;
    float ften = (float)iten;

    float fFive = 5.5f;
    float iFive=(int)fFive;

    int n = 10;
    string nstr = n.ToString();
    
    float f = 0.5f;
    string fstr = n.ToString();

    string strTen = "10";
    int iTen = Convert.ToInt32(strTen);

    string strSix = "6";
    int iSix = int.Parse(strSix);
}


6.Convert 와 Parse 는 어떤 차이가 있는지 설명해주세요.

Convert는 변환할 자료형이 뒤에 명시되어야 하고, Parse는 변환할 자료형이 앞에 명시되어야 하는것 같습니다.

  
2. 연산자 실습
   
{

    int ten = 10;
    //3 빼기
    //2 곱하기
    //1.5 곱하기
    //3 으로 나누기
    //4 로 나눴을때 나머지
    int seven = ten + 7;
    int three = ten - 3;
    int Ttwo = ten * 2;
    float Thalf = (float)ten * 1.5f;
    float Tthree = ten / 3;
    int Sfour = ten % 4;
}

{

    string name = "김도훈"; // 자신의 이름, 닉네임 으로 연습해보세요.
    int year = 2024;


    //위 변수를 이용해서 아래 문자열을 만들어 보세요.


    string introduce = "안녕하세요, 제 이름은 \"" + name + "\" 입니다."; // 안녕하세요. 제 이름은 "chad" 입니다.
    string thisYear = "올해는" + year + "년 입니다";  // 올해는 'year' 년 입니다. 
}

{

    int ten = 10;

    //아래의 결과값이 전부 true 가 되도록 논리연산을 만들어 보세요.

    bool result_1 = ten == 10;  // ten 이 10 이랑 같다
    bool result_2 = ten != 11;    // ten 이 11 이랑 같지 않다
    bool result_3 = ten < 20;    // ten 이 20 보다 작다
    bool result_4 = ten > 5;    // ten 이 5 보다 크다
}


4.사칙연산간 우선순위가 어떻게 될까요?

곱하기=나누기>덧셈=뺄셈


C# 사전 문법 기초는 4-4, if, else if, else 같이 쓰기까지 진행했습니다. 


# 4일차 개인학습
원래는 휴일이라 쉬는게 맞긴 한데, 입실을 눌러버려서 겸사겸사 추가학습을 했습니다.

![image](https://github.com/user-attachments/assets/afe74ef1-a7db-44f6-95db-3ab187bb175d)
![image](https://github.com/user-attachments/assets/9b20e431-dee2-423a-a1de-3fb74c0c61a8)
오늘은 함수와 클래스. 그리고 객체에 대해 학습했지만, 제대로 이해하고 사용하기엔 살짝 시간이 필요할 것 같습니다.

# 5일차 본격 프로그래밍 시작해보기
오늘은 문법 기초를 다시 되짚어보며 프로그램을 작성했습니다.

    string input = Console.ReadLine();
    
    int number;
    bool boolean;
    bool isnumber = int.TryParse(input,out number);
    bool isboolean=bool.TryParse(input,out boolean);

    if(isnumber==true)
    {
        Console.WriteLine("숫자입니다.");
    }

    else if(isboolean==true)
    {
        Console.WriteLine("불리언 입니다.");
    }
    
    else
    {
    Console.WriteLine("문자열입니다");
    }

1~2.프로그램에 입력된 것이 어떤 종류의 데이터인지 알려주는 프로그램(1-숫자와 문자열, 2-숫자와 문자열, 불리언까지)

    string input = Console.ReadLine(); // 데이터를 입력하고 Enter 를 누르면 다음으로 넘어갑니다.

    int number;
    bool isnumber = int.TryParse(input, out number);

    if (isnumber == false)
    {
    Console.WriteLine("숫자가 아닙니다.");
    }

    else if(number >= 100)
    {
    Console.WriteLine("`" +number+ "은(는) 100 보다 같거나 큰 수 입니다.`");
    }

    else
    {
    Console.WriteLine("`"+number+ "은(는) 100보다 작은 수 입니다.`");
    }
    3. 프로그램에 입력된 것이 100보다 같거나 큰 수인지, 작은 수인지, 아니면 숫자가 아닌지 알려주는 프로그램

    string input = Console.ReadLine(); // 데이터를 입력하고 Enter 를 누르면 다음으로 넘어갑니다.

    int number;
    bool isnumber = int.TryParse(input, out number);

    int divided = number / 2;
    int remainder = number % 2;

    if (isnumber == false)
    {
        Console.WriteLine("숫자가 아닙니다.");
    }

    else if (remainder==0)
    {
        Console.WriteLine( number+"은(는) 짝수 입니다.");
    }

    else
    {
    Console.WriteLine(number+"은(는) 홀수 입니다.");
    }
4. 프로그램에 입력된 것이 홀수인지, 짝수인지, 숫자가 아닌지 알려주는 프로그램(짝수는 2로 나눴을 때 나머지가 0인 것을 이용한)

5. 언제 if 를 쓰고 언제 case 를 쓸까요?
if는 논리 연산이나 새로운 변수를 통해 바뀌는 수를 체크하지만
case는 변할수 있거나, 새로운 변수가 아닌, "변수 하나의 고정된 값"만을 체크합니다.

# 6일차 Lv2. 제어문(조건문, 연산자)
오늘도 문법 기초를 다시 되짚어보며 프로그램을 작성했습니다.

    Console.WriteLine("첫번째 수를 입력해 주세요");
    string input = Console.ReadLine();
    
    Console.WriteLine("두번째 수를 입력해 주세요");
    string input2 = Console.ReadLine();
    
    int num;
    bool result1 = int.TryParse(input, out num);
    
    int num2;
    bool result2 = int.TryParse(input2, out num2);
    
    
    if (result1 && result2)
    {
        if (num == num2)
        {
            Console.WriteLine(num+"와(과)"+num2+"은(는) 같습니다.");
        }
        else if(num>num2)
        {
            Console.WriteLine(num+"은(는)"+num2+"보다 큽니다.");
        }
        else //(num<num2)를 대신하는 else
        {
            Console.WriteLine(num+"은(는)"+num2+"보다 작습니다.");
        }
    }
    
    else
    {
        Console.WriteLine("두 개의 숫자를 입력해주세요.");
숫자 구분+비교하기

    Console.WriteLine("대한민국의 수도는 어디인가요 ? 1.인천   2.평창   3.서울   4.부산");
    string input=Console.ReadLine();
    
    
    
    int num;
    bool isnum = int.TryParse(input, out num);
    
    if (isnum)
    {
        switch (num) // 정답 보고오니까... 그냥 if랑 else 쓰면 됐었음...
        {
            case 1:
                Console.WriteLine("오답입니다!");
                break;
            case 2:
                Console.WriteLine("오답입니다!");
                break;
            case 3:
                Console.WriteLine("정답입니다!");
                break;
            case 4:
                Console.WriteLine("오답입니다!");
                break;
            default:
                Console.WriteLine("1~4의 숫자를 입력해주세요.");
                break;
        }
    }
    else
    {
        Console.WriteLine("숫자가 아닙니다.");
    }
대한민국의 수도 찾기

    Console.WriteLine("어디로 여행을 가고 싶나요?");
    Console.WriteLine("1.제주도   2.코타키나발루   3.싱가포르   4.태국");
    string input = Console.ReadLine();
    int num;
    bool isnum = int.TryParse(input, out num);
    
    if (isnum)
    {
        switch (num) // 여기서 쓰는거였구나...
        {
            case 1:
                Console.WriteLine("제주도는 한국의 섬으로 비교적 방문이 쉽고 다양한 놀거리/먹거리가 준비되어 있습니다.");
                break;
            case 2:
                Console.WriteLine("코타키나발루는 말레이시아 사바주의 주도로, 말레이시아 동부 보르네오섬 최대의 도시입니다.");
                break;
            case 3:
                Console.WriteLine("싱가포르는 동남아시아, 말레이 반도의 끝에 위치한 섬나라이자 항구 도시로 이루어진 도시 국가입니다.");
                break;
            case 4:
                Console.WriteLine("태국은 중국문화, 말레이문화, 불교문화, 힌두문화, 이슬람 문화가 혼재되어 있습니다. 불교적인 모습을 많이 띄지만, 문화 자체는 색다르고 스펙트럼이 넓은 형태를 띄고 있어요.");
                break;
            default:
                Console.WriteLine("1~4의 숫자를 입력해주세요.");
                break;
        }
    }
    else
    {
        Console.WriteLine("숫자가 아닙니다.");
    }
휴양지 추천

    bool isperfect;
    
    do
    {
        Console.WriteLine("이름을 입력해주세요. (3~10글자)");
        string input = Console.ReadLine();
        int length = input.Length;
        Console.Clear();
    
        bool Nottoolow = length > 2;
        bool Nottoohigh = length < 11;
        if (length > 2)
        {
            if (length < 11)
            {
    
                Console.WriteLine("안녕하세요! 제 이름은 " + input + "입니다.");
            }
            else
            {
                Console.WriteLine("이름을 확인해주세요.");
            }
    
    
        }
        else
        {
            Console.WriteLine("이름을 확인해주세요.");
        }
    
        isperfect = Nottoolow && Nottoohigh;
    
    }
    while (!isperfect);
    // 내가 작성한 코드
    
    
    
    
    bool isSuccess;
    
    do
    {
        Console.WriteLine("이름을 입력해주세요. (3~10글자)");
        string input = Console.ReadLine();
    
        Console.Clear();
    
        if (input.Length >= 3 && input.Length <= 10)
        {
            Console.WriteLine("안녕하세요! 제 이름은 " + input + " 입니다.");
        }
        else
        {
            Console.WriteLine("이름을 확인해주세요.");
        }
    
        isSuccess = input.Length >= 3 && input.Length <= 10;
    }
    while (!isSuccess);
    // 정답 코드
3글자 이상~11글자 초과 이름 입력하기 / 올바른 답이 제출되기 전까지 프로그램이 실행되게 만들기

# 7일차 복습+홀수 출력반복문
오늘은 복습을 중점적으로 했습니다. if문은 기억하지 않고도 잘 쓸 수 있었지만. switch나 비교 연산자는 아직 기억이 잘 안 나서 기초 강의를 찾아보게 됐었습니다.

출력반복문:

    for (int i = 1; i <= 100; i++)
    {
        if (i%2 !=0)
        {
        Console.WriteLine(i);
        }
    }
    
    int j = 1;
    while (j <= 100)
     {
        if(j%2 !=0)
        {
            Console.WriteLine(j);
        }
        j++;
    }
    
    int k = 1;
    do
    {
        if (k % 2 != 0)
        {
            Console.WriteLine(k);
        }
        k++;
    } while (k <= 100);

# 8일차 기초반 복습+ 1. 홀수 출력 복습, 2. 배열을 사용한 합계 및 평균 계산
오늘도 복습을 중점적으로 했습니다. switch case를 사용해야 하는 상황이나, 반복문이 작동하기 위한 조건과 변수 초기화같은 것은 기억나질 않아 다시 찾아보긴 했습니다.
오늘 기억나지 않았던 걸 다시 기억해서 적자면

    switch(변수)
    {
    case n:
    코드 실행;
    break;
    ...
    }
    
    for (조건 초기화, 조건, 변화값)
    {코드 실행}
    
    while(조건)
    {코드 실행}
    
    do
    {코드 실행}
    while(조건)

이었던 것 같습니다.
반복문들은 홀수 출력을 복습하던 도중 기억이 안 났었고, switch case는 여행지 추천 코드때 기억이 안 났던 것 같습니다.

배열을 사용한 합계 및 평균 계산:

    int[] numbers = new int[5];
    Console.WriteLine("1번째 수를 입력해 주세요.");
    string result = Console.ReadLine();
    int iresult = Convert.ToInt32(result);
    Console.WriteLine("2번째 수를 입력해 주세요.");
    string result2 = Console.ReadLine();
    int iresult2 = Convert.ToInt32(result2);
    Console.WriteLine("3번째 수를 입력해 주세요.");
    string result3 = Console.ReadLine();
    int iresult3 = Convert.ToInt32(result3);
    Console.WriteLine("4번째 수를 입력해 주세요.");
    string result4 = Console.ReadLine();
    int iresult4 = Convert.ToInt32(result4);
    Console.WriteLine("5번째 수를 입력해 주세요.");
    string result5 = Console.ReadLine();
    int iresult5 = Convert.ToInt32(result5);
    numbers[0] = iresult;
    numbers[1] = iresult2;
    numbers[2] = iresult3;
    numbers[3] = iresult4;
    numbers[4] = iresult5;

    int numLength = numbers.Length;
    float sum = numbers[0] + numbers[1] + numbers[2] + numbers[3] + numbers[4];
    float Average = sum / numLength;

    Console.WriteLine("sum:" + sum);
    Console.WriteLine("Average:" + Average);
    // 일단 돌아가는 지시문

작성까진 했으나 "이게 과연 맞는건가?" 싶어서 반복문으로 다시 작성했습니다.

    int[] numbers = new int[5];
    for (int i = 0; i < numbers.Length; i++)
    {
        Console.WriteLine(i+1+"번째 숫자를 입력해주세요.");
        string input=Console.ReadLine();
        int iinput = int.Parse(input);
        numbers[i] = iinput;
    }
    int numLength = numbers.Length;
    int sum = numbers[0] + numbers[1] + numbers[2] + numbers[3] + numbers[4];
    float Average = sum / numLength;
    Console.WriteLine("sum:" + sum);
    Console.WriteLine("Average:" + Average);
    //아 이건 아니다 싶어서 다시 작성한 반복문

힌트를 안 보고 풀어야 실력이 늘 것이란 생각때문에 힌트를 안 봤더니 "입력한 값들"이 아닌, 지정된 값이라는 것을 몰라서, 좀 길게 돌아서 간 것 같습니다...

# 9일차 달리기반 3~6
오늘은 복습할 필요가 없다 판단해 그대로 달리기반 문제들을 진행했습니다.

3. 팩토리얼 계산
   
"왜 i가 iinput보다 작은데 실행되는거지?" 라는 오해 때문에 많이 헷갈렸던 것 같습니다.
i가 iinput보다 작은 것이 반복문의 종료 조건이라 생각했는데, 오히려 그것이 반복문 시작 조건이라는 걸 아느라 시간이 좀 걸렸습니다.
    
        Console.WriteLine("Enter a number:");
        string input = Console.ReadLine();
        
        int iinput = int.Parse(input);
        
        int finput = 1;
        
        for(int i=1;i<=iinput;i++)
        {
            finput *= i;
        }
                
        Console.WriteLine("Factorial of "+iinput+" is "+ finput);

5. 숫자 맞추기 게임
   
톺아보기에 있던 랜덤 숫자 생성 덕분에 이건 그렇게 어렵진 않았습니다.


        Random random = new Random();
        int randomNumber = random.Next(); // 0과 int.MaxValue 사이의 난수 생성
        int randomNumberInRange = random.Next(1, 101); // 1과 100 사이의 난수 생성
        
        bool isright=true;
        
        do
        {
        
            Console.WriteLine("Enter your guess (1-100):");
            string input=Console.ReadLine();
            int iinput=int.Parse(input);
        
            if(iinput==randomNumberInRange)
            {
                isright = false;
                Console.WriteLine("Congratulations! You guessed the number.");
            }
            else if(iinput> randomNumberInRange)
            {
                Console.WriteLine("Too high! Try again.");
            }
            else
            {
                Console.WriteLine("Too low! Try again.");
            }
        
        }
        while (isright);

6. 이중 반복문 출력
   
이건... 가로 출력과 세로 출력이 정확히 어떻게 작동하는건질 몰라서 숫자만 대충 바꿔보다가 얻어걸렸습니다.
얻어걸린 뒤 "이게 왜 되는거지" 를 생각하다가 이해했어요.

        int main;
        int sub=1;
        string[] result = new string[9];
        for (int i = 2; i <= 9; i++)
        {
            for (int j = 1; j <= 9; j++)
            {
                sub = i * j;
        
        
                result[j-1] = i +" x "+j+"=" + sub+"  ";
        
        
            }
        
            Console.WriteLine(result[0]+result[1]+result[2]+result[3]+result[4]+result[5]+result[6]+result[7]+result[8]);
        }
        //가로 출력
        
        
        int main;
        int sub=1;
        string[] result = new string[9];
        for (int i = 1; i <= 9; i++)
        {
            for (int j = 2; j <= 9; j++)
            {
                sub = i * j;
        
        
                result[j-1] = j +" x "+i+"=" + sub+"  ";
        
        
            }
        
            Console.WriteLine(result[0]+result[1]+result[2]+result[3]+result[4]+result[5]+result[6]+result[7]+result[8]);
        }
        //세로 출력


# 10일차 달리기반 7
오늘도, 복습이 그렇게 필요한 것 같진 않아서 바로 문제부터 풀었습니다.

7. 행맨 게임

팀원분들의 도움을 받아서 겨우 작성했습니다.

아직 어떻게 작동하는지도 잘 모르고, 그리고 직접 작성할 수 있도록 감을 잡기 위해 내일은 아마 행맨 게임이 어떻게 작동했는지를 이해하는 데에 시간을 할애할 것 같습니다.


        string secretWord = "hangman";
        char[] guessWord = new char[secretWord.Length];
        
        for (int j = 0; j < guessWord.Length; j++)
        {
            guessWord[j] = '_';
        }
        
        int attempts = 6;
        
        int i = 0;
        bool wordGuessed=false;
        
            for (; (wordGuessed==false) && (i<attempts); i++)
            {
                
                int Leftattempts = attempts - i;
                Console.WriteLine(guessWord);
                Console.WriteLine("알파벳을 입력하세요:");
                Console.WriteLine("기회가 " + Leftattempts + "회 남았습니다.");
                string input = Console.ReadLine();
                Console.Clear();
        
                char cinput;
                bool ischar = char.TryParse(input, out cinput);
        
            if (ischar)
            {
                for (int k = 0; k < guessWord.Length; k++)
                {
                    bool isEqual = cinput == secretWord[k];
                    if (isEqual)
                    {
                        guessWord[k] = cinput;
        
                    }
                }
        
            }
            else
            {
                Console.WriteLine("한 글자만 입력해주세요.");
            }
        
                wordGuessed = (new string(guessWord) == new string(secretWord));
            if(wordGuessed)
            {
                Console.WriteLine(guessWord);
                Console.WriteLine("축하합니다! 정답을 맞추셨습니다.");
            }
        
            }


8. 숫자 야구 게임

이건... 오늘은, 7번의 행맨 게임을 기반으로, 어떻게 작동해야 하는지에 대해 생각하며 주석을 달아놓는 정도로만 그쳤습니다.

아마도, 혼자 하려면 시간이 꽤 많이 걸릴 것 같아서, 내일도 팀원분들에게 물어봐야 할 것 같습니다.

    
    Random random = new Random();
    int[] targetNumber = new int[3];
    //프로그램이 지정할 문제의 배열
    
    for (int k = 0; (k < targetNumber.Length); k++)
    {
        targetNumber[k] = random.Next(0,9);
    }
    //배열 안에 무작위 난수를 넣는 코드
    
    int[] userGuess = new int[targetNumber.Length];
    bool guessedCorrectly = false;
    //유저 인풋 추가
    
    for (int attempts = 0; (guessedCorrectly == false); attempts++) //시도 횟수 선언, 숫자가 맞을때까지 반복, 매 반복마다 시도 횟수 추가
    {
    
        Console.WriteLine($"세 자리의 숫자를 맞춰 보세요:{userGuess}");
        string input = Console.ReadLine();
        Console.Clear();
        //문제 출력
    
        bool isnum = false;
        if (input.Length==3)
        {
            int iinput;
            isnum = int.TryParse(input, out iinput);
        }
        else
        {
            Console.WriteLine("세 자리 숫자를 입력해주세요.");
        }
        //세 자리 숫자 확인
    
    
        if (isnum)
        {
            for (int k = 0; k < userGuess.Length; k++)
            {
    
            }
    
        }
        //스트라이크 | 볼 확인
    
        else
        {
            Console.WriteLine("숫자가 아닙니다.");
        }
        //숫자가 아닐 경우 출력
    
        guessedCorrectly = (userGuess) == (targetNumber);
        if (guessedCorrectly)
        {
            Console.WriteLine(userGuess);
            Console.WriteLine($"축하합니다! 정답을 {attempts}번 안에 맞추셨습니다.");
        }
        //정답을 맞췄을 경우 출력
    
    }
    
    - `targetNumber`: 컴퓨터가 선택한 3자리의 숫자를 저장하는 배열입니다.
    - `userGuess`: 사용자가 추측한 숫자를 저장하는 배열입니다.
    - `strikes`: 자릿수와 숫자가 모두 맞는 경우의 개수를 저장합니다.
    - `balls`: 자릿수는 맞지 않지만 숫자가 포함된 경우의 개수를 저장합니다.
    - `guessedCorrectly`: 사용자가 숫자를 정확히 맞췄는지를 나타내는 불리언 변수입니다.

# 11일차 달리기반 8
오늘도, 복습이 그렇게 필요한 것 같진 않아서 바로 문제부터 풀었습니다.

숫자 야구는 어느정도 완성하긴 했지만, 중복 검사를 아직 완성하질 못 했습니다.

        Random random = new Random();
        int[] targetNumber = new int[3];
        //프로그램이 지정할 문제의 답
        
        for (int k = 0; (k < targetNumber.Length); k++)
        {
            targetNumber[k] = random.Next(0,9);
        }
        //배열 안에 무작위 난수를 넣는 코드
        
        do
        {
        
        
        }
        while()
        
        
        int[] userGuess = new int[targetNumber.Length];
        bool guessedCorrectly = false;
        //유저 인풋 추가
        
        string input = "000";
        int strike = 0;
        int ball = 0;
        //초기 변수 선언
        
        for (int attempts = 0; (guessedCorrectly == false); attempts++) //시도 횟수 선언, 숫자가 맞을때까지 반복, 매 반복마다 시도 횟수 추가
        {
            strike = 0;
            ball = 0;
            //스트라이크|볼 초기화
        
            Console.WriteLine($"세 자리의 숫자를 맞춰 보세요:{input}");
            input = Console.ReadLine();
            Console.Clear();
            //문제 출력
        
            bool isnum = false;
            if (input.Length==3)
            {
                int iinput;
                isnum = int.TryParse(input, out iinput);
            }
            //숫자인지 확인
        
            else
            {
                Console.WriteLine("세 자리 숫자를 입력해주세요.");
            }
            //세 자리 숫자가 아닐 경우 확인 및 출력
        
        
        
        
        
        
            if (isnum)
            {
                for (int j = 0; j < userGuess.Length; j++)
                {
                    userGuess[j] = int.Parse(input[j].ToString());
                }
                // 문자열을 숫자 배열로
        
                for (int k = 0; k < userGuess.Length; k++)
                {
        
                    for (int i=0; i<userGuess.Length; i++)
                    {
                        if (userGuess[k] == targetNumber[i])
                        {
                            if(k==i)
                            {
                                strike++;
                            }
                            else if (k!=i)
                            {
                                ball++;
                            }
                            // 스트라이크|볼 확인
                        }
                    }
                }
                Console.WriteLine($"{strike} 개의 스트라이크, {ball} 개의 볼 입니다.");
                //스트라이크|볼 횟수 출력
        
            }
            //반복문 끝
        
            else
            {
                Console.WriteLine("숫자가 아닙니다.");
            }
            //숫자가 아닐 경우 출력
        
        
            if (strike==userGuess.Length)
            {
                guessedCorrectly = true;
                Console.WriteLine($"축하합니다! 정답을 {attempts}번 안에 맞추셨습니다.");
            }
            //정답을 맞췄을 경우 출력
        
        }

