
>[!info] Vue3 기준으로 작성합니다


###### watch
---
1. 감시된 소스가 변경되었을때 데이터의 변경을 감지한다(현재값, 이전값 둘 다 감지 가능)
2. watch(checkdata, callback, options) - 순서대로 감시대상, 실행함수, 옵션값이다
3. obj가 아닌 이상 바로 첫번째 인자로 접근가능, obj일 경우에는 두번째 콜백으로 접근 가능
4. 두번째 콜백으로는 `getter`를 감시하는거며, `getter`를 감시할때는 `getter`의 반환 값이 변경된 경우에만 실행됩니다
5. watch로 감시하는 데이터는 ref 즉 반응형이야지 감시가 된다

```js
import { watch } from 'vue' 
// default
watch(checkList, (afetr, before) => {
	
}, options)

// obj
watch(() => obj.value.data, () => {
	// 두번째 인자로 -> getters 감시는 obj.value.data 데이터가 변경된 경우에만 반응한다
}, options)
```

4. options
	1. flush - vuc업데이트 종료 후 접근 (ex 천개 데이터 변경된다고 천번 실행 방지)
		1. post - 동일한 상태가 여러번 발생해도 마지막 한번만 실행한다
		2. sync - 여러번 발생하는게에 대해 동기적으로 한번씩 다 실행(이런경우는 거의없다)
	2. once - 한번만실행
	3. immediate - 최초 렌터링 후 강제 실행
	4. deep - true를 주게되면 해당 감시자는 깊은 감시를 하게 된다 
		1. 반응형 객체를 직접 감시할 때는 감시자는 자동으로 deep 모드가 된다
5. 조건이 있다면 기다렸다가 해당 조건이 충족될때 실행된다


###### watchEffect
---
1. watch처럼 첫번째 감지할 대상을 입력하지 않고 바로 콜백으로 들어간다(현재값만 감지 가능)
2. 명시하지 않고 바로참조 -> 콜백 내부에 있는 변경된 데이터에 대해서 감지
3. 감시자를 비동기식으로 생성해야 하는 경우는 거의 없으며, 가능하면 동기식 생성을 해야한다. 일부 비동기 데이터를 기다려야 하는 경우, 감시자 로직을 조건부로 만들 수 있다
4. options이 따로 `import`쪽에 해당 옵션으로 만들어져있는게 있어서 바로 사용할 수 있다

```js
import { watchSyncEffect, watchEffect } from 'vue'

watchSyncEffect(() => {
	// 반응형 데이터 변경 시 동기적으로 실행됨
})

// dom을 감지해 해당 dom이 최초에 렌더링될때의 조건 감지
watchEffect(() => {
	if (data.value) {
		// 데이터가 로드될 때 실행될 로직
		data.value.focus()
	} else {
		// 아직 마운트 되지 않았거나, 마운트 해제된 경우
	}
}
```

5. watchEffect는 여러가지 option이 존재하며, 해당 option용 컴포넌트도 존재한다 (공문참고)


>[!warning] 
>1. 얕은 데이터 구조는 컴포넌트에서 루트 수준 상태로만 사용해야 합니다
>2. 내부 깊숙이까지 반응형으로 동작하는 객체 내부에 중첩하는 경우, 반응형 동작에 일관성이 없는 트리가 생성되어 이해와 디버그가 어려울 수 있으니, 중첩하여 사용하면 안된다






#watch #watchEffect