---
title: "[알고리즘] 분할 정복을 이용한 거듭제곱"
categories:
  - algorithm
tags:
  - 분할 정복
  - divide and conquer
  - recursion
  - 재귀
  - 수학
last_modified_at: 2022-12-05 19:34:06 #cmd+shift+I
toc: true
toc_sticky: true
use_math: true
---

## 분할 정복을 이용한 거듭제곱

$ n^x $ 를 구하는 데에 있어 분할 정복을 이용하는 방법.
반복문 또는 재귀를 사용해 `n`을 단순히 `x`번 곱하는 naive한 방법의 시간복잡도가 $ O(1) $ 인데 비해, 분할 정복을 통해 $ O(\log n)$ 의 시간복잡도로 거듭제곱을 구해낸다.

$ k^x $ 를 `return`하는 함수를 `pow(k, x)`라 하자.

```c
pow(k, x) = x * pow(k, x/2) * pow(k, x/2) // x가 홀수라면
pow(k, x) = pow(k, x/2) * pow(k, x/2) // x가 짝수라면
```

`x`의 홀짝 여부에 따라 위와 같이 나타낼 수 있는데, `x`가 $ 1/2 $ 로 줄어 들 때 마다 `pow(k, x/2)`를 한번 계산 후 재사용하면 매 단계 계산이 절반으로 줄어 $ \log_2x $ 번의 계산으로(`x`가 홀수라면 1회 더) 구할 수 있다.

## 모듈러 연산이 필요한 경우

거듭제곱 연산의 경우 수가 기하급수적으로 커지기에 나머지를 구하도록 요구되는 경우가 잦다.
$ (k^x)\%m $ 을 구할 때에, 특히 자료형의 범위가 정해진 언어를 사용 할 시에 마지막에만 나머지를 취해주면 그 전에 오버플로우가 발생해 값이 꼬이는 일이 발생할 수 있다.

모듈러(나머지) 연산의 성질에 따라 다음의 식이 성립한다.

$$
(A \times B) \% m = ((A\%m)\times(B\%m))\%m


$$

따라서 각 단계에서 `m`으로 나눈 나머지를 취해 사용하면 된다.

## 구현

### python

```python
# version 1 : recurvice, top-down
def pow(k, x):
    if x == 0: return 1
    tmp = pow(k, x//2)
    if x % 2: # x가 홀수라면
        return k*tmp*tmp
    else: # x가 짝수라면
        return tmp*tmp

# version 2 : bottom-up
def pow(k, x):
    result = 1
    while x > 0:
        if x % 2: result *= k
        k *= k # result = result * result
        x //= 2
    return result

```

## 추천 문제

[1629번: 곱셈](https://www.acmicpc.net/problem/1629)

[11444번: 피보나치 수 6](https://www.acmicpc.net/problem/11444)
