Component
- 리액트의 컴포넌트 = 레고의 블럭같은 느낌 (떼었다가 붙였다가 가능)
- 컴포넌트라는 블록을 조립해서 만들고 싶은 형태로 구현
- 컴포넌트를 만들어봐라 : html태그를 리턴하는 함수를 만들어라

컴포넌트 사용시 주의해야할 점
- 컴포넌트의 가장 첫글자는 '대문자'로 시작한다.
- 컴포넌트를 만드는 파일은 대문자로 시작하는 카멜케이스로 만든다.

```
import React from 'react';
 
const App = () => {
  //return 문 위로 자바스크립트 쓸 수 있는 영역
  //컴포넌트 내부에서 쓰일 함수 쓰면 됨
 
  return (
    <div>
      {/*JSX(리액트에서 html을 사용하기 위한 문법)를 쓸 수 있는 영역*/}
    </div>
  )
};
//내가 만든 컴포넌트를 밖으로 내보내는 영역
export default App;
```

다른 컴포넌트를 품는 컴포넌트를 부모 컴포넌트라고 부르고,
다른 컴포넌트 안에서 품어지는 컴포넌트를 자식 컴포넌트라고 부른다.

```
import React from "react";
 
const Child = () => {
  return <div>연결 성공!내가 자식이오!</div>;
};
 
const Mother = () => {
  return <Child />;
};
 
const GrandFather = () => {
  return <Mother />;
};
 
const App = () => {
  return <GrandFather />;
};
 
export default App;
```
렌더링이란? : 화면에 보여지는 행위
