# <img src="https://github.com/user-attachments/assets/35925543-ea0b-4807-b4d8-2af0381be45e" alt="MIKO_LOGO_Square" width="25" height="25"> MIKO
> Meeting In Keyword Out

회의록 작성에 도움을 주는 다양한 서비스들이 있지만, 실시간으로 음성을 텍스트로 변환(STT)하고 키워드를 추출하여 회의 중간에 합류한 사람도 맥락을 쉽게 파악할 수 있도록 돕는 서비스는 없습니다. 
MIKO는 이러한 필요를 충족시키기 위해 개발된 서비스로, 실시간 STT 변환 및 키워드 추출 기능을 통해 회의 참여자들이 보다 효율적으로 회의를 진행할 수 있도록 도와줍니다.

- [MIKO](https://www.mi-ko.site/)  
- [MIKO 발표영상](https://www.youtube.com/watch?v=TdP1CQB0WRY)

## 팀 "해내야한다" 소개

카이스트 사관학교 정글 과정 나만의 무기에서 결성된 팀 "해내야 한다" 입니다.  

개발 기간 : 2024.06.12 ~ 2024.07.20

| **Name**     | 안태리                                                                  | 정재혁                                                                  |남청우                                                                   | 유흥국                                                                  | 문건우                                                                                                                                  
|:------------:|:--------------------------------------------------------------------:|:--------------------------------------------------------------------:|:--------------------------------------------------------------------:|:--------------------------------------------------------------------:|:--------------------------------------------------------------------:|
| **Profile**  |<img height="150" src="https://github.com/user-attachments/assets/7eaa7527-cd2d-48dd-9d67-3e47cf67cbd5">|<img height="150" src="https://github.com/user-attachments/assets/0afa4fed-4a82-4b1e-b328-fc8a9c9be896"> | <img height="150" src="https://github.com/user-attachments/assets/05b6f94f-50c2-43d1-bc2b-228fbe8ceb2f">| <img height="150" src="https://github.com/user-attachments/assets/673d808c-6562-4d9c-b8c1-c9aad1be12c2"> | <img height="150" src="https://github.com/user-attachments/assets/7dfe0f58-8722-4018-93c3-8fdea8544211"> |  
| **Position** | Backend <br/> (팀장)      | Backend              | Backend          | Frontend                   | Frontend            | 
| **Git** | [@T3rryAhn](https://github.com/T3rryAhn)       | [@Arklimits](https://github.com/Arklimits)    | [@malgcheong](https://github.com/malgcheong)      | [@hkyoo988](https://github.com/hkyoo988)    | [@GEONU-MOON](https://github.com/GEONU-MOON)            | 

## MIIKO 레포지토리 소개

| 구분 | 프로젝트 | 설명 |
|:---:|:---------:|:---|
| **Backend** | [**miko-main-server**](https://github.com/ProjectMIKO/miko-main-server) | - **미코 서비스의 메인 서버** <br> &nbsp;&nbsp;&nbsp;&nbsp;> 클라이언트에서 음성 파일을 받아 자연어 처리 서버로 전달하는 미들웨어 역할<br> &nbsp;&nbsp;&nbsp;&nbsp;> 회의방 소켓 통신 및 세션 관리 <br> &nbsp;&nbsp;&nbsp;&nbsp;> 키워드를 깊이에 따라 객체화하고 키워드를 추출하는 로직 |
|            | [**miko-nlp-server**](https://github.com/ProjectMIKO/miko-nlp-server) | - **미코 서비스의 자연어 처리 서버** <br> &nbsp;&nbsp;&nbsp;&nbsp;> 음성 파일을 받아 전처리 후 리턴제로 API에 STT 요청 <br> &nbsp;&nbsp;&nbsp;&nbsp;> 대화 기록을 바탕으로 OpenAI GPT에게 키워드 추출 및 회의록 요약 요청 후 결과를 메인 서버로 전송 |
|            | **openvidu**<br>                                                    | - **도커로 배포한 화상 통화 서버** |
| **Frontend** | [**miko-frontend**](https://github.com/ProjectMIKO/miko-frontend) | - **미코 서비스의 프론트엔드** <br> &nbsp;&nbsp;&nbsp;&nbsp;> vis.js를 통해 키워드를 네트워크 그래프로 시각화 |
| **Etc**     | [**stt-lab**](https://github.com/ProjectMIKO/stt-lab) | - **오디오 전처리 과정을 실험한 코드가 담긴 레포지토리**<br> &nbsp;&nbsp;&nbsp;&nbsp;> 오디오 정규화, 다른 오디오 라이브러리 테스트, 소음 제거, 이퀄라이징, 형태소 분석기 등을 테스트함 |
|            | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**MOM**](https://github.com/orgs/ProjectMIKO/projects/1/views/5)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | - **issue에 회의록을 작성한 레포지토리** |

## 🔧 서비스 구조도
![MIKO 아키텍쳐](https://github.com/user-attachments/assets/69982cc2-7a11-4191-930d-014a75b54deb)

## 📚 기술 스택
- **Frontend**: TypeScript, Next.js
- **Backend**: TypeScript, Nest.js, python, Flask
- **Database**: MongoDB
- **Infrastructure/DevOps**: AWS EC2, CloudWatch, Docker
- **Extension**: OpenVidu, Soket.io, openAi-gpt, torchAudio

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

## 📊 프로젝트 포스터
![MIKO (59 4 x 84 1 cm)](https://github.com/user-attachments/assets/29a39bc7-43d4-4161-8ad3-2e981c25f4f9)

## 설치방법

위의 서버들을 전부 실행하고 `http:localhost:3000/` 접속한다.

- [frontend 설치 및 실행]()
- [main-server 설치 및 실행](https://github.com/ProjectMIKO/miko-main-server/blob/main/README.md#-%EC%84%A4%EC%B9%98-%EB%B0%A9%EB%B2%95)
- [nlp-server 설치 및 실행](https://github.com/ProjectMIKO/miko-nlp-server?tab=readme-ov-file#nlp-server-%EC%84%A4%EC%B9%98-%EB%B0%8F-%EC%8B%A4%ED%96%89-%EB%B0%A9%EB%B2%95)
- [openvidu 설치 및 실행]()



