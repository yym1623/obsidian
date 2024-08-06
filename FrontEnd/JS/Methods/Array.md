
> [!info]  array 메소드를 작성한다


###### pop, push
---
```js
// pop() - 배열 뒷부분 삭제
arr.pop();
```

```js
// push() - 배열 앞부분 삽입
arr.push(5)
```

###### shift, unshift
---
```js
// shift() - 배열 앞부분 삭제
arr.shift(5)
```

```js
// unshift() - 배열 앞부분 삭제
arr.unshift()
```

###### splice
---
```js
// 배열의 특정위치에 요소를 추가하거나 삭제  
// splice(시작인덱스, 제거할 요소 개수, 배열에 추가될 요소)
arr.splice( 2, 1, "a", "b"); // 2번째 인덱스에서 1개 제거 후 "a"와 "b"를 추가
```

###### slice
---
```js
// slice(시작인덱스, 종료인덱스)
// 배열의 startIndex부터 endIndex까지에 대한 (endIndex 불포함) 배열을 새로운 배열 객체로 반환
arr.slice( 3, 6 ); // 3번째부터 5번째까지의 데이터를 새로운 배열로 반환
```

###### find
---
```js
// find() - 콜백함수의 조건을 충족하는 첫번째로 찾아진 요소를 리턴한다, 못찾으면 undefined
arr.find((v) => v !== 0)
```

###### concat
---
```js
// concat() - 다수의 배열을 합치고 병합된 배열을 새로운 배열로 반환
arr1 = arr2.concat(arr3)
```

###### forEach
---
```js
// forEach() - 배열의 각 원소별로 지정된 함수를 실행한다
arr.forEach((e, i) => {
	console.log('element' : e, 'index' : i)
})
```

###### map
---
```js
// map() - 배열의 각 원소별로 지정된 함수를 실행한 결과로 구성된 새로운 배열을 반환한다
arr.map((v) => return v !== 0) // v -> 0이 아닌 값들로 새로운 배열 반환
```

###### filter
---
```js
// filter() - 지정된 함수의 결과 값을 true로 만드는 원소들로만 구성된 별도의 배열을 반환한다
arr.filter((v) => return v !== 0) // v -> 0이 아닌 값들로만 새로운 배열 반환
```

###### reduce
---
```js
// reduce - 배열을 돌면서 모든 요소들에 콜백함수를 실행해 누적된 값을 리턴한다
// 콜백에 reutrn값을 지정하지 않으면 누적값이 저장되지 않아 undefined가 나온다
const arr = [ '4', '3', '2', '1' ]
// reduce(이전값, 현재값, 현재인덱스, 배열)
arr.reduce((acc, cur) => acc + cur)

acc += cur; // 4 += 3;
acc += cur; // 7 += 2;
acc += cur; // 9 += 1;
console.log(acc); // 10
```

###### reverse
---
```js
// reverse() - 배열의 원소 순서를 거꾸로 바꾼다
arr.reverse();
```

###### sort
---
```js
// sort() - 배열을 오름차순 혹은 내림차순으로 재정렬 할 수 있다
arr.sort((a, b) => a - b) // 오름차순
arr.sort((a, b) => b - a) // 내림차순
```

###### some
---
```js
// some() - 배열의 요소 중에서 하나라도 콜백함수의 조건을 충족하는 요소가 있는지 검사
// 배열의 요소 중에서 하나라도 콜백함수의 조건을 충족하는 요소 검사 (리턴값 = boolean)
arr.some((v) => v !== 0)
```

###### toString
---
```js
// toString() - 배열을 문자열로 바꾸어 반환한다
arr.toString()
```

###### valueOf
---
```js
// valueOf() - toString과 비슷, 그러나 배열을 반환
arr.valueOf()
```

###### join
---
```js
// join('구분자' - 선택사항) - 배열 원소 전부를 하나의 문자열로 합친다.
arr.join()
```

###### split
---
```js
// split() - string을 새로운 배열로 생성한다
string.split()
```


#pop #push #shift #unshift #splice #slice #find #concat #forEach #map #filter #reduce #reverse #sort #some #toString #valueOf #join #split