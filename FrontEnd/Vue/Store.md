
>[!info] 공문의 composition api 방식으로 작성합니다


###### Pinia 개념
---
1. ref() - state 
2. computed() - getters
3. function() - actions


###### Pinia 규칙
---
1. 함수를 생성할때는 이름에 use를 암묵적으로 붙인


###### 선언하기
---
1. `main.js`에서 pinia의 `createDefine`로 생성 후 `defineStore`에 등록하여 전역으로 사용 가능

```js
import { defineStore } from 'pinia'

export const useCounterStore = defineStore('counter', () => {
  const count = ref(0)

  const doubleCount = computed(() : number => count.value * 2)

  function increment() {
    count.value++
  }
  
  return { count, doubleCount, increment }
})
```


###### 사용하기
---

```js
import { useCounterStore } from '@/stores/counter'

const store = useCounterStore()


store.data // 반응형으로 가져온다 (컴포넌트에서도 수정도 가능하다)

const { data } = store // 반응형이 깨진
const { data } = storeToRefs(store) // 반응형이 유지되며 .value로 접근해야 한다


store.data = 2 // 각각 변경
store.$patch({ // 한꺼번에 변
	data = 2
})
```


>[!important] 컴포넌트로 데이터를 넘길 수 있다면 사용하지말고 전역으로 사용할 데이터만 사용하자



#pinia 