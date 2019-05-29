---
layout: post
title: A Graphics object cannot be created from an image that has an indexed pixel format.
categories: C#

---

## A Graphics object cannot be created from an image that has an indexed pixel format.

System.Exception

인덱싱된 픽셀 형식이 들어 있는 이미지로는 Graphics 개체를 만들 수 없습니다.  

<br>

<br>

비트맵 파일을 Mat으로 변환해서 그레이 스케일, 이진화 등의 연산 후 다시 Bitmap으로 변환했고

Graphics 로 다시 그리려 하니 발생하였다.<br>

이 문제는 동일한 크기의 빈 비트 맵을 만들고, 올바른 비트 맵을 만든 후 비트 맵에 draw를하면 해결할 수 있었다.



```C#
Bitmap EditableImg = new Bitmap(원본 이미지);
...
원본 이미지 = EditableImg;
```



인덱싱 된 이미지는 팔레트가있는 이미지라고한다.<br>

```C#
P[] = { RGB, RGB, RGB, RGB, RGB }

P[0] P[3] P[0] P[2] P[1]

P[1] P[2] P[4] P[1] P[0]

P[2] P[3] P[1] P[2] P[2]

P[0] P[3] P[2] P[3] P[1]

P[4] P[3] P[0] P[2] P[1]
```

인덱싱 된 색상 표는 색상 팔레트를 배열로 정의한 다음 각 픽셀 좌표에서 색상을 정의하는 대신 해당 색인을 참조하여 효과적으로 메모리와 디스크 공간을 절약하는데...

 GDI+ 가 인덱싱 된 이미지의 그리기를 지원하지 않으므로 생기는 오류라고 합니다.

 인덱싱되지 않은 이미지에 인덱싱 된 이미지를 그린 다음 인덱싱되지 않은 이미지에 텍스트를 그립니다.