# .NET Framework란?

2002년에 Microsoft에서 공개한 소프트웨어 개발 프레임워크이다. <br>
주로 Windows 운영체제에서 실행되는 애플리케이션들을 개발하기 위해 사용된다.

C#, VB.NET, F#과 같은 언어들이 제공된다.<br>
현재는 .NET Core, .NET 5+ 등으로 발전되었지만 여전히 많은 Windows 앱이 .NET Framework 위에서 동작한다.

<br>

## .NET Framework의 특징

### 1. CLR (Common Laungage Runtime)
- .NET Framework가 실행되는 가상 머신이다.
- C#, VB.NET, F#과 같은 언어로 작성된 코드를 IL(Intermediate Language)로 변환해 실행한다.
- 카비지 컬렉션(GC), 에외 처리, 메모리 관리 등을 자동으로 지원한다.


### 2. BCL (Base Class Language)
- 파일 입출혁, 데이터베이스 연결, 네트워킹, XML 처리 등 다양한 기본 기능을 제공하는 라이브러리 모음이다.


### 3. 언어 간 호환성 
- C#, VB.NET 등의 다양한 언어로 개발해도 CLR 위에서 돌아가므로 서로 쉽게 연동이 가능하다.

<br>

## .NET Framework의 장단점

### 장점
1. Windows에 최적화되어 있어 데스크톱/서버 개발에 강력하다.

2. 풍부한 라이브러리와 툴 지원한다. (특히 Visual Studio)

3. 언어 호환성이 뛰어나고 생산성이 높다.

### 단점

1. Windows 종속성이 강하다. (Linux/Mac 지원 어려움)

2. 무겁고 업데이트 주기가 느려 최신 기술 반영이 늦다.

3. 현재는 .NET Core 및 .NET 5+ 로 대체되는 추세이다.