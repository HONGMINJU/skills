# FDE 작업 기록 키트

목적은 문서를 많이 만드는 것이 아니라, **무슨 문제를 풀고 있고, 무엇을 근거로 결정했으며, 다음에 무엇을 해야 하는지** 잃지 않는 것이다.

이 폴더에는 범용 지침·빈 기록 양식 7개와 **핵심 작업 스킬 7개 + 보조 스킬 2개**가 있다. 스킬은 에이전트가 읽는 작업 지침이며 완성 과제나 자동 실행 프로그램이 아니다. 공식 도구 승인·시험 환경 호환성·성적을 보장하지 않는다.

## 처음 쓰거나 현재 위치가 궁금할 때

[초보자 도움말](HELP.md)에서 바로 쓸 요청 문장을 찾는다. 두 안내 스킬은 추가 작업 단계가 아니라 어느 단계에서든 필요할 때 사용하는 보조 기능이다.

- [fde-status](skills/fde-status/SKILL.md): “지금 어느 단계야?”, “끝난 것과 남은 것 알려줘”. 실제 기록을 읽고 짧게 답하며, 조회만으로 개발·테스트·기록 변경을 시작하지 않는다.
- [fde-guide](skills/fde-guide/SKILL.md): “스킬 도우미”, “지금 뭘 쓰면 돼?”, “처음부터 쉽게 설명해줘”. 현재 상황에 맞는 기능과 요청 문장을 추천한다. 없는 스킬을 설치된 것처럼 안내하지 않는다.

현재는 스킬 파일을 작성한 상태이며 전역 설치나 시험 환경의 자동 발견을 확인하지 않았다. 파일을 명시해 읽게 하는 방식과 자동 등록은 다르다. [공식 스킬 문서](https://learn.chatgpt.com/docs/build-skills)는 형식과 호출 방식을 설명하지만, 시험에서 제공하는 버전의 호환성은 별도 확인 대상이다.

## 핵심 스킬 7개

| 스킬 | 언제 쓰는가 | 연결 기록 |
| --- | --- | --- |
| [fde-discover](skills/fde-discover/SKILL.md) | 문제·성공 기준·담당자 질문 정리 | MISSION, DECISIONS, STATE |
| [fde-data-audit](skills/fde-data-audit/SKILL.md) | 데이터 의미·품질·계산 계약, 조건부 반도체 점검 | DATA, EVIDENCE, MISSION |
| [fde-design](skills/fde-design/SKILL.md) | 최소 흐름·입출력 계약·작업 분해 | PLAN, DECISIONS, STATE |
| [fde-build](skills/fde-build/SKILL.md) | 작은 단위 구현·검증·통합 | 실제 코드, PLAN, EVIDENCE |
| [fde-verify](skills/fde-verify/SKILL.md) | 독립 기준 검증·실패 재현·재검사 | 테스트·로그, EVIDENCE |
| [fde-acceptance](skills/fde-acceptance/SKILL.md) | 대표 업무의 판단·행동과 실제 사용자 확인 | EVIDENCE, MISSION, PLAN |
| [fde-handoff](skills/fde-handoff/SKILL.md) | 코드 설명·선택형 설명 연습·실행 인계·제출 준비 | HANDOFF와 기존 근거 |

모든 스킬을 매번 순서대로 실행하지 않는다. 명확한 작은 수정은 필요한 구현·검증만 수행하고, 데이터가 없으면 데이터 점검을 강제하지 않는다. 상태·도움말만 물으면 읽기 전용으로 답한다. 스킬 9개가 에이전트 9명을 뜻하지 않는다.

처음 과제를 시작할 때의 요청 예:

> AI 사용이 허용된 과제 단계야. 실제 과제 README와 제공 파일을 먼저 읽고 fde-discover부터 현재 필요한 핵심 스킬을 적용해줘. 중요한 모호함만 질문하고, 답을 기다리는 동안 독립 작업은 계속해. 작은 실행 흐름부터 개발·검증하고 기록을 갱신해줘. 자동 설치·외부 전송·제출은 하지 마.

자동 발견이 확인되지 않았다면 먼저 실제 위치의 `skills/fde-discover/SKILL.md`와 필요한 지침 파일을 명시해 읽게 한다. 단순 안내·설계 요청과 실제 구현 요청의 범위를 구별한다.

## 기존 스킬 안의 선택 기능

- **설명 연습:** fde-handoff에서 사용자가 직접 설명하는 연습을 요청하면 실제 근거로 질문 하나 → 사용자 답변 → 피드백 → 재설명을 진행한다. 일반 설명 요청에는 퀴즈를 강제하지 않는다. 필요한 연습 상태만 작업 사본의 HANDOFF에 남기며, 제출물 확정 후 대기·평가 단계에서는 사용하지 않는다.
- **반도체 데이터 점검:** fde-data-audit는 실제 반도체 검사·공정 데이터이거나 해당 점검을 요청한 경우에만 [전용 체크리스트](skills/fde-data-audit/references/semiconductor-checklist.md)를 읽는다. 결과는 기존 DATA·MISSION·DECISIONS·EVIDENCE에 연결한다. 회사 이름만으로 적용하지 않는다.

두 기능은 기존 9개 스킬의 보완이며 새 스킬·에이전트·필수 단계가 아니다. 외부 `semi yield`·`semi spc` 계산 도구를 포함하거나 설치하지 않는다.

## 단계별 산출물

| 단계 | 필요한 산출물 | 기록의 기준 파일 | 다음 작업으로 넘어갈 근거 |
| --- | --- | --- | --- |
| 문제정의 | 사용자·업무·문제 한 문단, 필수 요구와 성공 기준, 질문·가정 | `MISSION.md` | 구현을 바꾸는 핵심 모호함이 해소되거나 영향이 명시됨 |
| 데이터 확인 | 행의 의미·키·단위·품질·조인 규칙, 표본 대조 결과 | `DATA.md` | 대표 입력을 해석할 수 있고 중요한 데이터 위험이 드러남 |
| 개발 설계 | 최소 실행 흐름, 구성·입출력 계약, 작업 순서·파일 담당, 검증 계획 | `PLAN.md` | 첫 구현 단위와 기대 결과가 명확함 |
| 개발 | 실제 코드·설정·결과물, 변경 요약과 구현 위치 | 실제 파일 + `PLAN.md` | 대표 입력부터 출력까지 동작함. 문서만으로 완료 처리하지 않음 |
| 테스트 | 테스트 코드·실행 로그·검산 결과, 실패·수정·재검사 기록 | 실제 테스트/로그 + `EVIDENCE.md` | 필요한 기준을 실제 관찰로 확인하고 미검증을 구분함 |
| 현업 시나리오 확인 | 사용 절차, 기대하는 업무 판단, 실제 관찰·피드백·남은 차이 | `EVIDENCE.md` | 기술적 성공과 업무상 유용성을 구분해 확인함 |
| 설명·인계 | 입력→처리→출력 설명, 선택 이유, 실행법, 한계, 제출 점검 | `HANDOFF.md` | 다른 사람이 실행·이해할 수 있고 필수 산출물을 확인함 |

테스트 기준은 설계 때 정하고, 테스트와 설명은 개발 중에도 수행한다. 데이터 발견이나 담당자 답변으로 기준이 바뀌면 필요한 단계만 다시 살핀다.

## 기록 파일은 7개

- [STATE.md](templates/STATE.md): 새 세션의 입구. 현재 단계, 가장 큰 위험, 다음 행동, 읽을 파일만 요약한다.
- [MISSION.md](templates/MISSION.md): 문제·요구·질문·가정의 기준 기록이다.
- [DATA.md](templates/DATA.md): 데이터 의미와 점검 결과를 보관한다. 원본 데이터 전체를 복제하지 않는다.
- [PLAN.md](templates/PLAN.md): 설계·입출력 계약·작업 상태·파일 담당을 보관한다.
- [EVIDENCE.md](templates/EVIDENCE.md): 검증 실행과 현업 시나리오 관찰의 근거를 보관한다.
- [DECISIONS.md](templates/DECISIONS.md): 중요한 선택과 이유, 기각한 대안, 변경 이력을 보관한다.
- [HANDOFF.md](templates/HANDOFF.md): 제출 확정 전에 필요한 실행·설명·인계 내용을 정리한다.

새 질문은 MISSION, 새 결정은 DECISIONS, 실행 결과는 EVIDENCE에 쓴다. STATE에는 요약과 링크만 둔다. 코드를 수정했다고 테스트 성공을 추정하거나 HANDOFF에 별도 성능 수치를 만들지 않는다.

## 적용 방법과 공개 범위

공개 원본은 [HONGMINJU/skills](https://github.com/HONGMINJU/skills)다. 현재 공식 안내와 제공 환경에서 공개 저장소 반입을 허용하는 경우, 기존 파일과 겹치지 않는 위치에서 다음처럼 가져올 수 있다. 이 명령은 파일을 내려받을 뿐 스킬 설치·자동 등록을 수행하지 않는다.

```sh
git clone https://github.com/HONGMINJU/skills.git fde-kit
```

가져온 뒤에는 다음처럼 요청한다. 폴더 이름이나 위치가 다르면 실제 경로로 바꾼다.

> fde-kit/AGENTS.md와 fde-kit/README.md를 읽고 현재 요청에 필요한 스킬만 적용해줘. 중요한 모호함만 질문하고, 답변과 무관한 독립 작업은 계속해줘. 설치·외부 전송·제출은 하지 마.

1. 개인 준비 기록과 실제 과제 기록은 공개 원본과 분리해 보관한다. `templates/`는 빈 상태로 유지한다.
2. 시험 환경에서는 공식 안내에서 허용한 경로로 공개 자료를 가져온다. 개인 PC 파일 업로드를 전제로 하지 않는다.
3. 과제에 기존 문서나 지정 양식이 있으면 그것을 우선하고 같은 내용을 중복 생성하지 않는다.
4. 별도 기록이 필요하면 실제 과제 작업공간 안에 양식의 작업 사본을 만든다. 위치는 제공 환경과 제출 규칙을 확인해 정한다. `docs/fde/`는 위치 예시일 뿐 공식 경로가 아니다.
5. DATA는 데이터가 있을 때, HANDOFF는 필요한 내용이 생겼을 때 작성한다. 빈 문서를 채우려고 사실이나 테스트를 만들지 않는다.
6. 이 폴더를 하위 디렉터리에 clone했다고 상위 과제에 지침이 자동 적용되지는 않는다. 제공 환경에서 허용하면 `AGENTS.md`를 명시적으로 읽게 하거나 기존 지침과 충돌 없이 반영한다. 인증·전역 설정·Codex 버전을 바꾸지 않는다.
7. 공개 후보는 범용 지침과 **빈 양식**뿐이다. 작성한 과제 기록·문제·데이터·코드·결과·개인 안내문을 이 공개 원본에 넣거나 Push하지 않는다.

이 키트는 자동 설치·자동 저장·플랫폼 제출을 수행하지 않는다. 에이전트가 작업 중 파일을 갱신하는 방식이다.

대회에서 이 공개 자료를 활용한다면 결과 통지 전까지 저장소의 공개 상태를 유지한다. 공개돼 있다는 사실이 모든 기능의 공식 허가나 제공 버전과의 호환성을 뜻하지 않는다.

## 세션을 복원하는 순서

1. 현재 AI 사용이 허용된 단계인지 확인한다. 제출물 확정 이후라면 과제 지원을 재개하지 않는다.
2. 적용되는 프로젝트 지침과 작업 사본의 STATE를 읽는다.
3. MISSION의 목표·필수 요구를 확인하고, PLAN의 현재 작업과 연결된 자료만 읽는다.
4. 필요한 DATA·DECISIONS·EVIDENCE의 관련 항목을 읽는다. 모든 로그를 다시 읽지 않는다.
5. 실제 코드·변경 상태와 기록이 일치하는지 확인한다. 기록이 오래됐으면 불일치를 먼저 밝힌다.
6. 확정된 다음 작업을 진행한다. 중요한 모호함만 사용자에게 묻고 독립 작업은 계속한다.

복원 요청 예시:

> AI 사용이 허용된 과제 단계인지 먼저 확인해. 적용 지침과 STATE.md를 읽고, 필요한 기록과 실제 파일을 대조한 뒤 이어가 줘. 중요한 모호함만 물어보고, 답을 기다리는 동안 가능한 독립 작업은 계속해. 확인하지 않은 테스트를 통과로 표시하지 마.

## 기록을 갱신하는 시점

- 사용자 또는 담당자의 답으로 요구나 가정이 바뀌었을 때.
- 중요한 설계 선택, 핵심 기능 완성, 중요한 테스트 실패·수정이 생겼을 때.
- 세션 전환·중단 전, 또는 제출 준비를 시작할 때.

매 도구 호출마다 저장하거나 대화 전문을 복사하지 않는다. 갱신은 변경한 사실과 근거 중심으로 짧게 한다. 예기치 않은 중단에 대비해 큰 작업을 끝낼 때 STATE를 갱신한다.

## 선별 참고

- [cofa-triage](https://github.com/ripplelover/cofa-ready-kit/blob/main/skills/cofa-triage/SKILL.md): 요구·출처·확인 방법 연결.
- [data-audit](https://github.com/ColdTbrew/cofa-skills/blob/main/skills/data-audit/SKILL.md): 데이터 의미·품질 점검.
- [execute](https://github.com/bladem0117/cofa-kit/blob/main/.agents/skills/execute/SKILL.md): 파일 담당을 분리한 구현과 통합.
- [verify](https://github.com/hekate-louise/codex-harness/blob/main/skills/verify/SKILL.md): 실제 실행과 독립 검산.
- [explain](https://github.com/hekate-louise/codex-harness/blob/main/skills/explain/SKILL.md): 실제 코드·결정·검증에 근거한 설명.
- [cofa-explain](https://github.com/ripplelover/cofa-ready-kit/blob/main/skills/cofa-explain/SKILL.md): 사용자 답변을 먼저 듣고 근거와 대조하는 설명 연습.
- [cofa-semiconductor](https://github.com/ripplelover/cofa-ready-kit/blob/main/skills/cofa-semiconductor/SKILL.md): 검사 단위·분모·재검·공정 조건을 확인하는 조건부 도메인 점검.

위 저장소의 설치기·모델 설정·승인 정책을 그대로 채택하지 않는다. 참고 내용은 공식 규정보다 우선하지 않는다.
