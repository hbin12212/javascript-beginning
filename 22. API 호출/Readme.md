안녕하세요😄

> 이번시간에는 지금까지 배웠던 비동기적 처리 내용들을 사용해보면서, API 호출에 대해 배워보도록 하겠습니다.

# API란?

API(Application Programming Interface)는 앞선 강의들에서도 많이 언급을 했었는데요, 도대체 API란 무엇일까요?

인터넷에 API 정의를 검색해보면 API란 `"소프트웨어간에 데이터를 주고 받기 위한 프로토콜"` 이라고 나와있는데요,
쉽게 말하자면, 우리가 웹이나 앱에서 어떠한 방식으로 정보를 요청해야 하는지, 그리고 이러한 요청을 보냈을 때 어떤 형식으로 무슨 데이터를 전달받을 수 있는 지에 대해 정리한 규칙 이라고 할 수 있습니다.

아주 쉬운 예시를 통해 API란 무엇인지 자세하게 배워보도록 하겠습니다.

> 프로토콜이란, 데이터 통신을 원활하게 하기 위해 필요한 통신 규칙을 뜻합니다.

## 클라이언트와 서버의 통신

API에 대해 이해하려면, 먼저 클라이언트와 서버의 데이터 통신 즉, 우리가 웹이나 앱을 이용할 때 어떻게 원하는 데이터를 요청하고 받을 수 있는지를 먼저 이해해야합니다.

### 커피숍과 클라이언트-서버 통신

이러한 과정은 우리가 커피숍에 가서 커피를 주문하고 마시는 과정을 떠올려보면 쉽게 이해할 수 있습니다.

먼저, 우리가 커피숍에서 커피를 주문해 먹는 과정을 떠올려봅시다.

커피숍에서는 우리가 직접 커피숍에 들어가서 원두를 갈고 커피를 만들어 먹지 않고, 커피숍의 메뉴판을 통해 원하는 커피를 선택하고 직원에게 주문을 하게 됩니다.

커피숍에서 커피를 주문하는 자세한 과정을 단계로 나눠 보자면 다음과 같습니다.

![](https://velog.velcdn.com/images/hbin12212/post/fcfe1595-4305-48c9-b0c7-d38a9d8c2856/image.png)

1. 메뉴판을 보고 점원에게 원하는 커피를 주문합니다.
2. 점원은 주문받은 커피를 만들기 위해 필요한 재료들을 파악하고, 창고에서 재료를 꺼내 제작합니다.
3. 직원이 완성된 커피를 전달합니다.

이러한 과정은 우리가 웹이나 앱에서 데이터를 요청하고 전달받는 방식과 비슷합니다.

우리가 커피숍에서 커피를 주문하고 받는 과정과 마찬가지로 우리가 웹이나 앱에서 데이터를 요청하고 전달받는 방식을 단계별로 나눠보겠습니다.

![](https://velog.velcdn.com/images/hbin12212/post/2ac62c0f-90a7-4406-bd92-3973f9557e94/image.png)

1. 웹페이지에서 서버에게 원하는 데이터를 요청합니다.
2. 서버는 데이터베이스에서 요청받은 데이터를 찾고 꺼냅니다.
3. 서버가 웹페이지에 데이터를 전달합니다.

이 과정에 나오는 웹페이지(클라이언트), 서버, 데이터베이스, 데이터는
각각 커피를 주문하는 우리, 점원, 창고, 커피 라고 할 수 있습니다.

커피숍에서 커피를 시키는 과정과 마찬가지로 클라이언트는 원하는 데이터가 있을 경우, 직접 다른 서버의 데이터베이스에 접근하지 않고 원하는 데이터를 `요청` 합니다.

그 다음, 점원이 우리가 주문한 커피를 창고에서 알맞은 재료를 찾아 제작하듯이 서버 또한 클라이언트가 요청한 데이터를 데이터베이스에서 찾고 꺼냅니다.

마지막으로 점원이 완성된 커피를 우리에게 전달하는 것처럼, 서버는 클라이언트가 요청한 데이터를 전달하는 것이죠.

### 그래서 API란?

이렇게 클라이언트와 서버의 통신을 이해하셨다면, 소프트웨어간에 데이터를 주고 받기 위한 프로토콜인 API가 무엇인지는 바로 이해할 수 있겠죠?

API는 이렇게 서버와 클라이언트가 통신하는 과정 속에서 어떠한 규칙으로 데이터를 요청하고 전달하겠다는 약속이라고 할 수 있습니다.

그럼 이제는 API를 호출하는 방법 즉, 서버에게 데이터를 요청하고 전달받는 과정을 자바스크립트로 어떻게 작성해야 하는지
그리고 API 호출 시 정해져있는 약속들은 어떤 것들이 있는지 알아보도록 하겠습니다.

## API 호출

지금부터는 특정 서버에 데이터를 요청하고 받아보는 API 호출을 직접 실행해보겠습니다.

API 호출을 하기 위해서는 가장 먼저, 우리의 API 호출에 응답을 해줄 수 있는 서버가 필요한데요, 강의 실습을 위해 제작 해둔 별도의 서버가 없기 때문에 여러가지 api 예제들을 무료로 제공해주는 [jsonplaceholder](https://jsonplaceholder.typicode.com/) 라는 서비스를 이용해보도록 하겠습니다.

API 호출을 배우려면 json 형식에 대해 먼저 알아야하는데요,
https://jsonplaceholder.typicode.com/posts 에 접속해보면, 많은 `json 형식`의 데이터들을 볼 수 있습니다.

![](https://velog.velcdn.com/images/hbin12212/post/e4ec4640-f8c1-43bc-8f4a-a35dea6b1117/image.png)

json 이란 JavaScript Object Notation의 약자로 자바스크립트 객체 표기법 이라는 뜻을 갖고 있고, 보이는 것과 같이 key value 쌍으로 이루어져 있는 데이터 표기법 입니다.

다시 돌아와서 여기 웹페이지에 보이는 json 형식의 데이터들은 API 호출의 응답 결과들 입니다.

즉, 우리가 이 API를 이용해 호출을 하면 서버는 페이지에 보이는 것과 같은 json 데이터들을 전달해주게 된다는 뜻 입니다.

그럼 이제 실제로 API를 호출해보겠습니다.

우리는 jsonplaceholder에서 제공해주는 api 중 하나인, https://jsonplaceholder.typicode.com/posts/1 를 이용해서 API를 호출해보겠습니다.

```js
fetch("https://jsonplaceholder.typicode.com/posts/1").then((response) => console.log(response));
```

자바스크립트에서는 위의 코드와 같이 `fetch` 라는 내장함수를 이용해 API를 호출할 수 있습니다.

```js
fetch(url, options)
    .then((response) => console.log(response))
    .catch((error) => console.log(error));
```

내장함수 fetch는 위와 같이 파라미터로 url과 options 를 사용하고, then을 통해 호출 결과값을 받을 수 있고, catch 를 통해 에러처리를 할 수 있습니다.

여기서 알 수 있듯이, API는 url 형식으로 서버에 요청을 보낸다는 규칙이 있고, 동시에 여러가지 option들을 이용해 데이터를 요청할 수 있습니다.

그럼 다시 처음으로 돌아가서, 우리가 요청한 API의 결과값을 출력해보겠습니다.

작성한 코드를 실행시켜보면 다음과 같은 값이 출력됩니다.

![](https://velog.velcdn.com/images/hbin12212/post/98f1bfa5-4f6c-4f97-bc29-89f467f141c1/image.png)

json 형식의 데이터 값들이 아닌 이상한 값이 출력되었습니다.

이 출력 값은 요청에 대한 응답이 성공했는지 실패했는지 등에 대한 정보를 나태내고 있는 값이라고 생각하면 될 것 같습니다.

자세히 보시면 status: 200 이라고 적혀있는 것을 볼 수 있는데, 이 200 이라는 응답 코드는 "응답 성공" 을 뜻하는 숫자입니다.

이번 강의에서는 status 코드에 대한 자세한 내용은 다루지 않고 기본적인 값들만 언급하고 넘어가도록 하겠습니다.

그렇다면, 우리가 원하는 값을 얻기 위해서는 어떻게 코드를 작성해야 할까요?

```js
fetch("https://jsonplaceholder.typicode.com/posts/1")
    .then((response) => response.json())
    .then((data) => console.log(data));
```

위의 코드를 살펴보겠습니다.

API 응답 결과인 response 객체는 json() 메서드를 제공합니다.

이렇게 응답 객체의 json 메서드를 이용하면, 응답 결과 데이터를 json 형태로 파싱하여 요청에 대한 순수한 응답 데이터만 얻을 수 있습니다.

실제로 json 형태로 응답이 왔을 지 출력 결과를 살펴보겠습니다.

```
{
  "userId": 1,
  "id": 1,
  "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
  "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
}
```

출력 결과를 보면, 우리가 "https://jsonplaceholder.typicode.com/posts/1" 페이지에서 봤던 json 데이터와 동일한 값을 얻은 것을 확인할 수 있습니다.

## API와 비동기

이렇게 API의 개념과 API 호출 방법을 배워보았는데요, API를 호출 할 때에는 주의할 점이 있습니다.

API 호출은 필요한 데이터를 전달받기 위해 데이터를 요청하는 작업입니다.

데이터를 요청할 때에는 우리의 컴퓨터가 아닌, 다른 서버 프로그램에 요청하는 경우가 많기 때문에 네트워크 오류 혹은 인터넷 속도 등의 다양한 이유로 실패할 수 있다는 점을 주의해야합니다.

즉, API 호출을 통해 데이터 요청을 보낸 후 다양한 이유로 데이터를 어느 시점에 전달받을지 혹은 성공할지 실패할지를 알 수 없습니다.

언제 끝날지 모르는 작업을 모두 동기적으로 처리를 한다면, 많은 오류를 발생시킬 것입니다.

그렇기 때문에 우리는 API 호출을 할 때에는 async와 await을 이용해 비동기적으로 호출을 하게 됩니다.

위에서 작성했던 API 호출 코드를 비동기적으로 작성해보겠습니다.

```js
const getData = async () => {
    const response = await fetch("https://jsonplaceholder.typicode.com/posts/1");
    const data = await response.json();
    console.log(data);
};

getData();
```

비동기 동작을 수행할 함수 getData를 만들고, 함수 내부에서 fetch를 통해 API 호출을 비동기로 처리했습니다.

API 호출을 비동기로 처리했기 때문에 호출 이후 응답이 올 때 까지 아래 작성된 코드들은 실행되지 않습니다.

API 호출에 대한 응답이 오게되면 아래 작성된, 응답을 json으로 파싱하는 코드가 실행되고, 마찬가지로 응답을 json으로 파싱하는 과정이 완료되기 전까지 결과를 출력하는 코드가 실행되지 않습니다.

그럼 이번엔 async와 await을 이용했을 때 예외를 처리하는 방법인 try catch를 통해 더욱 정확한 코드를 작성해보겠습니다.

```js
const getData = async () => {
    try {
        const response = await fetch("https://jsonplaceholder123.typicode.com/posts/1");
        const data = await response.json();
        console.log(data);
    } catch (error) {
        console.log(`error : ${error}`);
    }
};

getData();
```

fetch 함수 내부의 url을 일부러 다른 주소로 작성해 오류를 발생시켜보았습니다.

try 내부의 코드들이 먼저 실행되고, 그 이후 오류가 발생한다면 catch 문을 통해 catch 내부 코드들이 실행되는 것을 확인할 수 있습니다.

이렇게 API 호출을 async와 await을 이용해 비동기적으로 처리한다면 오류없이 가독성 좋고 직관적으로 코드를 작성할 수 있고, 비동기 처리 방식으로 사고하지 않아도 된다는 장점이 있습니다.

---

# next

이번 시간에는 API를 이해하기 위해 클라이언트-서버 통신에 대해 배우고, 직접 API 호출을 해보았습니다.

그리고 API 호출을 왜 비동기적으로 처리해야하는지와 함께 async/await을 이용해 API 호출을 해보고 try catch를 통해 에러처리까지 해봤는데요,

이번 강의를 마지막으로, 준비한 자바스크립트 심화 커리큘럼은 끝이 났습니다.

다음시간에는 지금까지 배워온 개념들로 GOAL PROJECT를 만들어보도록 하겠습니다.

감사합니다😄

---
