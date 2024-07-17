
>[!note] tsconfig.json에 대한 옵션을 명시한다


```ts
{
  "compilerOptions": {
    "strict": true,
    "target": "ES6",
    "lib": ["ES2015", "DOM"],
    "module": "CommonJS",
    
    "baseUrl": ".", 
    // alias 설정 ( 번들러 설정파일이랑 맞춰야 인식한다 )
    "paths": {
      "@/*": ["src/*"]
    },
  },
  // 컴파일에 포함할 경로
  "include": [
    "src/**/*.ts"
  ],
  // 컴파일에 제외할 경로
  "exclude": [
    "node_modules"
  ]
}
```

1. vite-tsconfig-paths - plugins에 등록하면 