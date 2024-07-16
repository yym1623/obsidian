
> [!info]  blob 메소드를 작성한다


###### blob
---
1. 원랜 data가 많이 나오는데 그걸 url로 변환하는 방식으로 바꾼다
2. 너무 값이 커서 느리기 때문에 blob으로 나온걸 url로 변환해서 나온 주소가 해당 주소다 -> src에 적재

```js
const avatarUrl = document.getElementById("avatarUrl");
const data = new Blob([imageData], {type: "image/png"});
avatarUrl.value = URL.createObjectURL(data);
```


#blob
