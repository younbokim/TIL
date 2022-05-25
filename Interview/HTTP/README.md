# HTTP

***

## Table of Contents
- [HTTP Request Method](####HTTP-Request-Method)
- [Status Code](####Status-Code)
- 

***

#### HTTP Request Method [[Back](##Table-of-Contents)]


##### 1. HTTP Request Method란?[[참고링크](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)]

- 클라이언트가 웹 서버에 Request를 할 때, 요청하고자 하는 내용을 전달하는 수단(Method). 서버가 어떠한 액션을 취하기를 요청.
- Request Method에는 총 8개(GET, POST, PUT, DELETE, PATCH, HEAD, OPTIONS, TRACE)의 Request Method가 존재함
- Request Method 관련 체크 포인트
  - Request has body: request시 클라이언트 쪽에서 내용을 전달하는지 여부
  - Successful response has body: response 성공 시 내용을 전달받는지 여부  
  - Safe: Request-Response 과정에서 서버의 상태(데이터 내용 등)에 영향을 주는지 여부
  - Idempotent: Request의 순서를 바꾸거나 재시도해도 의도했던 결과를 동일하게 돌려받는지 여부
  - Casheable: Response 내용을 향후 재사용을 위해 저장할 수 있는지 여부

##### 2. Request Method별 기능

- GET: 서버로부터 특정한 리소스(하드웨어, 소프트웨어, 데이터 등 구성 요소)를 가져오도록 요청
  - Request has body : No(서버에 추가 리소스를 제공하지 않음)
  - Successful response has body : Yes(서버로부터 리소스 전달 받음)
  - Safe : Yes(조회만 진행, 서버 리소스에 영향 안줌)
  - Idempotent : Yes(조회만 하기 때문에 Request 순서 및 횟수 변화에 따라 결과가 바뀌지 않음)
  - Casheable: Yes(응답 결과 재사용 가능)
- POST: 서버에 리소스를 전달하고 리소스의 업데이트 또는 수정을 요청
  - Request has body : Yes(서버에 추가 리소스를 제공)
  - Successful response has body : Yes(서버로부터 리소스 전달 받음)
  - Safe : No(서버의 리소스에 수정발생)
  - **Idempotent : No(데이터를 받고 로직을 처리하면서 요청 순서 또는 횟수에 따라 변화 발생 가능)**
  - Casheable: Yes or No(요청의 내용에 따라서 다름)
- PUT: 서버 내 특정된 리소스를 클라이언트가 지정하는 리소스로 수정할 것을 요청
  - Request has body : Yes(서버에 추가 리소스를 제공)
  - **Successful response has body : No(서버 내 리소스에 대한 수정만 진행)**
  - Safe : No(서버의 리소스에 수정발생)
  - **Idempotent : Yes(특정 위치의 리소스를 지정해서 변경 수행, 요청 순서 또는 횟수 변경이 영향을 주지 않음)**
  - Casheable: No(응답 결과 재사용 불가)
- DELETE:서버 내 특정된 리소스를 서버 내 삭제하도록 요청
  - Request has body : Yes or No
  - Successful response has body : Yes or No
  - Safe : No(서버의 리소스에 수정 발생)
  - **Idempotent : Yes(특정 위치의 리소스를 삭제, 이미 삭제되었을 경우 작업 수행 안함, 결론은 요청 순서 및 횟수에 영향 없음)**
  - Casheable: No(응답 결과 재사용 불가)
- PATCH: **서버 내 리소스 중 일부에 대한 업데이트 또는 수정을 요청할 때(부분 변경이 PUT와의 차이점)**
  - Request has body : Yes(서버에 추가 리소스를 제공)
  - **Successful response has body : Yes**
  - Safe : No(서버의 리소스에 수정 발생)
  - **Idempotent : No(특정 위치의 리소스 중 일부만을 변경, 결론은 요청 순서 및 횟수에 영향을 받을 수 있음)**
  - Casheable: No(응답 결과 재사용 불가)
- HEAD: GET 메서드 요청시 받을 헤더 내용만을 요청
  - Request has body : No(서버에 추가 리소스를 제공하지 않음)
  - **Successful response has body : No**
  - Safe : Yes
  - Idempotent : Yes
  - Casheable: No
- OPTIONS: 서버와의 통신 옵션 현황을 요청
  - Request has body : No
  - Successful response has body : Yes(통신 옵션 관련 정보들을 제공)
  - Safe : Yes
  - Idempotent : Yes
  - Casheable: No
- TRACE: 서버와의 연결 상태를 테스트
  - Request has body : No
  - Successful response has body : No
  - Safe : Yes
  - Idempotent : Yes
  - Casheable: No
- CONNECT: 서버와의 양방향 연결 시작
  - Request has body : No
  - Successful response has body : Yes
  - Safe : NO
  - Idempotent : No
  - Casheable: No

***

#### Status Code [[Back](##Table-of-Contents)]

##### 1. Status Code란?
- 클라이언트가 서버에 Request를 전달했을 때 서버 측의 Response 결과에 대한 설명을 알려주는 것
- Status Code는 크게 100단위 / 200단위 / 300단위 / 400단위 / 500단위로 구성
- 100단위: Informational, 정보를 나타냄
    - 100: Continue, 계속 요청하라
    - 102: Processing, 요청한 내용 처리 중
- 200단위: Successful, 성공을 나타냄, 성공적으로 서버가 처리되었을때 보내줌
    - 200: OK, 요청한 리소스를 성공적으로 찾음
    - 201: Created, 리소스가 성공적으로 생성됨
    - 204: No Content, 해당하는 데이터가 없음
- 300단위: Redirection, 요청 url이 다른 곳으로 왔을 때 위치를 재조정
    - 301: Moved Permanently, 요청 내용은 영구적으로 다른 url로 감
    - 302: Found, 임시적으로 다른 곳으로 감
    - 303: See Other, get 요청에서만 가능, 302와 유사
    - 307: Temporary Redirect, 임시 리다이렉트, post 요청에 대해서만 다른 곳으로 이동
    - 308: Permanent Redirect, 영구 리다이렉트, post 요청에 대해서만 다른 곳으로 이동
- 400단위: Client error, 클라이언트 쪽이 잘못된 url을 전송했을 때 보내줌
    - 400: Bad Request, 리퀘스트가 잘못되거나 API가 잘못 구성된 경우
    - 401: Unauthorized, 권한이 없는 상대방이 요청했을때(예시, 로그인)
    - 403: Forbidden, 로그인 사용자이만 권한이 없을 때
    - 404: Not Found, 원하는 url이 존재하지 않을 때
    - 405: Method Not Allowed, url 수정 및 삭제 허용 안될 떄
    - 409: Conflict, 리소스가 이미 존재하거나 충돌할 때
- 500단위: Sercer error, 서버 쪽의 에러가 발생할 경우
    - 500: Internet Server Error, 서버 내부 문제
    - 502: Bad Gateway, 중간 서버에서 응답 처리가 안될 떄
    - 503: Service Unavarilable, 서버가 준비되지 않음