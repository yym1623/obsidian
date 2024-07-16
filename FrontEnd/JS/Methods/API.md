
> [!info] 클라이언트와 서버 간 데이터를 주고 받기 위해 HTTP 통신을 작성한다


######  fetch
---
1. fetch API는 Promise기반으로 동작한다
2. 기본 응답 결과는 Response 객체이다 -> json으로 바꾸거나 text로 바꾸는 처리 과정이 필요
3. Promise의 강력한 기능 및 async, await 사용으로 생산성 향상이 된다
   
```js
fetch(url, {
	methods: "",
	headers: { "Content-Type": "application/json", },
	body: JSON.stringify({
	    key : value
    })
}).then((response) => response.json())
  .then((data) => console.log(data));
  .catch()
  .finally()
```


###### axios
---
1. Axios는 브라우저, Node.js를 위한 Promise API를 활용하는 HTTP 비동기 통신 라이브러리이다
2. axios는 Promise기반으로 동작한다
3. 자동으로 JSON데이터 형식으로 변환된다
4. GET으로 요청시 뒤에 백틱으로 쿼리스트링으로 넘기거나, 객체로 전체를 날리거나 -> 둘 다 쿼리스트링

```js
// 1. 변수에 담아서 활용
const res = axios.methods(url, data)

// 2. then, catch 활용
axios.methods(url, data)
	.then()
	.catch()
	.finally()
```



#RESTFullAPI #API #fetch #axios