
>[!info] Vue3 기준으로 작성합니다


###### v-bind
---
1. 하나 이상의 속성 또는 컴포넌트 prop을 표현식에 동적으로 바인딩
2. 단축문법으로 `:`를 사용한다
3. `class`, `style` 및 `element`에 해당하는 옵션들로도 사용할 수 있다

```js
// v-bind
<div :style="{ style : data }"></div> // 조건이 true일 경우 렌더링
<div :class="{ class : data }"></div> // 조건이 true일 경우 렌더링
<input :value=""></div> // 데이터 바인딩

// 동적 v-bind
<button :[key]="value"></button> 

// v-bind 수식어
.camel // kebab-case 속성 이름을 camelCase로 변환.
.prop // 바인딩을 [DOM 속성(property: 이하 프로퍼티)]로 강제 설정
.attr // 바인딩을 [DOM 속성(attribute)]으로 강제 설정
```


#v-bind