---
layout: post
title: OpenCVSharp Camera 입력 받기
categories: OpenCVSharp

---



```c#
var capture = new VideoCapture(CaptureDevice.Any, index: 0);
```

VideoCapture 클래스 객체를 선언합니다. <br>

VideoCapture(CaptureDevice,캠 index) 로 선언합니다.<br>

VideoCapture(string IP카메라 Link) 를 입력하면 아이피 카메라의 영상을 불러올 수 있습니다.<br>



```C#
    VideoCapture capture;
	private Thread camera;
	bool isCameraRunning = false;
	private void CaptureCamera()
    {
        camera = new Thread(new ThreadStart(CaptureCameraCallback));
        camera.Start();
    }

    private void CaptureCameraCallback()
    {
        using (var capture = new VideoCapture(CaptureDevice.Any, index: 0))
        {
            using Mat frame = new Mat();
            while (isCameraRunning == true)
            {
                var interval = (int)(1000 / capture.Fps);
                capture.Read(frame);
                Cv2.ImShow("Cam", frame);
                Debug.WriteLine(interval);
            }
        }

    }
    private void Camera_Start()
    {
        CaptureCamera();
        isCameraRunning = true;

        capture.Release();
        isCameraRunning = false;
    }
    private void Camera_Stop()
    {
        capture.Release();
        isCameraRunning = false;
    }
```
전체 소스코드 <br>



<br>

```C#
using (var capture = new VideoCapture(CaptureDevice.Any, index: 0))
        {
            using Mat frame = new Mat(); // 8.0 문법입니다.
            while (isCameraRunning == true)
            {
                var interval = (int)(1000 / capture.Fps); 
                //현재 영상의 fps를 계산합니다.
                
                capture.Read(frame);
                //영상을 frame 에 담습니다. 프레임은 지속적으로 교체됩니다.
                
                Cv2.ImShow("Cam", frame);
                //영상을 "Cam" 윈도우 창에 계속 출력합니다.
                
                Debug.WriteLine(interval);
                //프레임을 Debug 로그에 계속 출력합니다.
            }
        }
```



팁: IDisposable 인터페이스를 이용하여 관리되는 Mat, VideoCapture 개체를 꼭 삭제하도록 하자.