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

## Typescript vs. Javascript
