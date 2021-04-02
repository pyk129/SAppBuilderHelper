# SAppBuilderHelper
S앱빌더 도움말 페이지 

# QNA

## 빌드가 안될 경우 (안드로이드)
- 프로젝트 저장소 설정이 정상적으로 설정 되어있나 확인
- (프로젝트 리스트 -> 등록된 프로젝트) 안드로이드 앱 폴더가 정상적으로 성정 되어있는지 확인 기본값 app
로 설정

## 안드로이드 하나의 프로젝트 소스를 활용해서 여러 소스셋으로 나누어서 빌드 하고 싶은 경우
- (프로젝트 리스트 -> 등록된 안드로이드 프로젝트) 빌드 베리언트 사용

## 빌드 과정 실패 날 경우 (안드로이드)
### 빌드 정보 다운로드 실패
- 정상적으로 형상관리 시스템과 연결이 되는지 확인
- S앱빌더 저장소 설정이 정상적으로 설정 되었는지 확인

### 안드로이드 빌드 전처리 실패)
- (온라인) gradle.com, dl.google.com, jcenter.bintray.com, repo.maven.apache.org/maven2등 Maven리포지토리들이 정상적으로 연결되는지 확인
- (오프라인) 내부구간의 Maven서버와 중계서버간 통신이 정상적으로 이루어지는지 확인
- (오프라인) DMZ 구간의 중계서버와 인터넷 구간(gradle.com, dl.google.com, jcenter.bintray.com, repo.maven.apache.org/maven2) 통신이 정상적으로 이루어지는지 확인

3) Wrapper 생성 실패
-> Gradle.zip 파일이 에이전트 경로에 존재하는지 확인
-> 에이젼트에 Gradle경로가 올바르게 쓰여져있는지 확인

4) APK 빌드 실패
-> Gradle.zip 파일이 에이전트 경로에 존재하는지 확인
-> 관리자의 오류 로그 확인 후 정상적인 Gradle Task(assembleRelease, assembleDebug등)Task가 실행되었는지 확인 -> 비정상적인 Task가 실행 되었을경우 관리자에 문의

5) ZipAlign 실패
-> 에이젼트의 설정 항목에 ZipAlign 경로가 정상적으로 작성 되었는지 확인

6) APK Signing 실패
-> 에이젼트의 설정 항목에 APkSignier경로가 정상적으로 작성 되었는지 확인

7) 결과 파일 업로드 실패
-> 결과 파일 업로드 서버 연결 여부 확인

3. 빌드가 안될 경우 (iOS)
1) 빌드정보다운로드 실패
-> 정상적으로 형상관리 시스템과 연결이 되는지 확인
-> S앱빌더 저장소 설정이 정상적으로 설정 되었는지 확인

2) IOS인증서설정 실패
-> 빌드 프로젝트의 정보와 일치하는 인증서가 프로젝트에 설정 되어있는지 확인

3) IOS프로비저닝설정 실패
-> 빌드 프로젝트의 인증서와 일치하는 프로비저닝이 프로젝트에 설정 되어있는지 확인  

4) XCode설정 실패
-> 프로젝트에 설정되어있는 Xcode 버전과 빌드 MAC PC에 설치되어 있는 Xcode 정보가 일치하는지 확인

5) IOS빌드전처리 실패
-> 빌드 스키마 정보가 프로젝트 정보와 일치하는지 확인
-> 빌드 구성 정보가 프로젝트 정보와 일치하는지 확인
-> 빌드 할 프로젝트의 정보와 일치하는지 확인 
   -> 배포용 인증서인데 개발용 프로비저닝이 프로젝트에 설정되어 있는지 확인  
   -> 개발용 인증서인데 운영용 프로비저닝이 프로젝트에 설정되어 있는지 확인 
-> 빌드 실패 로그파일 추출 후 담당자에 문의

6) Archive생성 실패
-> 빌드 스키마 정보가 프로젝트 정보와 일치하는지 확인
-> 빌드 구성 정보가 프로젝트 정보와 일치하는지 확인
-> 빌드 할 프로젝트의 정보와 일치하는지 확인 
   -> 배포용 인증서인데 개발용 프로비저닝이 프로젝트에 설정되어 있는지 확인  
   -> 개발용 인증서인데 운영용 프로비저닝이 프로젝트에 설정되어 있는지 확인 
-> 빌드 실패 로그파일 추출 후 담당자에 문의

7) IPA생성 실패
-> 빌드 실패 로그파일 내용중 plist가 정상적으로 작성 되었는지 확인 
-> 빌드 실패 로그파일 추출 후 담당자에 문의

8) 결과파일업로드 실패 
-> 결과 파일 업로드 서버 연결 여부 확인

### 장애 발생시 대쳐
1) 로그파일 담당자 전달
2) 관리자 빌드 로그파일 담당자 전달
-> 빌드 생성 및 빌드 이력 내의 log파일 다운로드 후 담당자 전달

3) 에이젼트 빌드 정보 담당자 전달 
-> 2)번 항목이 존재 하지 않을 경우 에이젼트가 설치되어 있는 MAC PC에서 에이젼트 설정 -> output 폴더 경로 확인
-> output경로 이동 -> (관라자) 빌드를 진행한 build_id 확인 (관리자에서 빌드를 한 URL을 보면 build_id=xxx와 같이 되어 있음 xxx번호를 확인) -> output폴더/build_id/폴더를 압축해서 담당자 전달 


## 용어정리
### 빌드 정책이란?
### 모듈 이란?
### 저장소란?
### 에이젼트란?
### 개발용 / 운영용 구분은 어떻게?
### 빌드 베리언트란?
### 안드로이드 프로젝트의 앱폴더란?
### 빌드 컨피그레이션이란?
### 스키마란? 
### 지원되는 Xcode 버젼은?


