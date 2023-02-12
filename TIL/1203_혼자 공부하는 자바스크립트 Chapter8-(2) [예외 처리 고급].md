예외 처리와 관련된 추가기능 두 가지
예외객체
throw 구문
-> 예전에는 고급기능 거의 사용 안했지만
    현재 자바스크립트 프로그램 개발에는 두 가지 모두 적극적으로 사용되고 있다.

### 예외객체
- 예외가 발생하면 예외와 발생된 정보를 확인할 수 있게 해주는 것
- 예외 객체는 모든 웹브라우저 공통으로 '예외 이름(name)'과 '예외 메시지(message)'를 갖는다

```
try {
 
} catch (exception) {
  //catch의 괄호 안에 입력하는 식별자가 '예외객체'
  //아무 식별자나 넣어도 되지만 e 나 exception 사용
 
  //JS가 정해놓은 배열의 크기보다 배열이 너무 크게 선언될 경우
  //예외객체 예시
  //exception.name -> RangeError
  //exception.message -> Invalid array length
}
```

### throw
- JS는 예외가 거의 발생하지 않아서 수많은 버그를 일으킬 수 있다
  따라서 상황에 따라서 throw 키워드를 통해 예외를 강제로 발생시켜줘야 하는 경우가 많다
  
```
//1. 단순하게 예외를 발생시키는 경우
기본 형태
throw '문자열'
 
출력 결과> 
Uncaught 문자열
 
//2. 조금 더 자세히 예외 발생시킬 경우
기본 형태
throw new Error(문자열)
 
출력 결과> 
Uncaught Error: 문자열
  at 파일 이름:줄 번호
```

예외를 강제로 발생시키는 이유
- 내가 만든 함수를 다른 사람이 사용할 때 내가 의도하지 않은 형태로 코드를 사용할 수 있음
  이 때 예외를 강제로 발생시키면 다른 사람에게 주의를 줄 수 있고, 
  내가 만든 함수를 내가 의도한대로 처리하게 유도할 수 있음
  
```
<script>
  function test(객체) {
    console.log(객체.a + 객체.b)
  }
 
  test({})
</script>
 
// 다른 프로그래밍 언어는 정의 되지 않은 속성(undefined)을 조작시 예외를 발생시킴
// 그러나 JS는 undefined + undefined 를 NaN으로 반환함(오류 없이 정상적으로 코드 실행)
// -> 사용자에게 강제로라도 함수를 잘못사용했음을 인지시켜줄 필요 생김
// -> 이를 위해 예외를 강제로 발생시켜줌
```

```
<script>
  function test(객체) {
    if (객체.a !== undefined && 객체.b !== undefined) {
      console.log(객체.a + 객체.b)
    } else {
      throw new Error("a 속성과 b 속성을 지정하지 않았습니다.")
    }
  }
 
  test({})
</script>
// 실행 결과 
// > Uncaught Error: a 속성과 b 속성을 지정하지 않았습니다.
-> 이를 통해 사용자가 코드의 문제점을 인지하고 해결 가능
```
