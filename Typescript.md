# 타입스크립트 왜 쓸까?  
확실한 타입을 정해줌으로써 자바스크립트보다 값의 불확실성을 줄여준다.</br>
</br>
</br>
# JS의 한계?
![스크린샷 2023-05-31 오후 9 35 16](https://github.com/kong1034/Frontend-Theory/assets/19910034/ef22bc9b-364c-43d8-ada8-21be0ee41fe0)

값에 의해 타입이 바뀌는 JS의 경우 프로젝트의 규모가 커지면 누군가 실수로 값을 바꿨을때 에러 없이 바뀌는 경우가 생길뿐 아니라 해킹의 공격에도 취약하다. 이러한 이유로 타입을 정확히 지정해주는 타입스크립트가 나온다.</br>
</br>
</br>
# 타입스크립트의 장단점

장점 - 값의 타입이 확실함. 실행속도가 JS보다 빠르다.</br>

단점 - 코드량이 증가하며 매번 타입을 지정해줘야 하고 컴파일 시간이 JS보다 오래 걸린다.</br>
</br>
</br>

# 타입스크립트 자주 쓰이는 문법

- 타입 명시
let a:string = '문자 or 문자열';
let b:number = 1;
let c:boolean = true or false;
let d:array = [];
let e:object = {};
let f:any = 모든 타입 가능</br>
</br>
</br>


- 타입 추론
let a = '문자 or 문자열'; // string
let b = 1; //number
let c = true or false; //boolean
let d = []; //array
let e = {}; //object</br>
</br>
</br>


- 함수 적용
const handle = (a:number, b:number): number => {
	return a+b;
}

파라미터와 함수의 결과값에 타입을 지정해줄수 있다.</br>
</br>
</br>


- interface

interface person {
	name: string,
	age: number
}

const profile = (param:person) => {
	console.log(param.name);
	console.log(param.age);
}
let a = { name: 'Jack', age:28 };
profile(a); // 'Jack', 28

만일 a 객체의 name 변수 값을 20으로 바꾼다면 타입에러가 발생한다.</br>
</br>
</br>

- interface extends

interface Food {
	name: string;
}

interface Price extends Food {
	price: number;
}

let order = {} as Price;
order.name = '김치찌개';
order.price = 1000;</br>
</br>
</br>


- Enum</br>


문자형 Enum - 문자로 값을 지정해준다.  </br>

enum Food {
	steak = "steak",
	pasta = "pasta",
	robster = "robster"
}  </br>
</br>
</br>

숫자형 Enum - 맨위부터 숫자로 값을 표시해줄경우 차례대로 늘어난다.</br>
만일 숫자를 표시 안할경우 0부터 자동으로 값이 지정된다.</br>

enum Sports {
	soccer,
	baseball,
	basketball
}

enum은 같은 유형의 값들을 모아놓을때 사용한다.</br>
</br>
</br>

- 유니온타입</br>

const Order = (price: string | number) {
	...
}
or 조건을 줄수있다.</br>
</br>
</br>

- intersection 타입</br>


interface Food {
	name: string;
}

interface Price {
	price: number;
}

type Order = Food & Price;

Order.name //사용가능
Order.price //사용가능</br>
</br>
</br>


- 제네릭</br>

const getUser<T>(text:T):T {
	return text;
}

getUser<string>('Hi!') // Hi!
getUser<number>(10) // 10

interface getFood<T> {
	name: string,
	price:T
}

const Order: getFood<string> = {
	name: '음식',
	price: '2000'
}

<T>는 어떤 타입이라도 지정해줄수있다는 의미이다.</br>
</br>
</br>
