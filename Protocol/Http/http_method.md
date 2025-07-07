# Http Method란?

**Http Method**는 클라이언트와 서버 사이의 **요청과 응답 데이터를 전송하는 방식**이다.

Method는 총 9개가 있으며, `GET`, `POST`, `PUT`, `PATCH`, `DELETE`를 주로 사용한다.

<br>

## Http Method의 종류

| 메서드         | 설명                              |
| ----------- | ------------------------------- |
| **GET**     | 서버로부터 리소스를 **조회**할 때 사용         |
| **POST**    | 서버에 **새로운 리소스를 생성**할 때 사용       |
| **PUT**     | 리소스를 **전체 수정(교체)** 할 때 사용    |
| **PATCH**   | 리소스를 **부분 수정**할 때 사용            |
| **DELETE**  | 서버의 리소스를 **삭제**할 때 사용           |
| **HEAD**    | `GET`과 같지만, **응답 본문 없이 헤더만 조회** |
| **OPTIONS** | 서버가 지원하는 **메서드 목록을 확인**할 때 사용   |
| **TRACE**   | 서버까지의 **요청 경로를 테스트**할 때 사용      |
| **CONNECT** | **프록시 터널링(HTTPS 연결)** 에 사용   |

<br>

## 자주 쓰이는 Http Method

### 1. GET
`GET` 메서드는 서버에서 **리소스를 조회**할 때 사용된다. <br>
서버의 데이터를 **변경하지 않고**, 오직 **데이터를 요청**하는 역할만 수행한다.

예시) /user/123의 정보 조회하기

```
GET /users/123 HTTP/1.1
Host: example.com
```

### 2. POST
`POST` 메서드는 서버에 **새로운 리소스를 생성**하거나 **데이터를 전송**할 때 사용된다.

클라이언트가 서버에 데이터를 보내면, 서버는 그 데이터를 처리하여 새로운 리소스를 만들거나, 기존 데이터를 수정하는 등의 작업을 수행한다.

**예시)** 새로운 사용자 등록하기

```
POST /users HTTP 1.1
Host: example.com
Content-Type: application/json

{
	"name" : "Sean-mn",
	"email" : "abc123@example.com"
}
```

### 3. PUT 
`PUT` 메서드는 서버에 있는 **기존 리소스를 완전히 대체할 때 사용**된다.

보낸 데이터로 **전체를 덮어쓰기** 때문에, 수정할 때도 **모든 필드를 함께 보내는 것**이 일반적이다.

**예시)** ID가 123인 사용자 정보 전체 수정하기

```
PUT /users/123 HTTP/1.1
Host: example.com
Content-Type: application/json

{
	"name": "Sean-mn",
	"email": "abc123@example.com"
}
```

### 4. PATCH
`PATCH` 메서드는 서버에 있는 **리소스를 일부만 수정할 때 사용**된다. <br>
`PUT` 과는 다르게, **변경하고 싶은 필드만 선택적으로 보내면** 된다.

**예시)** ID가 123인 사용자 이메일만 수정하기

```
PATCH /users/123 HTTP/1.1
Host: example.com
Content-Type: application/json

{
	"email": "abc123@example.com"
}
```

### 5. DELETE
`DELETE` 메서드는 서버에 있는 **리소스를 삭제할 때 사용**된다.
<br>
성공하면 서버에서 해당 리소스가 사라지게 된다.

**예시)** ID가 123인 사용자 삭제하기
```
DELETE /users/123 HTTP/1.1
Host: example.com
```