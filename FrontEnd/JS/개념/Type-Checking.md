
>[!info] typechecking의 필요성을 서술한다


###### 개념
---
1. `연산자`에 제공되는 `피연산자`들이 호환되는 `type`인지를 판단한다
2. 기본적으로는 `number`는 `number`끼리, `string`은 `string`끼리 연산을 한다
	1. 다른 `type`끼리 연산을 해도 `컴파일러`가 경고는 하지만 자동으로 타입변환을 시킨다

```js
const test1 = 1 + 1 // true
const test2 = 1 + '1' // false
```




#type-checking 