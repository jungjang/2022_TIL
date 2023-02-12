# if조건문

- 자바스크립트에서 가장 일반적인 조건문
- 쉬우면서도 많이 사용한다.
- 코드가 실행되는 흐름을 변경하는 것을 '조건분기'라고 부른다
- 조건에 따라서 코드를 실행하거나 실행하지 않을 때 쓰는 구문
- 이 때 조건은 Boolean형태를 의미한다.
- 비교연산자와 논리연산자 활용하여 조건 만든다.

- if(불 값이 나오는 표현식) {
    불 값이 참일 때 실행할 문장
  }

```
  오전과 오후를 구분하는 if 조건문
  <script>
    const date = new Date()
    const hour = gate.getHours()
    //if조건문
    if (hour < 12) {
    //표현식 hour < 12 가 참일 때 실행한다.
      alert('오전입니다.')
    }
    if (hour >= 12) {
    //표현식 hour >= 12 가 참일 때 실행한다.
      alert('오후입니다.')
    }
  </script>
 ```

 
if else 조건문
- 서로 반대되는 상황을 표현할 때 if구문을 두 개 쓰는게 아니라 'else'구문을 제공
- if 조건문 바로 뒤에 붙여서 if조건문이 거짓일 때 사용 ( 이를 조합한 조건문을 if else 조건문이라 한다.)
- 기본형태 

if ( 불값이 나오는 표현식) {
  불 값이 참일 때 실행할 문장
} else {
  불 값이 거짓일 때 실행할 문장
}

```
  //오전과 오후를 구분하는 if else 조건문
  <script>
    const date = new Date()
    const hour = gate.getHours()
    //if조건문
    if (hour < 12) {
      //표현식 hour < 12 가 참일 때 실행한다.
      alert('오전입니다.')
    } else{
      alert('오후입니다.')
    }
  </script>
```

중첩 조건문
- 조건문 안에 조건문을 중첩해 사용하는 것
- 여러번 중첩도 가능하다
- 형태
if ( 불 값이 나오는 표현식1) {
  if ( 불 값이 나오는 표현식 2) {
    표현식 2가 참일 때 실행할 문장
  } else {
    표현식 2가 거짓일 때 실행할 문장
  }
} else {
  if ( 불 값이 나오는 표현식 3 ) {
    표현식 3이 참일 때 실행할 문장 
  } else {
    표현식 3이 거짓일 때 실행할 문장
  }
}

if else if 조건문
- 중첩 조건문에서 중괄호를 생략한 형태로 겹치지 않는 3가지 이상의 조건으로 나눌 때 사용한다.

```
  if else if 조건문으로 시간 파악하기
  <script>
   // 변수 선언
    const date = new Date()
    const hour = gate.getHours()
    // if else if 조건문
    if (hour < 11) {
    // 표현식 hour < 11 가 참일 때 실행한다.
      alert('아침 먹을 시간입니다.')
    // 표현식 hour <11 이 거짓이고 hour <15 가 참일 때 실행
    } else if (hour <15) {
      alert('점심 먹을 시간입니다.')
     // 표현식 hour < 15가 거짓일 때 실행
    } else {
      alert('저녁 먹을 시간입니다')
    }
  </script>
```
 
