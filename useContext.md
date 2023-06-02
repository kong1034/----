# 리액트의 컴포넌트간 data 이동 방법<br/>
리액트는 단방향 데이터 흐름을 갖고있다.<br/>
즉, 부모 컴포넌트에서 자식 컴포넌트로 props를 이용하요 prop Drilling을 하게된다.<br/>
<br/>
<br/>

#### 장점<br/>
1. 컴포넌트가 몇 안되는 작은 규모의 프로젝트이면 에러 발견이 쉽다.<br/>
2. 데이터 흐름도 쉽게 읽을수 있어서 좋다.<br/>
<br/>

#### 단점<br/>
1. 컴포넌트가 조금이라도 많아지면 일일이 다 prop Drilling을 해야하므로 굉장히 비효율적으로 바뀐다.<br/>
<br/>
**만일 빨간색 컴포넌트에서 하얀색 컴포넌트 중 하나와 같은 props 또는 state를 사용해야한다면...?<br/>
자식 컴포넌트에서 부모 컴포넌트로 올라가야한다.<br/>
이럴경우 데이터의 흐름이 복잡해진다.<br/>
<br/>
<br/>

# context API<br/>
prop Drilling을 막기 위해 state를 전역으로 사용할수있는 context API가 생긴것이다.<br/>
<br/>
<br/>

#### 장점<br/>
1. state를 전역적으로 사용할수있다.<br/>

#### 단점<br/>
1. 렌더링 이슈가 발생할수있다.<br/>
<br/>

context API의 경우 사용하려면 provider라는 내장 기능을 이용하여 컴포넌트들을 포함시켜줘야한다.<br/>
만일 해당 컴포넌트의 하위 컴포넌트가 존재한다면 렌더링이 일어날때마다 하위컴포넌트까지 리렌더링 되는 문제가 발생한다<br/>
이 문제의 경우 useMemo()를 사용하면 해결되긴 하지만 쓰이는 컴포넌트가 많다면 하위컴포넌트들을 다 찾아서 useMemo를 써주는건 비효율적이다.<br/>

# useContext<br/>
컴포넌트간의 깊이가 깊을때는 props로 계속 내려줘야 하므로 (=prop Drilling) 이때 깊이와 상관없이 Context API + useContext를 사용한다.<br/>
<br/>
<br/>

#### Context API 와 redux의 차이는?<br/>

<redux><br/>
상태관리 도구이다.<br/>
<br/>

- 상태관리의 역할<br/>
1. 초기 값을 저장<br/>
2. 현재 값을 가져온다<br/>
3. 현재 값을 수정할수있다.<br/>

컴포넌트 리렌더링에 종속시키지 않을수 있다.<br/>

<Context API><br/>
- Context API의 역할<br/>
1. 초기 값을 저장한다.<br/>
2. 현재 값을 가져온다. => mapStateToprops, useSelector 사용<br/>
3. 현재 값을 수정할수있다. => useReducer 사용<br/>

컴포넌트 리렌더링에 종속된다.<br/>