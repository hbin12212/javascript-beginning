안녕하세요😄

> 이번 시간에는 웹 개발자라면 알고 있어야 하는 웹 에 대한 기본적인 지식들을 알아보도록 하겠습니다.

# 웹 사이트

웹 사이트란?

일반 URL을 통하여 보이는 웹 페이지들을 통틀어 말하는 말로, 대한민국에서 흔히 말하는 홈페이지라고 할 수 있습니다. (출처-위키백과)

이렇게 우리가 흔히 볼 수 있는 웹 사이트들은 보통 HTML, CSS, Javascript 로 이루어져있는데요, 그렇다면 먼저 HTML, CSS, Javascript 에 대해 아주 쉽게 알려드리겠습니다.

## HTML

HTML은 HyperText Markup Language로, 쉽게 말하면 브라우저에게 웹 사이트의 요소들이 어떻게 구성되어있는지를 알려주는 역할을 합니다.

## CSS

CSS는 Cascading Style Sheets로, 말 그대로 웹 사이트의 요소들을 꾸며주는 역할을 하는 sheet 입니다.

## Javascript

Javascript란 프로그래밍 언어로, 브라우저에서 다양한 일을 수행하고 웹 사이트의 여러 요소들을 생성시키거나 변형시킬 수 있는 언어입니다.

> HTML 은 웹 요소들을 구성하고, CSS 는 웹 요소들을 꾸며주고, Javascript는 웹 요소들을 생성, 삭제, 변형 한다.

HTML, CSS와는 다르게 Javascript는 어떻게 HTML로 작성된 웹 요소를 변형시킬 수 있을까요???

이를 설명하기 위해서는 DOM (Document Object Model) 이라는 객체에 대한 이해가 필요합니다.

## DOM

DOM 이란 무엇일까요?

![](https://velog.velcdn.com/images/hbin12212/post/6e7df781-f221-4201-8b4a-0e8077c48759/image.jpg)

DOM이란 HTML로 작성된 여러 요소들에 Javascript가 접근할 수 있도록 브라우저가 변환시킨 객체입니다.

쉽게 말해 작성한 HTML을 Javascript 가 이해할 수 있게 **객체로 변환** 한 것 입니다.

Javascript는 이러한 DOM을 통해 HTML로 짜여진 요소들을 생성 및 변형하고 삭제할 수 있게 됩니다.

DOM (Document Object Model) 은 이미지에서 왼쪽의 HTML을 오른쪽의 그림과 같이 트리구조로 나타냅니다.

그렇다면, DOM은 어떻게 브라우저로 동작이 되는지 간단하게 그림과 함께 보여드리도록 하겠습니다.

![](https://velog.velcdn.com/images/hbin12212/post/a9303b75-1f1b-421f-bfac-49728cefd60f/image.png)

우선, 브라우저는 HTML을 전달 받으면 HTML 파서를 통해, DOM 트리를 형성합니다.

그 다음 Style sheet들을 파싱하여 스타일 규칙들을 생성하게 됩니다.

![](https://velog.velcdn.com/images/hbin12212/post/44fd82c0-197c-4a8b-99d1-aea355e67c52/image.png)

생성된 스타일 규칙들과 DOM 트리를 Attachment, 합친 다음 Render Tree를 형성합니다.

이 Render Tree 는 실제로 화면에 그려질 Tree를 나타냅니다.

![](https://velog.velcdn.com/images/hbin12212/post/9b305a10-4076-4e4f-b7ab-54c0f740dc3b/image.png)

Render Tree가 형성 되면, 브라우저는 Layout을 수행합니다.

Layout은 RenderTree를 화면에 어느 위치에 어떤 크기로 배치할 것 인지를 계산하는 작업입니다.

마지막으로 Painting 을 수행하면, Layout 후 나온 결과값을 통해 픽셀단위로 변환하여 실제 화면에 나타내게 됩니다.

웹 브라우저는 이렇게 많은 과정을 수행 한 후 웹을 화면에 표시합니다.

웹 사이트에서 수정이 일어나게 되면, 이렇게 많은 과정을 다시 처음부터 반복적으로 수행하게 되어, 웹 사이트 전체가 다시 렌더링이 되어 비효율적이라는 단점이 있습니다.

---

# next

본격적으로 강의를 들어가기 전에, 우리가 배울 "웹 사이트" 란 무엇인지, 또 "웹 사이트" 는 어떻게 화면에 나타나게 되는지를 설명해보았습니다.

다음 시간에는 우리가 Goal Project를 개발하기 위해 알아야하는, 그리고 실제로 웹개발을 할 때 기본적으로 필요한 CSS 속성들 몇가지를 배워보도록 하겠습니다.

감사합니다🤗

---

```
🙏참고 & 출처

- 웹 브라우저 렌더링 순서 이미지
https://pinokio0702.tistory.com/362
```
