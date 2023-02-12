### 리액트 과제
아래 사진과 같이 양식을 만들고 빈 칸인지 검사 후 제출하면 alert가 뜨도록 만드는 과제였다.

<img src="https://user-images.githubusercontent.com/109060295/218325638-0c2b1d8c-f58a-478d-84e5-df1aaafb5a25.png" width="200px" height="250px" />

---
1) html 태그를 이용해 양식을 만들고
2) input 값이 없이 submit을 할 경우 '이 입력란을 작성하세요' 알림이 뜨게 하기 위해
    'input 태그 마지막에 required 를 넣었다.
    (ex. <input type="text" name="firstName" required />
- radio type 의 input 에 required를 적용시키려면 해당 radiotype input태그들의 속성중 name이 같아야했다.
3) submit을 할 때 alert가 뜨도록 하기 위해 전체 태그들을 <form></form>으로 묶고
폼 태그 속에 onsubmit="제출시 실행될 내가 script에 만든 함수()" 를 작성했다.

button의 속성에는 submit과 reset이 있다.
form 태그 안에서 버튼은 아래와 같은 역할을 한다.
```
<form>
  <button type="submit">    -> 폼 input에 입력된 데이터들을 제출
  <button type="reset">   -> 폼 input에 입력된 데이터들을 기본값으로 리셋
</form>
```
과제 완성 후 netlify 이용해서 배포하였다.
디렉토리 파일을 바로 드래그&드롭으로 업로드했다.

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>React S.A 과제</title>
  </head>
  <script>
    function alertSubmit() {
      alert("제출 완료!");
    }
  </script>
  <body>
    <form onsubmit="alertSubmit()">
      <label for="firstName">First Name :</label>
      <div>
        <input type="text" name="firstName" value="" required />
      </div>
      <label for="lastName">Last Name :</label>
      <div>
        <input type="text" name="lastName" value="" required />
      </div>
      <label for="email">Email :</label>
      <div>
        <input type="email" name="email" value="" required />
      </div>
 
      <label>Gender :</label>
      <input type="radio" name="gender" value="Male" required />Male
      <input type="radio" name="gender" value="Female" />Female
      <br />
 
      <label>Favorite :</label>
      <input type="checkbox" name="fav" value="HTML" />HTML
      <input type="checkbox" name="fav" value="JAVA" />JAVA
      <input type="checkbox" name="fav" value="JavaScript" />JavaScript
      <br />
 
      <label>Browser :</label>
      <select name="browser" id="browser-select">
        <option value="">브라우저를 선택하세요</option>
        <option value="크롬">크롬</option>
        <option value="파이어폭스">파이어폭스</option>
        <option value="엣지">엣지</option>
      </select>
      <br />
 
      <label for="date">Birthday :</label>
      <input type="date" />
      <br />
      <button>제출</button>
    </form>
  </body>
</html>
```
