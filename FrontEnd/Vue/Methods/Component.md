
>[!info] Vue3 기준으로 작성합니다


###### 비동기 컴포넌트 (defineAsyncComponent)
---
1. 페이지에서 실제로 렌더링될 때만 로더 함수를 호출하는 래퍼 컴포넌트입니다
2. Promise 통해서 서버에서 가져온 컴포넌트를 넣을 수 있습니다

```js
const inject = defineAsyncComponent(() => import('./components/injectTest/Inject.vue'))
```


>[!note] 비동기 사용하는 경우
>네트워크 요청, 파일 읽기/쓰기, 타이머, 이벤트 처리

>[!warning] 
>definecomponents는 동적 컴포넌트가 아닌 타입추론을 위한 컴포넌트다 (전역등록 후 사용)


###### 동적 컴포넌트
---
1. 객체로 만든 컴포넌트 리스트들을 `:is`에 넣어 탭형식으로 동적 클래스등 부여가 가능하다

```js
<component :is="..." :class="['tab-button', { active: currentTab === tab }]">
```


###### 폴스루(대체 속성)
---
1. 명시적으로 선언되지 않는속성(class, style.., v-on event)들이 해당 컴포넌트가 `루트 태그`를 생성할때 허용되는 프로퍼티로 생성하지 않으면 자동으로 추가된다(이미 있으면 병합된다)

```js
// 부모
<Chile class="test"></Chile>

// 자식 - root tag가 하나일 경우 부모의 선언되지 않는속성이 추가된다
<template>
	<div></div>
</template>
```

2. 중첩된 컴포넌트도 해당 루트 컴포넌트로 렌더링된다
3. defineOptions - `inheritAttrs`값으로 상속받지 않게 설정 가능(루트가 아닌 다른곳에 제어)
4. `$attrs` 객체에는 컴포넌트의 `props` 또는 `emits` 옵션으로 선언되지 않은 모든 속성
	1. ex) class, style, v-on 리스너 등이 포함됩니다
5. 폴스루 속성은 루트 태그에만 상속되므로 루트가 여러개일경우 상속되지 않으며 $attrs를 지정하지 않으면 오류발생한다

```js
// ex
v-bind="$attrs"
```


>[!important] v-bind="$attrs" -인자없는 v-bind는 객체의 모든 속성을 대상 엘리먼트의 속성으로 묶는다


##### 전역 컴포넌트

##### Transition
---
1. Transition - element, 요소에 대해 루트 element에 대해 transiton 적용 (중첩 - :durations 설정)
2. TransitionGroup - v-for같은 반복 items에 transition 적용

```js
// transition
<Transition>
  <p v-if="show">show_data</p>
</Transition>

// transitionGroup
<TransitionGroup name="list" tag="ui">
  <li v-for="item in items" :key="item">
    {{ item }}
  </li>
</TransitionGroup>

// transitions lifecycle
@before-enter
@before-leave
@enter
@leave
@appear
@after-enter
@after-leave
@after-appear
@enter-cancelled
@leave-cancelled (only v-show)
@appear-cancelled
```

>[!important]
>Transition & TransitionGroup 생성 시 css 라이프사이클 생성된다 -> name으로 구분 가능


###### Teleport
---
1. 컴포넌트 템플릿의 일부를 해당 컴포넌트의 DOM 계층 외부의 DOM 노드로 `이동` 할 수 있게 해주는 빌트인 컴포넌트
2. to - body element 연결 가능 (option)
3. disabled - 비활성화한다 (option)

```js
<Teleport to="body">

</Teleport>
```


###### KeepAlive
---
1. 다른 컴포넌트로 전환되면 컴포넌트가 마운트 해제된다
2. 내장된 `<KeepAlive>` 컴포넌트를 사용하여 비활성 컴포넌트를 `활성` 상태로 유지가 가능하다
3. 강제한다는 말은 캐시를 저장하여 해당 컴포넌트를 다시 열어도 해당 데이터를 유지시킨다
4. `activated` - `keep-alive` 컴포넌트가 활성화될 때 호출된다. (script hook)
5. `deactivated` : `keep-alive` 컴포넌트가 비활성화될 때 호출된다 (script hook)
6. `include` -  (options)
7. `exclude` -  (options)

```js
<KeepAlive>
	<components :is="data"></components>
</KeepAlive>
```


>[!warning] 
>keep-alive를 쓰는 컴포넌트의 경우 탭같은 기능의 이유로 초기화가 필요하다면 캐시 및 메모리를 남길려고 쓰는거니 이걸 날리는게 아닌 그 안 동적 컴포넌트의 데이터를 날려야한다


#defineAsyncComponent #dynamicComputed #폴스루속성 #KeepAlive