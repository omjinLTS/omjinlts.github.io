---
title: "[이첵티브 타입스크립트] 정리"
categories:
  - dev
tags:
  - typescript
  - 타입스크립트
last_modified_at: 2024-01-29 17:39:02
toc: true
toc_sticky: true
---

## 시작하며

react, react-native를 공부하며 typescript를 사용해보고 있었지만, 보다 효율적인 코드 작성을 위해 이펙티브 타입스크립트를 공부하며 정리합니다.

![이펙티브 타입스크립트 - 댄 벤더캄](https://image.yes24.com/goods/102124327/XL)

## 타입스크립트란?

> 마이크로소프트에서 구현한 JavaScript의 슈퍼셋(Superset) 프로그래밍 언어. 확장자로는 .ts를 사용하며, 컴파일의 결과물로 JavaScript 코드를 출력한다. 최종적으로 런타임에서는 이렇게 출력된 JavaScript 코드를 구동시키게 된다.\
> <sub><sub>출처: 나무위키</sub></sub>

## Why TypeScript?

본격적인 내용 정리에 앞서 타입스크립트에 대해서 간단하게만 짚어보겠습니다.

<h2 style="border:none">Safety!</h2>

frontend에서는 JavaScript가 강요되는 실상에서, 타입 안정성이 보장되지 않는 JavaScript의 단점을 보완하고자 등장한 것이 TypeScript입니다.

*Douglas Crockford*의 **JavaScript: The Good Parts: The Good Parts**의 서문에는 이런 문구가 있습니다.

> Most programming languages contain good and bad parts, but JavaScript has more than its share of the bad, having been developed and released in a hurry before it could be refined.
>
> 대부분의 프로그래밍 언어는 장단점이 있지만, 자바스크립트는 정제되기 전에 급하게 개발되고 출시된 탓에 단점이 대부분이다. \
> <sub>자바스크립트는 1995년 Netscape의 스크립트 언어로 Brenden Eich에 의해 10일만에 개발되었다. </sub>

'Type'Script라는 이름에서 알 수 있듯, TypeScript는 JavaScript의 단점 중 꽤나 큰 단점인 타입 안정성을 보장해준다는 점에서 장점을 지닙니다.\
JavaScript에서 타입 안정성이 보장되지 않는 예시인 다음의 코드를 보겠습니다.

```javascript
let a = [1, 2, 3, 4] + false;

function divide(a, b) {
  return a / b;
}

let b = divide("hello");
```

JavaScript에서 위와 같은 코드는 아무런 오류 없이 정상적으로 실행이 되며, `a`에는 `'1,2,3,4false'`가, `b`에는 `NaN`이 들어가게 됩니다.

한편 타입스크립트에서는 이러한 코드가 오류를 발생시키며 컴파일되지 않습니다.

> 해당 책은 타입스크립트를 사용한 경험이 있는, 보다 좋은 타입스크립트를 작성하고자 하는 독자를 대상으로 하기에, 차입스크립트에 대해 모르시는 분들은 내용이 이해되지 않을 수 있습니다.

## 목차

- [1장. 타입스크립트 알아보기]()
- [2장. 타입스크립트의 타입 시스템]()
- [3장. 타입 추론]()
- [4장. 타입 셜계]()
- [5장. any 다루기]()
- [6장. 타입 선언과 @types]()
- [7장. 코드를 작성하고 실행하기]()
- [8장, 타입스크립트로 마이그레이션하기]()

> **출처**
>
> ≪이펙티브 타입스크립트≫(댄 밴더캄 지음, 장원호 옮김, 인사이트, 2021)
