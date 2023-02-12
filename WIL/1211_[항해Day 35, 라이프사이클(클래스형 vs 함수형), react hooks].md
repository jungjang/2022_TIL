### 1. 라이프사이클(클래스형 vs 함수형)

<img src="https://user-images.githubusercontent.com/109060295/218326951-69632b2c-b1ae-46ae-8eda-5d7d67106725.png" width="700px" height="500px" />

라이프사이클은 생성될 때(Mount), 업데이트할 때(Update), 제거할 때(Unmount)로 나눠진다.

Mount: 처음 컴포넌트를 불러와서 생성하는 단계<br>
Update: 아래 4가지 경우로 인해 데이터가 바뀌거나 부모 컴포넌트가 랜더링할 때 일어나는 단계<br>
(업데이트 조건)
props가 바뀔 때<br>
state가 바뀔 때<br>
부모 컴포넌트가 업데이트 되었을 때(=리렌더링했을 때)<br>
강제로 업데이트 했을 때 (forceUpdate())<br>
Unmount: 페이지를 이동하거나, 사용자의 행동으로 인해 컴포넌트가 화면에서 사라지는 단계<br>
 

리액트는 클래스형과 함수형으로 컴포넌트를 생성할 수 있는데,<br>
이제는 리액트 공식 발표상 함수형 컴포넌트만 사용된다.<br>
( 함수형 컴포넌트는 함축적인 프로그래밍이 가능하다는 이유에서 )

 

클래스형 라이프사이클<br>
render() 메소드와 Component 상속 필수<br>
state, props 사용이 불편하고, 많은 메모리 사용한다는 단점

 

함수형 라이프사이클<br>
간편한 컴포넌트 선언 및 프로그래밍 가능 React Hook을 사용<br>
state와 생명주기(Life Cycle) 메소드를 별도로 구현해야 함 => useState, useEffect 사용

 

 

### 2. react hooks

함수형태의 컴포넌트에서 사용되는 몇가지 기술을 Hook이라고 부름 <br>
상태관리를 위한 useState, 랜더링 직후의 작업을 실행설정하는 useEffect 등<br>
(클래스형 컴포넌트의 단점을 상쇄하기 위해 만들어진 함수형컴포넌트, 그런데 클래스형 컴포넌트의 장점이었던<br>
 state사용이나 life cycle을 직접 다루는 기능을 함수형에서도 쓰기 위해 등장한것이 react hook! )

 

 
