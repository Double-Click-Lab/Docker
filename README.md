# Docker

* * *

## 사용 이유

* 개발 환경을 동일하게 맞출 수 있음
* 복잡한 설치 과정을 줄일 수 있음
* 프로그램을 빠르게 실행하고 삭제 가능
* 개발, 테스트, 배포 환경 관리가 쉬움
* 여러 서비스를 한 번에 실행 가능

* * *

## 핵심 개념

* Image : 실행에 필요한 파일과 설정
* Container : Image를 실행한 상태
* Dockerfile : Image를 만드는 설명서
* Docker Compose : 여러 Container를 한 번에 실행하는 도구

* * *

## 사용 환경

* Windows / macOS / Linux
* Docker 설치 필요
* 터미널 사용 가능
* 실습용 프로젝트 폴더 필요

* * *

## 사용 방법

### 1. Docker 설치 확인

    docker --version

### 2. 테스트 실행

    docker run hello-world

### 3. nginx 실행

    docker run -d -p 8080:80 nginx

### 4. 브라우저 접속

    http://localhost:8080

### 5. 실행 중인 컨테이너 확인

    docker ps

### 6. 컨테이너 중지

    docker stop 컨테이너ID

### 7. 컨테이너 삭제

    docker rm 컨테이너ID

* * *

## Dockerfile 사용 방법

### 1. Dockerfile 생성

    FROM node:20

    WORKDIR /app

    COPY package*.json ./

    RUN npm install

    COPY . .

    CMD ["npm", "start"]

### 2. Image 빌드

    docker build -t my-app .

### 3. Container 실행

    docker run -p 3000:3000 my-app

* * *

## Docker Compose 사용 방법

### 1. docker-compose.yml 생성

    services:
      web:
        image: nginx
        ports:
          - "8080:80"

### 2. 실행

    docker compose up

### 3. 백그라운드 실행

    docker compose up -d

### 4. 종료

    docker compose down

* * *

## 실습 순서

* Docker 설치 확인
* hello-world 실행
* nginx 컨테이너 실행
* localhost 접속
* 컨테이너 중지 및 삭제
* Dockerfile로 Image 생성
* Docker Compose로 실행

* * *

## 주의 사항

* 포트가 이미 사용 중이면 실행 실패 가능
* Container 삭제 시 내부 데이터도 사라질 수 있음
* 중요한 데이터는 Volume 사용
* 필요 없는 Image와 Container는 정리
* 운영 환경에서는 보안 설정 확인 필요

* * *

## 정리

Docker는 실행 환경을 Image로 만들고 Container로 실행하는 도구.

핵심은 아래와 같음.

    Image = 실행 준비물
    Container = 실행 중인 프로그램
    Dockerfile = Image 생성 파일
    Docker Compose = 여러 Container 실행 도구

Docker를 사용하면 개발 환경 구성, 프로그램 실행, 배포를 더 쉽고 안정적으로 관리할 수 있음.
