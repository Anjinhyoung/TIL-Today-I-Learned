# 클래스
 * 프로그래밍 방법을 객체지향 프로그래밍이라고 함 - oop
 * 1. 설계도를 만들어 그 설계도에 의한 제품을 만든다.
   2. 제품은 완제품, 부품일 수 있다. ㅡ> 하나의 제품을 하나의 부품으로 완성 또는 하나의 제품을 두 개 이상의 부품으로 완성
   3. 설계도: 클래스, 완제품(부품):객체, 인스턴스
      * 객채랑 인스턴스는 동일한 의미이다.
 * oop는 조립방식이다.
 * 클래스 만들기 ㅡ> 기능(함수) + 상태(형태, 디자인)(변수)
 * 클래스는 최대 2 가지의 구성 요소를 갖는다:함수, 변수

# 클래스와 메서드
* 클래스는 class에 클래스 이름을 지정하고 ':'을 붙인 뒤 다음 줄부터 def로 메서드를 작성하면 됨
* 메서드는 클래스 안에 들어있는 함수를 뜻
* 메서드의 첫 번째 매개변수는 반드시 self를 지정해야 함
* ```python
  class 클래스 이름:
    def 메서드(self):
        코드
  ```

# 인스턴스 속성
* 인스턴스 속성(attribute)을 만들 때는 __init__ 메서드 안에서 self.속성에 값을 할당함
*  ```python
   class 클래스이름:
    def __init__(self):
        self.속성 = 값
   ```
* ```python
  class Person:  
    def __init__(self):
        self.hello = "안녕하세요"

    def greeting(self):
        print(self.hello)

   anjinhyung = Person()
   anjinhyung.greeting()
  ```
* 출력 결과
* ```
  안녕하세요
  ```
* __init__(initialize)이라는 이름 그대로 인스턴스(객체)를 초기화함
     1. 다수의 객체에 공통 사항이 필요하면 여기에 서술한다.
     2. 객체를 만드는 시점에서 추가적인 옵션이 매게 변수를 만든다.
* 앞 뒤로 '__' 이렇게 붙은 메서드는 파이썬이 자동으로 호출해주는 메서드인데 스페셜 메드라고 부름
* 인스턴스 속성은 __init__ 메서드에서 만든다는 점과 self에 '.'을 붙인 뒤 값을 할당함
* 클래스 안에서 인스턴스 속성을 사용할 때도 self.hello처럼 self에 점을 붙여서 사용하면
* self는 인스턴스 자기 자신을 의미함
* 인스턴스를 생성할 때 self.hello = '안녕하세요'처럼 자기 자신에 속성을 추가함
## 인스턴스를 만들 때 값 받기
   * __init__메서드에서 self 다음에 값을 받을 때 매개변수를 지정함
   * 매개변수를 self.속성에 넣어줌
   * ```python
     class 클래스 이름:
          def __init__(self,매개변수1,매개변수2):
              self.속성1 = 매개변수1
              self.속성2 = 매개변수2
     ```
   ## 예시
   * ```python
     class Car:
         def __init__(self, brand, color):
             self.brand = brand  # 자동차 브랜드 속성
             self.color = color  # 자동차 색상 속성
  
         def start_engine(self):
             print(f"{self.color}의{self.brand}가 자동차의 엔진이 시작되고 있습니다.")
             # 자동차의 엔진을 시작하는 메시지를 출력하는 메서드
     
         def drive(self, distance):
              print(f"{self.color}의{self.brand}가 {distance} 킬로미터 주행하는 중입니다.")
              # 주행 거리를 출력하는 메시지를 출력하는 메서드

         def stop_engine(self):
             print(f"{self.color}의{self.brand}가 엔진이 중단되었습니다.")
             # 자동차의 엔진을 중지하는 메시지 출력를 출력하는 메서드
     
     my_car = Car("포르쉐", "파란색")  # "포르쉐" 브랜드, "파란색" 색상의 자동차 객체 생성
     my_car.start_engine()  # 자동차의 엔진 시작 메서드 호출
     my_car.drive(50)  # 자동차 주행 메서드 호출, 50킬로미터 주행
     my_car.stop_engine()  # 자동차의 엔진 중지 메서드 호출
     ```
  * 출력 결과
  * ```
    파란색의 포르쉐가 자동차의 엔진이 시작되고 있습니다.
    파란색의 포르쉐가 50 킬로미터 주행하는 중입니다.
    파란색의 포르쉐가 엔진이 중단되었습니다.
    ```
   * 클래스 바깥에서 속성에 값을 바꿀 수 있음
   * ```python
     class Car:
          def __init__(self, brand, color):
              self.brand = brand  # 자동차 브랜드 속성
              self.color = color  # 자동차 색상 속성

          def start_engine(self):
              print(f"{self.color}의{self.brand}가 자동차의 엔진이 시작되고 있습니다.")
              # 자동차의 엔진을 시작하는 메시지를 출력하는 메서드

          def drive(self, distance):
              print(f"{self.color}의{self.brand}가 {distance} 킬로미터 주행하는 중입니다.")
              # 주행 거리를 출력하는 메시지를 출력하는 메서드

          def stop_engine(self):
              print(f"{self.color}의{self.brand}가 엔진이 중단되었습니다.")
              # 자동차의 엔진을 중지하는 메시지 출력를 출력하는 메서드

     my_car = Car("포르쉐", "파란색")  # "포르쉐" 브랜드, "파란색" 색상의 자동차 객체 생성
     my_car.color="빨간색"   # "빨간색" 색상으로 변경
     my_car.start_engine()  # 자동차의 엔진 시작 메서드 호출
     my_car.drive(50)  # 자동차 주행 메서드 호출, 50킬로미터 주행
     my_car.stop_engine()  # 자동차의 엔진 중지 메서드 호출
     ```

   * 출력 결과
   * ```
     빨간색의 포르쉐가 자동차의 엔진이 시작되고 있습니다.
     빨간색의 포르쉐가 50 킬로미터 주행하는 중입니다.
     빨간색의 포르쉐가 엔진이 중단되었습니다.
     ```

# 비공개 속성 사용하기
* 비공개 속성은 변수 앞에 '__'로 시작해야 함
* 단 '__init__'처럼 밑줄 두 개가 양 옆에 왔을 때는 비공개 속성이 아님
* ```python
  class 클래스 이름:
    def 메서드(self,매개변수):
        self.__속성 = 매개변수
  ```
* ```python
  class Wallet:
    def __init__(self,wallet):
        self.__wallet = wallet # 변수 앞에 __를 붙여서 비공개 속성으로 만듦
    def pay(self,amount):
        self.__wallet -= amount # 비공개 속성은 클래스 안의 메서드에서만 접근할 수 있음
        print(f"지갑에 {self.__wallet}이 있습니다.")

   jin = Wallet(10000)
   jin.pay(5000)
  ```
* 출력 결과
* ```
  지갑에 5000이 있습니다.
  ```
# 클래스 속성 사용하기
* 클래스 속성은 클래스에 속해 있으며 모든 인스턴스에서 공유함 
* 클래스 속성은 다음과 같이 클래스에 바로 속성을 만듦
* ```python
  class 클래스 이름:
     속성 = 값
  ```
* 예시
* ```python
  class Bag:
     bag = []
     def put_bag(self, stuff):
        Bag.bag.append(stuff)   # 클래스 이름으로 클래스 속성에 접근
  
  a = Bag()
  a.put_bag("연필")

  b = Bag()
  b.put_bag("지우개")

  print(a.bag)
  print(b.bag)
  ```
* 출력 결과
* ```
  ['연필', '지우개']
  ['연필', '지우개']
  ```
* Bag 클래스에 bag 클래스 속성을 넣고 put_bag 메서드를 만듦
* 인스턴스 두 개를 만든 뒤 각각 put_bag 메서드를 사용함
##### 가방을 공유하고 싶지 않다면?
* 가방을 여러 사람이 공유하지 않으려면 bag을 인스턴스 속성으로 만들면 됨
* ```python
  class Bag:
    def __init__(self):
        self.bag = []

    def put_bag(self, stuff):
        self.bag.append(stuff) 


   a = Bag()
   a.put_bag("연필")

   b = Bag()
   b.put_bag("지우개")

   print(a.bag)
   print(b.bag)
  ```
* 출력 결과
* ```
  ['연필']
  ['지우개']
  ```

# 클래스 속성 vs 인스턴스 속성
* 인스턴스 속성은 인스턴스별로 독립되어 있으며 서로 영향을 주지 않음
* 클래스 속성: 모든 인스턴스가 공유 인스턴스 전체가 사용행 하는 값을 저장할 때 사용

# 비공개 클래스 속성 사용하기
* 클래스 안에서만 접근할 수 있고, 클래스 바깥에서는 접근할 수 없음
* ```python
  class 클래스 이름:
    __속성 = 값 # 비공개 클래스 속성
  ```
* 예시
* ```python
  class Knight:
    __item_lmit = 10 # 비공개 클래스 속성
    def print_item_limit(self):
        print(Knight.__item_lmit) # 클래스 안에서만 접근할 수 있음
        
        
   x = Knight
   x.print_item_limit() # 10

   print(Knight.__item_lmit) # 클래스 바깥에서는 접근할 수 없음 실행하면 에러남
  ```
# 정적 메서드 사용하기
* 정적 메서드는 다음과 같이 메서드 위에 @staticmethod를 붙임
* 정적 메서드는 매개변수에 self를 지정하지 않음
* ```python
  class 클래스 이름:
    @staticmethod
    def 메서드(매개변수1, 매개변수2):
        코드
  ```
* @staticmethod처럼 앞에 @이 붙은 것을 데코레이터라고 하며 메서드에 추가 기능을 구현할 때 사용함
* 예시
* ```python
  class Calc:
    @staticmethod
    def add(a,b):
        print(a+b)
    @staticmethod
    def mul(a,b):
        print(a*b)
        
  Calc.add(10,20) # 클래스에서 바로 호출
  Calc.mul(10,20) # 클래스에서 바로 호출
  ```
* 출력 결과
* ```
  30
  200
  ```
* 정적 메서드는 self를 받지 않으므로 인스턴스 속성에는 접근할 수 없음
* 정적 메서드는 인스턴스 속성, 인스턴스 메서드가 필요 없을 때 사용함
* 정적 메서드는 메서드의 실행이 외부 상태에 영향을 끼치지 않는 순수 함수를 만들 때 사용함
* 정적 메서드는 인스턴스의 상태를 변화시키지 않는 메서드를 만들 때 사용함

# 클래스 메서드 사용하기
* 클래스 메서드는 다음과 같이 메서드 위에 @classmethod를 붙임
* 클래스 메서드는 첫 번째 매개변수에 cls를 지정해야 함
* ```python
  class 클래스 이름:
    @classmethod
    def 메서드(cls,매개변수1,매개변수2):
        코드
  ```
* 예시
* ```python
  class Peson:
     count = 0

     def __init__(self):
           Peson.count+=1 # 인스턴스가 만들어 질때 클래스 속성 count+=1을 더함

     @classmethod
     def print_count(cls):
           print("{0}명이 생성되었습니다.".format(cls.count)) # cls로 클래스 속성에 접근

   a=Peson()
   b=Peson()

   Peson.print_count()
  ```
* 출력 결과
* ```
  2명이 생성되었습니다.
  ```
