## 코딩 표준

- 표현식이나 문장의 끝에는 세미콜론(;)을 넣는다.

- 선언은 const로 하는것을 기본으로하되 필요에 따라 let을 사용한다. var 를 사용하거나 선언하지 않은 변수를 사용하는 것은 지양한다.
```
예)
// O
const nums = [1, 2, 3, 4];
const oddNums = nums.filter(v => v % 2);
// 세모
let nums = [1, 2, 3, 4];
nums = nums.filter(v => v % 2);
// X
var nums = [1, 2, 3, 4];
// X
nums = [1, 2, 3, 4];
```

- 문자열 리터럴 작성 시 단일인용부호(')를 우선 사용하고 필요에 따라 템플릿 리터럴(`)을 사용하며 이중인용부호(") 사용은 지양한다.
```
( 소스의 일관성을 유지하기 위함인데 단일인용부호가 이중인용부호보다 타이핑하기 쉬우므로 단일인용부호를 사용하기로 함 )
예)
const hello = 'world'     // O
const hi = "hello"        // X
const foo = `${hi} world` // O
```

- 비동기(Promise) 로직은 async await 구문을 사용하며 then 메서드 사용은 지양한다.
```
( 가급적 들여쓰기를 줄이고 순차적으로 코드를 작성하여 가독성을 높이기 위함 )
예)
// O
async getList() {
	const resp = await axios.get('/list');
	this.list = resp.data;
	...
}
// X
getList() {
	axios.get('/list').then(resp => {
		const data = resp;
		this.list = resp.data;
		...
	})
}
```

- 컴포넌트 명명은 PascalCase로 통일한다.
```
(소스 검색 및 수정 편의를 위함)
예)
[컴포넌트 선언부]
name: 'SomeComponent'
[컴포넌트 사용]
<SomeComponent />
[컴포넌트 파일명]
SomeComponent.vue
```

- prop 명명은 CamelCase로 통일한다.
```
(소스 검색 및 수정 편의를 위함)
예)
[컴포넌트 선언부]
props: {
  helloWorld: String
}
[컴포넌트 사용]
<SomeComponent helloWorld="hi" />
```