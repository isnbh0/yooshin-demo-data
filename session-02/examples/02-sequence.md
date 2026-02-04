# Sequence Diagram (시퀀스 다이어그램)

시퀀스 다이어그램은 여러 참여자 간의 메시지 흐름을 시간 순서대로 표현합니다.

아래 코드를 [mermaid.live](https://mermaid.live)에 붙여넣고 결과를 확인해 보세요.

```
sequenceDiagram
    participant 직원
    participant 예약시스템
    participant 관리자

    직원->>예약시스템: 회의실 예약 요청
    예약시스템->>예약시스템: 가용 여부 확인
    예약시스템-->>직원: 예약 가능 목록
    직원->>예약시스템: 회의실 선택
    예약시스템->>관리자: 예약 알림
    관리자-->>직원: 예약 확정
```

## 바꿔 보세요

- 참여자(`participant`)를 추가해 보세요 (예: `participant 상사`)
- 메시지 텍스트를 바꿔 보세요
- `Note over 직원,예약시스템: 여기에 메모` 를 중간에 추가해 보세요
