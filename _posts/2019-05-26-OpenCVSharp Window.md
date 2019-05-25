---
layout: post
title: OpenCVSharp Window
categories: OpenCVSharp
---

**Mat** WindowImage = new **Mat**("./Resource.jpg", ImreadModes.AnyColor);

이미지를 담고있는 Mat 구조체를 선언합니다.

**Window** OpenCVWindow = new **Window**("OpenCVWindow", WindowImage); 



new **Window**("윈도우 이름", Mat); 

OpenCVSharp 네임스페이스에 있는 Window클래스 객체를 생성합니다.



**Debug**.WriteLine(**Cv2**.WaitKey());

특정 키를 대기할 때 까지 기다리며 입력받은 키를 디버깅 창에 출력합니다.