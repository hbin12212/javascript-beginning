안녕하세요🙂

> 이번 시간에는 저번에 배운 position 속성에 이어, 알아두면 굉장히 유용하고 편리한 CSS 속성인 display 에 대해 배워보도록 하겠습니다.

# display

display는 HTML 에서 생성되는 렌더링 박스의 타입을 지정하는 속성으로
실제 정말 많이, 그리고 유용하게 사용하는 속성으로 웹을 개발하기 위해 꼭 알고있어야 하는 속성 중 하나라고 생각합니다.

display 속성에는 none, block, inline, inline-block 그리고 grid, flex 등의 다양한 값들이 있습니다.

![](https://velog.velcdn.com/images/hbin12212/post/35af0656-b059-4512-972d-6bcace776393/image.jpg)

먼저, 위의 그림에서 보이는 코드를 통해 block, inline, inline-block, none 의 값을 갖는 박스들의 배치를 보여드리겠습니다.

class 이름이 **속성값-setting** 으로 되어있는 요소들은 오른쪽 코드처럼 CSS 상에서, width 와 height 의 값을 각각 300px, 200px 으로 고정해놓고 시작하겠습니다.

위의 코드를 실행하면 아래의 그림과 같은 화면이 렌더링 됩니다.

![](https://velog.velcdn.com/images/hbin12212/post/39dace42-b27c-4c80-8038-52c7d13fe617/image.png)

## block

먼저 display **block** 값을 갖는 요소를 보면,
기본적으로 가로의 길이가 100% 로 설정이 되며,
한 줄의 하나의 박스만 배치되는 것을 확인 할 수 있습니다.

**block-setting** 이라고 적힌 박스를 보면, 우리가 설정했던 길이와 높이의 값이 적용이 되어 표시 되는 것을 알 수 있습니다.

## inline

inline 값이 적용된 박스들도 확인을 해보겠습니다.

위의 그림에서 볼 수 있듯이, **inline** 값은 기본적으로 한 줄에 여러개의 박스가 배치되고,
길이와 높이의 값을 **설정**해놓더라도 inline 박스 안의 내용에 따라 길이와 높이가 결정되는 것을 볼 수 있습니다.

## inline-block

**inline-block** 은 말 그대로, inline 특징과 block 특징 모두가 적용된 값으로,
기본적으로 한 줄에 여러개의 박스가 배치되며,
박스 안의 내용에 따라 길이와 높이가 결정되지만

**inline-block setting** 에서 처럼 길이와 높이를 설정하면
설정한 값으로 크기가 적용이 되는 것을 확인할 수 있습니다.

## none

코드에는 **none** 이라는 박스가 있지만, 위의 그림에서는 확인이 되지 않습니다.

display 속성값을 none 으로 주게 되면, 이렇게 그 요소가 존재하지 않았던 것처럼 사라지게 됩니다.

> [ 정리 ] display : none, block, inline, inline-block

> ![](https://velog.velcdn.com/images/hbin12212/post/ef51a18c-e4ca-401a-bd8e-6e248e5ef198/image.png)

## grid

다음으로 display grid 에 대해 알아보겠습니다.

grid 는 말그대로 격자를 뜻합니다.
grid 값을 설정하게 되면, 해당 요소 바로 밑에 있는 모든 자식 요소들은 grid-item 이 됩니다.

![](https://velog.velcdn.com/images/hbin12212/post/0ec19267-912d-46c2-b1f0-0a291dc1deec/image.jpg)

위의 그림은 grid-wrapper 박스에 display grid 값을 적용한 배치입니다.

이렇게 display 속성에 grid 값만 적용하게 되면,
아이템을 columns가 5개, row가 1개인 grid 형태의 구조로 생성합니다.

### grid-template

grid 의 행과 열은 `grid-template-rows`, `grid-template-columns` 속성으로 조절할 수 있습니다.

![](https://velog.velcdn.com/images/hbin12212/post/97bc5ffb-4604-4f02-9a11-df43f811df3b/image.png)

위의 그림은 `grid-template-columns` 를 통한 배치입니다.

첫 번째 그림과 같이, columns 에 들어갈 아이템의 길이를 80px 씩 3개로 입력하게 되면,
1개의 행에 3개의 row가 80px 의 크기로 생성됩니다.

두 번째 그림에서는 첫 번째 그림과는 다르게 fr 이라는 단위로 작성되어있는 것을 볼 수 있습니다.

fr 이라는 단위는 사용 가능한 공간을 일정 비율로 나타낸 단위로,
그림처럼 2fr 1fr 1fr 로 사용할 경우, 1개의 행에 길이가 2 : 1 : 1 의 비율인 요소 3개가 들어가게 됩니다.

![](https://velog.velcdn.com/images/hbin12212/post/a7264efe-ea62-45a8-a397-feedfeb2b822/image.png)

`grid-template-rows` 도 위의 그림을 통해 확인해보도록하겠습니다.

grid-template-columns와 마찬가지로, 1개의 row에 위의 코드에 작성된 높이 만큼 아이템이 배치되어있는 것을 볼 수 있습니다.

> grid-template-columns 는 columns에 들어갈 아이템의 길이를,
> grid-template-rows는 rows에 들어갈 아이템의 높이를 설정

## flex

![](https://velog.velcdn.com/images/hbin12212/post/05b71b73-ec80-4359-8a7e-e97aa626f93c/image.jpg)

display flex 값을 적용한 박스 안의 요소들은, 위의 그림처럼 일열로 배치되게 됩니다.

이렇게 배치된 요소들은 어떤 방향으로든 배치될 수 있고,
커지거나 축소하여 크기 조정 및 정렬을 쉽게 조작할 수 있도록 유연해지게 됩니다.

flex 값이 적용 된 박스의 하위 요소들을 조작하기 위해서는
두 가지 속성을 알아야합니다

`justify-content` 속성과 `align-items` 속성을 순서대로 설명드리겠습니다.

### justify-content

![](https://velog.velcdn.com/images/hbin12212/post/359de54b-51e1-470c-b6ef-6b96cdae2af6/image.jpg)

위의 그림을 통해, justify-content 속성에 대해 알아보겠습니다.

display flex 값을 적용하게 되면 기본적으로 justify-content **flex-start** 값이 적용되며, 요소들을 flex 박스의 왼쪽으로 정렬합니다.

**flex-end** 는 요소들을 flex 박스의 우측 (끝) 으로 정렬합니다.

**center** 는 요소들을 flex 박스의 정중앙으로 정렬합니다.

![](https://velog.velcdn.com/images/hbin12212/post/5558d26a-f8d1-48f1-8122-b222c18183a3/image.jpg)

> 위의 그림에서 하늘색은 요소 (item) 들을 , 녹색은 간격의 길이를 나타냅니다.

**space-around** 는 위의 그림처럼, 요소 주변의 (양옆) 간격을 동일하게 두고 정렬됩니다.

**space-between** 는 첫 번째 요소는 가장 왼쪽에 (시작), 마지막 요소는 가장 오른쪽에 (끝) 두고, 나머지 요소들은 사이의 간격을 동일하게 두고 정렬됩니다.

마지막으로 **space-evenly** 는 요소 사이의 간격을 전부 동일하게 두고 정렬이 됩니다.

### align-items

align-items 속성은 justify-content 속성과는 다르게 세로를 기준으로 하위 요소들의 위치를 조절하는 속성입니다.

![](https://velog.velcdn.com/images/hbin12212/post/1ffa540f-c373-4149-8683-61ea6917f712/image.jpg)

위의 그림처럼 display flex 가 적용된 박스의 높이를 100px 로 잡고,
align-items 속성 값을 변경하면서 보여드리겠습니다.

align-items 값을 **start** 로 적용하면, 하위 요소들은 박스의 시작 부분
즉 가장 윗 부분에 정렬됩니다.

**center** 값을 적용하면 박스의 중앙 부분,

**end** 값을 적용하면 박스의 가장 아랫부분 으로 정렬이 되는 것을 볼 수 있습니다.

start, center, end 값과 달리 align-items **stretch** 값을 적용하게 되면 ,
하위 요소들의 높이가 display flex 값이 적용된 박스의 높이와 동일하도록 늘어나게 됩니다.

---

# next

display 속성만 잘 알고있어도 웹 요소들을 자유자재로 원하는 위치에, 원하는 크기로 배치할 수 있습니다.

오늘은 정말 유용하게 사용되는 CSS 속성인 display 에 대해 알아봤습니다.

다음 시간부터는 본격적으로 javascript 기초 부터 심화 개념까지 하나씩 자세하게 다뤄보도록 하겠습니다.

감사합니다😄

---
