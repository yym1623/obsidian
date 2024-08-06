
>[!info] Vue3 기준으로 작성합니다


###### ref & reactive (반응형)
---
1. ref - 반응형으로 연결할때 사용한다 (`.value`로 접근해서 사용한다, 모든 형식에 사용가능)
2. reactive - 반응형으로 연결할때 사용한다 (`.value`없이 바로 접근한다, obj, arr만 가능)
3. `element`부분의 `dom`연결할때도 ref를 사용한다 (선언한 변수명과 일치하면 연결된다)
4. 즉 `ref`는 `data - ref`, `dom - ref` 두 가지로 사용이 가능하다

```js
import { ref, reactive } from 'vue'

// data ref
const data = ref(''); // all
const datas = reactive({}) // {} or []

// dom ref
const dom = ref(null);
```


###### shallowRef
---
1. 동적으로 컴포넌트를 변경해야 할 경우 사용(`ref`보다 가볍다)

```js
import { shallowRef } from 'vue'

const data = shallowRef('')
```


>[!warning]  
> 1. ref에 let 객체가 들어가있어서 ref로 생성한 객체는 수정이 가능하다
> 2. const로 만든건 상수라 변경이 불가능하지만 const안에 ref로 만든건 변경이 가능하다
> 3. 수정하는건 const안에 ref 즉 그 안 .value로 변경하는 let객체를 변경하는거기 떄문이다




#ref #reactive #shallowRef #dom