
>[!info] Vue3 기준으로 작성합니다


###### slot
---
1. slot - 부모가 제공한 슬롯 컨텐츠가 렌더링되어야 하는 위치를 나타낸다
2. 텍스트뿐 말고도 컴포넌트나 여러 데이터도 넣을 수 있다
3. `slot`사이에 제공되는 값이 없을경우 기본값도 지정할 수 있다 (단일은 기본값 default로 연결)
4. v-slot 단축 -> #, 동적 -> `v-slot:[name]`

```js
// slot 단일
// 부모
<Chile>데이터</Chile>

// 자식
<template>
	<div><slot></slot></div>
</template>

// slot 다중 - name으로 연결한다
// 부모
<Chile v-slot:header v-slot:footer>데이터</Chile>

// 자식
<template>
	<div><slot name="header"></slot></div>
	<div><slot name="footer"></slot></div>
</template>
```

4. slot components props (slot이 부모에게 데이터 전달 가능)

```js
// 부모
<Chile v-slot="slotPlus" />

// 자식
<div><slot :text="text" :count="1"></slot></div>
```

5. slot의 name은 예약되어 있기 떄문에 props에 포함되지 않는다

>[!note]
>slot 을 최대한 활용해야 컴포넌트 `props` `driring`을 막을 수 있다
>slot은 시각적 표현을 사용할때 유용하다




#slot