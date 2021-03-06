# When to Use What: REST, GraphQL, Webhooks, & gRPC

API 설계에는 다양한 방법이 있다.

* REST
* gRPC
* GraphQL
* Webhooks

## REST

REST 설계는 가장 대중적으로 알려져 있다. REST는 Roy Fielding이 처음 정의했다. 웹 API 설계를 표준화하는 무상태 디자인 방법을 사용하여 웹 서비스를 설계하는 기초적인 작업이었다. REST 자체는 상태가 존재하지 않는다. 자원(Resource)을 표현하려고 무상태 방식을 차용했다. REST에 사용할 GET, POST, PUT 그리고 다른 HTTP 메소드를 표준으로 정의했다.

REST API의 최종 목적은 클라이언트와 서버를 느슨하게 연결하기 위함이다. 클라이언트와 서버 모두 자원을 자유롭게 조작하게 해준다.

REST는 계층화된 설계 구조를 제공한다. 이 중 현대적이고 효율적인 캐싱과 높은 확장성을 제공한다.

## gRPC

REST가 확실히 현대적이라면, gRPC는 오래된 방법이다. RPC 는 Remote Procedure Call 의 준말이다. RPC는 원격 서버의 작업을 실행하는 메소드다. 장단점이 분명하다.

gRPC와 REST의 차이점은 다음과 같다. REST는 요청을 보낼 때 표준화된 내용으로 통신한다. 반면, RPC는 계약 관계다. 클라이언트는 실행의 의무가, 원격 서버에는 자원을 이용한 조작과 계산의 의무를 가진다.

이러한 특징으로 RPC는 IoT 기기와 저전력 기기들에게 널리 쓰인다. REST는 자원을 중점으로 요청하는 반면, RPC는 극단적으로 저전력인 상황에서도 쓰일 수 있다. gRPC는 RPC 개념을 확장시키고 더 넓은 기능들을 포함시켰다.

gRPC에 추가된 가장 큰 특징은 `protobufs`의 개념이다. `protobufs`는 데이터를 **직렬화**하는 플랫폼 시스템 또는 언어를 의미한다. gRPC는 구글의 토큰 기술 기반 시스템인 SSL/TLS를 활용하여 효율적이고 강력한 인증 시스템을 사용한다.

## GraphQL

GraphQL은 클라이언트 서버 관계에 주목하여 오랜 통신 방법을 뒤집었다. 더 이상 서버가 주는 자원의 API 통신을 고집할 필요가 없다. GraphQL로 클라이언트가 어떤 자원을 원하는지 서버에게 보내주고 서버가 그에 맞는 자원을 반환한다. 복잡한 정보를 얻기 위해 다양한 API 콜을 할 필요가 없으며 한 번의 통신으로도 얻을 수 있다.

## Webhooks

GraphQl은 API를 확장시키는 선택지인 반면, Webhooks는 아예 색다른 자원 접근 방법이다. Webhook은 상대적으로 간단하다. 어떤 이벤트가 발생했을 때 HTTP POST 메소드로 요청을 보낸다.

전통적인 클라이언트 서버의 관계를 역전 시켰다. 서버가 자원을 수정하면, 자동적으로 클라이언트에게도 자원 정보가 보내진다. 서버에서 데이터를 `푸시`한다. 클라이언트는 더이상 요청하는 주체가 아니며, 수동적으로 받는 주체가 된다.

## 참고 문서

https://nordicapis.com/when-to-use-what-rest-graphql-webhooks-grpc/