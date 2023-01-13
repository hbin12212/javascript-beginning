안녕하세요🤗

이전 강의에서 배운것 처럼, 웹 개발을 위해서는 HTML 로 작성한 웹 요소들을 배치하고 꾸며주어야합니다.

> 이번 시간에는 우리가 만들 Goal Project를 개발하기 위해 알아야하는,
> 그리고 실제 개발을 할 때 가장 기본이 되는 CSS의 몇 가지 속성들을 배워보도록 하겠습니다.

# position

첫 번째로 우리가 배울 속성은 **"position"** 입니다.

position 속성은 웹 문서 상에 요소를 배치하는 방법을 지정합니다.

position 속성의 값으로는 static, relative, absolute, fixed, sticky 가 있고,
top, right, bottom, left 속성으로 요소를 배치할 최종 위치를 결정합니다.

하나씩 그림으로 설명해드리겠습니다.

```
예시로 사용된 코드 입니다.

<body>
    <div class="yellow"></div>
    <div class="blue"></div>
    <div class="green"></div>
</body>

```

## static

![](https://velog.velcdn.com/images/hbin12212/post/2cb16c6e-1184-4a3f-ac4f-4fb33f62fb98/image.jpg)

모든 웹 요소들은 기본적으로 position 값이 static 입니다.
static의 경우, 노랑 파랑 초록 순서로 쌓이게 됩니다.

## relative

![](https://velog.velcdn.com/images/hbin12212/post/cb61a62a-ec87-4dbd-9001-1e09658f5bbd/image.jpg)

position 값이 relative 일 경우를 살펴보겠습니다.

position 값이 **static 일 때의 위치를 기준**으로
웹 요소들의 위치를 변경하고 싶을 때, 값을 relative로 설정합니다.

위의 그림으로 확인해보시면, right 50px 이 적용된 노랑 div 는 왼쪽으로 50px 만큼,
left 50px 이 적용된 파랑 div는 오른쪽으로 50px 만큼,
bottom 50px 이 적용된 초록 divs 는 위로 50px 만큼 이동된 것을 볼 수 있습니다.

## absolute

![](https://velog.velcdn.com/images/hbin12212/post/55e3d007-b887-4f99-aed3-9eb4ff38202a/image.jpg)

position absoulte 는 relative 와는 다르게,
position 값이 **static 이 아닌 부모를 기준**으로 움직입니다.

위 그림의 코드에서, class 가 parent 인 div의 position 속성 값이 _relative 일 때 와 아닐 때_ 2가지의 경우를 나눠서 확인해보도록 하겠습니다.

우선, class 가 parent 인 div 를 회색 배경으로 표시 해두고,
부모 div 의 position 값이 relative 일 경우를 먼저 살펴보겠습니다.

![](https://velog.velcdn.com/images/hbin12212/post/8cd4b1b5-f40f-454c-8882-c65b76868990/image.jpg)

부모 div 의 position 값이 relative 라면, position 값이 absolute인 yellow, blue, green div의 위치는 위의 그림과 같습니다.

부모 div를 기준으로 오른쪽에서, 왼쪽에서, 아래에서 각각 50px 만큼 떨어져 있는 것을 확인 할 수 있습니다.

그럼, 만약 class 가 parent인 div 가 position static 값을 가지고 있다면 노랑, 파랑, 초록 div 들의 배치는 어떻게 될 까요?

![](https://velog.velcdn.com/images/hbin12212/post/e5d7ce6d-af73-4580-90e2-97feb59858c3/image.jpg)

부모의 position 값이 static 일 경우 그림에서 볼 수 있듯이 부모인 parent div 가 아닌,
조상인 **body 를 기준**으로 top, bottom, right, left 값이 적용되는 것을 확인할 수 있습니다.

## fixed, sticky

position fixed와 sticky 는 서로 비교를 하면서 설명해드리겠습니다.

![](https://velog.velcdn.com/images/hbin12212/post/c6f53f83-8f3f-42ca-8f19-5ec3d5825c56/image.jpg)

스크롤이 가능한 웹 페이지를 위해 body의 높이를 1000px 로 설정 후 parent div의 크기를 위와 같이 설정하겠습니다.

노랑색 div 의 position 값을 sticky 로 주고, 파랑색 div의 position 값을 fixed로 줍니다.

![](https://velog.velcdn.com/images/hbin12212/post/3e9c0e56-13d4-45bc-ba33-541b012c7df5/image.jpg)

스크롤을 내리면서 확인 해보면, 스크롤을 아무리 내리더라도
파랑색 div 가 left 50px 의 동일한 위치에 표시되는 것을 볼 수 있습니다.

이렇게 position 값을 fixed 로 설정하면, 해당 요소는 항상 특정 위치에 고정이 됩니다.

![](https://velog.velcdn.com/images/hbin12212/post/a356ad71-4826-4a89-8e9e-d2dfe8525a8f/image.gif)

반면에, sticky 의 값을 준 노랑색 div의 위치를 확인해보면,
parent div를 기준으로 top 0의 위치에 있다가
스크롤 시 parent div와 함께 사라지는 것을 확인할 수 있습니다.

이렇게 position의 값을 sticky로 설정하면,
parent div 를 기준으로 top, right, bottom, left의 값이 적용 되며,
스크롤 시 부모 div 안에서 고정되어 있다가 부모 div까지 밀리게 되면
자연스럽게 sticky div 도 밀리게 되는 것을 볼 수 있습니다.

---

# next

오늘은 기본적인 웹 요소들을 배치하는 방법인 position 속성에 대해 알아봤습니다.

다음 시간에는 마찬가지로 웹 개발을 할 때 아주 기본이 되는 CSS 의 display 속성에 대해 배워보도록 하겠습니다.

감사합니다!!

---
