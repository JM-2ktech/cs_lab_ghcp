---
title: 용어집
nav_order: 9
---

# 용어집 📖

이 과정에서 쓰는 핵심 용어를 처음 등장 순서대로 정리했습니다. 각 항목에 고정 id가 붙어 있어 다른 페이지에서 `./glossary.html#id`로 바로 연결할 수 있습니다(id는 각 항목 제목 옆에 회색 코드로 표기).

### 하네스 (harness) `#harness`
{: #harness }
Copilot Studio에서 만든 것을 실제로 돌리는 런타임. 모델과 내가 만든 것 사이에 있으면서, 언제 모델을 부를지·무엇을 보낼지·돌아온 것을 어떻게 해석해 어느 도구를 부를지를 정한다. 하네스가 셋이고, 무엇을 고르느냐에 따라 쓸 수 있는 부품과 과금이 구분된다.

### GitHub Copilot 하네스 `#ghcp-harness`
{: #ghcp-harness }
셋 중 추론이 긴 다중 단계 업무를 맡는 쪽. 목표를 받아 스스로 단계를 나누고, Word·Excel·PowerPoint·PDF를 만들고 고치며, [Skill](#skill)·[Memory](#memory)·[Sandbox](#sandbox)를 쓴다. 오늘 쓰는 것이 이것이다. 과금은 [Copilot Credits](#copilot-credits).

### 표준 하네스 `#standard-harness`
{: #standard-harness }
규칙 기반 Agent와 정해진 대화를 맡는 쪽. 내가 그린 [토픽](#topic)과 규칙을 그대로 따라 예측 가능하게 움직인다. Copilot Studio 초급 과정이 다루는 자리.

### Copilot 채팅 하네스 `#chat-harness`
{: #chat-harness }
M365 Copilot Chat 을 사내 자료로 확장하는 쪽. 사람을 정보에 잇는 것이 목적이라 파일 생성·[Skill](#skill)·[Memory](#memory)는 다루지 않는다. 오늘 이 하네스로 만드는 것은 없고, Lab 4에서 M365 Copilot 노드를 붙일 때 한 번 만난다.

### Agent `#agent`
{: #agent }
무엇을 해야 하는지 판단하고 실제 업무를 수행하는 주체. GHCP 하네스에서는 길을 미리 그려 두지 않고, 입력과 자료를 보고 무슨 일인지 스스로 판단한다.

### 토픽 (topic) `#topic`
{: #topic }
사용자의 말을 미리 정해 둔 경로로 분기시키는 [표준 하네스](#standard-harness)의 부품. **GHCP 하네스에는 없다.** 초급 과정의 개념을 그대로 옮겨 오면 가장 먼저 어긋나는 자리다.

### Knowledge `#knowledge`
{: #knowledge }
회사가 알고 있어야 하는 것. 제작자가 설계 시점에 붙여 두어 모든 대화가 같은 근거를 쓴다. 오늘은 비용 처리 규정이 여기 들어간다. 업로드는 PDF·Word·Excel·PowerPoint를 받는다.

### 첨부 (attachment) `#attachment`
{: #attachment }
사용자가 대화 중에 그때그때 올리는 파일. [Knowledge](#knowledge)와 다르다. 그 대화에서만 쓰이고, 주는 쪽이 사용자다. 지원 형식은 이미지·PDF·텍스트(txt·csv·html·md)·URL이고, 파일당 16 MiB, 대화 마지막 활동으로부터 28일 보존된다.

### Skill `#skill`
{: #skill }
업무를 수행하는 방법. 이름·설명·마크다운 지시문으로 된 재사용 가능한 덩어리다. 「무엇을 하라」가 아니라 **「이 일을 이런 방식으로 수행하라」**를 담는다. SKILL.md 한 장으로도 되고, 스크립트·템플릿·참고 문서를 함께 넣은 ZIP 패키지로도 올린다.

### Sandbox `#sandbox`
{: #sandbox }
파일과 데이터를 실제로 다루는 실행 공간. 파일 자체를 열어 전부 읽고 계산한다. 요약본을 건네받는 것과 다르다. 오늘 1,000행 대사가 여기서 돈다.

### 만들어진 파일 `#created-file`
{: #created-file }
Agent가 대화 중에 만들어 내려주는 파일. 응답 아래에 파일 카드로 붙고 **다운로드**로 받는다. 파일당 10 MB까지이고, 넘으면 응답에 나오지 않는다. 보존은 첨부와 같은 28일.

### Memory `#memory`
{: #memory }
사용자에게 지속적으로 적용되는 업무 맥락. 회사 규정은 여기 넣지 않는다. 그건 [Knowledge](#knowledge)다. 「이 사용자는 프로젝트 코드를 먼저 확인받기를 선호한다」가 여기 들어간다.

### Workflow `#workflow`
{: #workflow }
언제 시작하고 어떤 순서로 진행하며 결과에 따라 어디로 갈지를 통제하는 구조. 판단은 [Agent](#agent)에게 맡기고, 프로세스는 여기서 쥔다.

### Copilot Credits `#copilot-credits`
{: #copilot-credits }
GHCP 하네스의 사용량 기반 과금 단위. 만드는 것·테스트하는 것·쓰는 것이 모두 소비한다. 전체 데이터를 읽어 처리하면 그만큼 더 나간다.

### 대사 `#reconciliation`
{: #reconciliation }
두 자료를 정해진 키로 맞춰 보고 어긋난 것을 찾는 일. 오늘의 대사 키는 **승인일자 · 가맹점 · 금액** 셋이다(규정 §4.1). 행 수를 세는 것과 다르다.

### 명세 · 증빙 대장 `#statement-ledger`
{: #statement-ledger }
**명세**는 카드사에서 내려받은 결제 기록이고, **증빙 대장**은 직원들이 증빙을 올리며 등록한 목록이다. 둘은 원본이 다르므로 어긋날 수 있고, 그 어긋남을 찾는 것이 오늘의 업무다.

### 증빙 면제 `#exemption`
{: #exemption }
증빙 대장에 올리지 않아도 되는 건. 규정 §3.3이 정한 정기결제 계약 건이 여기 해당한다. **명세에는 있고 대장에는 없지만 불일치가 아니다.** 규정을 읽지 않으면 증빙 누락으로 잘못 잡힌다.

### 불일치 세 유형 `#three-mismatches`
{: #three-mismatches }
규정 §4.2가 정한 것으로, 이 셋 말고는 불일치로 분류하지 않는다.

- **증빙 누락**: 명세에는 있고 대장에는 없다
- **금액 불일치**: 승인일자와 가맹점은 같고 금액이 다르다
- **중복 증빙**: 같은 건이 대장에 두 번 이상 올라와 있다
