안녕하세요😄

> 이번시간에는 자바스크립트의 반복문에 대해 배워보도록하겠습니다.

# 반복문

반복문은 특정 작업을 반복적으로 할 때 사용할 수 있는 구문으로, 프로그래밍을 할 때 아주 유용하게 자주 쓰이는 중요한 개념입니다.

자바스크립트에서 사용할 수 있는 반복문은 여러가지가 있습니다.

하나씩 살펴보겠습니다.

## for문

for문은 가장 기본적인 반복문으로, 일정 횟수만큼 조건에 따라 반복 실행해야 할 때 사용됩니다.

1부터 10까지 출력하는 프로그램을 작성해보겠습니다.

```js
console.log(1);
console.log(2);
    .
    .
    .
console.log(10);
```

반복문을 사용하지 않는다면, 같은 코드를 10번씩 숫자만 바꿔서 작성해야합니다.

이번에는 for 문을 이용해 같은 프로그램을 작성해보겠습니다.

```js
for (let i = 1; i <= 10; i++) {
    console.log(i);
}
```

반복문을 사용하면 이렇게 위의 코드처럼 짧게 단축해서 작성할 수 있습니다.

그럼 이 for문을 어떻게 사용하는지 자세하게 살펴보겠습니다.

```js
for (초기화; 조건; 증감식;) {
    //반복 수행할 코드
}
```

위의 for 문 구조를 참고해서, 아래 작성된 for 문의 실행 순서를 알아보겠습니다.

```js
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
```

1. (let i =1;) 변수 i 를 선언하고, 초기값을 1로 할당합니다.
2. (i <= 5;) 조건을 비교합니다.
   1 <= 5 조건식이 성립하기 때문에 console.log(i)를 실행합니다.
3. 증감식으로 이동해, i++ 이 실행되어 i의 값이 2로 변경됩니다.
4. 1,2,3 번을 반복합니다.
5. i 의 값이 6이 되었을 경우, 조건식 6 <= 5 가 성립하지 않기 때문에 for문이 종료됩니다.

## while문

while문은 특정 조건이 참이라면, 특정 코드를 반복 수행하는 반복문입니다.

for문은 특정 변수의 초기값과 조건문을 비교하고 그 조건문이 참이라면 변수의 값을 증감시켜 코드를 반복 수행하지만,
while문은 단순하게 괄호안의 조건문만 확인하여 코드를 반복 수행한다는 차이점이 있습니다.

이번에도 1부터 10까지의 숫자를 출력하는 코드를 while 문으로 작성해보겠습니다.

```js
let i = 1;

while (i <= 10) {
    console.log(i);
    i++;
}
```

while문에서는 괄호안의 조건문이 참이면 while문 내부의 코드를 계속 수행하기 때문에, while문 내부에서 반복 횟수를 결정하는 변수의 값을 직접 변화시켜 주어야합니다.

위의 코드에서는, 1부터 10까지의 숫자만을 출력하기 위해, 변수 i의 값을 출력할 때마다 i 의 값을 1씩 늘려주었습니다.

while 문을 작성하실 때에는 조건문이 언젠가는 false가 되어 종료될 수 있도록 주의해서 작성해주어야 합니다.

## 배열과 반복문

이러한 for문과 while문은 자바스크립트에서 배열의 모든 요소들에 접근해야 할 때 유용하게 사용됩니다.

for문을 이용해 배열의 모든 요소를 접근하는 반복문을 작성해보겠습니다.

```js
let arr = [1, 2, 3, 4, 5];

for (let i = 0; i < arr.length; i++) {
    console.log(arr[i]);
}
```

배열의 length 프로퍼티는 배열의 길이를 가지고 있기 때문에, 위의 코드처럼 for문의 조건식 부분에 arr.length 를 통해 정확하게 배열의 크기만큼 for문을 실행시킬 수 있고,

0부터 1씩 증가하는 i 변수로, 배열의 인덱스를 하나씩 늘려가면서 모든 배열의 요소에 접근할 수 있게 됩니다.

## 객체와 반복문

이렇게 반복문 중에서 for문과 while문을 알아보면서, 배열을 반복문을 이용해 순회할 수 있다는것을 알아보았습니다.

우리는 배열 뿐만아니라, 객체의 프로퍼티도 반복문을 활용하여 순회할 수 있습니다.

객체의 모든 프로퍼티에 접근하기 위해서는 객체를 배열 형태로 변경해야합니다.

```js
let person = {
    name: "홍길동",
    age: 25,
    height: 180,
    pet: "cat",
};

console.log(person);
//{name: "홍길동", age: 25, height: 180, pet: "cat"}
```

이 person 객체를 배열로 변경하는 방법은 3가지가 있습니다.

```js
console.log(Object.keys(person));
console.log(Object.values(person));
console.log(Object.entries(person));
```

각 방법들을 이용해서 객체를 배열로 변경 후, 반목문을 이용해 객체를 순회해보도록하겠습니다.

### 1. Object.keys()

첫 번째 방법입니다.

Object.keys는, Object라는 객체의 메서드로, 인자로 받은 객체의 `key`를 모두 찾아 아래와 같이 배열로 반환합니다.

```js
console.log(Object.keys(person));
//["name", "age", "height", "pet"]
```

그럼 객체를 key 값들로 이루어진 배열로 변환했으니, 반복문을 사용해 객체의 프로퍼티들을 모두 순회해보도록하겠습니다.

```js
let newArray = Object.keys(person);
// person 객체를 [key, key] 형태의 배열로 변환

for (let i = 0; i < newArray.length; i++) {
    let nowKey = newArray[i]; // newArray 배열의 요소 순서대로 접근
    console.log(`key : ${nowKey}`);
    console.log(`value : ${person[nowKey]}`);
}
```

위의 코드에서는, 먼저 newArray 라는 변수에, person 객체를 배열로 변환한 결과를 담았습니다.

그다음 for문을 통해 newArray 요소를 하나씩 모두 순회합니다.

newArray 의 요소, 즉 person 객체의 key값을 알고있기 때문에 객체의 프로퍼티를 모두 출력할 수 있습니다.

### 2. Object.values()

객체를 배열로 변경하는 두 번째 방법은 Object.values를 이용하는것입니다.

이 메서드의 인자로 객체를 넘기면, 해당 객체의 `values`를 모두 찾아 아래와 같이 배열로 반환합니다.

```js
console.log(Object.values(person));
//["홍길동", 25, 180, "cat"]
```

Object.values를 이용하면 객체의 key 값을 알 필요 없이 value 값을 바로 알 수 있습니다.

```js
let newArray = Object.values(person);
// person 객체를 [value, value] 형태의 배열로 변환

for (let i = 0; i < newArray.length; i++) {
    console.log(`value : ${newArray[i]}`);
}
```

위의 코드에서는, newArray에 바로 객체의 value 값들로 이루어진 배열이 저장되기 때문에 for문을 통해 바로 value 값을 꺼내 출력할 수 있습니다.

### 3. Object.entries()

객체를 배열로 변경하는 마지막 방법은 Object.entries() 입니다.

entries 메서드는 객체를 받으면 `[[key, value], [key, value]]` 형태의 배열로 변환합니다.

```js
console.log(Object.entries(person));
//[ ["name", "홍길동"], ["age", 25], ["height",180],["pet","cat"] ]
```

마찬가지로, Object.entries()를 이용해 객체를 배열로 변환 후 객체의 모든 프로퍼티에 접근해보겠습니다.

```js
let newArray = Object.entries(person);
// person 객체를 [[key,value], [key,value]] 형태의 배열로 변환

for (let i = 0; i < newArray.length; i++) {
    console.log(`key : ${newArray[i][0]}`);
    console.log(`value : ${newArray[i][1]}`);
}
```

위의 코드를 실행시켜보면, person 객체의 key, value 들이 잘 출력되는 것을 볼 수 있습니다.

Object.entries 는 인자로 받은 객체의 모든 key, value 쌍을 배열에 담아 반환하기 때문에 객체의 모든 프로퍼티를 출력할 수 있습니다.

## for...of 와 for...in

이렇게 반복문과 함께 배열의 모든 요소와, 객체의 모든 프로퍼티에 접근할 수 있는 방법을 배워보았습니다.

이번에는 알아두면 유용한 자바스크립트의 반복문들을 몇 가지 알려드리겠습니다.

### for...of

for...of 문은 주로 배열의 모든 요소에 접근해야 될 때 사용됩니다.

```js
let arr = [1, 2, 3, 4, 5];

for (let num of arr) {
    console.log(num);
}
```

```
1
2
3
4
5
```

위의 코드를 실행하면, arr 배열안에 있는 요소들이 순서대로 출력되는 것을 볼 수 있습니다.

### for...in

for...in 문은 주로 객체에서 사용되며, for문과는 달리 객체의 모든 프로퍼티를 순회할 수 있도록 해줍니다.

```js
let person = {
    name: "홍길동",
    age: 25,
    height: 180,
    pet: "cat",
};

for (let key in person) {
    console.log(`${key} : ${person[key]}`);
}
```

```
name : 홍길동
age : 25
height : 180
pet : cat
```

for...in 문을 사용하면,객체를 배열로 변환하는 과정 없이 한 번에 객체의 모든 프로퍼티에 접근할 수 있습니다.

---

# next

이번 시간에는 자바스크립트의 여러가지 반복문과 함께 배열과 객체를 순회하는 몇 가지 방법들을 배워보았습니다.

다음 시간에는 많이 쓰이고, 꼭 알아야 하는 자바스크립트 배열의 내장함수들에 대해 다뤄보도록하겠습니다.

감사합니다!

---
