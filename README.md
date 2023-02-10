# AOS UI Reference
---

1. <a href = "#1">ConstraintLayout</a></br>
   1.1 GuideLine
2. <a href = "#2">dataBinding && XML</a></br>
   2.1 @{} 표현 정리</br>
   2.2 View.GONE, View.VISIBLE</br>
   2.3 true, false</br>
   
<a href = "#ref">참고링크</a></br>  

---

><a id = "1">1. ConstraintLayout</a>

1.1 GuideLine</br>
-뷰의 탑에서 33% 지점에 투명 가이드라인을 만든다.
```xml
    <androidx.constraintlayout.widget.Guideline
        android:id="@+id/guideline"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:orientation="horizontal"
        app:layout_constraintGuide_percent="0.33" />
```
><a id = "2">2. dataBinding && XML</a>

2.1 @{} 표현 정리</br>


---
><a id = "ref">참고 링크</a>

액션바 뒤로가기 버튼</br>
https://programmingworld1.tistory.com/15</br>

Status bar 색상 변경</br>
https://origogi.github.io/android/dark-mode/

커스텀다이얼로그 데이터 바인딩</br>
https://github.com/HYUNJUNEPARK/BasicAOSApp/blob/main/1_BMICalculator/app/src/main/java/com/june/androidApp/bmicalculator/ResultDialog.kt
