---
layout: post
title: OpenCVSharp Window
categories: OpenCVSharp
---



```c#
Mat WindowImage = new Mat("./Resource.jpg", ImreadModes.AnyColor);  
```

이미지를 담고있는 Mat 구조체를 선언합니다.  

<br/>

```c#
Window OpenCVWindow = new Window("OpenCVWindow", WindowImage,);   
```

```c#
new Window("윈도우 이름", Mat);   
```

OpenCVSharp 네임스페이스에 있는 Window클래스 객체를 생성합니다.  

<br/>

```c#
new Window("OpenCVWindow", WindowMode.AutoSize,WindowImage);
```

WindowMode Flag를 설정하여 창의 모드를 설정할 수 있습니다.

- `WindowMode.AutoSize` : 이미지의 크기로 출력, 윈도우 창 크기 조정 불가 
- `WindowMode.OpenGL` : OpenGL을 지원하는 윈도우 창 
- `WindowMode.Normal` : 상태 표시줄 및 도구 모음이 없는 윈도우 창 
- `WindowMode.Fullscreen` : 전체 화면 
- `WindowMode.FreeRatio` : 가로 세로 비율 수정 
- `WindowMode.KeepRatio` : 이미지 비율 유지 

 <br/>

```c#
Debug.WriteLine(Cv2.WaitKey());  
```

특정 키를 대기할 때 까지 기다리며 입력받은 키를 디버깅 창에 출력합니다.  

