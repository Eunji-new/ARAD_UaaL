# ARAD_Project
### ARAD - AR로 즐기는 새로운 앱테크 App을 출시하게 되어 Github를 이용하여 해당 프로젝트에 대한 전박적인 설명과 절차를 정리했습니다.
# 1) ARAD 앱 화면
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/d6e47aa0-6713-480e-927f-291f9887f6d7" width="180" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/cb926de5-33eb-46d2-a6d8-c3ef6e84dca3" width="180" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/662f5a81-5ef4-49cb-a973-5f370dfb8c0e" width="180" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/a97ac82a-33b3-4a2d-bfd9-8de9eb927b8f" width="180" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/585f06da-b59c-43d3-b180-4ac7c00e5ffc" width="180" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/4e5bb0e1-3b92-45e1-91b6-0205fde399d0" width="180" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/4b68bb9d-e610-46de-93c4-90fadd0f861a" width="180" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/a5f915ee-a355-4600-8b51-bba8d41b925d" width="180" height="400"/>


1. ARAD 앱은 유저의 참여에 대한 보상을 제공하는 앱입니다.
2. 사용자의 위도 경도를 바탕으로 AR 컨텐츠를 즐기실 수 있습니다
3. 쿠팡 파트너스 및 업체의 AR 광고를 통해 보다 뛰어난 마케팅 사업을 진행할 수 있습니다.

# 2) URL
깃허브 : https://github.com/rohhyungwoo/ARAD_Project.git \
스토어 : https://play.google.com/store/apps/details?id=com.anyractive.arad_january
# 3) 설명

## 서버 송수신

서버와 http 통신을 하여 실시간으로 데이터를 공유합니다\
앱과 서버간의 REST API 통신을 도와주는 라이브러리로 Retrofit2를 사용 했습니다

<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/30422454-1f48-4966-8476-889389b94ca5" width="50%" height="100%"/>

카카오 & 구글 소셜 로그인 기반으로 회원의 고유 ID를 생성하고 보상 및 AR 컨텐츠를 즐기기 위한 데이터를 저장합니다.
아래는 사용자가 촬영한 이미지, 위치 정보, 촬영지 정보가 서버에 업로드 된 모습 입니다.

<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/bfdf7190-8a49-42d8-88d9-3d6c0ab1992e" width="45%" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/f9fece64-76ad-409d-89e9-2e86555628c5" width="45%" height="400"/>

관리자가 사용자가 업로드한 이미지를 가지고 반려, 승인을 판단하여 처리하게 되면\
Client는 서버로 부터 안내 메시지를 받을 수 있습니다.

<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/9d505148-e75b-4189-a730-8882de376250" width="30%" height="100%"/>

안내 메시지를 받는 방법은 Push Token을 구글 파이어베이스를 통해 유저의 고유 푸시 token을 발급받고 Post Man과
자사 서버를 사용해 해당 기능을 구현 했습니다

## AR 컨텐츠 실행
보다 입체적인 AR 이미지를 표현하기 위해 Unity를 통해 개발된 프로젝트를\
기존 안드로이드 앱에 적용하는 Uaal(Unity as a Library)을 사용합니다

<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/cd397da4-1bac-4939-bd27-81c2df950493" width="45%" height="400"/>
 <img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/b90aa497-8625-4f4e-86a2-84842e21b96b" width="45%" height="400"/>

- AR Core 기반 AR 이미지 모델링\
 AR Core란 Google에서 개발한 AR 증강현실 기술입니다 \
 사용자의 카메라와 위치에 엑세스 하여 수평면을 찾아, 가상의 객체를 3D 공간에 고정 및 배치합니다


 - AR 이미지 생성 및 관심 위치(POI) 저장\
 카메라와 위치를 기반으로 AR Core가 공간에서 초기 포지션에서 추적 가능한 한 지점을 나타내고 해당 지점을 앵커로 만들어 냅니다\
 또한 getPose를 통해 관심 위치에 대한 좌표값을 알 수 있게 됩니다.

 - Unity 모듈 연동\
 안드로이드에 Unity 프로그램을 라이브러리로 활용 했습니다
 
 <img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/dfd4b216-c895-444e-a036-78768244c5d0" width="45%" height="400"/>

 Unity 라이브러리를 생성하여 안드로이드 프로젝트 package 경로에 저장합니다.
 이 다음 Unity 라이브러리를 정상적으로 사용하기 위해서는 몇가지 작업을 진행해야 됩니다.

 > app 내부 build.gradle 설정\
gradle.properties 수정\
UnityLibrary 의 build.gradle 수정.\
string.xml 추가\
Maniifest에서 Intent Filter 수정\
ndk 설치 및 경로 추가\
Duplicate 오류 해결\
setting.grandle 파일에 include ':unityLibrary' 추가 \
android:process(:Unity) 추가
도야

위 설정이 끝나면 아래 코드를 통해서 Unity Program을 실행 할 수 있습니다 
>startActivity(Intent(this, UnityPlayerActivity::class.java))

Uaal 설정하는 방법에 대한 더욱 자세한 내용은 제 블로그를 방문해 주시면 감사합니다.



## 소셜 로그인, 구글 맵 연동

<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/4164ade1-38fb-4aca-8997-6294ed17f9ef" width="200" height="400"/>
<img src="https://github.com/rohhyungwoo/ARAD_Public/assets/67363759/e1746836-56c1-41ff-a789-1bad9d874199" width="200" height="400"/>


# 4) 추가 이미지

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
