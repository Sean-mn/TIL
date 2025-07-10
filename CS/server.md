# Web Server VS WAS

우리가 서버 공부를 하며 **Web Server**와 **WAS**를 많이 접하게 된다. <br>
이 둘은 클라이언트의 요청을 처리하는 서버라는 공통점은 있지만, 각자의 역할과 처리 방식에 분명한 차이점이 존재한다.

<br>

## Web Server란?

**Web Server**는 클라이언트의 요청 중에서 <br>
HTML, CSS, JS, 이미지, 영상 등과 같은 정적 파일을 처리하고 응답하는 서버이다.

### 역할
- 정적인 리소스를 클라이언트에게 전달

- 요청을 받아 알맞은 정적 파일로 응답

- WAS로 요청을 포워딩하는 역할도 수행

### 예시
- Apache HTTP Server

- Nginx

- Microsoft IIS

<br>

## WAS (Web Application Server)란?

**WAS**는 Web Server가 처리하지 못하는 동적인 요청을 처리하는 서버이다. <br>
즉, 비즈니스 로직이 필요한 요청은 WAS에서 처리된다.

### 역할
- Java, C#, Python 등으로 작성된 서버 애플리케이션 실행

- DB와의 연동, 사용자 인증, 게시판 글 작성 등 비즈니스 로직 처리

- 처리된 결과를 Web Server로 전달하여 사용자에게 응답


###  예시
- Apache Tomcat (Java 기반)

- ASP.NET Core (C# 기반)
