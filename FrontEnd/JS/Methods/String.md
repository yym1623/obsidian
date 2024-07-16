
> [!info]  문자열 메소드를 작성한다


###### length
---
```js
// length - 문자열 내의 문자 갯수를 반환한다
str.legnth()
```


###### toString
---
```js
toString - 문자열로 반환함
str.toString()
```


###### indexOf, lastIndexOf
---
```js
// indexOf - 특정 문자나 문자열이 처음으로 등장하는 위치의 인덱스를 반환한다
str.indexOf('찾을 문자')
```

```js
// lastIndexOf - 특정 문자나 문자열이 마지막으로 등장하는 위치의 인덱스를 반환한다
str.lastIndexOf('찾을 문자')
```


###### match
---
```js
// match - 인수로 전달받은 정규 표현식에 맞는 문자열을 찾아서 하나의 배열로 반환한다
const str = 정규표현식
str.match()
```


###### includes
---
```js
// includes - 인수로 전달받은 문자열이 포함되어 있는지를 검사한 후 그 결과를 불리언 값으로 반환한다
str.includes()
```


###### charAt
---
```js
// charAt - 문자열에서 인자로 넘긴 index에 해당하는 문자형 데이터를 반환한다
str.charAt(index)
```


###### replace
---
```js
// replace - 최초의 일치하는 찾을문자를 두 번째 인자로 넘긴 치환할 문자로 대체한다
str.replace("찾을문자", "치환할 문자")
```


###### substring, substr
---
```js
// substring - 첫 번째 index부터 두 번째 index 앞까지 문자열을 반환한다
str.substring(0, 5) // 0부터 5까지의 문자 반환
```

```js
// substr - 첫 번째 Index부터 두 번째 문자개수만큼 문자열을 잘라 반환한다
str.substr(6, 5) // 6번째부터 5개 문자 반환
```


###### split
---
```js
split - 첫 번째 문자를 기준으로 하여 문자열을 잘라 각 배열 요소에 담은 뒤에 해당 배열 객체를 반환한다
str.split("/")

console.log(result) // [ 'Hello', 'World' ]
console.log(result[0]) // Hello
console.log(result[1]) // World
```


###### toLowerCase, toUpperCase
---
```js
toLowerCase - 문자열 안에 대문자를 모두 소문자로 변환한다
str.toLowerCase()
```

```js
toUpperCase - 문자열 안에 소문자를 모두 대문자로 변환한다
str.toLowerCase()
```


###### concat
---
```js
concat - 넘어온 문자열을 기존 문자열 뒤에 합친다
str.concat(str2)
```


###### trim
---
```js
trim - 문자열 양쪽 끝에 공백을 제거한다
str.trim()
```



#length #toString #indexOf #lastIndexOf #match #includes #charAt #replace #substring #substr #split #toLowerCase #toUpperCase #concat #trim
