
>[!info] Vue3 기준으로 작성합니다


###### v-on
---
1. inline type - 첫번째 인자로 `event` 인자가 전달된다
2. block type - `블럭함수`로 전달할 인자에 `$event`로 연결해서 전달한다
3. `element` 이벤트 리스너를 연결한다
4. 단축문법으로 `@`를 사용한다
5. 객체 문법을 사용할 경우 첫번째 인자로 `이벤트 인자`를 넘겨받는다 (`inline` 문법은 못 받음)
6. 특수 속성인 `$event`로 `v-on:click="handle('ok', $event)"`와 같이 이벤트 객체에 접근 가능
7. `v-on`은 인자 없이 `이벤트(키): 리스너(값)` 형식의 객체 바인딩도 지원합니다. 수식어는 객체 문법을 사용할 때는 지원하지 않는다

```js
// v-on 
@click
@keyup
@keydown
@mouseup
@mousedown
@dblclick

// 동적 v-on (5번항목)
@[event]="data"

// v-on 수식어 (여러개 붙여서 사용 가능)
@click.stop // event.stopPropagation() 호출 - 드릴링을 막아주는 역할도 한다
@click.prevent // event.preventDefault() 호출
@click.capture // 캡처 모드로 이벤트 등록
@click.self // 이벤트가 이 엘리먼트에서 전달된 경우에만 트리거 된다
@click.{keyAlias} // 이벤트가 특정 키에 대해서만 트리거 된다
@click.once // 이벤트가 한 번만 트리거 된다(일회용처럼)
@click.left // 마우스 왼쪽 버튼으로만 이벤트가 트리거 된다
@click.right // 마우스 오른쪽 버튼으로만 이벤트가 트리거 된다
@click.middle // 마우스 중앙(힐 클릭) 버튼으로만 이벤트가 트리거 된다
@click.passive // `{ passive: true }` 옵션으로 DOM 이벤트를 등록한다
```




#v-on