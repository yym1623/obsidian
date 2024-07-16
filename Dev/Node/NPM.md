
>[!info] 유용한 패키지를 기록합니다


###### sentry
---
1. 클라이언트 에러를 트래킹하여  연동해서 알림을 주는 서비스 (에러 로그 모니터링)


###### eslint
---
1. 에러 표출 관련


###### vuex-persistedstate
---
1. vuex사용 시 새로고침해도 삭제 안되고 로컬스토리지처럼 캐시 삭제안하면 남아있는 패키지


###### babel
---
1. 최신 ES6, ES7 버전의 javascript코드를, ES5버전의 코드로 바꾸어주는 Node.js 패키지
2. javascript 최신 코드를 이해하지 못하는 웹 브라우저에서도 페이지에 접속할 수 있도록 해줍니다!
3. 즉 최선버전의 자바스크립트 문법으로 개발하며 빌드할때 바벨을 이용하면 브라우저가 이해할 수 있게 된다

```
// .babelrc
// 실행할때도 babel로 실행시켜야 변환된다
{
	"presets" : ["@babel/preset-env"]
}
```


###### Environment
---
1. 환경별 탭을 두어, 개발 환경에서 오류가 났는지, 배포 환경에서 오류가 났는지 알 수 있게 해준다.

```
// bundler config.js

Sentry.init({
  environment: process.env.NODE_ENV,
});
```


###### dotenv
---
1. 환경변수 설정
2. 개발환경 & 빌드환경을 각각 만들어 적용되게 만들 수 있다
3. 기본적으로 `npm run dev` -> `.env.development`, `npm run build` -> `.env.procution`로 정의됨
4. `custom env`를 만들려면 실행할때 `custom env`를 적용해서 사용할 수 있다
5. 접두사 없이 바로 사용할 수 있다
6. `dotenv config()`를 설정해야 생성한 `env`를 사용할 수 있다
7. `dotenv`는 `js -> commons`이다

```js
// 선언
APP_IP = 127.0.0.1

// 사용
process.env.APP_IP // 127.0.0.1
// custom 사용 -> package.json
dev:custom: "dotenv -e .env.custom vite"
```

>[!warning] 주의사항
>1. 기본적으로 `dev`, `prod` 에는 `NODE_ENV`가 정의되어 있다 
>2. 즉 `custom`으로 만들때도 `NODE_ENV`를 정의하지 않으면 `title`같은건 적용되지만 다른 옵션들은 정의되지 않는다 -> 파일명과 같게 `NODE_ENV를` 정의해야 `custom env`가 적용된다
>3. `js`가 `commons` & `esm`인지로 `dotenv -> process.env`, `import.meta -> vite` 나뉘어진다
>4. `process.env -> node` & `vite -> brower` 환경만 가능하다

#npm패키지 