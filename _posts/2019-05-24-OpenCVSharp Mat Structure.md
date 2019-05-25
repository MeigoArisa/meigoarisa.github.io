---
layout: post
title: OpenCVSharp Mat structure
categories: OpenCVSharp
---



**Mat**구조체는 OpenCVSharp 에서 가장 기본이 되는 데이터 타입의 행렬 구조체이다.

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

