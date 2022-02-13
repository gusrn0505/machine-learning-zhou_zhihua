### 라그랑주 승수법(Lagrange Multiplier Method)

##### 의의

- 제약 조건 g(x) 아래에서, f(x) 함수의 극댓값과 극솟값을 찾을 수 있음 



##### 제약 조건이 등식일 시

1. **기하학적 해석**
   
   - ![](ML_study/ch06/screenshot/1.png)
     
     > 제약 조건 : g(x,y) = c 
     > 
     > 최적해를 찾아야 하는 함수 : f(x,y) =k (이때 k는 정해진 것이 아님)
   
   - 목적은 k의 값을 최대화 또는 최소화는 것이며, 이는 g(x,y) =c 와 f(x,y) =k 가 한 점에서 접할 때 달성된다. 
     
     - 임의의 k값을 부여함으로써, f(x,y)의 그래프를 g(x,y)=c 의 만족시키는 내에서 최대/최소 값을 탐색한다고 가정하자.  
       
       - 조건 1) g(x,y) =c 를 만족시키는 지점이 있다 <=> g(x,y)의 그래프와 f(x,y) =k 그래프간 점접이 있다. 
       
       - 조건 2) k은 f(x,y) 함수의 y절편으로 f(x,y) =k 직선 그래프를 최대한 우측으로 이동시키면 최대값이,  좌측으로 이동시키면 최소값이 된다. 
       
       - =>  **g(x,y) =c 와 f(x,y) =k가 한 점에서 접하는 때** 조건 1), 조건 2)를 충족시킨다. 
   
   - 접하는 지점을 $x^*$ 이라고 정의할 때, g(x,y) = c 와 f(x,y) =k 는 $x^*$ 에 접하기 때문에 $x^*$ 지점에서 gradient vector가 서로 상수배인 관계에 있다.  
     
     > $\nabla f(x^*) + \lambda \nabla g(x^*) =0 $  (식 1)
     > 
     >  s.t. $\lambda != 0 $
   
   - 라그랑주 승수법에서는 식 1을 아래와 같은 방식으로 보조 함수를 정의한다. 
     
     > $L(x,y, \lambda) = f(x, y) - \lambda(g(x,y) -c)$ (식 2) 
   
   - 즉, <mark>제약 조건 g(x,y) =c 아래에서 f(x,y)의 최대값을 찾는 문제</mark>는, 라그랑주 승수법에 따라<mark> $L(x,y, \lambda)$ 의 편미분 값이 0을 만족시키는 $\lambda$ 와 $x^*, y^*$ 의 값을 찾는 문제로 변경할 수 있다</mark>



2.  **전미분 (total differential)을 이용한 해석**
   
   > 제약 조건 g(x) 와 최적해를 찾는 f(x)를 3차원 함수로 표현하겠음. 추후 다변수 함수까지 일반화 가능 
   
   - 어떠한 함수 $f(x,y,z)$ 의 최소값, 최대값은 $df =0$ 인 지점 중에 존재한다. 
     
     > ![](https://t1.daumcdn.net/cfile/tistory/99839F3C5ACAC4D237)
     
     - 변수 $dx, dy, dz$ 가 각각 독립적이라면 함수 $df = 0$이 되는 조건은 아래의 식과 같다. 
       
       - $dx, dy, dz$ 가 독립적 <=>  $dx, dy, dz$ 각각은 서로 다른 변수의 곱과 합으로 대체 불가능하다
       
       > ![](https://t1.daumcdn.net/cfile/tistory/9912F1415ACAC4D739)
   
   - 제약 조건 $g(x,y,z) = 0$ 에 대해서 전미분을 하면 아래의 식을 얻을 수 있다. 
     
     > ![](https://t1.daumcdn.net/cfile/tistory/99EF72385ACAC4E02A)
     
     - 식 (7) 을 $dz$ 에 대해서 정리하면 다음과 같다 
       
       > ![](https://t1.daumcdn.net/cfile/tistory/99829E375ACAC4DC35)
   
   - 식 (8) 에서 계산한 $dz$ 를 식 (5) 에 대입하면 아래 식을 얻을 수 있음 
     
     > ![](https://t1.daumcdn.net/cfile/tistory/9974313D5ACAC4EE0E)
   
   - 식 (10)을 $dx, dy$ 에 묶어냄 
     
     > ![](https://t1.daumcdn.net/cfile/tistory/9932E0405ACAC4F201)
   
   - $\lambda$ 를 아래의 식 (12) 와 같이 정의하고, 식 (6)에서 증명했듯 $dx, dy$가 독립이기 때문에 식 (13)은 식 (16) 으로 정리할 수 있다. 
     
     > ![](https://t1.daumcdn.net/cfile/tistory/991F81405ACAC4F92C)
     > 
     > ![](https://t1.daumcdn.net/cfile/tistory/99E5193A5ACAC4FE2F)
     > 
     > <mark>$\frac{\partial f}{\partial x} = \lambda \frac{\partial g}{\partial x} , \frac{\partial f}{\partial y} = \lambda \frac{\partial g}{\partial y}$ (16)</mark>
   
   

##### 결론

- 등식 제약조건 g(x) 아래 f(x)의 최적해를 찾는 문제는 라그랑주 함수 $L(x, \lambda)$ 의 최적화 문제로 전환한다. 



p.s. 부등식 제약조건 g(x) 의 경우는 카루쉬 - 쿤 - 터커 조건과 연결되므로 여기선 생략하겠음 :) 


