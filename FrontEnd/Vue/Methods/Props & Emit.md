
>[!info] Vue3 기준으로 작성합니다


###### props
--- 
1. 부모에서 자식에게 데이터를 내려준다

```js
// 부모
<Chile :data="data />

// 자식
const props = defineProps({ data : String }) // js

const props = defineProps<{ // ts
  data: string
}>()

<div>{{ myData }}</div>
```
 
 2. 자식에선 부모에게 받은 props를 사용하며 수정할 수 없다(읽기모드)
 3. 부모쪽 `props`이 변경될 때 계산된 속성은 자동으로 업데이트 된다(자식에서 `ref`가 아닌 `computed`로 변수에 넣어야 자동 갱신된다)


###### emit
---
1. 자식에서 부모에게 데이터(이벤트)를 올려준다

```js
// 부모
<Chile @click="myData />

function myData(emitData) {
	console.log(emitData)
}

// 자식
const emit = defineEmits(); // js

const emit = defineEmits<{ // ts
  (e: 'change', id: number): void
}>()

function myData() {
	emit('myData', 'myData')
}

// 1. defineEmits
<div @myData="myData"></div>

// 2. $emit
<div $emit="myData('myData')"></div>
```

2. 부모는 자식이 두번째 인자로 올려준 데이터를 인자로 받을 수 있다
3. defineEmits, $emit(전역) 두 가지 방법이 있다


>[!note]
>props, emit 둘 다 보통은 변수에 담아서 그 안 속성까지 접근해서 사용한다


###### defineExpore - 예외
---
1. 부모에서 자식의 특정 이벤트 실행

>[!warning] emit & defineExpore 차이점
>1. emit - 자식이 원할때 자기 부모에게 이벤트 보낸다 
>2. defineExpore - 자식이 원하던 말던 부모에서 자식의 특정 이벤트 실행
>


#props #emit #defineExpore