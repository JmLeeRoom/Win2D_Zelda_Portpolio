# 프로그램 실행

## Server.exe 실행
![image](https://github.com/user-attachments/assets/88c83756-106d-4e2c-84cd-935b8bdb9945)

## Client.exe 실행
1. Client
![image](https://github.com/user-attachments/assets/aa63a917-f7b4-4f50-9ee8-373ea4f2a4f7)

2. Server
![image](https://github.com/user-attachments/assets/c6cd0566-24af-410d-819c-f3004dd03cbc)

# ServerCore

## 프로젝트 개요
1. 비동기 네트워크 통신을 통한 서버 성능 향상 기대
2. IOCP 기반 이벤트 처리 방식으로 클라인언트 연결 관리
3. 멀티스레딩 프로그래밍을 활용하여 성능 최적화
4. 클라이언트 서버 모델 설계를 활용하여 확장 가능 구조로 구현
5. 세션 및 패키 처리를 모듈화 하여 관리 효율성 증가

## 프로젝트 구조

1. Architecture
![image](https://github.com/user-attachments/assets/f0dc26b2-b773-4808-b8b9-f067ff60da90)

2. 프로그램 주요 흐름
- 클라이언트 연결 요청 : Listener가 AcceptEx를 통해 클라이언트 수락
- 세션 생성 : Session이 생성되며 ServerService또는 ClientService에 등록됨
- IOCP 이벤트 처리 : IocpCore가 수신된 이벤트를 적절한 핸들러로 전달
- 데이터 송수신 : RecvBuffer와 SendBuffer를 이용해 데이터를 관리하고 송수신 처리
- 세션 종료 : 클라이언트 연결이 종료되면 Session을 해제하고 IOCP에서 제거

## 사용 기술
1. Windows IOCP
2. 비동기 소켓 프로그래밍
3. 멀티스레딩
4. 스마트 포인터

## 클래스 분석
1. IocpCore
- IOCP 핸들 생성 및 이벤트 처리
2. IocpObject
- IOCP에 등록될 객체의 인터페이스
3. Session
- 클라이언트와의 네트워크 연결을 관리
4. Listener
- 클라이언트 연결 요청을 처리
5. Service
- 클라이언트 및 서버의 공통로직 관리
6. PacketSession
- 패킷 단위의 데이터 송수신 처리

# Server

## 프로젝트 개요
1. 클라이언트와 서버 사이의 멀티플레이어 게임을 위한 A* 기반 몬스터 AI 시스템 및 서버 개발

## 프로젝트 구조
1. Architecture
![image](https://github.com/user-attachments/assets/b0f02168-dfb4-48f9-b2ba-93f7d1fc58da)

## 주요 기능
1. 서버 - 클라이언트 구조
- TCP/IP 기반의 비동기 서버
2. 게임 객체 관리
3. 멀티스레딩
- IOCP / Epoll 비동기 소켓 입출력 처리
4. 몬스터 A* 길찾기 알고리즘
5. protobuf 기반 패킷 통신
- 프로토콜 생성 및 패킷 직렬화
6. 이벤트 기반 패킷 처리

# Client

## 프로젝트 개요
1. 멀티스레딩 기반 네트워크 시스템 구축
2. 네트워크 통신을 활용한 멀티플레이 지원
3. 상속 구조를 활용한 시스템 구현
4. UI 시스템 및 입력처리
5. 게임 Scene 관리및 더블 버퍼링을 활용한 부드러운 렌더링 구현

## 프로젝트 구조
1. Architecture
![image](https://github.com/user-attachments/assets/02db603f-5a52-4fec-8d77-cbe5dfbb1227)

## 주요 기능
1. 객체지향 설계를 활용한 모듈화된 클라이언트 개발
2. 더블 버퍼링을 활용한 부드러운 렌더링
3. 멀티스레딩 기반 네트워크 기술 활용
4. Protobuf 기반 데이터 직렬

# DummyClient

## 프로젝트 개요
1. 멀티스레드 비동 기반 네트워크 프로그래밍 테스트 클라이언트
2. 서버와 연결하고 패킷을 송수신하고, 네트워크 성능 및 안정성 테스트
3. protobuf를 활용한 패킷 직렬화 및 처리 지원
4. 패킷 핸들러 기반의 네트워크 패킷 처리 시스템 구축

## 프로젝트 구조
![image](https://github.com/user-attachments/assets/65c1c70c-09ed-49fe-9e8d-d49d07ad2fda)

## 네트워크 흐름
1. 초기화
2. 클라이언트 서비스 생성
3. 서비스 시작
4. 멀티스레드 실행
5. 패킷 처리
6. 네트워크 종료
