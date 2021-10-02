# Swift 문법 정리 - 1주차

## [1] 이름짓기, 콘솔로그, 문자열 보간법
강의 영상: <https://www.youtube.com/watch?v=8Xe_fr_WRgc>

1.	이름 짓기
```
  1. Lower Camel Case: function, method, variable, constant
  ex) someVariableName
  
  2. Upper Camel Case: type(class, struct, enum, extension…)
  ex) Person, Point, Week
```

2.	콘솔로그
```
  1. print: 단순 문자열 출력
  
  2. dump: 인스턴스의 자세한 설명(description property)까지 출력
```

3.	문자열 보간법(String Interpolation)
```
  : 프로그램 실행 중 문자열 내에 변수 또는 상수의 실질적인 값을 표현하기 위해 사용
  * 사용법: \() => 괄호 사이에 넣어주게 되면 문자열에서 자동으로 치환이 되어 나타남
  
  example: import Swift
           let age: Int = 10
           
           ”안녕하세요! 저는 \(age)살입니다.”
           // == “안녕하세요! 저는 10살입니다.” 
           
           ”안녕하세요! 저는 \(age + 5)살입니다.”
           // == “안녕하세요! 저는 15살입니다.”

```


## [2] 상수와 변수
강의 영상: <https://www.youtube.com/watch?v=umgxytoUdsE>

1. 상수
```
  1. 키워드: let
  
  2. 선언 방식: let 이름: 타입 = 값 (타입이 명확할 경우 타입 생략 가능)
  ex) let constant: String = “차후에 변경이 불가능한 상수 let”
  * 상수 선언 후 나중에 값을 할당하는 것이 가능하다.
```

2. 변수
```
  1. 키워드: var
  
  2. 선언 방식: var 이름: 타입 = 값 (타입이 명확할 경우 타입 생략 가능)
  ex) var variable: String = “차후에 변경이 가능한 변수 var”
  variable = “변수는 차후에 다른 값을 할당할 수 있다.”
  * 변수에 값이 할당되지 않은 상태에서 변수를 사용할 시 에러가 남
```


## [3] 옵셔널 / 옵셔널 값 추출
강의 영상: <https://www.youtube.com/watch?v=RxScvfe1dyU>

1. Optional
```
  : 값이 '있을 수도, 없을 수도 있음'
  - 열거형(enum)과 general의 합작
```

2. Optional의 필요성
```
  [ nil의 가능성을 명시적으로 표현함 ]
    - nil 가능성을 문서화 하지 않아도 코드만으로 충분히 표현가능
      * 문서 / 주석 작성 시간을 절약
    - 전달받은 값이 옵셔널이 아니라면 nil체크를 하지 않더라도 안심하고 사용
      * 효율적인 코딩
      * 예외 상황을 최소화하는 안전한 코딩
    ex) // someOptionalParam can be nil
        func someFunction(someOptionalParam: Int?){
        //...
        }
        
        //someParam must not be nil
        func someFunction(someParam: Int){
        //...
        }
        
        => someFunction(someOptionalParam: nil) [O]
        => someFunction(someParam: nil) [X]
```

3. Optional의 사용
```
  1. Optional의 사용
    ex) enum Optional<Wrapped> : ExpressibleByNilLiteral{
             case none
             case some(Wrapped)
        }
      
        let optionalValueL Optional<Int> = nil
       let optionalValue: Int? = nil
    
  2. ! 사용 : 암시적 추출 옵셔널(Implicitly Unwrapped Optional)
    - 
    ex) var optionalValue: Int! = 100
  
        switch optionalValue {
            case .none:
                print("This Optional variable is nil")
            case .some(let value):
                print("Value is \(value)")
        }
      
```

4. 


