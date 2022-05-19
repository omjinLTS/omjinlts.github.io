---
title: "\\[백준 17419\\] 비트가 넘쳐흘러 Python"
categories:
  - dev
tags:
  - cpp
  - xcode
  - m1 mac
  - mac
last_modified_at: 2022-05-19 19:08:56
---

## bits/stdc++ 사용 설정

vscode에서 include path 오류나, xcode로 개발 시 bits/stdc++.h를 사용하고 싶을 때 설정해주어야 한다.

1. stdc++.h 파일 생성
   [stdc++.h 파일 내용](https://gist.github.com/frankchen0130/9ac562b55fa7e03689bca30d0e52b0e5) 링크의 코드를 복사해 편한 위치에 stdc++.h의 이름으로 생성한다. 아래에 설명할 위치에 바로 만들어도 되지만, xcode가 업데이트되면 파일이 없어져 매번 새로 만들어야 하니 편한 위치에 만들어 두는것을 추천. 본인은 `~/Documents/stdc++.h`로 만들어두고 사용함.

2. 터미널로 이동

```bash
cd /Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX.sdk/usr/include/c++/v1
```

```bash
sudo mkdir bits
```

```bash
sudo cp ~/Documents/stdc++.h ./bits
```

`~/Documents/stdc++.h` 부분은 본인이 만들어 둔 stdc++.h 파일의 경로를 적어주면 된다.
