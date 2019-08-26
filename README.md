# docker 기본 학습
## 1. Docker란?
- 경량화된 가상머신 기술

## 2. VM vs Docker
- VM의 경우, 추가적인 운영체제 설치시 Hypervisor 프로그램 기반으로 Guest OS가 설치됨
- 여기서 해당 운영체제의 모든 내용을 메모리에 올리며 운영체제가 실행될 때 엄청난 overhead가 발생됨
- Docker를 사용할 경우, Docker Engine 프로그램 기반으로 Application(컨테이너)이 실행되는 구조

## 3. 이미지와 컨테이너
- 이미지 : 메모리에 올라가기 전 패키징 된 상태. 즉, 컨테이너를 실행하는 데 필요한 내용의 집합체
- 컨테이너 : 이미지를 메모리에 올린 상태(프로세스). 즉, 이미지를 실행 상태로 바꾼 것

## 4. Docker 명령어

#### 이미지 관리
docker pull 이미지:태그(버전) - 이미지 받아오기
docker images – 설치된 이미지 확인
docker rmi [이미지 ID] / docker rmi $(docker images –qa) 설치된 단일/전체 이미지 삭제 

#### 컨테이너 관리
- $docker run 이미지:태그 – 컨테이너 생성 및 실행
  ##### 옵션
   * -i –t : 표준 입력을 활성화 및 유지/TTY 모드 사용
 	          - Bash에 명령을 입력하기 위해 사용
   * -p : 포트 포워딩(특정 포트로 들어온 트래픽을 다른 시스템의 포트로 트래픽을 넘겨주는 행위)
   * --name : 컨테이너 이름 
   * -d : 백그라운드 실행
   * /bin/bash : Bash 셀에 연결

- $docker ps (-a) : 실행 중인(모든) 컨테이너 프로세스 확인 
- $docker rm NAMES(or 컨테이너 이름)/docker rm $(docker ps –qa) 해당/전체 컨테이너 삭제
- $docker start [컨테이너 이름] : 컨테이너 실행
- $docker stop [컨테이너 이름] : 컨테이너 중지
- $docker exec –i –t [컨테이너 이름][명령]: 실행 중인 컨테이너 접속 
- $docker attach [컨테이너이름][명령] : 실행 중인 컨테이너 접속
- $docker cp [host 파일경로] [컨테이너이름]:[컨테이너 내부 경로] 호스트->컨테이너 파일 복사(역으로 가능)
