# 레이스 컨디션 (Race Condition)이란?

**레이스 컨디션 (Race Condition)** 이란 프로그램에서 둘 이상의 스레드나 프로세스가 동시에
<br>
같은 자원에 접근하면서 실행 순서에 따라 결과가 달라지는 상황이다.

쉽게 말해, 누가 먼저 실핼하느냐에 따라 결과가 달라느는 문제이다.

<br>

## 레이스 컨디션 예시

```csharp
int count - 0; // 공유 자원

// 여러 스레드가 동시에 Increase()를 실행
public void Increase()
{
		count++;
}
```

만약 여러 스레드가 `Increase()`  함수를 실행시키면 문제가 발생할 수 있다.

### 왜 문제가 발생할까?

- `count++` 은 한번에 `count` 값에 1을 더하는 것 같지만, 사실 3가지 단계로 이루어져 있다.
    1. `count`의 값을 읽음
    2. 1을 더함
    3. 1을 더한 결과를 `count`에 씀

이 과정에서 두 스레드가 동시에 `count`를 읽고, 더하고, 쓰게 되면 **둘 다 같은 값을 읽게 되어 증가가 누락** 

**되는 상황이 발생**할 수 있다.

<br>

## 해결 방법

### 1. 락 (Lock) 사용하기

- `lock`, `mutex`  등을 이용하여 **자원에 접근하는 코드를 한 번에 하나만 실행**되게 해준다.
    
    ```csharp
    object _lockObj = new object();
    int count = 0; // 공유 자원
    
    public void Increase()
    {
    		lock (_lockObj)
    		{
    				count++;
    		}
    } 
    ```
    

### 2. Interlocked 클래스 사용하기 (C#)

- **원자적 연산 기능을 제공**하는 `Interlocked` 클래스를 사용하여 **레이스 컨디션을 방지**한다.
    
    ```csharp
    int count = 0; // 공유 자원
    
    public void Increase()
    {
    		Interlocked.Increment(ref count);
    }
    ```
    

### 3. Volatile, Atomic 등의 언어 별 키워드 사용하기

- 공유 자원의 접근을 동기화하거나, 원자성을 보장하는 도구를 활용한다.