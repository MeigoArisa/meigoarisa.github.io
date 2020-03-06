---
layout: post
title: OpenCVSharp BackgroundSubtractor
categories: OpenCVSharp
---

> **BackgroundSubtractor**



배경제거알고리즘은 많은 비전기반 전처리 단계에서 주로 사용된다.

```c#
public void BackgroundSubtractor_Example()
{
	VideoCapture capture = new VideoCapture(0);
	using var MOG2 = BackgroundSubtractorMOG2.Create();
    using var MOG = BackgroundSubtractorMOG.Create();
    using var GMG = BackgroundSubtractorGMG.Create();
    using var KNN = BackgroundSubtractorKNN.Create();

    using Mat frame = new Mat();
    using Mat MOG2remove = new Mat();
    using Mat MOGremove = new Mat();
    using Mat GMG2remove = new Mat();
    using Mat KNNremove = new Mat();

    Window win_MOG2 = new Window("MOG2");
    Window win_GMG = new Window("GMG");
    Window win_MOG = new Window("MOG");
    Window win_KNN = new Window("KNN");

    while (Cv2.WaitKey(1) < 0)
    {
        capture.Read(frame);
        MOG2.Apply(frame, MOG2remove);
        MOG.Apply(frame, MOGremove);
        GMG.Apply(frame, GMG2remove);
        KNN.Apply(frame, KNNremove);

        win_MOG2.ShowImage(MOG2remove);
        win_GMG.ShowImage(MOGremove);
        win_MOG.ShowImage(GMG2remove);
        win_KNN.ShowImage(KNNremove);
    }
}
```




BackgroundSubtractorMOG

이는 가우시안 혼합을 기반으로한 전경또는 배경을 분할하는 알고리즘이다.

Mixture에 대한 가중치는 색상이 위치에 머무는 시간의 비율을 나타낸다.



BackgroundSubtractorMOG2

이는 가우시안 혼합을 기반으로한 전경또는 배경을 분할하는 알고리즘이다.

이전 MOG 알고리즘보다 조명 변화로 인한 다양한 장면에 대해서 더 나은 적응력을 보이는 알고리즘이다.



BackgroundSubtractorGMG

이는 처음의 몇(120개) 프레임을 배경 모델링하는데 사용한다. 

이는 베이지안 추론을 사용하여 전경 객체일 확률을 구하는 확률적 전경 분할 알고리즘에 이용된다.

이 추측은 적응적이다. 

변덕스러운 조명에 적응하기 위해 새로운 관측들은 기존의 관측보다 더 높은 가중치를 가진다. 

`closing`과 `opening`과 같은 몇몇 형태학적인필터링으로 원하지 않는 노이즈를 제거할 수 있다. 

처음 몇 프레임동안은 검정 창을 보게 된다.



BackgroundSubtractorKNN

`BackgroundSubtractorMOG2` 및 `BackgroundSubtractorKNN` 은 서로 다른 두 개의 백그라운드 뺄셈 알고리즘을 구현 한 것이다. 

전경 픽셀 수가 적은 경우 매우 효율적.

하지만 `BackgroundSubtractorKNN` 알고리즘에는 `setBackgroundRatio` 가 필요하지 않다.