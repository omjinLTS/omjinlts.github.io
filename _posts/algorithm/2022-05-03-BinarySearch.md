---
title: "이분 탐색 (Binary/Parametric Search)"
categories:
  - algorithm
tags:
  - 이분탐색
  - 분할정복
  - 재귀
last_modified_at: 2022-05-03 19:38:48
toc: true
toc_sticky: true
---

정렬되어있는 리스트에서 범위를 절반씩 줄여나가며 탐색함.

## 구현

### Python 3

```python
#arr : 오름차순 정렬된 배열

#재귀
def binarySearch(arr, l, r, x):
  if r >= l:
    mid = l + (r-l) // 2
    if arr[mid] > x:
      return binarySearch(arr, l, mid-1, x)
    elif arr[mid] < x:
      return binarySearch(arr, mid+1, r, x)
    else: return mid
  else: return -1

#반복
result = -1
while (l < r):
  mid = (l+r) // 2
  if arr[mid] > x: r = mid-1
  elif arr[mid] < x: l = mid+1
  else:
    result = mid
    break

```
