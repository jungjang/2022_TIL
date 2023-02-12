### state

state는 변수를 선언할수 있다.
값이 변하게 되면 렌더링이 일어난다. <br>
즉, 값이 변하게 되면 연관있는 컴포넌트들이 재렌더링이 되어 화면이 바뀌게 된다. 이때 state와 함께 사용 되어 값을 바꿔줄 수 있는 것이 함수가 setState이다.
```
const ShowYourName = () => {
  const [name, setName] = useState("John Doe");
 
  const changeName = () => {
    setName(name === "John Doe" ? "John Doe" : "NoName");
  };
 
  return (
    <div>
      <h1>내 이름은 {name}이야.</h1>
      <button onClick={changeName}>Change</button>
    </div>
  );
}
```
name이라는 변수명에 John Doe 라는 초기값을 넣었고, change버튼을 통해 John Doe 에서 NoName으로 바뀌게 된다.

---

### props

props 는 properties 의 줄임말로 <br>
어떠한 값을 부모 컴포넌트로부터 자식 컴포넌트로 전달하고 싶을때 props를 사용하게 된다.
```
//부모 컴포넌트인 App
const App = () => {
  const data = { John Doe: "신원확인", NoName: "신원미상" };
 
  return (
    <div>
      <ShowYourName data={data} />
    </div>
  );
}
 
//자식 컴포넌트인 ShowYourName
const ShowYourName = (props) => {
  const [name, setName] = useState("John Doe");
 
  const changeName = () => {
    setName(name === "John Doe" ? "John Doe" : "NoName");
  };
 
  console.log(props.data);
  // data = { John Doe: "신원확인" } 가 들어온 것을 확인할 수 있다.
 
  return (
    <div>
      <h1>내 이름은 {name}이야.</h1>
      <button onClick={changeName}>Change</button>
    </div>
  );
}
```

---

### 리렌더링 발생 조건

1. 내 state가 바뀌었을 때
setState() 메서드를 사용하여 state의 값이 바뀌게 변하게 되면
연관있는 컴포넌트들이 재렌더링이 되어 화면이 바뀌게 된다.
2. 내 props가 바뀌었을 때
부모 컴포넌트로부터 받은 props 값이 변경됐다면 리렌더링이 된다.
3. 부모 컴포넌트가 리렌더링 될 때
새로운 prop 이 들어오지 않더라고 부모컴포넌트가 리렌더링 된다면 자식컴포넌트 역시 리렌더링이 된다.
4. 강제 업데이트(forceUpdate)가 실행될 때
props 나 state 가 아닌 다른 값이 변경되었을 때 리렌더링을 하고 싶다면 그때 사용할수 있는 메서드 이다.
