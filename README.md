## ⚽️ [FINAL] 풋살 매치 사이트 Shoots 

![Image](https://github.com/user-attachments/assets/c7f91ea5-b554-456c-bf26-fd2f800040e0)


🔗 배포 URL : [https://www.goshoots.site](https://www.goshoots.site/Shoots/main)


## 💻 PROJECT INTRODUCTION
- 목적 
  - 일회성 매치시스템과 커뮤니티를 함께 구현하여 취미 축구인들의 네트워크 구축
  - 기존 풋살장 예약 페이지의 복잡한 UI, 예약 페이지와 커뮤니티 분리로 인한 소통의 불편함을 해소하기 위해 웹 사이트를 간결하고 직관적으로 변경
  - 사용자에게 편의성을 제공함과 동시에 하나의 웹 사이트에 매치기능과 커뮤니티를 함께 구현해 취미 축구인들의 네트워크를 구축
    
- 기능
  - 원하는 장소, 날짜, 시간에 맞는 매치를 조회 및 신청
  - 매치 확정 시 팀원들과의 팀 채팅방 개설로 매치 전 팀원 간의 다양한 소통 가능
  - 현재 위치 기반 가까운 제휴 풋살장 검색 가능
  - 자유게시판을 통해 자유로운 소통 및 중고게시판으로 쉽고 간편한 중고거래

## 🗓️ DEVELOPMENT PERIOD
2024.12.30 - 2025.02

|게시글 및 댓글 신고, 팀 채팅|

## ⚙️ DEVELOPMENT ENVIRONMENT
- Programming Language : Java 17
- Framework : Spring Boot
- Database : MySQL, Redis / MySQL Workbench, DBeaver 
- Front : HTML/CSS, JavaScript, Tymeleaf, Bootstrap
- Tooling/ DevOps : Intellij IDEA, GitHub, Docker, Postman, GitHub Action
- Environment : AWS, Jenkins
- Etc : Figma, Notion, Slack 

> <h3>Branch strategy</h3>
- Git-Flow 전략 기반
- main, develop, feature 브랜치 운용
  - main : 배포 가능한 상태만을 관리
  - dev : 통합 브랜치 역할, 개발 단계에서 master 역할
  - feature : 기능 단위로 팀원간의 독립적인 개발환경을 보장하기 위해 사용


## 💡 김동휘 주요 기능(Feature)
### 📍 STOMP WebSocket을 이용한 실시간 채팅
- 오버헤드를 줄이기 위해 Backoff 전략과 Heartbeat 설정을 추가하여 효율적인 채팅 시스템을 구현.
### 📍 Modal과 fetch, RestController를 이용한 신고 기능
- 오류를 없애기 위해, 유효성 검사와 댓글과 게시글의 idx를 읽어와 async와 await으로 비동기의 흐름 제어하여 전달하여 mybatis xml mapper로 DB 등록.

## 📑 DEMO

| 메인 페이지 | 기업 페이지 - 차단 고객 |
| :--------: | :--------: |
| <img src="https://github.com/user-attachments/assets/c7f91ea5-b554-456c-bf26-fd2f800040e0" width="960"> | <img src="https://github.com/user-attachments/assets/11417949-a100-47a8-86ef-d30a96bb81c1" width="960"> |

| 매치 리스트 페이지 | 매치 상세 페이지 |
| :--------: | :--------: |
| <img src="https://github.com/user-attachments/assets/05d0a5ad-26f1-4f0b-b7e0-d1d8243541ad" width="960"> | <img src="https://github.com/user-attachments/assets/19ae3f1d-c438-4712-89d4-4779daef04ef" width="960"> |

| My 매치 리스트 페이지 | 실시간 채팅 페이지 유저1 |
| :--------: | :--------: |
| <img src="https://github.com/user-attachments/assets/9572d04f-c520-4320-8521-a33919fa459e" width="960"> | <img src="https://github.com/user-attachments/assets/1ed1167b-3f54-4e29-b30b-86a127c73fcd" width="960"> |

| 실시간 채팅 페이지 유저2 | 신고 관리 페이지 |
| :--------: | :--------: |
| <img src="https://github.com/user-attachments/assets/0a862786-6b4c-44d8-badd-2424b418bece" width="960"> | <img src="https://github.com/user-attachments/assets/01b12c2e-2c5c-4efd-ab30-8f49b6616383" width="960"> |

| 댓글/게시글 신고 페이지 |
| :--------: |
| <img src="https://github.com/user-attachments/assets/9251e4b6-7e02-4dfc-bbe6-e09dacf0c2ed" width="960"> |

## Contribute File Structure
```
├─main
│  │  .DS_Store
│  │
│  ├─java
│  │  ├─com
│  │  │  └─Shoots
│  │  │      │  ShootsApplication.java
│  │  │      │  WebConfig.java
│  │  │      │
│  │  │      ├─controller
│  │  │      │      ReportController.java

│  │  │      │
│  │  │      ├─domain
│  │  │      │      Board.java
│  │  │      │      chat_room.java
│  │  │      │      chat_room_log.java
│  │  │      │      Report.java

│  │  │      │
│  │  │      ├─livechat
│  │  │      │  │  ChatController.java
│  │  │      │  │  ChatMessage.java
│  │  │      │  │  MessageType.java
│  │  │      │  │
│  │  │      │  └─config
│  │  │      │          MyWebSocketHandler.java
│  │  │      │          WebSocketConfig.java
│  │  │      │          WebSocketEventListener.java
│  │  │      │
│  │  │      ├─mybatis
│  │  │      │  └─mapper
│  │  │      │          chat_mapper.java
│  │  │      │          ReportMapper.java
│  │  │      │
│  │  │      ├─security
│  │  │      │      WebSocketSecurityConfig.java
│  │  │      │
│  │  │      ├─service
│  │  │      │  │  chat_service.java
│  │  │      │  │  chat_serviceImpl.java
│  │  │      │  │  ReportService.java
│  │  │      │  │  ReportServiceImpl.java
│  │  │      │  │
│  │  │      │
│  │  │
│  └─resources
│      │  application-deploy.properties
│      │  application.properties
│      │
│      ├─mybatis
│      │  ├─config
│      │  │      mybatis-config.xml
│      │  │
│      │  └─mapper
│      │          Chat.xml
│      │          Report.xml
│      │
│      ├─static
│      │  ├─css
│      │  │      livechat.css
│      │  ├─js
│      │  │  │  livechat.js
│      │  │  │  postList.js
│      │  │  │  postView.js
│      │  │  │
│      │  │
│      │  └─sql
│      │          chat_room.sql
│      │          report.sql
│      │
│      └─templates
│          ├─admin
│          │      postList.html
│          │      reportList.html
│          │
│          │
│          ├─livechat
│          │      livechat.html
│          │
│          ├─notice
│          │      noticeDetail.html
│          │      noticeList.html
│          │
│          ├─post
│          │      post_list.html
│          │      post_view.html
│          │
│          └─report
│                  post1.html
│                  post2.html
│                  reportAdd.html
│                  reportList.html
│                  reportView.html
│
└─test
    └─java
        └─com
            └─Shoots
                    ShootsApplicationTests.java
```                    
