# AOS UI Reference
---

1. <a href = "#1">ConstraintLayout</a></br>
   1.1 GuideLine
2. dataBinding && XML</br>
   <a href = "#2_1">2.1 @{ } 표현 정리</a></br>
   <a href = "#2_2">2.2 View.GONE, View.VISIBLE</a></br>
   <a href = "#2_3">2.3 true, false</a></br>
   <a href = "#2_4">2.4 Boolean 에 따른 다른 이벤트 지정</a></br>
   <a href = "#2_5">2.5 Null 일 때 데이터 대체</a></br>
   
<a href = "#ref">참고링크</a></br>  

---
<br></br>
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

<br></br>
>2. dataBinding && XML</br>

<a id = "2_1">2.1 @{ } 표현 정리</a>
```xml

//2.1.1. 클릭 이벤트 : 파라미터가 필요없는 메서드
android:onClick="@{()->main.showDialog()}"

//"2.1.2. @{BooleanValue ? a : b}"
<variable
   name="BooleanValue"
   type="Boolean" />
-BooleanValue의 디폴트는 b 로 적용된다.
-BooleanValue가 true 라면 a 가, false 라면 b 가 적용된다.

//2.1.3 alpha 세팅
android:alpha="@{isFold ? 0.5f : 1.0f}"

//2.1.4 EditText의 Text를 onClick 함수 parameter로 가져오기
 <EditText
     android:id="@+id/search_text"
           
<ImageButton
   android:onClick="@{()->viewModel.onClickSearch(searchText.getText().toString())}"
```

<a id = "2_2">2.2 View.GONE, View.VISIBLE</a>
```xml
#Example
<import type="android.view.View"/>

#ex.1 visibility 관련 부정표현(Gone) 변수
<variable
   name="isGoneBiometricUI" 
   type="Boolean" />
   
#ex.2 visibility 관련 긍정표현(Visible) 변수  
<variable 
   name="isVisibleBiometricUI"
   type="Boolean" />   
   
#ex.1   
android:visibility="@{isGoneBiometricUI ? View.GONE : View.VISIBLE}
-isGoneBiometricUI 가 Activity에서 초기화 되지 않는다면, View.VISIBLE
-isGoneBiometricUI 가 true 라면 View.GONE, false 라면 View.VISIBLE

#ex.2
android:visibility="@{isVisibleBiometricUI? View.VISIBLE : View.GONE}"
-isVisibleBiometricUI 가 Activity에서 초기화 되지 않는다면, View.GONE
-isVisibleBiometricUI 가 true 라면 View.VISIBLE, false 라면 View.GONE
```

<a id = "2_3">2.3 true, false</a></br>
```xml
#ex.1 enabled 관련 부정표현(Unable) 변수
<variable
   name="isUnableBiometric"
   type="Boolean" /> 
   
#ex.1
android:enabled="@{isUnableBiometric? false : true}"
-isUnableBiometric 가 Activity에서 초기화 되지 않는다면, true
-isUnableBiometric 가 true 라면 false, false 라면 true
```

<a id = "2_4">2.4 Boolean 에 따른 다른 이벤트 지정</a></br>
```xml
android:onClick="@{()-> aBoolean ? viewmodel.methodOne() : viewmodel.methodTwo()}"
```

<a id = "2_5">2.5 Null 일 때 데이터 대체</a></br>
```xml
android:text='@{accountEntity.userId ?? "-"}'
```



<br></br>
---
><a id = "ref">참고 링크</a>

액션바 뒤로가기 버튼</br>
https://programmingworld1.tistory.com/15</br>

Status bar 색상 변경</br>
https://origogi.github.io/android/dark-mode/

커스텀다이얼로그 데이터 바인딩</br>
https://github.com/HYUNJUNEPARK/BasicAOSApp/blob/main/1_BMICalculator/app/src/main/java/com/june/androidApp/bmicalculator/ResultDialog.kt

Databinding</br>
https://lunadev.tistory.com/30

