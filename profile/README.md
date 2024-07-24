# PROJECT MIKO
## MIKO
> Meeting In Keyword Out


***
## 팀 "해내야한다" 소개
카이스트 사관학교 정글 과정 나만의 무기에서 결성된 팀 "해내야 한다" 입니다.


**Member**: 안태리, 남청우, 정재혁, 유흥국, 문건우
- **팀장**: 안태리
- **frontend**: 문건우, 유흥국
- **backend**: 정재혁, 남청우
- **기간**: 2024/6/12 ~ 2024/7/20

***
# MIKO 아키텍처
![image](https://github.com/user-attachments/assets/c6a42340-47bd-4a7f-919c-f0234296243d)


***
# MIIKO 레포지토리 소개
## backend
### miko-main-server
https://github.com/ProjectMIKO/miko-main-server

미코 서비스의 회의방 관리 서버
클라이언트, 자연어처리서버, 화상통화(오픈비두)은 main-server를 통해 통신한다.

클라이언트에서 보내는 데이터 (음성파일, 소켓 통신)을 받고 자연어 처리 서버로 보내 키워드나, stt, 회의록을 받아 클라이언트에게 돌려준다.
클라이언트가 회의방에 접속할때 
청우형 작성

### miko-nlp-server
https://github.com/ProjectMIKO/miko-nlp-server

미코 서비스의 자연어 처리서버
- 음성파일을 받으면 오디오 전처리를 거치고 리턴제로 api에 stt 요청을 보내고 받아온다. 받은 stt를 main-server에 전송한다.
- main-server로 부터 대화기록을 받으면 openai gpt 에게 키워드 추출 요청을 보내고 받아서 main-server에 전송한다.
- main-server로 부터 대화기록을 받으면 openai gpt 에게 회의록 요약 요청을 보내고 받아서 main-server에 전송한다.

### openvidu-server
도커에 배포되어있어 miko 레포지터리에는 없습니다.

## frontend
### miko-frontend
https://github.com/ProjectMIKO/miko-frontend

## etc
### stt-lab
https://github.com/ProjectMIKO/stt-lab

오디오 전처리 과정을 실험해본 코드가 담긴 레포지터리 입니다.
오디오 정규화, 다른 오디오 라이브러리 테스트, 소음제거, 이퀄라이징, 형태소 분석기 등을 테스트해보았습니다.
### MOM
https://github.com/orgs/ProjectMIKO/projects/1/views/5

issue에 회의록을 작성한 레포지터리입니다. 위 링크는 projects의 회의록으로 이동합니다.

***
# <img src="https://github.com/user-attachments/assets/35925543-ea0b-4807-b4d8-2af0381be45e" alt="MIKO_LOGO_Square" width="25" height="25"> MIKO
회의록 작성에 도움을 주는 다양한 서비스들이 있지만, 실시간으로 음성을 텍스트로 변환(STT)하고 키워드를 추출하여 회의 중간에 합류한 사람도 맥락을 쉽게 파악할 수 있도록 돕는 서비스는 없습니다. 
MIKO는 이러한 필요를 충족시키기 위해 개발된 서비스로, 실시간 STT 변환 및 키워드 추출 기능을 통해 회의 참여자들이 보다 효율적으로 회의를 진행할 수 있도록 도와줍니다.

https://www.mi-ko.site/

## 📚 기술 스택
- **Frontend**: TypeScript, Next.js
- **Backend**: TypeScript, Nest.js, Soket.io, python, Flask, openAi-gpt, torchAudio
- **Database**: MongoDB
- **Infrastructure/DevOps**: AWS EC2, CloudWatch, Docker
- **Extension**: OpenVidu

## 📝 서비스 소개

### 1. 실시간 STT 제공
회의 중 실시간으로 음성을 텍스트로 변환하여 참가자들에게 제공

<img src="https://github.com/user-attachments/assets/05e2ca6b-64c9-4637-a59e-e619246f3015" alt="STT 기능" width="400" height="400">

### 2. 5문장마다 자동 키워드 추출 (네트워크 그래프로 시각화)
회의 내용에서 중요한 키워드를 추출하고 이를 네트워크 그래프로 시각화

<img src="https://github.com/user-attachments/assets/d2f5d54e-70ad-4f65-8c80-04593930a351" alt="키워드 추출" width="700">

### 3. 키워드 간 연결 및 연결 해제
키워드 간의 관계를 시각적으로 표현하고, 필요에 따라 연결을 해제

### 4. 비회원 참여 지원
비회원도 링크를 통해 회의에 쉽게 참여할 수 있도록 지원

<img src="https://github.com/user-attachments/assets/6fda4187-aad4-4678-ae85-86fbac4ff7ae" alt="비회원 링크 공유" width="700">

### 5. 결과 페이지에서 회의록 및 음성 기록 제공
회의 종료 후 결과 페이지에서 자동 생성된 회의록과 음성 기록을 제공

<img src="https://github.com/user-attachments/assets/edde0c41-7513-4e3e-a1ae-f966a3fd3f12" alt="결과 페이지" width="700">

### 6. 결과 페이지 유지
회의 종료 후에도 구글 OAuth를 통해 회의 정보를 지속적으로 제공

<img src="https://github.com/user-attachments/assets/c46cd5fa-bcc2-454f-910e-f143d2356749" alt="게시글" width="700">

***
## 📊 프로젝트 포스터
![MIKO (59 4 x 84 1 cm)](https://github.com/user-attachments/assets/29a39bc7-43d4-4161-8ad3-2e981c25f4f9)
***
# 설치방법
## frontend 설치 및 실행

## main-server 설치 및 실행
https://github.com/ProjectMIKO/miko-main-server/blob/main/README.md#-%EC%84%A4%EC%B9%98-%EB%B0%A9%EB%B2%95
## nlp-server 설치 및 실행
https://github.com/ProjectMIKO/miko-nlp-server?tab=readme-ov-file#nlp-server-%EC%84%A4%EC%B9%98-%EB%B0%8F-%EC%8B%A4%ED%96%89-%EB%B0%A9%EB%B2%95
## 오픈비두 서버 설치 및 실행

위의 서버들을 전부 설치후 각각실행한후 `http:localhost:3000/` 접속한다.
***
