# REST란?

**REST**는 **Representational State Transfer**의 약자로, <br>
자원을 URI로 표현하고, 그 자원의 상태(정보)를 HTTP를 통해 주고받는 아키텍처 스타일이다.

**REST**는 웹의 기본 철학을 따르며, <br>
리소스를 명확하게 표현하고, 그 상태를 전송하는 방식으로 동작한다.

<br>

## REST의 3가지 구성 요소

- **자원(Resource)** : HTTP URI

- **자원에 대한 행위(Verb)** : HTTP Method를 사용한 CRUD

- **자원의 표현(Representation)** : 자원의 상태를 전달하는 데이터

<br>

## REST의 특징

- Client-Server (클라이언트-서버 구조)

- Stateless (무상태성)

- Cachable (캐시 처리 가능)

- Layered System (계층 구조)

- Uniform Interface (인터페이스 일관성)

- Self-Descriptiveness (자체 표현)

<br>

# REST API란?

**REST API**란 이름 그대로 REST의 원리를 따르는 API이다. <br>
REST의 원리를 따르며 API를 설계하려면 몇가지 규칙이 있다.

<br>

## REST API 설계 규칙

### 1. URI에는 명사를, 소문자를 쓴다.
```
Bad Example  : http://example.com/Finding/
Good Example : http://example.com/find/
```

### 2. 마지막에는 슬래시(/)를 포함하지 않는다.
```
Bad Example  : http://example.com/find/
Good Example : http://example.com/find
```

### 3. 언더바(_) 대신 하이폰(-)을 이용한다.
```
Bad Example  : http://example.com/find_player
Good Example : http://example.com/find-player
```

### 4. 행위를 포함하지 않는다.
```
Bad Example  : http://example.com/delete-player/1
Good Example : http://example.com/player/1
```

<br>

# RESTful API란?

**RESTful API**란 REST 아키텍처 스타일을 잘 준수하여 설계된 API를 말한다. <br>

단순히 REST API를 만든다고 해서 모두 RESTful하다고 할 수는 없다. <br>

URI 설계, HTTP Method 사용, 상태 표현 방식 등 REST의 원칙을 일관성 있게 따르는 것이 중요하다.