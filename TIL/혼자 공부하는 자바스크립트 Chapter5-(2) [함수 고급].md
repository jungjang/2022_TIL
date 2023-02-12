## 05-2. 함수 고급
( JS는 함수도 하나의 자료로 취급, 따라서 변수에 할당할 수도 있고, 매개변수로 전달하여 활용도 가능)

 ### 콜백함수
- 매개변수로 전달하는 함수를 뜻함
 
### .forEach()
- 가장 기본적인 콜백 함수.
- 배열 내부의 요소를 사용해 콜백 함수를 호출
- 기본 형태 
function (value, index, array) { } 

```
  const numbers = [273, 52, 103, 32, 57]
 
		# array는 잘 쓰이지 않음
  numbers.forEach(function (value, index, array) {
    console.log(`${index}번째 요소 : ${value}`)
  })
    
  실행결과
  0번째 요소 : 273
  1번째 요소 : 52
  2번째 요소 : 103
  3번째 요소 : 32
  4번째 요소 : 57
```

### .map()
- 콜백 함수에서 리턴한 값을 기반으로 새로운 배열을 만드는 함수

```
  let numbers = [273, 52, 103, 32, 57]
  numbers = numbers.map(function (value, index) {
    return value + '이지롱'
  })
 
  console.log(numbers)
  ['273이지롱', '52이지롱', '103이지롱', '32이지롱', '57이지롱']
```

### .filter()
- 콜백함수에서 리턴하는 값이 true인 것들만 모아서 새로운 배열을 만드는 함수

```
const numbers = [0,1,2,3,4,5]
const evenNumbers = numbers.filter(function (value) {
	return value % 2 === 0
})
 
console.log(`{evenNumbers}`)
 
결과 : 0, 2, 4
```
 
### 화살표 함수
- 콜백함수에 활용하는 function () { } 의 단순한 형태
- map(), filter() 처럼 단순한 형태의 콜백함수를 쉽게 입력하고자 만들어진 함수 생성 방법
- function 키워드 대신 화살표 ( => )를 사용
- 기본 형태
(매개변수) => { }

### 타이머 함수
- 특정 시간마다, 특정 시간 이후에 콜백함수를 호출할 수 있는 함수
setTimeout(함수, 시간) : 특정 시간 후에 함수를 한 번 호출합니다.
setInterval(함수, 시간) : 특정 시간마다 함수를 호출합니다.

```
setTimeout(() => {
	console.log('1초 후 실행됩니다')
}, 1* 1000)
 
결과 : (함수 실행 1초 후 ) 1초 후 실행됩니다
 
let count = 0
setInterval(() => {
	console.log(`1초마다 실행됩니다(${count}번째)`)
    count++
}, 1* 1000)
 
결과
1초마다 실행됩니다(0번째)
1초마다 실행됩니다(1번째)
1초마다 실행됩니다(2번째)
...반복...
```

### 엄격모드
- script 블록 가장 위쪽에 'use strict' 문자열 등장하는 것을 볼 수 있다.
- 엄격모드라 불리는 기능으로, 이 문자열을 읽어들인 다음부터는 엄격하게 코드를 검사한다.
```
<script>
	data = 10
    console.log(data)
</script>
 
실행결과 10
```
이건 가능하지만
but , use strict 쓰면 오류라고 뜬다
```
<script>
	'use strict'
    data = 10
    console.log(data)
</script>
 
실행결과
Uncaught ReferenceError: data is not defined
```

### 선언적함수 vs 익명함수
- 익명함수를 쓰는게 대세
- 이유 : 익명함수가 안전하기 때문
( 선언적 함수는 호출이 위에 있더라도 선언적 함수 우선 실행 됨,
익명 함수보다 아래 있어도 우선 실행됨.
다른 <script>에서 호출했을 때 실행될 수도 있음
(그럴 일은 없지만 다른 스크립트의 익명함수 전에 호출이 적혀있을 경우)
익명함수는 순서대로 읽힘.(호출이 위에 있으면 오류 발생))
