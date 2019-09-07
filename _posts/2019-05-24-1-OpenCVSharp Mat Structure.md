---
layout: post
title: OpenCVSharp Mat structure
categories: OpenCVSharp
---



**Mat**구조체는 OpenCVSharp 에서 가장 기본이 되는 데이터 타입의 행렬 구조체이다.

*Mat* 클래스는 n-차원의 단일-채널 혹은 멀티-채널 값numerical을 표현한다. 

실수나 복소수로 구성된 벡터 혹은 매트릭스, 그레이 스케일 이나 칼라 이미지, 3차원 부피voxel volumes, 벡터 필드vector fields, 점의 집합point clouds, 텐서tensors, 히스토그램(고차원 히스트그램의 경우 *SparseMat*를 사용하는 것이 더 효율적이지만)을 사용할 수 있다.

```c#
 Mat(IntPtr ptr);  
 Mat(Mat m, Rect roi);   
 Mat(Mat m, params Range[] ranges);   
 Mat(Size size, MatType type);   
 Mat(IEnumerable sizes, MatType type);   
 Mat(string fileName, ImreadModes flags = [ImreadModes.Color]);   
 Mat(Size size, MatType type, Scalar s);   
 Mat(Mat m, Range rowRange, Range? colRange = null);   
 Mat(IEnumerable sizes, MatType type, Scalar s);   
 Mat(int rows, int cols, MatType type);   
 Mat(int rows, int cols, MatType type, Scalar s);   
 Mat(IEnumerable sizes, MatType type, IntPtr data, IEnumerable steps = null);   
 Mat(IEnumerable sizes, MatType type, Array data, IEnumerable steps = null);   
 Mat(int rows, int cols, MatType type, IntPtr data, long step = 0);   
 Mat(int rows, int cols, MatType type, Array data, long step = 0);   
 protected Mat(Mat m);  
```

