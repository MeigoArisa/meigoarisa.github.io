---
layout: post
title: OpenCVSharp Split Merge
categories: OpenCVSharp
comments: true
---



```C#
public void Merge_method()
{
    Mat OriginalImage = new Mat("../../opencv.png", ImreadModes.AnyColor);
    Mat FillMatrix = Mat.Zeros(OriginalImage.Size(), MatType.CV_8UC1);

    Mat[] rgb;

    Cv2.Split(OriginalImage, out rgb);

    Mat[] r = { FillMatrix, FillMatrix, rgb[2] };
    Mat[] g = { FillMatrix, rgb[1], FillMatrix };
    Mat[] b = { rgb[0], FillMatrix, FillMatrix };

    Mat merge = new Mat();

    Cv2.Merge(r, merge);
    Cv2.ImShow("r", merge);

    Cv2.Merge(g, merge);
    Cv2.ImShow("g", merge);

    Cv2.Merge(b, merge);
    Cv2.ImShow("b", merge);

    Cv2.Merge(rgb, merge);

    Cv2.ImShow("remerge", merge);
    Cv2.WaitKey();
}

```



색의 삼원소, 채널을 분리하고 다시 각 채널을 합치는 소스코드입니다.

<br>

```C#
Cv2.Split(Mat, out Mat[]);
```

이미지 원본을 채널 3개로 나눕니다.

Mat 배열에 0번에 파란색, 1번에 초록색, 2번에 빨간색을 담습니다.

<br>

<br>

```C#
Cv2.Merge(Mat[], Mat);
```

채널 3개로 나뉘어진 Mat 배열을 하나의 이미지로 합칩니다.



결과:

![Image Alt ]({{site.url}}/images/Split/Blue.PNG ){: width="80%" height="80%"}

![Image Alt ]({{site.url}}/images/Split/Green.PNG ){: width="80%" height="80%"}

![Image Alt ]({{site.url}}/images/Split/Red.png ){: width="80%" height="80%"}

![Image Alt ]({{site.url}}/images/Split/remerge.PNG ){: width="80%" height="80%"}

<br>