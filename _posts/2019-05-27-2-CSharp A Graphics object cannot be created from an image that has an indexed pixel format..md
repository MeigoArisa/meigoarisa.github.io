---
layout: post
title: A Graphics object cannot be created from an image that has an indexed pixel format.
categories: C#

---

## A Graphics object cannot be created from an image that has an indexed pixel format.

비트맵 파일을 Mat으로 변환해서 그레이 스케일, 이진화 등의 연산 후 다시 Bitmap으로 변환했고

Graphics 로 다시 그리려 하니 발생하였다.

이 문제는 동일한 크기의 빈 비트 맵을 만들고, 올바른 비트 맵을 만든 후 비트 맵에 draw를하면 해결할 수 있었다.



```C#
Bitmap EditableImg = new Bitmap(원본 이미지);
...
원본 이미지 = EditableImg;
```

