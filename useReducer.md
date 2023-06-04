# useReducer<br/>
여러가지 하위값을 포함한 복잡한 useState를 다룰때 사용하면 좋은 리액트의 Hook 중 하나이다.<br/>

![스크린샷 2023-06-05 오전 1 20 25](https://github.com/kong1034/Frontend-Theory/assets/19910034/ca75d7d5-1dc8-4799-96af-ca6ffadb2408)


이럴때 useReducer를 이용하면 코드 간결성 및 유지보수에도 도움을 준다.<br/>
<br/>
<br/>

#### 구성요소 및 역할<br/>
Dispatch - state의 변경를 요구하는 함수<br/>
Action - state를 어떻게 변경하고싶다는 내용을 담은 함수 <br/>
Reducer - Dispatch와 Action의 내용을 담아 state를 어떻게 바꿀건지를 담은 함수<br/>
<br/>
<br/>

#### 사용방법<br/>
<img width="212" alt="스크린샷 2023-06-05 오전 2 31 13" src="https://github.com/kong1034/Frontend-Theory/assets/19910034/7500d7bd-794d-4ac3-bda2-38d3a8f2b97e">
<br/>
<br/>

<img width="402" alt="스크린샷 2023-06-05 오전 2 51 46" src="https://github.com/kong1034/Frontend-Theory/assets/19910034/ddd89db3-5259-44bd-b6ab-bbfbce5cafc0"><br/>
- useReducer에는 reducer와 data의 초기값을 받는다. 그리고 변수에 dispatch도 같이 만들어준다.<br/>
- data는 useState를 이용해도 되지만 useReducer에 사용하는게 더 깔끔하다.<br/>
<br/>

- dispatch 함수 안에 액션을 정의한다.<br/>
- Action은 type과 payload를 지정해준다.<br/>
<br/>

<img width="468" alt="스크린샷 2023-06-05 오전 2 54 25" src="https://github.com/kong1034/Frontend-Theory/assets/19910034/fc9b1f42-ae0c-4fd8-b907-15e4ecbe4cac"><br/>

- Ruducer 함수 안에는 action의 타입별로 state를 어떻게 변경시킬건지에 대한 내용을 정의해준다.
