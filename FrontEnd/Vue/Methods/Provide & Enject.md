
>[!info] Vue3 기준으로 작성합니다


###### provide, inject
---
1. provide(키, 값) - 객체의 키 값은 심볼을 추천한다(의존성)
2. inject(키, 기본값) - 기본값은 provide 키 값을 제공 안 할 경우

```js
import { myKey } from '../../key.js'

// provide
const injectData = ref(13) // 반응성
provide(myKey, injectData)

// inject
const message = inject(myKey, '기본값테스트')
```

3. `provide`에 객체에 함수를 보내서 해당 함수를 이용하면 `inject`부분에서 변경가능하다
4. `provide` 데이터를 바꾸지 못하게 하기위해 보내는 데이터를 `readonly`로 감싸서 보내면 `inject`에선 변경못하고 감지밖에못한다
5. 키가 제공되지 않은 경우 런타임 경고 - 기본값 설정가능


>[!note] Symbol 활용
>1. 잠재적 충돌을 피하기 위해 obj key는 symbol로 생성하자 -> 파일로 관리하는게 유용
>2. provide에서 사용한 심볼과 inject에서 사용한 심볼은 같은 심볼 객체를 참조한다
>3. 이들은 서로다른 심볼 값이며 독립적으로 생성된다. 하지만 Vue.js의 내부 로직에 따라 이들은 연결되어 데이터 전달이 이루어진다


#provide #inject