스마트 모바일 프로그래밍 약쏙 최종 보고서
===================================
목차   
-----


### 1.소개
>#### 1-1 개발배경
>#### 1-2 사용한 기능
>#### 1-3 기대효과

### 2. 기능 구현
>#### 2-1 사용자 생성
>>##### 2-1-1 회원가입
>>##### 2-1-2 로그인
>>##### 2-1-3 아이디 찾기 및 비밀번호 재설정
>>##### 2-1-4 구글 로그인
>>##### 2-1-5 회원정보 수정
>#### 2-2 약국 찾기
>>##### 2-1-1 위치 관련 퍼미션 허용과 GPS 활성화


<hr/>

## 1. 소개

### 1-1 개발배경

### 1-2 사용한 기능

### 1-3 기대효과

<hr/>

## 2. 기능 구현

### 2-1 사용자 생성
회원가입과 로그인 및 로그아웃을 위해 데이터를 저장해 놓을 Firebase가 필요하다.
>#### 2-1-1 회원가입
Firebase에 개발을 진행할 프로젝트를 등록한다. Google 로그인을 사용할 예정이므로 SHA-1 정보도 저장해준다.   
이후 Firebase Android 구성 파일(google-services.json)을 다운로드하여 등록한 프로젝트에 추가한다.   
앱에서 Firebase 제품을 사용할 수 있도록 google-services 플러그인을 Gradle 파일에 추가힌다.
<pre>
<code>
dependencies {
    classpath 'com.google.gms:google-services:4.2.0'  // Google Services plugin
  }
}
</code>
</pre>
모듈(앱 수준) Gradle 파일(일반적으로 app/build.gradle)에서 다음 줄을 파일 하단에 추가한다.
<pre>
<code>
apply plugin: 'com.android.application'

android {
  // ...
}
apply plugin: 'com.google.gms.google-services'  // Google Play services Gradle plugin
</pre>
모듈(앱 수준) Gradle 파일(일반적으로 app/build.gradle)에서 핵심 Firebase SDK의 종속 항목을 추가한다.
<pre>
<code>
dependencies {
 implementation 'com.google.firebase:firebase-core:17.0.0'
 }
</code>
</pre>
