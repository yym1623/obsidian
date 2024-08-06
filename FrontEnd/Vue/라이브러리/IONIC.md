
>[!info] Web, App 하이브리드 라이브러리


###### 개념
---
1. `WEB -> APP`으로 변환해주는 라이브러리 (IONIC Capacitor)
2. `React`는 `Native`가 존재하지만 `Vue`는 존재하지  않기 때문에 라이브러리를 빌려 사용한다


###### 사용법
---

```js
// 설치
npm install -g @ionic/cli@latest native-run cordova-res

// App 생성
ionic start myApp tabs --type vue --capacitor - ionic

// 실행
ionic serve

// ionic android / ios 환경 설치
ionic cap add android
ionic cap add ios

// 동기화
ionic cap sync
```
  




#IONIC