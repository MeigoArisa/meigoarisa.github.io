---
layout: post
title: OpenCVSharp Drawing
categories: OpenCVSharp
comments: true
---



```C#
public void Drawing_method()
{
    Mat OriginalImage = new Mat("../../opencv.png", ImreadModes.AnyColor);

    Cv2.Line(OriginalImage, new Point(10,10),new Point(630,10), Scalar.Blue);
    Cv2.Circle(OriginalImage,new Point(100,100),40, Scalar.Blue);
    Cv2.Rectangle(OriginalImage,new Rect(20,20,40,40),Scalar.Red);
    Cv2.Ellipse(OriginalImage,new RotatedRect(new Point2f(120,120),new Size2f(200,100),10),Scalar.Yellow);
    Cv2.PutText(OriginalImage,"OpenCVSharp",new Point(600,600),HersheyFonts.Italic,5,Scalar.Black);

    Cv2.ImShow("draw", OriginalImage);
    Cv2.WaitKey();
}
```



Mat 이미지에 선, 도형, 글을 넣는 방법입니다.

<br>

```C#
Cv2.Line(OriginalImage, new Point(10,10),new Point(630,10), Scalar.Blue);
```

선을 그립니다.

<br>

```C#
 Cv2.Circle(OriginalImage,new Point(100,100),40, Scalar.Blue);
```

원을 그립니다.

<br>

```C#
Cv2.Rectangle(OriginalImage,new Rect(20,20,40,40),Scalar.Red);
```

사각형을 그립니다.

<br>

```C#
Cv2.Ellipse(OriginalImage,new RotatedRect(new Point2f(120,120),new Size2f(200,100),10),Scalar.Yellow);
```

타원형을 그립니다.

<br>

```C#
 Cv2.PutText(OriginalImage,"OpenCVSharp",new Point(600,600),HersheyFonts.Italic,5,Scalar.Black);
```

텍스트를 삽입합니다.

영어 이외에 안되는 언어가 많으며 안되는 언어들은 Bitmap으로 변환시켜 Graphics로 삽입하여야합니다.

<br>



결과:

![Image Alt ]({{site.url}}/images/draw/draw.PNG ){: width="80%" height="80%"}

<br>