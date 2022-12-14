# Docker

## 목차

### 1. Docker install

1. Install docker desktop

### 2. Docker image Container: Core building

1. 사전 빌드된 이미지 사용
2. Nodejs 이미지 사용하기
3. Dockerfile로 자체 이미지 빌드
4. 자체 이미지 기반으로 컨테이너 실행하기
5. EXPOSE & 약간의 유틸리티 기능
6. 이미지 레이어 이해하기
7. 실행중인 컨테이너 연결
   1. `docker run`으로 실행하면 기본 attach 모드
   2. `docker start`로 실행하면 기본 detach 모드
   3. `attach`된 상태라면 콘솔에 로그를 남길 경우 터미널에 찍힌다
8. 인터렉티브 모드로 들어가기
9. 이미지 & 컨테이너 삭제
10. 컨테이너에/컨테이너로부터 파일 복사하기
    1. `docker cp {복사하려는 파일} {컨테이너네임}:복사하려는 위치`
    2. `docker cp {컨테이너네임}:복사하려는 파일 {복사하려는 위치}`
11. 컨테이너와 이미지에 이름 지정 & 태그 지정하기

### 3. 데이터 관리 및 볼륨으로 작업하기

1. named 볼륨으로 구조하기
2. 익명 볼륨 제거하기
3. 바인드 마운트 시작하기(코드 공유)
4. 바인드 마운트 - 바로 가기(shortcuts)
5. 다른 볼륨 결합&병합하기
   1. named 볼륨을 한 상태라면 `Dockerfile`의 `COPY` 명령을 사용한 상태에서 바인드 마운트를 하면 로컬의 내용으로 해당 내용들을 다 덮어버린다
   2. 때문에 `RUN` 명령어로 생성됐던 `node-modules`도 전부 사라지게 된다
   3. 익명 볼륨을 통해 해당 컨테이너 내부에 이미 일부 파일이 있음을 알려줘야 한다
6. Nodejs 특화 : 컨테이너에서 Nodemon 사용하기
7. 읽기 전용 볼륨 살펴보기
8. Docker 볼륨 관리하기
9. COPY 사용 vs 바인드 마운트 사용
10. dockerignore 파일 사용하기
11. .dockerignore 파일에 추가하기
12. 환경변수 & .env 파일 작업
    1. `--env or -e로 실행 시 환경변수를 설정하거나 Dockerfile 안에 ENV로 설정하기`
    2. `.env` 파일로 생성해서 설정한 후 `실행 시 --env-file로 환경변수 파일 지정`
13. 환경변수 & 보안
14. 빌드 인수 사용하기

### 4. 네트워킹: (교차) 컨테이너 통신

1. 컨테이너 외부 API 통신
2. 컨테이너와 로컬 호스트 통신
3. 컨테이너 간 통신 - 기본 솔루션
4. 컨테이너 간 통신 - docker network
5. Docker가 IP주소를 해결하는 방법

### 5. Docker로 다중 컨테이너 애플리케이션 구축하기

1. MongoDB 서비스 도커화 하기
2. Node 앱 도커화 하기
3. React SPA 컨테이너로 옮기기
   1. `React` 앱의 경우 실행할 때 `-it` 옵션으로 명령어로 상호작용하도록 설정해줘야 한다
4. Docker network 구성하기
5. Volume으로 MongoDB에 데이터 지속성 추가하기
6. NodeJS 컨테이너의 볼륨, 바인딩 마운트 및 폴리싱(Polishing)
7. 바인드 마운트로 React 컨테이너에 대한 라이브 소스 업데이트 하기

### 6. Dokcer Compose: 다중 컨테이너 오케스트레이션

1. Docker-Compose : 무엇이며 왜 사용하는가
2. Compose 파일 만들기
3. Compose 파일 구성(Configuration) 자세히 알아보기
4. Docker Compose Up과 Down
5. 다중 컨테이너로 작업하기
6. 또 다른 컨테이너 추가하기
7. 이미지 빌드 & 컨테이너 이름 이해하기

### 7. 유틸리티 컨테이너로 작업하기 & 컨테이너에서 명령 실행하기

1. 유틸리티 컨테이너를 사용하는 이유?
2. 컨테이너에서 명령을 실행하는 다양한 방법
3. 첫 번째 유틸리티 컨테이너 구축
4. ENTRYPOINT 활용
5. Docker Compose 사용
6. 유틸리티 컨테이너, 권한 & Linux

### 8. 더 복잡한 설정: Laravel & PHP 도커화 프로젝트

1. Target 설정
2. Nginx(웹 서버) 컨테이너 추가
3. PHP 컨테이너 추가
4. MySQL 컨테이너 추가
5. Composer 유틸리티 컨테이너 추가
6. Composer 유틸리티 컨테이너로 Laravel 앱 만들기
7. 오류 수정하기
8. 일부 Docker Compose 서비스만 구동하기
9. 더 많은 유틸리티 컨테이너 추가하기
10. Dockerfile이 있거나, 없는 Docker Compose
11. 바인드 마운트와 COPY - 언제 뭘 써야 하는지

### 9. Docker & 컨테이너 배포하기

1. 배포 프로세스 & 프로바이더
2. production에서 바인드 마운트
3. 가상머신에 도커 설치하기
4. 도커 이미지 푸쉬하기
5. 앱 실행하기
6. 현재 방식의 문제점
7. 수동 배포에서 관리형 서비스로(ECS)
8. 안정적인 도메인을 위해 로드 밸런서 사용하기
9. ECS로 EFS 볼륨 사용하기
10. 데이터베이스 & 컨테이너: 중요한 고려 사항
11. MongoDB Atlas로 이동하기
12. 프로덕션에서 MongoDB Atlas 사용하기
13. 빌드 전용 컨테이너 만들기
14. 멀티 스테이지 소개
15. 멀티 스테이지 이미지 구축

### 10. Docker & 컨테이너 요약

### Kubernetes

## 목차

### 1. Kubernetes 시작하기

1. 수동 배포의 더 많은 문제점들
2. 왜 Kubernetes인가?
3. Kubernetes가 정확히 무엇인가
4. Kubernetes: 아키텍쳐 & 핵심 개념
5. Kubernetes는 인프라를 관리하지 않습니다
6. 워커 노드 자세히 살펴보기
7. 마스터 노드 자세히 살펴보기
8. Kubernetes Core Concepts

### 2. 실전 Kubernetes - 핵심 개념 알아보기

1. Kubernetes 객체(리소스) 이해하기
2. Deployment 객체(리소스)
3. Deployment - 명령적 접근 방식
4. kubectl 작동 배경
5. Service 객체(리소스)
6. Service로 Deployment 노출하기
7. 컨테이너 재시작
8. 실제 스케일링
9. Deployment 업데이트 하기
10. Deployment 롤백 & 히스토리
11. 명령적 접근방식 vs 선언적 접근방식
12. Pod와 컨테이너 사양 추가
13. Label 및 Selector로 작업하기
14. 선언적으로 Service 만들기
15. 리소스 업데이트 & 삭제
16. 다중 vs 단일 Config 파일
17. Label & Selector에 대한 추가 정보
18. Liveness Probes

### 3. Kubernetes로 데이터 & 볼륨 관리하기

1. Kubernetes 볼륨
2. Kubernetes 볼륨 - 이론 & Docker와 비교
3. 새 Deployment & Service 만들기
4. Kubernetes 볼륨 시작하기
5. Kubernetes 볼륨 - emptyDir 유형
6. Kubernetes 볼륨 - hostPath 유형
7. CSI 볼륨 유형 이해하기
8. 볼륨에서 영구(Persistent) 볼륨으로
9. 영구 볼륨 정의하기
10. 영구 볼륨 클레임 생성하기
11. 영구 볼륨 클레임 사용하기
12. 볼륨 vs 영구 볼륨
13. 환경 변수 & ConfigMaps

### 4. Kubernetes 네트워킹

1. 첫 번째 배포 만들기
2. Service에 대한 또 다른 관점
3. 하나의 Pod안에 있는 다중 컨테이너
4. Pod 내부 커뮤니케이션
5. 다중 Deployments 생성
6. IP 주소 & 환경 변수를 사용한 Pod간 통신
7. Pod간 통신에 DNS 사용하기
8. 어떤 접근 방식이 최고인가
9. 컨테이너화된 프론트엔드 추가하기
10. Kubernetes로 프론트엔드 배포하기
11. 프론트엔드에 리버스 프록시 사용하기

### 5. Kubernetes 배포
