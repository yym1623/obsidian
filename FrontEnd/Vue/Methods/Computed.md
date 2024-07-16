
>[!info] Vue3 기준으로 작성합니다


###### Computed (계산된 데이터)
---
1. 계산된 문법은 `getter`전용 -> 바로 적으면 `getters`로 변하는 거에 대한 값을 가져온다
2. 만약 할당을 위한 `set`을 사용할 경우 할당된 값은 `set`의 첫번째 인자로 들어온다
3. 할당된 값으로 `set`이 끝나면 해당 값이 `get`쪽으로 넘어와 이어서 계산하면 된다

```js
import { computed } from 'vue'
// get - default
const calculate = computed({
	return
})

// get, set
const calculate = computed({
	get() {
	
	},
	// 첫번째 인자 - 할당된 값
	set(newValue) {
	
	}
})
```

>[!warning] computed & watch 차이점
>1. dom만 업데이트하는거면 `computed`를 사용하는게 좋다
>2. `data`를 조작하는 거면 `watch`를 사용하는게 좋다
>3. 하지만 `watch`를 사용할 일이 없는게 좋다 -> `script`단에서 데이터 변경을 알아차릴려면 `watch`를 써야하지만 그런 구조를 안 만드는게 가장 좋다
>4. 부모에서 내려온 props를 자식 컴포넌트에서 script로 알아야할 일은 없으니까 말이다


#computed