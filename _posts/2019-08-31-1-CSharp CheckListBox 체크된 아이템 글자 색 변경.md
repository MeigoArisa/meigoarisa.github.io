---
layout: post
title: C# CheckedListBox 체크된 아이템 글자 색 변경
categories: C#

---

## CheckedListBox

Winform에 있는 CheckedListBox 라는 컨트롤이 있다.

이 컨트롤을 사용하면서 큰 불편함을 한가지 느꼈다.



바로 각 아이템 별로 글자색, 배경색, 폰트 등을 바꿀 수가 없었다.

이 문제점을 해결할 수 있는 방법을 찾아내었다.



일단 유저 커스텀 컨트롤을 추가한다.

![Image Alt ]({{site.url}}/images/2019-08-31-1/1.jpg ){:}

그러고 난 뒤 커스텀 컨트롤에 CheckedListBox를 상속한다.
그리고 아래와 같은 코드를 추가한다.

```C#
protected override void OnDrawItem(DrawItemEventArgs e)
{
    DrawItemEventArgs e2 =
        new DrawItemEventArgs(
        e.Graphics, 
        e.Font, 
        new Rectangle(e.Bounds.Location, e.Bounds.Size),
        e.Index, 
        e.State, 
        this.CheckedIndices.Contains(e.Index) ? Color.Red : Color.Black,
        e.BackColor
        );
    base.OnDrawItem(e2);
}
```

위와 같은 코드를 삽입 한 뒤 폼에 추가시켜서 사용한다.



체크 표시를 하면 빨간색으로 글자가 바뀌는 것을 볼 수 있다.

![Image Alt ]({{site.url}}/images/2019-08-31-1/2.jpg ){: }







원한다면 저 소스코드를 수정하여 배경색, 폰트도 바꿀 수 있다.

