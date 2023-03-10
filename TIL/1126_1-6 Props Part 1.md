### props
- 부모 컴포넌트로부터 자식 컴포넌트가 받아온 데이터이다.
- props는 오직 부모에서 자식컴포넌트 방향으로만 전달 가능
- 부모 컴포넌트가 자식 컴포넌트에게 넘겨준 데이터들의 묶음(객체)
- 부모 컴포넌트에서 자식컴포넌트로 데이터를 내려보내기 위해서 props를 사용

어떻게 적용할까?
부모컴포넌트는 리턴값으로 자식컴포넌트 태그를 가지는데
자식 컴포넌트 태그 안에 내리고싶은 데이터를 JSX로 적고
자식컴포넌트는 매개변수 안에 props를 써준다

그러면 부모컴포넌트의 리턴값 안의 자식컴포넌트 태그 안에 넣었던 데이터를
자식컴포넌트가 매개변수에 props 를 써서 받을 수 있다.

* props의 파라미터 이름을 꼭 'props'라고 설정할 필요 없다. ( a, aa, b, 뭐든 가능)
 - 가독성을 위해 props라고 설정했을 뿐

### children
- 데이터를 전달하는 다른 방식
- 레이아웃 컴포넌트를 만들 때 자주 쓰이게 된다.
- props가 데이터 보내던 방식과는 다르게

return
 <자식태그>보낼 내용</자식태그>
로 보내고

자식컴포넌트도 매개변수로 props, 리턴에 <div>{props.children}</div> 의 양식으로 받는다.

구조분해 할당과 Props
- 구조분해 할당을 props에 적용하면 props에서 값을 가져올 때 더 간편하면서도 가독성 오름.
- 간단히 말하면 , 매개변수가 들어갈 자리에 중괄호 안에 객체의 key name을 적어주는 것
 ex. function Todo({ title }){ 
        return <div>{title}</div>
     }


defaultProps
- props가 없을경우 나타내는 기본값
- 구조분해 할당을 통해서 직접 객체에 접근한 경우에는 ({title= '기본제목'})이런식으로
 디폴트값 지정 가능
Child.defaultProps={
  name: '기본 이름'
}
