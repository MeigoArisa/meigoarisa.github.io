---
layout: post
title: OpenCVSharp Mat 구조체 행렬데이터에 접근하기
categories: OpenCVSharp
comments: true
---

**Mat**  구조체의 행렬 데이터에 직접 접근하여 수정할 수 있습니다.



At  방식으로 지정된 배열 요소에 값을 반환합니다.

Item0, Item1, Item2에 (255 - Matvec3b)

색상 반전 연산을 하여 지정된 배열에 다시 값을 저장합니다.

<br>

```c#
private void AtVec3b(Mat image)
{
	for (int i = 0; i < image.Rows; i++)
	{
		for (int j = 0; j < image.Cols; j++)
		{
			var Matvec3b = image.At<Vec3b>(i, j);
			Matvec3b.Item0 = (byte)(255 - Matvec3b.Item0);
			Matvec3b.Item1 = (byte)(255 - Matvec3b.Item1);
			Matvec3b.Item2 = (byte)(255 - Matvec3b.Item2);
			image.Set<Vec3b>(i, j, Matvec3b);
		}
	}
}
```
<br>

C++ 처럼 포인터를 이용하여 **Mat** 구조체 데이터에 접근할 수 있습니다.

```C#
private unsafe void UsingData(Mat image)
{
    for (int i = 0; i < image.Rows; i ++)
    {
        for (int j = 0; j < image.Cols; j++)
        {
            byte r, g, b;

            // byte *data = (byte *)image.Data.ToPointer();
            byte* data = (byte*)image.DataPointer;

            b = data[i * image.Step() + j * image.ElemSize() + 0];
            g = data[i * image.Step() + j * image.ElemSize() + 1];
            r = data[i * image.Step() + j * image.ElemSize() + 2];

            data[i * image.Step() + j * image.ElemSize() + 0] = (byte)(255 - b);
            data[i * image.Step() + j * image.ElemSize() + 1] = (byte)(255 - g);
            data[i * image.Step() + j * image.ElemSize() + 2] = (byte)(255 - r);
        }
    }
}
```

<br>

Mat.ForEachAs(type) 로 **Mat** 구조체 데이터에도 접근할 수 있다.

```c#
private unsafe void ForEachAsVec3b(Mat image)
{
	image.ForEachAsVec3b((ptrValue, ptrPosition) =>
	{
		ptrValue->Item0 = (byte)(255 - ptrValue->Item0);
		ptrValue->Item1 = (byte)(255 - ptrValue->Item1);
		ptrValue->Item2 = (byte)(255 - ptrValue->Item2);
	});
}
```

