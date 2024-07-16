
>[!info] Symbol의 개념을 작성합니다


###### Symbol
---
1.  js의 원시타입 중 하나로 고유함을 보장하는 값을 나타낸다
2. 각각의 변수에 같은 값을 넣고 비교해도 각 symbol은 고유값을 반환하기 때문에 false가 나온다
3. 문자열이 아닌 값을 제공하면 에러가 발생합니다

```js
// Symbol module export (ts)
import type { InjectionKey } from 'vue'

const key = Symbol() as InjectionKey<string>

export default key
```


