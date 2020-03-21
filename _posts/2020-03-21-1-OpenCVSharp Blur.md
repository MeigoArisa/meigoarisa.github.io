---
layout: post
title: OpenCVSharp blur
categories: OpenCVSharp
---

> **Blur**



`Image Blurring`

이웃 화소들을 평균화 합니다.

 다른 말로 `low pass filter` 라고 부릅니다.



```C#
public void Blur_Example()
{
	using Mat WindowImage = new Mat("./Resource.png", ImreadModes.AnyColor);
	using Mat blurImage = new Mat();
	using Mat box_filter = new Mat();
	using Mat median_blur = new Mat();
	using Mat gaussian_blur = new Mat();
	using Mat bilateral_filter = new Mat();
    
	Cv2.Blur(WindowImage, blurImage, new Size(9, 9),new Point(-1,-1));
	Cv2.BoxFilter(WindowImage, box_filter, WindowImage.Type(),new Size(5,5));
	Cv2.MedianBlur(WindowImage, median_blur, 5);
	Cv2.GaussianBlur(WindowImage, gaussian_blur, new Size(9, 9), 3);
	Cv2.BilateralFilter(WindowImage, bilateral_filter, 10,50,50);
	

	using var Blur = new Window("Blur", WindowMode.AutoSize, blurImage);
	using var BoxFilter = new Window("BoxFilter", WindowMode.AutoSize, box_filter);
	using var MedianBlur = new Window("MedianBlur", WindowMode.AutoSize, median_blur);
	using var GaussianBlur = new Window("GaussianBlur", WindowMode.AutoSize, gaussian_blur);
	using var BilateralFilter = new Window("BilateralFilter", WindowMode.AutoSize, bilateral_filter);
	
	Cv2.WaitKey();
}
```



`Averaging Blur`

Box 형태의 커널을 이미지에 적용하여 평균값을 Box 중심점에 적용합니다.

```C#
Cv2.Blur(WindowImage, blurImage, new Size(9, 9),new Point(-1,-1));
```

 ![Image Alt ]({{site.url}}/images/2020-03-21-1/Blur.png ){:width="80%" height="80%" }



BoxFilter 로도 사용할 수 있습니다.

```C#
Cv2.BoxFilter(WindowImage, box_filter, WindowImage.Type(),new Size(5,5));
```

 ![Image Alt ]({{site.url}}/images/2020-03-21-1/BoxFilter.png ){:width="80%" height="80%" }



`MedianBlur`

커널 영역 내의 중앙값으로 픽셀을 대체하는 중앙값 블러 입니다.

전체 이미지를 일정한 작은 영역으로 나누고 영역의 모든 화소를 크기 순으로 정렬한 뒤 중간값을 찾습니다. 그 영역을 가운데 화소를 찾아낸 중간값으로 대체합니다.

정상적인 데이터를 이용하여 노이즈를 덮습니다.

```C#
Cv2.MedianBlur(WindowImage, median_blur, 5);
```

 ![Image Alt ]({{site.url}}/images/2020-03-21-1/MedianBlur.png ){:width="80%" height="80%" }



`GaussianBlur`

현재 픽셀값과 주변 이웃 픽셀값들의 가중 평균을 이용해서 현재 픽셀의 값을 대체합니다..

현재 픽셀에서 가까울수록 더 큰 가중치를 갖게되고 멀수록 더 작은 가중치를 갖게됩니다.

가우시안 필터는 이미지는 공간적으로 천천히 변하기 때문에 가까이 있는 픽셀들은 비슷한 값들을 갖는다는 사실에 기반하여 만들어졌고 노이즈 값은 상대적으로 이웃 픽셀들 값과 상관성이 작기 때문에 이웃 픽셀값들의 가중 평균의 방식으로 완화시킬 수 있습니다.

```c#
Cv2.GaussianBlur(WindowImage, gaussian_blur, new Size(9, 9), 3);
```

 ![Image Alt ]({{site.url}}/images/2020-03-21-1/GaussianBlur.png ){:width="80%" height="80%" }



`BilateralFilter`

경계를 보존하면서 선형으로 처리되지 않고, 선명도를 증가시키고, 가장자리와 노이즈를 줄여주어 부드러운 영상이 만들어지게 됩니다.

변수의 값이 클수록 픽셀에 미치는 영향이 커져서 가중치가 커지게 됩니다.

```c#
Cv2.BilateralFilter(WindowImage, bilateral_filter, 10,50,50);
```

 ![Image Alt ]({{site.url}}/images/2020-03-21-1/BilateralFilter.png ){:width="80%" height="80%" }