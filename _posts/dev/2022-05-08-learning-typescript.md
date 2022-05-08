---
title: "[타입스크립트] 타입스크립트 정리"
categories:
  - dev
tags:
  - typescript
  - 타입스크립트
last_modified_at: 2022-05-08 18:44:10
toc: true
toc_sticky: true
---

## 시작하며

react, react-native를 공부하며 typescript를 사용해보며 대충 익히고 있었지만, 그 문법이나 특징에 대해 제대로 공부해본 적은 없었다. 최근 react-native 프로젝트와 react 프로젝트에서 본격적인 개발에 들어갔는데, typescript에 대해 제대로 익히기 위해 공부하며 정리를 하려 한다.

공부는 최근 생긴 노마드 코더의 무료 Typescript 강의인 [Typescript for Beginners](https://nomadcoders.co/typescript-for-beginners)를 통해 하려 한다. 타입스크립트를 블록체인을 만들며 핵심적인 부분을 짚는 느낌의 강의인데, 당장의 개발에 필요한 핵심 주요 기능들을 익히기 좋아보이고, 블록체인에 대해 관심도 생긴 터라 해당 강의를 선택했다.

## 타입스크립트란?

> 마이크로소프트에서 구현한 JavaScript의 슈퍼셋(Superset) 프로그래밍 언어. 확장자로는 .ts를 사용하며, 컴파일의 결과물로 JavaScript 코드를 출력한다. 최종적으로 런타임에서는 이렇게 출력된 JavaScript 코드를 구동시키게 된다.\
> <sub><sub>출처: 나무위키</sub></sub>

## Why TypeScript?

<h2 style="border:none">Safety!</h2>

frontend에서는 JavaScript가 강요되는 실상에서, 타입 안정성이 보장되지 않는 JavaScript의 단점을 보완하고자 등장한 것이 TypeScript이다.

*Douglas Crockford*의 **JavaScript: The Good Parts: The Good Parts**의 서문에는 이런 문구가 있다

> Most programming languages contain good and bad parts, but JavaScript has more than its share of the bad, having been developed and released in a hurry before it could be refined.
>
> 대부분의 프로그래밍 언어는 장단점이 있지만, 자바스크립트는 정제되기 전에 급하게 개발되고 출시된 탓에 단점이 대부분이다. \
> <sub>자바스크립트는 1995년 Netscape의 스크립트 언어로 Brenden Eich에 의해 10일만에 개발되었다. </sub>

'Type'Script라는 이름에서 알 수 있듯, TypeScript는 JavaScript의 단점 중 꽤나 큰 단점인 타입 안정성을 보장해준다는 점에서 장점을 지닌다.\
JavaScript에서 타입 안정성이 보장되지 않는 예시인 다음의 코드를 보자.

```javascript
let a = [1, 2, 3, 4] + false;

function divide(a, b) {
  return a / b;
}

let b = divide("hello");
```

JavaScript에서 위와 같은 코드는 아무런 오류 없이 정상적으로 실행이 되며, `a`에는 `'1,2,3,4false'`가, `b`에는 `NaN`이 들어가게 된다.

## 목차

[1. TypeScript 훑어보기 - Types (예정)]()

[2. TypeScrip의 함수 (예정)]()
