# 항해99 WIL(3주차, 5/23~5/29)  

## 학습 내용

### 학습 키워드: Restful API, package.json

#### 1. Restful API

##### 1 ) Restful API란 무엇인가?

- Rest은 Representational State Transfer의 약자로, 무언가 대표할 수 있는 상태를 전송하는 것을 의미함. 클라이언트가 서버에 어떠한 정보를 요청했을 떄, 서버가 Rest원리에 따라 리소스를 클라이언트에 전달한다면, 이는 Restful한 API라고 이야기 할 수 있다.

##### 2 ) Restful API를 지키기 위한 조건

- RESTful System: 6guiding constraints(Restful한 API를 만들기 위해 필요한 6가지의 조건)
    - Client-server architecture :클라이언트의 종류가 어떠한 것(브라우저, 스마트폰 등)라도 데이터를 제공해야 함
    - Statelessness: 하나의 요청이 다른 요청에 영향 주면 안됨(html은 자동)
    - Cacheability: 캐시 가능하게 디자인(html은 자동)
    - Layered System: 클라이언트가 서버 계층이 어떠하던지 동일한 API를 사용해야 함
    - Code on Demand: 클라이언트가 원한다면 클라이언트가 수행해야하는 코드를 서버가 보내줄 수 있는지
    - Uniform interface: Fundamental to the design of any RESTful system
        - Resource Identification in requests: 클라이언트 요청에서 서버의 어떠한 리소스를 요청하는 것인지 식별할 수 있어야 한다. 서버 쪽의 리소스 저장 형태가 어떠하던지 클라이언트가 이해할 수 있는 형태(html, JSON 등)으로 데이터를 서버가 전송해줄 수 있어야 한다.
        - Resource manipulation through representation: 서버로부터 받은 해당 리소스에 대해서 향후 수정 시 어떤 형식으로 수정이 이루어져야 하는지에 대한 설명이 있어야 한다.
        - Self-descriptive message: 응답 데이터 안에는 클라이언트가 어떻게 처리해야하는지에 대한 설명이 있어야 한다.(예, html에 content type을 알려주는 것 등)
        - Hypermedia as the engine of application state(HATEOAS): 하이퍼미디어를 어플리케이션의 엔진 스테이트로 제공해야 한다. 클라이언트가 서버로부터 해당 URL로부터 할 수 있는 모든 액션들에 대한 설명을 링크된 url로 제공해주어야 한다.

#### 2. Package.json

- Package.json 파일은 개발자가 개발 중인 프로젝트에 대해 패키지 설치 정보 등 현재의 개발 환경을 정리한 문서.
- 해당 파일은 json 파일 양식으로 구분되어 있으며, key(항목) : value(내용)으로 각각 작업 환경들을 표시함. 
- 주요 내용 정리
  - package name: 패키지 이름
  - version: 프로젝트 버전
  - description: 프로젝트 설명
  - entry point: js파일의 실행 시작 지점. 가장 main이 되는 js파일
  - test command: 코드 테스트를 실시할 때 입력할 명령어
  - git repository: 코드가 저장된 원격 저장소 주소
  - keywords: npm에서 패키지를 쉽게 찾을 수 있는 keywords를 적는 공간
  - author: 작가, 패키지를 작성한 개발자
  - license: 패키지의 라이센스

<br>

### 이번주 진행 내용

#### 1. 주특기 기초 과정 마무리

- 항해 3주차에 돌입한 가운데, 지난주 금요일부터 진행했던 주특기(내 경우에는 Node.js) 기초 과정을 목요일부로 마무리지었다. 이번 과정의 경우에는 API 개발과 관련한 기초 강의를 제공하고, 이를 바탕으로 주어진 개인 및 팀 과제를 완료하는 것이 주요 내용이었다. 
- 지난주에 이어서 클라이언트의 Request에 따라 적절한 Response를 제공하는 API 개발을 완료하였다. 이번 기초과정의 경우에는 제공된 강의 내용이 상당히 함축되어 있었는데, 주특기 언어(자바스크립트 및 노드)와 관련한 도서와 강의를 추가적으로 보강하면서 해당 과제들이 어떠한 매거니즘으로 파악해야하는지에 대한 이해도가 상당히 늘어나가 되었다.
- 특히 과정이 진행되면서 코딩 과정에서 데이터가 들어오고 나가는 방식이 단순한 숫자 또는 문자형 자료에서 객체 형태로 이루어지는 경우가 많아졌는데, 앞으로는 이러한 객체 지향 프로그래밍에 대한 이해를 늘리기 위해서 현재 사용하고 있는 패키지와 코딩 내용에 대한 Document 항목을 자주 참고해야겠다는 생각을 하게 되었다.
