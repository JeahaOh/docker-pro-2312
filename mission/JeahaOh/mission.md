# 사전미션

## 1. 컨테이너 기술이란 무엇입니까? (100자 이내로 요약)

OS에서 실행되는 여러 프로세스를 컨테이너라는 개념으로 격리하여 별도의 운영 환경을 제공하는 기술.  
프로세스가 사용하는 자원을 격리하며 가상머신과 마찬가지로 어플리케이션과 관련 라이브러리 및 종속 항목을 함께 패키지로 묶어 SW 서비스 구동을 위한 격리 환경을 제공함.

## 2. 도커란 무엇입니까? (100자 이내로 요약)

리눅스 컨테이너에서 리눅스 어플리케이션을 프로세스 격리기술을 사용하여 더 쉽게 컨테이너로 실행하고 관리할 수 있게 해주는 오픈소스 프로젝트. 도커는 일반적으로 도커 엔진 혹은 도커에 관련된 모든 프로젝트를 의미함.

## 3. 도커 파일, 도커 이미지, 도커 컨테이너의 개념은 무엇이고, 서로 어떤 관계입니까?

### 도커 파일

도커 파일은 도커에서 이미지를 생성하기 위한 용도로 작성하는 파일이다. 만들 이미지에 대한 정보를 기술해 둔 템플릿이라고 생각하면 된다.  
여러가지 명령어를 토대로 토커 파일을 작성하면 설정된 내용대로 도커 이미지를 만들 수 있다.

### 도커 이미지

도커 이미지는 컨테이너를 생성할 때 필요한 요소이며, 가상 머신을 생성할 때 사용하는 \*.iso 파일과 비슷한 개념임.  
이미지는 컨테이너를 생성하고 실행할 때 읽기 전용으로 사용되며 여러 계층으로 된 바이너리 파일로 존재함.

### 도커 컨테이너

도커 컨테이너는 도커 이미지로 생성할 수 있으며, 컨테이너를 생성하면 해당 이미지의 목적에 맞는 파일이 들어있는, 호스트와 다른 컨테이너로부터 격리된 시스템 자원 및 네트워크를 사용할 수 있는 독립된 공간(프로세스)가 생성됨.  
대부분의 도커 컨테이너는 생성될 때 사용된 도커 이미지의 종류에 따라 알맞는 설정과 파일을 가지고 있기 때문에 도커 이미지의 목적에 맞도록 사용되는 것이 일반적임.  
컨테이너는 이미지를 읽기 전용으로 사용하되 이미지에서 변경된 사항만 컨테이너 계층에 저장하므로 컨테이너에서 무엇을 하든지 원래 이미지는 영향을 받지 않음.  
또한 생성된 각 컨테이너는 각기 독립된 파일세스템을 제공받으며 호스트와 분리돼 있으므로 특정 컨테이너에서 어떤 어플리케이션을 설치하거나 삭제해도 다른 컨테이너와 호스트에는 변경이 없음.

도커 컨테이너는 가상화된 공간을 생성하기 위해 리눅스 자체 기능인 chroot, 네임스페이스(namespace), cgroup을 사용함으로써 프로세스 단위의 격리 환경을 만들기 때문에 성능 손실이 거의 없음. 컨테이너에 필요한 커널을 공유해서 사용하고, 컨테이너 안에는 어플리케이션을 구동하는 데 필요한 라이브러리 및 실행 파일만 존재하기 때문에 컨테이너를 이미지로 만들었을 때 이미지의 용량 또한 가상 머신에 비해 대폭 줄어듦. 따라서 컨테이너를 이미지로 만들어 배포하는 시간이 가상 머신에 비해 빠르며, 가상화된 공간을 사용할 때의 성능 손실도 거의 없다는 장점이 있음.

## 4. [실전 미션] 도커 설치하기
