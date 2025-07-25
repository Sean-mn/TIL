# 캐시(Cache)란?

**캐시(Cache)** 란 자주 사용하는 값을 미리 복사해 놓은 임시 저장소이다. <br>
[메모리 계층](memory_hierarchy.md)에서도 볼 수 있듯이 캐시는 저장 공간이 작고 비용이 비싸지만 매우 빠른 성능을 제공한다. <br>
이는 CPU가 메인 메모리(RAM)에 직접 접근하는 시간보다 캐시에 접근하는 시간이 훨씬 짧기 때문에, 전체 시스템 <br> 성능을 높이는 데 중요한 역할을 한다.

<br>

## Local Cache vs Global Cache

**Local Cache(로컬 캐시)** 와 **Global Cache(글로벌 캐시)** 는 캐시의 범위와 접근 대상에 따라 구분된다.
| 항목     | Local Cache                 | Global Cache             |
| ------ | --------------------------- | ------------------------ |
| **범위** | 특정 사용자나 프로세스에 국한됨           | 여러 사용자 또는 시스템 전체가 공유함    |
| **예시** | CPU 코어 내부의 L1 캐시, 사용자 세션 캐시 | 웹 서버의 공유 메모리 캐시, Redis 등 |
| **속도** | 더 빠름 (메모리와 가까움)             | 상대적으로 느림 (범위가 넓음)        |
| **장점** | 빠른 접근 속도, 사용자 맞춤 최적화        | 데이터 중복 방지, 자원 효율적 관리     |
| **단점** | 캐시 일관성 문제, 데이터 중복 발생 가능     | 성능 저하 가능성, 병목 현상 발생 가능   |


- Local Cache는 특정한 사용자 또는 쓰레드, 프로세스 단위로 유지되는 캐시로, 속도는 빠르지만 다른 컴포넌트와는 공유되지 않는다.

- Global Cache는 여러 사용자나 프로세스가 공유할 수 있는 캐시로, 일관성을 유지하며 자원을 절약할 수 있지만, 접근 속도는 상대적으로 느릴 수 있다.