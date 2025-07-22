# HTTP 매서드 PUT과 PATCH의 차이

HTTP 매서드에서 PUT과 PATCH 매서드는 둘 다 리소스에 대한 업데이트를 뜻 한다.
<br>
두 메서드 모두 업데이트를 목적으로 하지만, 업데이트의 범위와 방식에서 차이가 있다

<br>

## PUT

PUT 매서드는 **리소스의 모든 것**을 업데이트하는 매서드이다.

아래와 같은 리소스가 있다고 할 때,
| 플레이어  | 데이터  |
|----------|--------|
| name     |  Sean  |
| level    |    5   |

<br>

PUT 요청을 보내면

```json
PUT /player
Content-Type: application/json

{
    "name" : "Sean2",
    "level" : 10
}
```
<br>

| 플레이어  | 데이터  |
|----------|--------|
| name     |  Sean2  |
| level    |    10   |

이러한 응답을 받는다.
하지만 이번에는 레벨을 넣지 않고 요청을 보내면,
```json
PUT /player
Content-Type: application/json

{
    "name" : "Sean2"
}
```

<br>


| 플레이어  | 데이터  |
|----------|--------|
| name     |  Sean2  |
| level    |    (삭제됨)   |

요청을 보내지 않은 속성은 삭제되게 된다.

<br>

## PATCH

PATCH 매서드는 **리소스의 일부**를 업데이트하는 매서드이다. <br>
변경하고자 하는 필드만 포함하여 요청하면, 해당 필드만 업데이트되고 나머지 필드는 그대로 유지된다.

아래와 같은 리소스가 있다고 할 때,
| 플레이어  | 데이터  |
| ----- | ---- |
| name  | Sean |
| level | 5    |


PATCH 요청을 보내면
```json
PATCH /player
Content-Type: application/json

{
    "level": 10
}
```

<br>

| 플레이어  | 데이터  |
| ----- | ---- |
| name  | Sean |
| level | 10   |

이러한 응답을 받는다.

PUT과 달리 하나의 속성만 요청을 보내도 요청에 포함된 범위만 수정된다.