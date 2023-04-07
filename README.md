# Stats-Craft-LAB

# 1. 조건부확률과 Bayes 정리

날짜: 2023/04/03
발표자: 예진
참여자: 덕훈, 선중, 수진, 예진, 현호
키워드: Bayes, Binary Symmetric Channel, Combined experiment, 독립, 배반, 전확률, 조건부확률

### 강의자료

[확률 및 통계](http://www.kocw.net/home/search/kemView.do?kemId=1056974)

---

# 1. sample space → S(set) : 일종의 전체집합

- 아웃풋이 랜덤하게 나와서 우리가 예측할 수 없는 결과들을 뽑을 때 가능한 
모든 outcome들의 집합
- **확률공간을 다룰 때 전제조건**이 되는 것이 sample space
- sample space를 벗어나는 것은 생각할 필요가 없다

# 2.  Event(A) : A ⊂ S

- sample space의 **부분집합**
- P(A) : A라는 이벤트가 발생할 확률, prob(outcome ∈ A)
    - 특정한 outcome을 뽑았을 때, 그 outcome이 A라는 집합에 속할 확률
    

# 3. Conditional Probability(조건부확률)

### P(B|A) : **A라는 condition이 발생했을 때, B라는 이벤트가 발생하게 될 확률**

$$
P(B|A) = \frac{P(B∩A)}{P(A)}=\frac{P(B∩A|S)}{P(A|S)}
$$

- 분자: A와 B가 동시에 발생하는 것, A라는 집합과 B라는 집합의 교집합의 확률
- 분모: A에 해당하는 확률
    - 의미를 다시 생각해보면, P(A) ~ 일종의 전체집합(sample space)
- P(A) : sample space가 있을 때 A가 발생할 확률
- P(B∩A | S) : sample space가 있을 때 A하고 B하고 동시에 발생할 확률
- 그런데 이 sample space라고 하는 것을 굳이 condition 파트에 넣지 않는다: $\frac{P(B∩A|S)}{P(A|S)}$
- 우리가 구하는 특정 이벤트의 확률들은 **어떤 sample space가 있다**, 라고 조건이 설정된 확률
    - ex) **주사위**를 던지든, **동전을 두번 세번** 던지든, …
    - 그것에 맞는 sample space를 조건으로 해서 확률을 계산하게 된다

- 결국 조건부확률이라는 것은 A라는 것이 전체, 새롭게 형성된 일종의 sample space.
- 다만 전체 S라는 sample space의 일부분일 것
- 조건부확률의 여러 case
    - **P(today’s weather | yesterday weather, 2-day ago weather, …, 20-day ago weather)**
        - 오늘의 날씨가 어떻게 될까에 대한 확률
        - 오늘의 날씨가 오늘 뿐만 아니라 어제 날씨, 이틀 전 날씨, … 20일 전 날씨를 바탕으로
        - **조건부확률: 기존의 어떤 것들을 전제로 한다**
            - 그 전제가 발생했을 때, 우리가 원하는 event의 발생할 확률이 어떻게 되느냐
        - 기존 애들(yesterday weather, 2-day ago weather, …, 20-day ago weather)이 today’s weather에 얼마나 관련이 있는지, 그것을 따지는 것이 조건부확률
    

# 4. Total Probability(전확률)

- **A라는 event가 발생하게 될 확률**을 구하자: P(A)
- A라는 사건을 겹치지 않는 **여러 개의 독립적인 배반사건으로 나눠서** 각각의 확률의 **합**으로
    - $P(A) = P(A_1)+P(A_2)+... +P(A_n)$
    - {A1, A2, …, An} : Partition(분할) of S ~ **Sample space의 일종의 파티션**, (2강에서 수정하심)
    **각각의 요소는 S의 부분집합**
    
    ## **total probability 그림 + 참고)**
    
    ![Untitled](1%20%E1%84%8C%E1%85%A9%E1%84%80%E1%85%A5%E1%86%AB%E1%84%87%E1%85%AE%E1%84%92%E1%85%AA%E1%86%A8%E1%84%85%E1%85%B2%E1%86%AF%E1%84%80%E1%85%AA%20Bayes%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20c13e2430aa9040b5a782a9071dfe2dd0/Untitled.png)
    
    # 참고) **15-8. 전확률과 베이즈 정리**
    
    집합 $A$의 **분할(partition)** $\rm \left\{A_1, A_2, \dots, A_n\right\}$은 다음의 성질들을 만족합니다.
    
    - $\rm A_i \subset A, i=1,2,…,n$. 분할의 원소는 A의 부분집합입니다.
    - $\rm A_i \cap A_k = \varnothing, i=1,2,…,n; k=1,2,\dots,n; i \not= k$. 분할의 원소($A$의 부분집합)는 서로 배타적입니다.
    - $\rm A1∪A2∪⋯∪An=A$. 분할의 모든 원소를 모으면 $A$가 됩니다.
    
    ![Untitled](1%20%E1%84%8C%E1%85%A9%E1%84%80%E1%85%A5%E1%86%AB%E1%84%87%E1%85%AE%E1%84%92%E1%85%AA%E1%86%A8%E1%84%85%E1%85%B2%E1%86%AF%E1%84%80%E1%85%AA%20Bayes%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20c13e2430aa9040b5a782a9071dfe2dd0/Untitled%201.png)
    
    위와 같이 $A$ 의 분할이 주어졌을 때 임의의 사건 $B$ 의 확률을 다음과 같이 표현할 수 있습니다.
    
    $$
    \rm P(B)= \sum_{i=1}^{n}P(B\cap A_i)= \sum_{i=1}^{n}P(B∣A_i)P(A_i)
    $$
    
    이 식을 **전확률(total probability)** 정리 라고 합니다.
    
    이어서 마찬가지로 $A$ 의 분할과 사건 $B$ 가 주어졌을 때, 사건 $B$ 를 조건으로 하는 임의의 사건 $A_i$ 의 조건부 확률은 다음과 같습니다.
    
    $$
    \rm P(A_i∣B) = {P(A_i \cap B) \over P(B)}
    
    $$
    
    여기에서 $P(B)$에 전확률 정리를 대입하면 식은 다음과 같습니다.
    
    $$
    \rm {P(A_i \cap B) \over P(B)} = {P(A_i \cap B) \over \sum _{k=1}^{n}P(B∣A_k)P(A_k)}
    
    $$
    
    여기에 확률의 곱셈정리를 이용해 $P(A_i \cap B) = P(B|A_i)P(A_i)$를 대입하면 최종적으로 다음과 같이 정리할 수 있습니다.
    
    $$
    \rm P(A_i∣B)= {P(B∣A_i)P(A_i) \over  \sum_{k=1}^{n}P(B∣A_k)P(A_k)}
    $$
    
    이 식을 **베이즈 정리(Bayes' theorem)**라고 합니다.
    
    $P(B)$의 확률을 알고 있을 경우, 간단하게 다음과 같이 정리하기도 합니다.
    
    $$
    \rm P(A_i∣B)={P(B∣A_i)P(A_i) \over P(B)}
    
    $$
    
    - A1이 일어날 경우의 확률: $P(A_1) = P(A_1∩A)=P(A|A_1)$
    - $P(A) = \sum^{n}\limits_{i=1} P(A|A_i)P(A_i)$
        
        ## 참고) **확률의 곱셈정리**
        
        ---
        
        확률이 $0$이 아닌 두 사건 $A$와 $B$에 대해 
        조건부 확률 $\rm P(A|B) ~\text{과}~ P(B|A)$는 정의에 따라 
        
        $\rm P(B∣A)= {P(B \cap A)\over P(A)}, P(A∣B)= {P(A \cap B) \over P(B)}$
        
        이므로, 이를 정리하면 다음과 같은 식을 얻을 수 있습니다.
        
        $\rm P(A \cap B)=P(B∣A)P(A)=P(A∣B)P(B)$
        
        이것이 확률의 곱셈정리입니다.
        
        - 어떨 때 쓰나? $P(A|A_i)$가 존재할 때 ~ 사전에 알고 있는 것
        - 특정한 경우가 발생했을 때 전체적으로 어떤 경우가 발생하느냐
        - 문장이나 실제 상황에서 대단히 많이 발생한다
        - 역이 성립하기 때문에 언제든지 사용할 수 있음
    - $P(A|A_i)$: conditional probability(조건부확률)
    - 조건부확률이 주어져야, 각각의 배반사건을 적용해서 쓸 수 있다
        - 이런 조건부확률들을 사전에 알고 있다, 라고 해서 
        **priori ~ 선행적으로 알고 있는 조건부 확률**
    

# 5. Bayesian Theorem

- A라는 확률을 구하는 게 아니라, 
priori라는 선행 확률이 주어져 있는 조건의 위치가 서로 반대일 때, 주로 많이 다루게 된다
- 조건부확률의 입장에서 생각해보면,
    - $P(B|A) = \frac{P(B∩A)}{P(A)}$
    - $P(A|B) = \frac{P(B∩A)}{P(B)}$를 사용해서,
    - $P(B|A) = \frac{P(B∩A)}{P(A)}=\frac{P(A|B)P(B)}{P(A)}$
        - P(B|A)를 구해야 되는데, 이걸 단번에 구하기 어려운 상황일 때, 
        A와 B의 위치를 바꾸어(P(A|B))를 구한다 ~ 일종의 priori probability처럼 주어져 있을 때
        ⇒ Bayesian(베이지안)
- 파티션에 적용 ~ ex) $P(A_i |A)$ 를 구하라
    - 전체 A 확률에서 특정 사건 Ai가 일어날 확률
    일부분에 해당하는 Ai는 얼마나 되는가? 비율을 따지는 문제
    - 사전에 알려져 있을만한 priori prob를 사용하면,
        - $P(A_i|A) = \frac{P(A|A_i)P(A_i)}{P(A)}$로 변환
        - 분자에 해당하는 부분: priori prob를 통해 구할 수 있고,
        분모에 해당하는 부분: total prob를 통해 구할 수 있다
- 이렇게 **조건의 위치를 서로 바꾸어 가면서 문제를 푸는 기본적인 수학적인 방법**을 우리가 **Bayesian**이라고 말을 붙인다
- 주로 언제 쓰나?
    - A: observation data ~ 우리가 이미 관측한 데이터, 얻은 것에 해당하는 결과가 원래 어디에서 부터 비롯된 건지, 일종의 아웃풋
    - Ai: unknown original(input) data ~ 정말로 이게 맞을까?
    - A라는 것을 구해놓고, Ai라는 게 A에서 비롯될 수 있는지 확인
    - $P(A_i |A)$를 구할 때 받은 것(Ai)을 가지고 단번에 무엇인지 알 수 없기 때문에 변환해서 사용하는 것

# 5-2. 베이지안 예시 
Ex 1.7 > Binary Symmetric channel

- 통신 시스템의 채널 중 가장 간단한 예
: 2개의 데이터 심볼을 전송하는 하나의 환경

![Untitled](1%20%E1%84%8C%E1%85%A9%E1%84%80%E1%85%A5%E1%86%AB%E1%84%87%E1%85%AE%E1%84%92%E1%85%AA%E1%86%A8%E1%84%85%E1%85%B2%E1%86%AF%E1%84%80%E1%85%AA%20Bayes%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20c13e2430aa9040b5a782a9071dfe2dd0/Untitled%202.png)

- input symbols : { x1(0), x2(1) }
(binary니까 디지털 환경에서 0 또는 1을 보낸다)
    - 데이터를 전송하는 입장(transmitter)
- output symbols : { y1(0), y2(1) }
    - 데이터를 수신하는 입장(receiver)
- x1을 보냈을 때 동일하게 y1을 받으면 좋은데, 항상 그렇지 않음
→ 100%가 아니라 어떤 확률 값으로 존재한다
- 1을 보냈는데 1을 받을 확률: P11
마찬가지로 x2을 보내서 y2을 받을 확률: P22
    - => 이 경우들은 모두 올바르게 전송이 되는 경우, 
    P11과 P22가 1이면 아무런 에러가 없음
- 근데 문제는 에러가 발생을 할 것이다
x1 -> y2 일 확률: P12
x2 -> y1 일 확률: P21
- 여기서 P11 = P22, P12=P21이 같으면, Symmetric(대칭적)이다

---

- Bayesian으로 돌아와서 다시 살펴보면,
    - x1, x2: **original(input) data**
    - y1, y2: **observation data**
- p11이 실제로 어떤 의미의 확률 값인가 → 조건부 확률!
    - x1(0)을 계속 보내본다 ~ 수신하는 사람이 값을 확인
    - 계속 0을 보내고 있다는 것을 서로 알고 있는 상황에서
    - 에러가 생길 때가 있음: relative frequency처럼 경험적으로 측정
    - 그래서 그 값을 구한다
    - 수학적으로 표현: $P_{11}=P(y_1|x_1)$ (0을 보내서 0을 받게 될 확률)
    - 생각보다 조건부확률로 표시되어야 할 것들이 많다
    - 나머지도 다 구해보면, (priori)
        - $P_{11}=P(y_1|x_1)$
        - $P_{22}=P(y_2|x_2)$
        - $P_{12}=P(y_2|x_1)$
        - $P_{21}=P(y_1|x_2)$
    - P11 + P12 = 1, 
    P22 + P21 = 1
    → 여기서 1이 sample space
    - 1을 보냈을 때 받는 경우의 수는 2가지(0 또는 1)이니까
    - 이런 sample space를 문장에서 파악해야 한다
    - P(x1), P(x2): 사전에 실험적으로 직접 많이 해봐서 구할 수 있음 ⇒ priori(사전에 주어진 조건)

### 1) $P_{error}$

- transmission 환경에서 error가 발생할 확률
- x1을 보냈는데 y2를 받거나, x2을 보냈는데 y1을 받거나 ⇒ 총 2가지 경우
- $P_{error}=Prob(x_1\ trans\ + y_2\ receive)\ + \ Prob(x_2\ trans\ + \ y_1\ receive)$
    
    $=P(y_2|x_1)P(x_1)\ + \ P(y_1|x_2)P(x_2)$
    
    - x1 전송이 발생했을 때 y2 수신 확률 
    ~ 이때 x1 전송이 반드시 일어나야 해서 곱을 해준다(반대도 마찬가지)
    - error가 발생하는 전체 확률이므로 **unconditioned error**

### 2) when y2 received → what prob of x1 transmission?

- $P(x_1|y_2)$를 구하는 것
    - y2는 받은 신호니까 ~ observation data
    - 내가 뭔가 가지고 있는 observation data가 있는데 
    그것으로부터 original data가 무엇인지 확률적으로 예측해보겠다
    → 이런 문제는 모두 bayesian 룰에 의해 풀어본다!
    - $P(x_1|y_2)=\frac{P(y_2|x_1)P(x_1)}{p(y_2)}$
        - P(x1|y2)를 직접적으로 알 수 없지만, 
        변환해서 priori에 해당하는 값들을 알 수 있으면 구할 수 있다
        - 분자: x1을 전송해서 y2를 받게되는 확률
        - 분모: y2를 받게 될 확률
            
            $P(y_2) = P(y_2|x_1)P(x_1)\ + \ P(y_2|x_2)P(x_2)$
            

$$
P(x_1|y_2)=\frac{P(y_2|x_1)P(x_1)}{P(y_2|x_1)P(x_1)\ + \ P(y_2|x_2)P(x_2)}
$$

### 3) $P(x_1|_{error})$

- 조건이 error: error가 발생했다, transmission이 x1일 때 error가 발생했을 확률?
- $P(x_1|error) = \frac{P(error|x_1)P(x_1)}{P(error)}$
    - 위에서 구한 식 활용(베이지안 룰 적용)
    
    $$
    P(x_1|error) = \frac{P(y_2|x_1)P(x_1)}{P(y_2|x_1)P(x_1)\ + \ P(y_1|x_2)P(x_2)}
    $$
    

---

- 단말기나 시스템들이 랜덤하게 넘어오는 심볼
(0과 1 뿐만 아니라, 4개가 될 수도 있고, 8개가 될 수도 있고, … 2의 거듭제곱 수로 설계됨)
- 이 심볼의 개수가 늘어나면 늘어날수록 전송할 수 있는 데이터의 양이 상당히 커지는 것
- 그 심볼을 받았을 때, 받았다고 해서 바로 결정하는 것이 아니라, 확률적으로 분석함
- 내가 이걸 받았는데, 이게 0이라는 값인지 1이라는 값인지 확률적으로 비교를 해서
가장 가능성이 높은 녀석으로 결정을 해준다

### 활용> 통신 환경에서 노이즈가 있는 경우 / 페리티 체크(parity check)

![Untitled](1%20%E1%84%8C%E1%85%A9%E1%84%80%E1%85%A5%E1%86%AB%E1%84%87%E1%85%AE%E1%84%92%E1%85%AA%E1%86%A8%E1%84%85%E1%85%B2%E1%86%AF%E1%84%80%E1%85%AA%20Bayes%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20c13e2430aa9040b5a782a9071dfe2dd0/Untitled%203.png)

- 디지털 값을 보낸다: 0 / 1
- 한 시점에 전압의 값을 측정을 해보면 0이라는 값인지, 1이라는 값인지 decision
- 그런데 채널 환경에서 우리가 전송하려고 하는 식의 에너지의 값이나 전압의 값이나
깔끔하게 떨어지는게 아니라 노이즈가 있음
- 그 노이즈가 더해진다
그래서 1이라는 값, 0이라는 값이 아니라, 0.8, 0.1 이런 식으로 값이 왔다갔다 함
- 그런 값을 받았음에도 얘가 1이 될 확률, 0이 될 확률을
앞으로 배우게 될 확률 모델의 입장에서 계산하게 됨
- 그런데 노이즈가 대단히 크다: 바람도 불고 비도 오고 그러면
통신 환경에서 채널 상태가 좋지 않으니까 노이즈가 상대적으로 커진다
- 이때 운이 없이 어떤 시점(가장 낮아졌을 때)에서 값을 뽑아봤을 때,
0.3쯤 나왔다(사실은 1에 가깝다고 봐야하는데), 노이즈 때문에
그러면 0.5보다 작으니까 0으로 decision할 확률이 높아지는 것
- 그래서 단순하게 값을 보는 것이 아니라, 0과 1이라는 무수히 많은 비트스트림들을
적당히 한 덩어리씩 묶어서 -> (010000)(------)
- **페리티 체크(parity check)**: 1의 개수가 짝수개 였는지 홀수개 였는지
짝수개였으면 0을 넣어주고, 홀수개였으면 1을 넣어주고 해서
1의 개수가 일정하게 만들어줌(ex. 짝수개가 되게끔)
- 그러면 적어도 1비트 정도의 오차는 어디서 발생했는지 몰라도 
**오류인지 아닌지를 알 수 있다**
- 지로나 공과금 고지서를 보면, 개인번호-금액-맨마지막 숫자(체크코드)
체크코드를 통해서 오류인지 아닌지를 체크하게 해줌
- 비트 하나하나를 결정하는 것도 확률모델을 통해 하게 된다
~ 확률이 맞는지 틀린지를 체크코드로 확인하려고 하는 것 => **채널 코딩**

# 6. (1.8) Independent Events(독립 사건)

- If A and B are (mutually) independent, 
조건부 확률로 정의:

$$
 P(B|A) ≜ P(B) \\ (P(A|B) ≜ P(A)) 
$$

- A가 발생했을 때 B가 발생할 확률 ~ 상관이 없음, 서로 간에 영향을 주지 않는다
- 참고: 수학 기호
    
    [수학 기호 목록 (+,-, x, /, =, ...)](https://www.rapidtables.org/ko/math/symbols/Basic_Math_Symbols.html)
    
- 조건부 확률 위에서 식 풀어쓴대로 바꿔보자
    - $P(B|A)=\frac{P(A∩B)}{P(A)}=P(B)$
        - $P(A∩B)=P(A)P(B)$
    - $P(A|B)=\frac{P(A∩B)}{P(B)}=P(A)$
        - $P(A∩B)=P(A)P(B)$
- 결국 독립인지 아닌지를 확인하기 위해서는 $P(A∩B)=P(A)P(B)$만 확인하면 된다!
    
    ⇒ 가장 쉬운 예) repeated restored(매번 같은 조건이어야 함) trials
    
    - ex) 주사위를 한 번 던지고 → 두 번째 던졌을 때: 앞의 결과가 뒤의 결과에 영향을 주지 않음!
    - restored(복원) 의 의미
        - 공 뽑기
        
        ![Untitled](1%20%E1%84%8C%E1%85%A9%E1%84%80%E1%85%A5%E1%86%AB%E1%84%87%E1%85%AE%E1%84%92%E1%85%AA%E1%86%A8%E1%84%85%E1%85%B2%E1%86%AF%E1%84%80%E1%85%AA%20Bayes%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20c13e2430aa9040b5a782a9071dfe2dd0/Untitled%204.png)
        
        꺼낸 공을 다시 집어넣느냐(복원) 아니냐(비복원 ~ dependent)에 따라 달라진다
        
- **Independent라는 조건은 확률 문제를 풀 때 문제를 상당히 단순하게 만들어준다**

### ex) 날씨

- t라는 시점에서의 날씨 확률을 모델링
- $P(W_t\ | \ W_{t-1},\  \ W_{t-2},\  ...,\  W_{t-n})$
    - t-1시점, t-2시점, … 과거 시점에서의 날씨가 t시점의 날씨에 영향을 줄 확률?
    - 그런데 생각해보면 과거 시점의 날씨가 지금에 영향? → 연관성이 떨어진다
    - 연관성이 떨어지는 것을 independent라고 함
    - 서울의 날씨를 계산하는데, 뉴욕의 풍향/습도 등을 슈퍼컴퓨터에 넣어서 계산하지는 않는다
    - 그런 수없이 많은 인자들 중에 대부분은, 특정한 상황을 구하려고 할 때 영향이 없을 것이다
    - 위의 식) 그래서 많은 인자들 중, 이틀 정도 전의 날씨만 영향을 주고 
    나머지는 independent라고 가정해보자
- $P(W_t\ | \ W_{t-1},\  \ W_{t-2},\  ...,\  W_{t-n}) = P(W_t\ | \ W_{t-1},\  \ W_{t-2})$
    - 뒤에 있는 것들은 다 조건에서 사라진다

### ex2) State machine / state transition ~ Markov

- State machine

![[https://www.controleng.com/articles/finite-state-machine-for-embedded-systems/](https://www.controleng.com/articles/finite-state-machine-for-embedded-systems/)](1%20%E1%84%8C%E1%85%A9%E1%84%80%E1%85%A5%E1%86%AB%E1%84%87%E1%85%AE%E1%84%92%E1%85%AA%E1%86%A8%E1%84%85%E1%85%B2%E1%86%AF%E1%84%80%E1%85%AA%20Bayes%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20c13e2430aa9040b5a782a9071dfe2dd0/Untitled%205.png)

[https://www.controleng.com/articles/finite-state-machine-for-embedded-systems/](https://www.controleng.com/articles/finite-state-machine-for-embedded-systems/)

- Markov

![Untitled](1%20%E1%84%8C%E1%85%A9%E1%84%80%E1%85%A5%E1%86%AB%E1%84%87%E1%85%AE%E1%84%92%E1%85%AA%E1%86%A8%E1%84%85%E1%85%B2%E1%86%AF%E1%84%80%E1%85%AA%20Bayes%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20c13e2430aa9040b5a782a9071dfe2dd0/Untitled%206.png)

- 어떤 동그라미에서 다른 동그라미로 갈 확률이 얼마냐 ~ 등을 계산하게 된다
(각각의 연결된 확률이 다름!)

## Independent(독립) ≠ exclusive(배반)

- 상관성이 없다(independent)는 말과 공통된 부분이 없다(exclusive)는 것은 다른 의미이다!
- **교집합이 없다고 해서(exclusive) 서로 간에 영향을 안 준다거나 그렇지는 않다**

> If A and B are indep.

A와 $\bar B$ (B의 complement, 여집합)
$\bar A$와 B
$\bar A$와 $\bar B$ 

⇒ 모두 independent
> 

![Untitled](1%20%E1%84%8C%E1%85%A9%E1%84%80%E1%85%A5%E1%86%AB%E1%84%87%E1%85%AE%E1%84%92%E1%85%AA%E1%86%A8%E1%84%85%E1%85%B2%E1%86%AF%E1%84%80%E1%85%AA%20Bayes%20%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%85%E1%85%B5%20c13e2430aa9040b5a782a9071dfe2dd0/Untitled%207.png)

# 7. (1.9) Combined Experiments

- combined: 두 가지 이상의 시행
- for two experiments with S1, S2

**⇒ S(sample space) = S1 X S2
(X : cartesian product)**

- cartesian product ~ 순서쌍 만들어주는 것
- $S=\{(x_i,y_j)\ |\ x_i∈S_1,\  y_j∈S_2\}$

ex) 3 coins tossing

- S = {HHH, HHT, HTH, THH, HTT, THT, TTH, TTT} : 8가지 경우의 수

⇒ 3 experiments of 1 coin tossing

- S1 = {H, T}
- S2 = {H, T}
- S3 = {H, T}
- **S = S1 X S2 X S3**
