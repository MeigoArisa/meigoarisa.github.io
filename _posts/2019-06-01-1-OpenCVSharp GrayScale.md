---
layout: post
title: OpenCVSharp GrayScale
categories: OpenCVSharp
comments: true
---

```C#
public Mat GrayScale(){
    Mat OriginalImage = new Mat(imgsource,imreadmodes);
    Mat GrayImage = new Mat();
	Cv2.CvtColor(OriginalImage, GrayImage, ColorConversionCodes.RGB2GRAY);
    return GrayImage;
}
```

Cv2.CvtColor: 한 색상 공간에서 다른 색상 공간으로 이미지를 변환합니다.



ColorConversionCodes.RGB2GRAY 를 이용하여 RGB를 Gray로변환합니다.



ColorConversionCodes Enum으로 어떤 이미지에서 다른 색상 공간으로 변환할지 선택합니다.

139개의 변환식을 지원합니다.



BGR2BGRA = 0<br>
        RGB2RGBA = 0<br>
        BGRA2BGR = 1<br>
        RGBA2RGB = 1<br>
        BGR2RGBA = 2<br>
        RGB2BGRA = 2<br>
        RGBA2BGR = 3<br>
        BGRA2RGB = 3<br>
        BGR2RGB = 4<br>
        RGB2BGR = 4<br>
        BGRA2RGBA = 5<br>
        RGBA2BGRA = 5<br>
        BGR2GRAY = 6<br>
        RGB2GRAY = 7<br>
        GRAY2BGR = 8<br>
        GRAY2RGB = 8<br>
        GRAY2BGRA = 9<br>
        GRAY2RGBA = 9<br>
        BGRA2GRAY = 10<br>
        RGBA2GRAY = 11<br>
        BGR2BGR565 = 12<br>
        RGB2BGR565 = 13<br>
        BGR5652BGR = 14<br>
        BGR5652RGB = 15<br>
        BGRA2BGR565 = 16<br>
        RGBA2BGR565 = 17<br>
        BGR5652BGRA = 18<br>
        BGR5652RGBA = 19<br>
        GRAY2BGR565 = 20<br>
        BGR5652GRAY = 21<br>
        BGR2BGR555 = 22<br>
        RGB2BGR555 = 23<br>
        BGR5552BGR = 24<br>
        BGR5552RGB = 25<br>
        BGRA2BGR555 = 26<br>
        RGBA2BGR555 = 27<br>
        BGR5552BGRA = 28<br>
        BGR5552RGBA = 29<br>
        GRAY2BGR555 = 30<br>
        BGR5552GRAY = 31<br>
        BGR2XYZ = 32<br>
        RGB2XYZ = 33<br>
        XYZ2BGR = 34<br>
        XYZ2RGB = 35<br>
        BGR2YCrCb = 36<br>
        RGB2YCrCb = 37<br>
        YCrCb2BGR = 38<br>
        YCrCb2RGB = 39<br>
        BGR2HSV = 40<br>
        RGB2HSV = 41<br>
        BGR2Lab = 44<br>
        RGB2Lab = 45<br>
        BayerBG2BGR = 46<br>
        BayerRG2RGB = 46<br>
        BayerGB2BGR = 47<br>
        BayerGR2RGB = 47<br>
        BayerRG2BGR = 48<br>
        BayerBG2RGB = 48<br>
        BayerGR2BGR = 49<br>
        BayerGB2RGB = 49<br>
        BGR2Luv = 50<br>
        RGB2Luv = 51<br>
        BGR2HLS = 52<br>
        RGB2HLS = 53<br>
        HSV2BGR = 54<br>
        HSV2RGB = 55<br>
        Lab2BGR = 56<br>
        Lab2RGB = 57<br>
        Luv2BGR = 58<br>
        Luv2RGB = 59<br>
        HLS2BGR = 60<br>
        HLS2RGB = 61<br>
        BayerBG2BGR_VNG = 62<br>
        BayerRG2RGB_VNG = 62<br>
        BayerGB2BGR_VNG = 63<br>
        BayerGR2RGB_VNG = 63<br>
        BayerRG2BGR_VNG = 64<br>
        BayerBG2RGB_VNG = 64<br>
        BayerGR2BGR_VNG = 65<br>
        BayerGB2RGB_VNG = 65<br>
        BGR2HSV_FULL = 66<br>
        RGB2HSV_FULL = 67<br>
        BGR2HLS_FULL = 68<br>
        RGB2HLS_FULL = 69<br>
        HSV2BGR_FULL = 70<br>
        HSV2RGB_FULL = 71<br>
        HLS2BGR_FULL = 72<br>
        HLS2RGB_FULL = 73<br>
        LBGR2Lab = 74<br>
        LRGB2Lab = 75<br>
        LBGR2Luv = 76<br>
        LRGB2Luv = 77<br>
        Lab2LBGR = 78<br>
        Lab2LRGB = 79<br>
        Luv2LBGR = 80<br>
        Luv2LRGB = 81<br>
        BGR2YUV = 82<br>
        RGB2YUV = 83<br>
        YUV2BGR = 84<br>
        YUV2RGB = 85<br>
        BayerBG2GRAY = 86<br>
        BayerGB2GRAY = 87<br>
        BayerRG2GRAY = 88<br>
        BayerGR2GRAY = 89<br>
        YUV2RGB_NV12 = 90<br>
        YUV2BGR_NV12 = 91<br>
        YUV2RGB_NV21 = 92<br>
        YUV420sp2RGB = 92<br>
        YUV2BGR_NV21 = 93<br>
        YUV420sp2BGR = 93<br>
        YUV2RGBA_NV12 = 94<br>
        YUV2BGRA_NV12 = 95<br>
        YUV2RGBA_NV21 = 96<br>
        YUV420sp2RGBA = 96<br>
        YUV2BGRA_NV21 = 97<br>
        YUV420sp2BGRA = 97<br>
        YUV2RGB_YV12 = 98<br>
        YUV420p2RGB = 98<br>
        YUV2BGR_YV12 = 99<br>
        YUV420p2BGR = 99<br>
        YUV2RGB_IYUV = 100<br>
        YUV2RGB_I420 = 100<br>
        YUV2BGR_IYUV = 101<br>
        YUV2BGR_I420 = 101<br>
        YUV2RGBA_YV12 = 102<br>
        YUV420p2RGBA = 102<br>
        YUV2BGRA_YV12 = 103<br>
        YUV420p2BGRA = 103<br>
        YUV2RGBA_IYUV = 104<br>
        YUV2RGBA_I420 = 104<br>
        YUV2BGRA_IYUV = 105<br>
        YUV2BGRA_I420 = 105<br>
        YUV2GRAY_420 = 106<br>
        YUV2GRAY_NV21 = 106<br>
        YUV2GRAY_NV12 = 106<br>
        YUV2GRAY_YV12 = 106<br>
        YUV2GRAY_IYUV = 106<br>
        YUV2GRAY_I420 = 106<br>
        YUV420sp2GRAY = 106<br>
        YUV420p2GRAY = 106<br>
        YUV2RGB_UYVY = 107<br>
        YUV2RGB_Y422 = 107<br>
        YUV2RGB_UYNV = 107<br>
        YUV2BGR_UYVY = 108<br>
        YUV2BGR_Y422 = 108<br>
        YUV2BGR_UYNV = 108<br>
        YUV2RGBA_UYVY = 111<br>
        YUV2RGBA_Y422 = 111<br>
        YUV2RGBA_UYNV = 111<br>
        YUV2BGRA_UYVY = 112<br>
        YUV2BGRA_Y422 = 112<br>
        YUV2BGRA_UYNV = 112<br>
        YUV2RGB_YUY2 = 115<br>
        YUV2RGB_YUYV = 115<br>
        YUV2RGB_YUNV = 115<br>
        YUV2BGR_YUY2 = 116<br>
        YUV2BGR_YUYV = 116<br>
        YUV2BGR_YUNV = 116<br>
        YUV2RGB_YVYU = 117<br>
        YUV2BGR_YVYU = 118<br>
        YUV2RGBA_YUY2 = 119<br>
        YUV2RGBA_YUYV = 119<br>
        YUV2RGBA_YUNV = 119<br>
        YUV2BGRA_YUY2 = 120<br>
        YUV2BGRA_YUYV = 120<br>
        YUV2BGRA_YUNV = 120<br>
        YUV2RGBA_YVYU = 121<br>
        YUV2BGRA_YVYU = 122<br>
        YUV2GRAY_UYVY = 123<br>
        YUV2GRAY_Y422 = 123<br>
        YUV2GRAY_UYNV = 123<br>
        YUV2GRAY_YUY2 = 124<br>
        YUV2GRAY_YVYU = 124<br>
        YUV2GRAY_YUYV = 124<br>
        YUV2GRAY_YUNV = 124<br>
        RGBA2mRGBA = 125<br>
        mRGBA2RGBA = 126<br>
        RGB2YUV_I420 = 127<br>
        RGB2YUV_IYUV = 127<br>
        BGR2YUV_I420 = 128<br>
        BGR2YUV_IYUV = 128<br>
        RGBA2YUV_I420 = 129<br>
        RGBA2YUV_IYUV = 129<br>
        BGRA2YUV_I420 = 130<br>
        BGRA2YUV_IYUV = 130<br>
        RGB2YUV_YV12 = 131<br>
        BGR2YUV_YV12 = 132<br>
        RGBA2YUV_YV12 = 133<br>
        BGRA2YUV_YV12 = 134<br>
        BayerBG2BGR_EA = 135<br>
        BayerRG2RGB_EA = 135<br>
        BayerGB2BGR_EA = 136<br>
        BayerGR2RGB_EA = 136<br>
        BayerRG2BGR_EA = 137<br>
        BayerBG2RGB_EA = 137<br>
        BayerGR2BGR_EA = 138<br>
        BayerGB2RGB_EA = 138<br>
        COLORCVT_MAX = 139