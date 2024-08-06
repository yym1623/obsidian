
>[!info] Vue3 기준으로 작성합니다


###### v-html
---
1. v-html -html렌더링(웹에서 임의의 html을 동적으로 렌더링하면 `XSS` 취약점이 발생할 수 있다)

>[!warning] 
>scoped를 지정한 style은 v-html 내부 컨텐츠에 적용되지 않는다
>왜냐하면 해당 HTML은 Vue의 템플릿 컴파일러에서 처리되지 않기 때문이다
>즉 범위를 지정한 css로 v-html에 지정하려는 경우 전역 `<style>` element로 적용할 수 있다


###### v-text
---
1.  엘리먼트의 텍스트 컨텐츠를 업데이트합니다

```js
<span v-text="msg"></span>
```


###### v-show
---
1. 인라인 스타일을 통해 `display` CSS 속성을 설정하여 요소에 트리거한다

```js
<span v-show="data"></span>
```


###### v-if
---
1. 표현식의 `truthy` 값을 기반으로 `엘리먼트` 또는 `템플릿` 일부를 조건부로 렌더링
2. 즉 `v-if`가 토글되면 렌더링되고, 토글이 안되면 내부 컨첸츠가 전혀 렌더링되지 않는다

```js
<span v-if="data"></span>
<span v-else-if="data2"></span>
<span v-else></span>
```


###### v-for
---
1. 소스 데이터를 기반으로 엘리먼트 또는 템플릿 블록을 여러 번 렌더링한다
2. 강제로 엘리먼트를 재정렬하려면, 특수 속성 `key`를 사용하여 순서 지정을 위한 힌트를 제공
3. vue3부터는 `template`에도 사용이 가능하며 `template`마다 `key`값이 주어진다

```js
<div v-for="item in items" :key="item.id"> {{ item.text }} </div>
```


###### v-model
---
1. 사용자 입력을 받는 폼(form) 엘리먼트 또는 컴포넌트에 양방향 바인딩을 만듭니다.
2. 사용가능 항목 (input, select, textarea, component)

```js
// v-model
// script
const data = ref('')

// template
<input v-model="data"></input>

// v-model 수식어
.lazy // input 대신 change 이벤트를 수신함.
.number. // 유효한 입력 문자열을 숫자로 변환하여 전달.
.trim // 사용자 입력의 공백을 트리밍.
```


###### v-slot
---
1. 이름이 있는 슬롯 또는 props를 받을 것으로 예상되는 범위형 (Scoped) 슬롯을 나타냅니다

```js
// default - 단일
<component v-slot:default />

// name - 다중
<component v-slot:header />
```


###### v-cloak
---
1. 준비될 때까지 컴파일되지 않은 템플릿을 숨기는 데 사용됩니다
2. 렌더링 되기 전에 스타일 적용으로 안 보이게 할 수 있다

```js
// [v-cloak] { display: none }
// <div>는 컴파일이 완료될 때까지 표시되지 않습니다.
<div v-cloak>
  {{ message }}
</div>
```


>[!note] 그 외 빌트인 
>1. v-once - 엘리먼트와 컴포넌트를 한 번만 렌더링하고, 향후 업데이트를 생략합니다
>2. v-memo - 템플릿의 하위 트리를 메모합니다


###### readonly
---
1. 읽기모드로 변해서 재할당할때 못바꾸게 경고가 나온다

```js
import { readonly } from 'vue'

const original = reactive({ count: 0 })

const copy = readonly(original) // warning
```


###### nextTick
---
1. 다음 `DOM` 업데이트 주기가 끝난 후 실행할 지연된 콜백
2. 데이터를 수정한 직후에 이 방법을 사용하여 업데이트된 `DOM`을 가져온다

```js
function nextTest() {
	console.log('test')
	nextTick((e) => {
		// 업데이트 된 dom에 접근 가능
	})
}
```




#v-html #attres  #nextTick #readonly #빌트인옵션