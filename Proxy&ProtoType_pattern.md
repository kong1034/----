## 프록시 패턴<br/>
프록시 패턴은 원래 객체를 대신하여 로직을 처리하여 흐름을 제어하는 기법이다.<br/>
<br/>
![43-1 PNG](https://github.com/kong1034/Frontend-Theory/assets/19910034/c7ffdf66-946b-4b6a-961a-970d51e17b12)<br/>
<br/>
<br/>

- 장점<br/>
1. 보안적으로 좋다.<br/>
2. 캐싱데이터를 사용할수있어서 서버에 부담이 적다.<br/>
3. 데이터 유효성 검사가 가능하다.<br/>
<br/>
<br/>

- 딘점<br/>
1. 객체 생성이 많아지면 성능 저하가 일어난다.<br/>
2. 프록시 내부에서 할 일이 많아지면서 성능저하가 일어난다.<br/>
<br/>
<br/>

- 코드<br/>
<br/>
<img width="517" alt="스크린샷 2023-06-28 오후 11 14 58" src="https://github.com/kong1034/Frontend-Theory/assets/19910034/84b4c148-d13d-4f79-955a-5d415c38c56a"><br/>
<br/>
Person 객체를 생성해서 바로 수정하는게 아닌 Proxy 객체의 get, set을 이용하여 대신 수정 및 가져오기를 실행한다.<br/>
<br/>
<br/>
<br/>
<br/>

## 프로토타입 패턴<br/>
다양한 객체들이 같은 프로퍼티를 가져야할때 사용하면 좋다.<br/>
다양한 객체들에게 프로퍼티를 줘야할때 하나씩 개별로 주는게 아닌 인스턴스의 프로토타입을 새로 추가해주면 모든 객체들이 가질수있게 된다.<br/>
<br/>
<img width="234" alt="스크린샷 2023-06-29 오전 1 18 53" src="https://github.com/kong1034/Frontend-Theory/assets/19910034/aebdc0c1-d932-4208-a752-3ff59a1d7469"><br/>
<br/>
dog1,2,3 모두 bark라는 함수를 갖고있다.<br/>
여기서 만약 다른 함수를 추가하고싶을때 prototype을 사용할수있다.<br/>
<br/>
<img width="348" alt="스크린샷 2023-06-29 오전 1 22 21" src="https://github.com/kong1034/Frontend-Theory/assets/19910034/99b833e9-3356-4f2d-b2d2-3564bee69b3c"><br/>
<br/>
지금의 방법을 부모 클래스와 자식 클래스 사이의 상속을 해가며 사용하면 프로토타입 체인이다.
