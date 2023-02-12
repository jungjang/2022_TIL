## switch 조건문과 짧은 조건문

### switch 조건문
- 값에 따라서 조건 분기를 걸어주는 조건문이다.
- 기본형태 ( default키워드는 생략할 수 있다 )

switch (자료) {
  case 조건A:
    break
  case 조건B:
    break
  default:
    break
}

-예제 ( 짝홀을 구해주는 switch코드 )

```
    <script>
      const input = Number(prompt("숫자를 입력하세요", "숫자"));
      switch (input % 2) {
        case 0:
          alert("짝수입니다");
          break;
 
        case 1:
          alert("홀수입니다");
          break;
 
        default:
          alert("숫자가 아임다");
          break;
      }
    </script>
```

- break : switch 조건문이나 반복문을 빠져나가기 위해 사용하는 키워드
- switch 조건문의 괄호 안에는 비교할 값을 입력한다
- 입력한 표현식과 case 키워드 옆의 표현식이 같다면 case 키워드 바로 다음에 오는 문장을 실행(중괄효 필요x)


### 조건부 연산자
- 삼항연산자 라고 부르기도 한다
- 조건문과 비슷한 역할을 하는 연산자
- 기본형태
불 표현식 ? 참일때의 결과 : 거짓일 때의 결과

```
  <script>
    // 변수를 선언
    const input = prompt("숫자를 입력하시라요", "");
    const number = Number(input);
 
    // 조건문(삼항연산자)
    const result =
      number > 0 ? "0 이상의 숫자 입니다" : "0 이하의 숫자입니다";
    alert(result);
  </script>
```

### 짧은 조건문
- 논리 연산자(논리곱(&&), 논리합(||) 연산자)의 특성을 조건문으로 활용하는 것
- 다른 조건문 코드와 비교했을 때 이해하기 어려워 사용하지 말자는 개발자가 많다.
