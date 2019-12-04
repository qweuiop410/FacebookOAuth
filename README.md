### FacebookOAuth 입니다

<img src="https://postfiles.pstatic.net/MjAxOTEyMDRfOTkg/MDAxNTc1NDIyNTgxMjMz.QmWNvFRxqcgvJn8fsYgnVyGOP9IfdJIVDlSvdMtYgycg.bO3ajI67QfsrPpsSiDg4h8p1AQgnJQKAvF_TzXn1Ds4g.PNG.whdals410/fb_OAuth_1.png?type=w773" width="40%" height="30%" title="px(픽셀) 크기 설정" alt="IMG"></img>

<img src="https://postfiles.pstatic.net/MjAxOTEyMDRfMjc5/MDAxNTc1NDIyNTgxMjM2.Dy2dTfuKF0-3zCPUkG0YiOEGFfGfhFIyCIXD6AZVSgUg.LCvQhsexlmCBv8f-qqpWyT_Sc2hUvaNSxK-jDsQkX9Ug.PNG.whdals410/fb_OAuth_3.png?type=w773" width="40%" height="30%" title="px(픽셀) 크기 설정" alt="IMG"></img>

<img src="https://postfiles.pstatic.net/MjAxOTEyMDRfODQg/MDAxNTc1NDIyNTgxMjI3.LItF3IofIzPYKMMRyJblU7D1G0qQ3wpJXEZmOJn_3I0g.x43qWphLQdIEZ4x8TV0XTPj1VnGu1E_eT54muy9O-pQg.PNG.whdals410/fb_OAuth_2.png?type=w773" width="40%" height="30%" title="px(픽셀) 크기 설정" alt="IMG"></img>

+ 참고
  + [facebook for developers](https://developers.facebook.com/docs/facebook-login/android)

+ UI는 최소한으로 사용한 OAuth 예제입니다
	+ 로그인 버튼, 로그아웃 버튼,프로필사진으로 만구성했습니다.
+ 인터넷을 사용하기위해 아래코드를 'AndroidManifest.xml'에 추가
``` xml
<uses-permission android:name="android.permission.INTERNET" />
```

+ 제공되는 LoginButton .xml
```xml
<com.facebook.login.widget.LoginButton
        android:id="@+id/login_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center_horizontal"
        android:layout_marginTop="30dp"
        android:layout_marginBottom="30dp"
        />
```

+ 'build.gradle'에 추가
```java
dependencies {
...
implementation 'com.facebook.android:facebook-login:5.9.0'
...
}
```

+ 프로필 이미지 처리는 Fresco를 사용했습니다
``` xml
<com.facebook.drawee.view.SimpleDraweeView
        android:id="@+id/my_image_view"
        android:layout_width="130dp"
        android:layout_height="130dp"
        />
```
+ 'build.gradle'에 추가
``` java
dependencies {
...
implementation 'com.facebook.fresco:fresco:2.0.0'
...
}
```

+ 로그인 성공시 결과
``` json
{"id":"회원정보 아이디","name":"김종민","email":"uiop410@nate.com"}
```
+ 프로필 사진
  + http://graph.facebook.com/회원정보 아이디/picture?type=large 
+ 로그아웃 메세지
``` java
LoginManager.getInstance().logOut();
```

+ 로그인한 계정에서 앱 관리
   + 페이스북 :  설정 -> 앱 및 웹사이트
   
<img src="https://postfiles.pstatic.net/MjAxOTEyMDRfMTY4/MDAxNTc1NDIyNTgxMjIy.E-20HF76GNFXXDNmfGkQm19kYk4ErRskUCBdM-utE1Ug.OF11c_tA6eqg5yErMTMBn5ImHsz7DgZUf3xUA1-cs-wg.PNG.whdals410/fb_OAuth_4.png?type=w773" width="40%" height="30%" title="px(픽셀) 크기 설정" alt="IMG"></img>
