---
layout: post
title: OpenCVSharp Binarization
categories: OpenCVSharp
comments: true
---



```C#
public Mat Binarization_method()
        {
            Mat OriginalImage = new Mat("ImageLink",ImreadModes.AnyColor);
            Mat GrayImage = new Mat();
            Mat thresimg = new Mat();
            Cv2.CvtColor(OriginalImage, GrayImage, ColorConversionCodes.RGB2GRAY);
            Cv2.Threshold(GrayImage, thresimg, 100, 255, ThresholdTypes.Trunc);
            return GrayImage;
        }
```

이진화할 이미지를 선택한 후 Gray 이미지로 변환해줍니다.

또는 ImreadModes를 GrayScale로 선택하는 방법도 있습니다.

<br>

Cv2.Threshold(원본, 결과, 임계값, 최댓값, ThresholdTypes);

임계값은 100일 경우 100을 기준으로 100보다 이하면 0으로 100보다 이상이면 최댓값으로 변경합니다. 

ThresholdTypes에서 처리할 알고리즘을 선택합니다.

<br>

<br>

결과:

![Image Alt ]({{site.url}}/images/Binarization/Binari1.PNG )

![Image Alt ]({{site.url}}/images/Binarization/Binari2.PNG )

![Image Alt ]({{site.url}}/images/Binarization/Binari3.png )

![Image Alt ]({{site.url}}/images/Binarization/Binari4.PNG )

![Image Alt ]({{site.url}}/images/Binarization/Binari5.png )

![Image Alt ]({{site.url}}/images/Binarization/Binari6.PNG )

<br>