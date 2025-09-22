# 봉투 패턴 (Envelop Pattern)

봉투 패턴(Envelop Pattern)은 데이터를 캡슐화하는 방법 중 하나이다. <br>
실제 데이터와 그 데이터를 둘러싸는 메타데이터를 분리하여 표현하는 패턴이다.

핵심 정보가 있고, 이를 부가 정보들이 감싸는 방식으로 통신하거나 처리하는 방식이다.

비유하자면 우리가 편지를 보낼 때 편지지(핵심 정보)를 봉투(부가 정보)에 넣어서 보내는 방식과 비슷하다고 볼 수 있다.

<br>

## 예시

```json
{
    "userId": 1,
    "playerName": "A",
    "playerLevel": 10
}
```
위와 같은 플레이어의 데이터를 보내주는 메세지가 있다고 가정을 해보자.

우리가 여러 플레이어의 데이터를 받으려면 일반적인 방법으로는
```json
{
    "data": [
        {
            "userId": 1,
            "playerName": "A",
            "playerLevel": 10
       },{
            "userId": 2,
            "playerName": "B",
            "playerLevel": 10
        },{
            "userId": 3,
            "playerName": "C",
            "playerLevel": 10
        },
        ...
        ,{
            "userId": 99,
            "playerName": "Z",
            "playerLevel": 10
        }
    ]
}
```

위와 같이 단순히 배열에 데이터를 넣어서 던져주는 형태일 것이다.

<br>

## 봉투 패턴 적용

하지만, 만약에 플레이어 데이터의 개수를 클라이언트에게 알려줘야 한다면? <br>
혹은 응답 성공 여부, 요청 시간, 에러 코드 같은 추가 정보도 같이 전달해야 한다면 단순 배열만으로는 부족하다.

이런 경우 봉투 패턴이 사용된다.

```json
{
    "meta": {
        "playerCount": 3,
        "success": true
    },
    "data":  [
        {
            "userId": 1,
            "playerName": "A",
            "playerLevel": 10
        },
        {
            "userId": 2,
            "playerName": "B",
            "playerLevel": 10
        },
        {
            "userId": 3,
            "playerName": "C",
            "playerLevel": 10
        }
    ]
}
```
- `data` : 실제 데이터
- `meta` : 부가 정보