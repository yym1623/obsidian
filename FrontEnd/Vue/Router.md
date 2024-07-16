
>[!info] 공문의 composition api 방식으로 작성합니다


###### 생성
---
1. `main.js`에서 생성한 라우터의 경로를 등록함으로써 전역으로 사용이 가능하다
2. `history`모드를 선택한 후 해당하는 컴포넌트를 라우터에 등록함으로 사용이 가능하

```js
import { createWebHistory, createRouter } from 'vue-router'
// components
import HomeView from '@/components/HomeView.vue'
import AboutView from '@/components/AboutView.vue'

const router = createRouter({
  history: createWebHistory(),
  
  routes: [
    { path: '/', component: HomeView },
    // /:id -> 동적 라우팅 (여러개 설정 가능)
    { path: '/about/:id', component: AboutView },
  ],

  // 라우팅 후 스크롤 이벤트
  scrollBehavior(to, from, savedPosition) {
    return { top : 0, behavior: 'smooth' }
  },
})

export default router
```


###### 접근 - 컴포넌트 방식
---
1. 컴포넌트에서는 `$route` 옵션으로 접근할 수 있다

```js
// RouterView - view 컴포넌트가 설정한 컴포넌트들의 집합체다
<RouterView></RouterView>

// RouterLink - to옵션을 통해 이동할 컴포넌트를 선택할 수 있다
<RouterLink :to="url"></RouterLink>
```


###### 접근 - 컴포저블 방식
---
1. 라우터 인스턴스를 router라고 한다 -> createRouter()에 의해 반환된 객체
2. `router`로 데이터를 넘길 때 인코딩을 직접해야하는 문자열로 넘기는거랑 path로 넘길때는 url 인코딩을 자동으로 해주는 차이가 있다

```js
import { useRoute, useRouter } from 'vue-router'

// 각각 라우터 인스턴스와 현재 라우트에 접근하는 데 사용된다
const router = useRouter()
const route = useRoute()

// 인코딩 문제로 추천되는 방식 - params는 name으로 보내야 인코딩이 된다
router.push({ name: 'user', params: { username } })
```


###### 옵션
---
1. 같은 컴포넌트에서 파라미터만을 변경을 위해 라우팅이 일어날 경우 감지하는 방법

```js
// 네비게이션 가드
onBeforeRouteUpdate(async (to, from) => {
  // 라우트 변경에 반응합니다...
  userData.value = await fetchUser(to.params.id)
})

// watch
watch(router, () => {

})
```

2. 이동

```js
router.go(1)
```



>[!note] `router-view` name 설정 및 `chiled`옵션 등등 추가적인 옵션들이 있다 -> 공문 참고



#router
