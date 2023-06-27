## 싱글톤 패턴<br/>
1개의 인스턴스를 전역에서 사용하게끔 해주는 디자인 패턴 기술이다.<br/>

- Java, C++ etc<br/>
<br/>
￼<img width="489" alt="스크린샷 2023-06-27 오후 12 06 34" src="https://github.com/kong1034/Frontend-Theory/assets/19910034/475e9689-f303-48f3-8a17-8d9c99ffb877"><br/>
<br/>
Object.freeze를 사용하여 객체내 함수의 추가, 수정이 불가하게끔 만들었다.<br/>
이후 export를 하여 1개의 인스턴스를 전역에서 사용할수있게끔 만드는 기법이 싱글톤 기법이다.<br/>
<br/>
<br/>

- Javascript<br/>
<br/>
￼<img width="177" alt="스크린샷 2023-06-27 오후 6 32 34" src="https://github.com/kong1034/Frontend-Theory/assets/19910034/4962323a-3514-415f-b1cd-161240ca05bf">
<br/>
<br/>
<br/>

- 장점<br/>
인스턴스가 하나이므로 메모리 절약에 효율적이다.<br/>
<br/>
<br/>

- 단점<br/>
Javascript에서는 객체 리터럴만 사용해도 더 간단하게 구현이 가능해서 잘 쓰지 않는다.<br/>
앱의 규모가 커졌을때 참조하는 컴포넌트들이 많아지고 이에 따라 데이터의 흐름을 파악하기 어려워진다.<br/>
<br/>
<br/>

- React에서 사용?<br/>
React에서는 싱글톤 패턴 대신 Redux, React Context를 이용하여 전역 상태관리를 한다.<br/>
<br/>
<br/>
<br/>

## 팩토리 패턴<br/>
하나의 카테고리에 포함되는 여러가지 객체를 만들때 사용된다.<br/>
<br/>
<br/>
- 장점<br/>
동일한 카테고리에 포함되는 여러 객체들을 쉽게 만들수있다.<br/>
<br/>
<br/>

- 단점<br/>
Class를 활용하지 않으면 메모리 절약면에서 좋지 못하다.<br/>
<br/>
<br/>

- 예시<br/>
<br/>
<img width="200" alt="스크린샷 2023-06-27 오전 2 01 53" src="https://github.com/kong1034/Frontend-Theory/assets/19910034/18c472ce-9773-45c1-9caa-5262c765db14"><br/>
<br/>

￼

각각의 동물들의 타입별로 나이값을 리턴값으로 설정해놓은 함수가 있다.<br/>
￼<img width="342" alt="스크린샷 2023-06-27 오전 2 05 03" src="https://github.com/kong1034/Frontend-Theory/assets/19910034/aea68c9c-ccac-4568-9df9-a97159071f52"><br/>
<br/>


동물을 타입별로 객체생성 할수있게끔 객체 생성 공장같은 느낌의 함수를 하나 만들어둔다.<br/>
<img width="317" alt="스크린샷 2023-06-27 오전 2 05 29" src="https://github.com/kong1034/Frontend-Theory/assets/19910034/01b8b07e-acac-4898-b773-54d43f68549a"><br/>
<br/>

￼
객체 생성 공장에서 정의 해놓은 createAnimal(animalType)을 통해 객체 생성을 받는다.<br/>
그리고 처음에 지정해둔 age를 불러온다.<br/>
