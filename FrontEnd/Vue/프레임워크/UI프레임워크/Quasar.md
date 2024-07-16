
>[!info] 공식문서 기준으로 작성합니다


>[!note] 프레임워크에서 만든 옵션 및 클래스 사용시 주의사항
>컴포넌트 사용시 해당 프레임워크에서 만든  옵션을 사용할 수 있고(컴포넌트마다 다르다)
>
>클래스는 모든 요소가 사용할 수 있다 


###### Layout - grid
---
```
// grid - 한 줄당 12 col 기준
<div class="col"></div> // col - 필요한 경우 축소나 늘리면서 모든 공간을 차지
<div class="col-1~12"></div> // auto - 셀이 렌더링 해야 하는 공간만 차지
<div class="col-auto"></div>

// grid - 반응형
<div class="col-sm-1~12"></div> // sm - mobile
<div class="col-md-1~12"></div> // md - tablet
<div class="col-lg-1~12"></div> // lg - pc
```

> [!note] 플랫폼 감지 헬퍼
> 플랫폼 감지 헬퍼를 사용하여 플랫폼마다의 조건을 걸어 실행 가능


###### Layout - flex
---
```
// flex
<div class="row & columns"></div>
<div class="row nowrap grow shrink"></div>
<div class="row justify-start ~ end items-start ~ end content-start ~ end"></div>
<div class="row">
	<div class="self-start ~ end"></div>
</div>

```

>[!note] grow & shrink 차이점
> grow - 셀이 렌더링에 필요한 최소 공간만 차지
> shrink - 셀이 렌더링에 필요한 최대 공간만 차지(사용 공간이 충분하지 않으면 축소한다


###### Layout - gutter
---
```
// gutter - 단순 마진 및 패딩 지정?
q-gutter-{size} // 부모 상단과 좌측에 - 마진, 자식 상단과 좌측에 + 마진
q-col-gutter-{size} // 부모 상단과 좌측에 - 마진, 자식 상단과 좌측에 + 패딩
```

> [!note] gutter - 주의사항
> 1. size - none,-xs,-sm,-md,-lg,-xl는 디바이스 화면 너비가 아닌 요소 사이의 간격 너비다
> 2. size부분에는 단순 사이즈나, x, y에 대한 사이즈도 정할 수 있다
> 3. 부모 요소의 좌상단에 마진을 적용하고 자식 요소의 좌상단에는 +마진을 적용함
> 4. gutter의 css가 깨지지 않도록 다른 간격 클래스와 함께 사용할 때 이점에 유의하자
> 5. q-gutter-{size}는 서로 간격 두려는 요소가 너비를 지정하는 col, offset이 없을 때
> 6. q-col-gutter-{size}는 서로 간격 두려는 요소가 너비를 지정하는 col, offset이 있을 때


###### Layout - padding & margin
---
```
// padding & margin
<div class="q-ma-sm q-pa-md"></div>
```

> [!note] 간격 옵션
> 1. padding - q-p[$]-[size]
> 2. margin - q-m[$]-[size]
> 3. $ -> a - all, t - top, l - left, r - right, b - bottom, x - (left + right)
> 4. size -> xs, sm, md, lg, xl
> 


###### Options - table
---
```
// template
<q-input class="ellipsis" dense outlined :rules="[data]" lazy-rules />
<q-select class="ellipsis" dense outlined v-model :options />
<q-btn class="ellipsis" color flat />

<q-table row-key :columns="columns" :data="data">
 <template v-slot:[header ~ body]="props">
  <q-tr :props="props">
   <q-td key="" :props="props"></q-td>
  </q-tr>
 </template>
</q-table>

// script
columns: [ // name 개수만큼 데이터가 들어감
 name : '',
 label: '',
 align: '',
 sortable: true, // 정렬 ON
 format: val => `${val}`,
 field: row => row.name, // row랑 맞춰줄 키 -> 정렬에 필요(맞출 기준)
]
data : [] // columns -> name(key)랑 연결 -> 연결은 정렬에 필요(안 할거면 상관없음)
```
 
> [!note] options input 관련 주의사항
> 1. mask 설정에 따라 input활용도를 바꿀 수 있다 ex) mask="date"
> 2. input & select & btn에 적용될 옵션들이 있다
> 	1. dense - 가늘게 만들어준다
> 	2. outlined - 
> 	3. flat - 버튼 백그라운드 제거
> 	4. rules - 유효성 검사 -> q-form을 사용한다면 submit evnet로 rules -> true면 넘긴다
> 3. q-select는 option넣는 부분에 한 객체당 label, value로 설정하면 매칭된다
> 4. q-select -> value부분은 문자열로 key랑 맞아야 매칭된다
> 5. q-dete는 포맷값이 YYYY/MM/DD 이다 -> 불러오는 데이터 형식이 / / 여도 맞춰진다

> [!note] options table 관련 주의사항
> 1. 옵션 중 columns 및 data를 지정 후 props로 불러오는 형태
> 2. table뿐 아니라 다른 옵션 값 중 상세하게 자식태그에 접근하기 위해 v-slot을 설정한다
> 	1. ex) v-slot:header="props" & v-slot:body="props"
> 	2. 

> [!note] 주의사항
> columns key값을 v-if로 따로따로 지정해도 key값이 같으면 중복현상이 일어난다
> 
> ex) 클릭이벤트가 다른 v-if에서도 먹음
> 
  해당 키값의 클릭 이벤트에 조건으로 해당 값을 기준으로만 하게 조건을 건다


###### options - rules
---
```
// rules ex
	:rules="[
		val =>
			(val && val.length > 0) ||
			'ID를 입력해주세요'
	]"
```


###### Plugin
---
> [!note] 플러그인 설정
> vue -> use -> plugin에 등록하여 사용
> 
> 등록한 플러그인은 useQuasar를 $q에 등록하여 사용

```
// notify

```

```
// dark mode

```


#quasar #quasar-layout #quasar-options #quasar-plugin