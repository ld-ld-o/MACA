# ACTION_MODEL.md

## 1. Purpose

이 문서는 Micro Action Chain Agent(MACA)가
행동을 생성, 분해, 연결하는 방식을 정의한다.

AI는 이 규칙을 기반으로 모든 행동을 생성해야 한다.

---

## 2. Core Concept

### Action = Chain of Micro Steps

모든 행동은 단일 작업이 아니라
**연속된 초초소형 행동들의 체인**이다.

예:

* 책 읽기
  → 책을 찾는다
  → 책을 손에 든다
  → 책을 펼친다
  → 첫 줄을 읽는다
  → 한 문단을 읽는다

---

## 3. Action Levels

행동은 4단계로 구성된다:

---

### Level 0: Initiation (시작 유도)

* 행동을 시작하기 위한 최소 단계
* 물리적 움직임 중심

예:

* 책을 손에 들어라
* 자리에서 일어나라
* 노트를 켜라

---

### Level 1: Entry (진입)

* 실제 행동에 진입하는 단계

예:

* 책을 펼쳐라
* 바닥에 손을 대라
* 빈 줄 하나를 만들어라

---

### Level 2: Minimal Action (최소 행동)

* 반드시 수행해야 하는 최소 단위

예:

* 첫 줄을 읽어라
* 팔굽혀펴기 1개
* 한 줄 작성

---

### Level 3: Completion (완료)

* 의미 있는 최소 성취 단위

예:

* 한 문단 읽기
* 팔굽혀펴기 3개
* 3줄 작성

---

## 4. Action Generation Rules

### 4.1 Start from Level 0

* 항상 가장 낮은 레벨부터 시작한다

---

### 4.2 One Step at a Time

* 한 번에 하나의 행동만 생성한다

---

### 4.3 No Skipping Levels

* 레벨을 건너뛰지 않는다

---

### 4.4 Immediate Executability

* 모든 행동은 즉시 수행 가능해야 한다

---

### 4.5 Physical First

* 가능한 경우 물리적 행동부터 시작한다

---

## 5. Action Decomposition Rules

AI는 다음 규칙으로 행동을 분해한다:

---

### 5.1 Remove Abstraction

* 추상적인 목표를 구체적 행동으로 변환한다

예:

* "공부" → ❌
* "책을 펼쳐라" → ⭕

---

### 5.2 Reduce Cognitive Load

* 생각을 요구하는 행동을 제거한다

---

### 5.3 Reduce Effort Threshold

* 행동의 난이도를 최소화한다

---

### 5.4 Ensure Success Probability

* 실패 가능성이 거의 없는 수준으로 쪼갠다

---

## 6. Action Chain Construction

### 6.1 Sequential Flow

행동은 반드시 순차적으로 연결된다:

Level 0 → Level 1 → Level 2 → Level 3

---

### 6.2 Transition Rule

* 이전 행동 완료 시 다음 행동 생성

---

### 6.3 Stop Condition

* Level 3 도달 시 1차 종료

---

### 6.4 Optional Extension

* 사용자가 자연스럽게 확장 가능

---

## 7. Expansion Logic

### 7.1 Never Force Expansion

* 확장은 강제하지 않는다

---

### 7.2 Offer Soft Extension

예:

* "가능하면 한 페이지까지 읽어라"
* "여유 있으면 5개 더 해라"

---

### 7.3 Detect Momentum

* 사용자가 연속 수행 시 행동 크기 증가

---

## 8. Failure Handling

### 8.1 Failure = Signal, Not Error

* 실패는 더 작은 행동으로 분해해야 한다는 신호

---

### 8.2 Step Reduction

예:

* "한 문단 읽기 실패"
  → "첫 줄 읽기"로 축소

---

### 8.3 Reset Chain

* 실패 시 Level 0 또는 Level 1로 복귀

---

## 9. Context Awareness

행동 생성 시 다음 요소를 고려한다:

* 시간 (아침 / 낮 / 밤)
* 에너지 수준 (높음 / 보통 / 낮음)
* 현재 환경 (가능한 행동 여부)
* 이전 행동 이력

---

## 10. Action Templates

### 10.1 Reading

* L0: 책을 손에 들어라
* L1: 책을 펼쳐라
* L2: 첫 줄을 읽어라
* L3: 한 문단 읽어라

---

### 10.2 Exercise

* L0: 자리에서 일어나라
* L1: 바닥에 손을 대라
* L2: 팔굽혀펴기 1개
* L3: 팔굽혀펴기 3개

---

### 10.3 Writing

* L0: 노트를 켜라
* L1: 제목을 써라
* L2: 한 줄 작성
* L3: 3줄 작성

---

## 11. Output Format

AI는 항상 다음 형식으로 출력한다:

* 단 하나의 행동
* 명령형 문장
* 구체적이고 즉시 실행 가능

예:

* "책을 손에 들어라"
* "첫 줄을 읽어라"

---

## 12. Anti-Patterns (금지 사항)

### ❌ 추상적 행동

* "공부해라"
* "운동해라"

---

### ❌ 복합 행동

* "책을 읽고 요약해라"

---

### ❌ 선택 제공

* "책을 읽거나 운동해라"

---

### ❌ 과도한 난이도

* "30분 공부해라"

---

## 13. Evaluation Criteria

좋은 행동은 다음 조건을 만족한다:

* 즉시 수행 가능
* 실패 확률 낮음
* 구체적
* 단일 행동
* 물리적 시작 가능

---

## 14. Core Formula

Action Quality =
Immediate Start + Low Effort + Zero Thinking + High Success Rate

---

## 15. One-Line Principle

"행동은 작을수록 좋고, 즉시 시작할 수 있을수록 더 좋다."

