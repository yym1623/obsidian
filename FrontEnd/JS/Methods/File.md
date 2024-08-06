
> [!info]  blob 메소드를 작성한다


###### blob
---
1. `:data=""`값을 url로 변환하는 방식으로 바꾼다
2. 값이 커서 느리기 때문에 blob으로 나온걸 url로 변환해서 나온 주소가 해당 주소다

```js
const avatarUrl = document.getElementById("avatarUrl");
const data = new Blob([imageData], {type: "image/png"});
avatarUrl.value = URL.createObjectURL(data);
```


#blob
