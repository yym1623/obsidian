
> [!info]  blob 메소드를 작성한다


###### Object.keys, Object.values, Object.entries
---
```js
// Object.keys - 객체가 가지고 있는 키들의 목록을 배열로 리턴한다
Object.keys(obj) // ['key1', 'key2']
```

```js
// Object.values - 객체가 가지고 있는 밸류들의 목록을 배열로 리턴한다
Object.values(obj) // ['value1', 'value2']
```

```js
// Object.entries - 객체의 키와 값의 쌍으로 이루어진 길이 2짜리 배열로 이루어진 배열을 리턴한다
Object.entries(obj) // [['key1', 'value1'], ['key2', 'value2']]
Object.entries(obj[0]) // ['key1', 'key2']
Object.entries(obj[1]) // ['value1', 'value2']
```


>[!note] 객체 안에서의 함수 생성시 this -> 해당 객체다 


#this #ObjectKeys #ObjectValues #ObjectEntries 