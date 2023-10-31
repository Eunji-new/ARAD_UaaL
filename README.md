
# AR로 즐기는 새로운 앱 테크 App

<h1 align="center"> <img src="arad_icon.png" width="300" height="300"  /> </h1>


# 📌프로젝트 소개
### 언제든지 원하는 곳에 AR을 만들며 포인트를 얻어가자! ([Download URL](https://play.google.com/store/apps/details?id=com.anyractive.arad_january))

* ARAD 앱은 유저의 참여에 대한 보상을 제공하는 앱입니다. <br> 
* 이벤트 AR 이미지가 생성된 곳에 촬영을 하면 포인트를 받을 수 있어요. <br>
* 유저들은 지급 받은 포인트로 상품권이랑 교환할 수 있습니다. <br> 
* 쿠팡 파트너스 및 업체의 AR 광고를 통해 보다 뛰어난 마케팅 사업을 진행할 수 있습니다. 
<br>
<br>

# 🔎사용 기술
<br>
<div align=center> 
  <img src="https://img.shields.io/badge/java-007396?style=for-the-badge&logo=java&logoColor=white"> 
  <img src="https://img.shields.io/badge/kotlin-232F3E?style=for-the-badge&logo=kotlin&logoColor=white"> 
  <img src="https://img.shields.io/badge/unity-FCC624?style=for-the-badge&logo=unity&logoColor=black"> 
<img src="https://img.shields.io/badge/csharp-512BD4?style=for-the-badge&logo=csharp&logoColor=#512BD4">
   <img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white">
  <img src="https://img.shields.io/badge/git-F05032?style=for-the-badge&logo=git&logoColor=white">

</div>
<br>

<br>

# 🎁서비스 아키텍쳐

![Alt text](image.png)
<br>

# 🖥서버 통신
* <b>REST API 라이브러리</b> : Retrofit2 사용 <br>

  <img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/30422454-1f48-4966-8476-889389b94ca5" width="50%" height="100%"/>


  ### 서버 ( 구글 클라우드 플랫폼 )<br>
  1. 사용자의 회원가입 정보와 POI(관심지역정보) 저장<br>

  ### Android
  1. 서버와 http 통신으로 데이터를 교환<br>
  2. 데이터를 유니티 앱에 전달<br>
  3. 유니티 앱에서 송신한 데이터를 서버에 저장<br>

  ### Unity as a Library
  1. AR 컨텐츠를 실행하고 AOS앱에서 전달받은 결과 값 표출<br>
  2. 새로운 결과 값(POI)를 AOS앱에 전달<br><br>



# 주요 기능

## 1. 소셜 로그인
  구글 및 카카오 소셜 로그인
  <br>

  | **구글 로그인** | **프로필 이미지 적용** | 
  |---|---|
  | "<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/4164ade1-38fb-4aca-8997-6294ed17f9ef" width="200" height="400"/> | <img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/e1746836-56c1-41ff-a789-1bad9d874199" width="200" height="400"/> | 
<br>

## 2. AR 컨텐츠 실행(UaaL 사용)
 ### Uaal(Unity as a Library) :  Unity로 개발된 AR 앱을 AOS 네이티브 앱에 적용

### 1. ARCore Geospatial API 사용
  - 현재 위치의 정확도를 통해 Localization

### 2. 원하는 Plane에 마커 Object 생성
   - 터치를 통해 마커를 생성합니다.

### 3. 캡쳐 기능
   - 자신이 생성한 마커를 캡쳐할 수 있습니다.

       <img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/cd397da4-1bac-4939-bd27-81c2df950493" width="45%" height="400"/>

### 4. 캡쳐 후, 마커 POI 정보 업로드
   - Unity as Library로 안드로이드 네이티브에 생성한 POI 정보를 전송합니다.

### 5. AR 실행 시, 저장된 POI 정보를 안드로이드 네이티브로부터 수신

### 6. 수신된 POI들은 웹뷰로 표현됩니다.
  <img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/4e5bb0e1-3b92-45e1-91b6-0205fde399d0" width="180" height="400"/>
<br><br>

 - [Unity 모듈 연동]( https://velog.io/@romin1027/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C%EC%97%90%EC%84%9C-Uaal-%ED%99%9C%EC%9A%A91)<br>
 안드로이드에 Unity 프로그램을 라이브러리로 활용 했습니다<br>
 

<br>

## 3. 데이터 서버 업로드

 사용자가 촬영한 이미지, 위치 정보, 촬영지 정보가 서버에 업로드 된 모습

<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/bfdf7190-8a49-42d8-88d9-3d6c0ab1992e" width="45%" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/f9fece64-76ad-409d-89e9-2e86555628c5" width="45%" height="400"/>
<br><br>


## 4. 승인-반려 알림 전송
1. 사용자가 업로드한 이미지를 통해 관리자가 반려 or 승인 처리<br>
2. Client에게 알림 전송
<br><br>
![Alt text](image-3.png)
<br><br>
안내 메시지를 받는 방법은 Push Token을 구글 파이어베이스를 통해 유저의 고유 푸시 token을 발급받고 Post Man과
자사 서버를 사용해 해당 기능을 구현 했습니다

<br><br>


# 결과 화면
<br>
<h1 align="center">

| **권한 요청** | **소셜 로그인** | **쿠팡 웹뷰** | **Main 화면** |
|---|---|---|---|
| <img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/d6e47aa0-6713-480e-927f-291f9887f6d7" width="180" height="400"/> | <img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/cb926de5-33eb-46d2-a6d8-c3ef6e84dca3" width="180" height="400"/> | <img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/662f5a81-5ef4-49cb-a973-5f370dfb8c0e" width="180" height="400"/>| <img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/a5f915ee-a355-4600-8b51-bba8d41b925d" width="180" height="400"/>

| **AR View1** | **AR View2** | **AR View3** | **POI Upload** | 
|---|---|---|---|
| <img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/a97ac82a-33b3-4a2d-bfd9-8de9eb927b8f" width="180" height="400"/> | <img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/4b68bb9d-e610-46de-93c4-90fadd0f861a" width="180" height="400"/> | <img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/4e5bb0e1-3b92-45e1-91b6-0205fde399d0" width="180" height="400"/> |<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/585f06da-b59c-43d3-b180-4ac7c00e5ffc" width="180" height="400"/> 


<br>

# 추가 이미지
<br>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/603dcf60-d4b1-49f6-ad84-e1eb2e421514" width="200" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/0a56b022-078f-47af-9335-6399c986e1da" width="200" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/cb926de5-33eb-46d2-a6d8-c3ef6e84dca3" width="200" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/49e81617-15b1-4610-8f92-7f14ab90983c" width="200" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/ca911f00-851d-485a-afaa-003b562f2e1c" width="200" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/0a0e35d9-f923-4c24-9cf6-e848eab35fa6" width="200" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/2db0b438-eb98-4361-bbce-55c2fd4587d8" width="200" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/388028b6-5cea-4314-ba0c-954ab6d5fb35" width="200" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/b752a58b-b131-4d18-90f5-a90810c3a1f2" width="200" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/cd397da4-1bac-4939-bd27-81c2df950493" width="200" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/7280f386-86eb-484b-856d-20384cf8e5a3" width="200" height="400"/>
