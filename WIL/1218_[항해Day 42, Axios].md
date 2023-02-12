### Axios란? 

Axios는 브라우저, Node.js를 위한 Promise API를 활용하는 HTTP 비동기 통신 라이브러리


### axios의 기능

- 브라우저 환경: *XMLHttpRequests 요청 생성
- Node.js 환경: http 요청 생성
- Promise API 지원
- 요청/응답 차단(Intercept)
- 요청/응답 데이터 변환
- 취소 요청
- JSON 데이터 자동 변환
- 사이트 간 요청 위조(XSRF) 보호를 위한 클라이언트 사이드 지원

### axios의 특징

- 요청 객체에 url이 있다.
- 써드파티 라이브러리로 설치가 필요
- data 속성 사용
- data는 object를 포함
- status가 200, statusText가 ‘OK’이면 성공
- 요청에 타임아웃을 걸 수 있다.
- HTTP 요청을 가로챌수 있음
- download 진행에 대해 기본적인 지원을 함
- 좀더 많은 브라우저에 지원

### 사용법

get
```
const axios = require('axios');
 
// ID로 사용자 요청
axios.get('/user?ID=12345')
  // 응답(성공)
  .then(function (response) {
    console.log(response);
  })
  // 응답(실패)
  .catch(function (error) {
    console.log(error);
  })
  // 응답(항상 실행)
  .then(function () {
    // ...
  });
```
```
post
axios.post('/user', {
    firstName: 'Fred',
    lastName: 'Flintstone'
  })
  .then(function (response) {
  //post요청이 성공했을 때,
    console.log(response);
  })
  .catch(function (error) {
  //post 요청이 실패했을 때,
    console.log(error);
  });
```
