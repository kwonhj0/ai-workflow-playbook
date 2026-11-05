# 공개 도구를 골라 쓰기

2026-11-05에 공개 저장소와 주요 파일을 읽고 정리한 선택 메모입니다. 설치·실행 성능이나 특정 환경의 호환성을 보증하는 목록은 아닙니다. 아래 도구의 설치기는 실행하지 않았습니다.

## 먼저 고를 것

이 저장소의 지침만 읽어도 요구 확인, 구현, 리뷰와 인계 작업을 진행할 수 있습니다. 외부 도구는 반복해서 빠뜨리는 일이 있을 때 추가합니다.

| 필요한 일 | 먼저 사용할 것 |
|---|---|
| 조건을 놓쳤는지 확인 | PROMPTS.md의 ‘질문을 한 번 더 점검하기’ |
| 계산이나 배정 방법 결정 | ‘계산·배정·최적화 방법 선택’ |
| 실제로 되는지 확인 | ‘완료 근거 확인’과 프로젝트의 실행 가능한 검사 |
| 내가 구현을 이해했는지 확인 | ‘내 설명 검토’ |
| 상태 전환과 기록을 도구로 관리 | 아래 codexclaw를 별도 연습 프로젝트에서 검토 |
| 반복 업무를 이름으로 호출 | 필요한 SKILL.md와 그 의존 자료만 프로젝트에 설치 |

이 문서의 도구 목록을 읽었다는 이유로 설치를 시작하지 않습니다. 서로 다른 작업 관리 도구를 함께 쓸 때는 계획·기록·리뷰 담당이 중복되는지 먼저 확인합니다.

## 비교한 저장소

| 저장소 | 확인한 구성 | 선택 시 고려할 점 |
|---|---|---|
| [lidge-jun/codexclaw](https://github.com/lidge-jun/codexclaw) | 계획·감사·구현·검증·완료 상태 관리, 인터뷰, 역할별 에이전트, 31개 훅 | 기록 관리 기능이 많다. 재시작·훅 승인·환경 확인이 필요하고 일부 기능은 별도 준비가 필요하다. |
| [leey00nsu/cofa-hackathon-kit](https://github.com/leey00nsu/cofa-hackathon-kit) | Matt Pocock 스킬 고정본, 요구·코드·실행 근거 연결, 구현 설명 연습 | MIT와 원본 출처가 명시돼 있다. 기본 설치는 스킬 11개이며 기존 문서와 설치 대상 경로를 먼저 확인해야 한다. |
| [frank081999-glitch/cofa-harness](https://github.com/frank081999-glitch/cofa-harness) | 표 데이터 점검, 검증·인계·자기 설명용 스킬 | 비교적 단순한 구성. 설치기는 AGENTS에 지침을 덧붙인다. 확인한 파일 목록에서는 재배포 라이선스를 찾지 못했다. |
| [choiYhunn/cofa-public-ops-toolkit](https://github.com/choiYhunn/cofa-public-ops-toolkit) | 알고리즘 선택, 데이터·관계·용량 검사, 제한된 최소비용 배정 도구 | 목적과 수학적 제약을 비교하는 관점이 유용하다. 배정 도구는 도로 노선·시간창 문제까지 해결하지 않는다. 재배포 라이선스는 확인하지 못했다. |
| [alslrl/cofathon-kit](https://github.com/alslrl/cofathon-kit) | 짧은 작업 지침, 요구·인터뷰 양식, 인계 스킬 | 설치 스크립트는 인계 스킬까지 설치하지 않는다. 재배포 라이선스는 확인하지 못했다. |
| [itssosunny/cofa-loop-graph](https://github.com/itssosunny/cofa-loop-graph) | 모델별 역할, 데이터 검사, 요구·코드·검사 연결, 평가 MCP | 설치기가 전역 Codex 설정과 에이전트 파일을 변경한다. 평가 도구에는 별도 모델 API를 호출하는 경로가 있다. 재배포 라이선스는 확인하지 못했다. |

공개 여부, 재배포 조건, 실행 환경의 허용 범위는 각각 확인합니다. 라이선스를 확인하지 못한 저장소의 원문·코드를 이 저장소에 복사하지 않았습니다. 위 목록은 출처를 찾기 위한 링크이며 포함된 기능을 전부 권장한다는 뜻은 아닙니다.

## 필요한 스킬만 사용하기

Skill은 작업 절차를 담은 폴더이고, MCP는 도구 연결 방식입니다. 플러그인은 스킬·도구·훅 등을 묶어 배포할 수 있습니다. 훅은 특정 시점에 실행되는 프로그램이므로 단순한 지침 파일보다 확인할 범위가 넓습니다.

Codex의 스킬 폴더에는 `SKILL.md`가 있고, 앞부분에 `name`과 `description`이 필요합니다. 이름만 같은 파일을 여러 개 설치해도 내용이 자동으로 합쳐지지 않습니다. [공식 스킬 안내](https://learn.chatgpt.com/docs/build-skills)

설치를 하지 않고 내용만 참고하려면 Codex 대화창에 다음과 같이 요청합니다.

```text
[공개 저장소 URL]을 아직 없는 별도 하위 폴더에 내려받아줘.
설치 스크립트는 실행하지 말고, [필요한 스킬]의 SKILL.md와 참조 파일을 읽어줘.
현재 프로젝트에 맞는 절차만 적용하고, 원본에 의존하는 도구나 파일이 없으면 알려줘.
프로젝트 규칙, 기존 파일과 실제 사용 가능한 도구를 우선해줘.
출처와 적용한 범위를 짧게 기록해줘.
```

자주 사용할 스킬을 설치하려면 다음과 같이 범위를 정합니다.

```text
선택한 스킬의 실제 이름, 참조 파일, 필요한 프로그램과 라이선스를 확인해줘.
이 프로젝트의 .agents/skills에 필요한 폴더만 설치해줘.
기존 동명 스킬은 덮어쓰지 말고 충돌을 알려줘.
외부 연결이나 전역 설정 변경이 필요하면 그 내용을 먼저 설명해줘.
```

설치 후에는 Codex 안에서 `/skills`로 확인하고 `$실제-스킬-이름`으로 호출합니다. 이는 터미널의 셸 명령이 아닙니다. 목록에 없다면 실제 SKILL.md 경로를 읽도록 요청할 수 있습니다. 변경이 반영되지 않으면 작업 상태를 기록한 뒤 Codex를 다시 엽니다. 하위 폴더에 저장소를 내려받는 것만으로 그 안의 스킬이 모두 자동 등록되는 것은 아닙니다. [공식 발견 경로와 호출법](https://learn.chatgpt.com/docs/build-skills)

[mattpocock/skills](https://github.com/mattpocock/skills)의 인터뷰 계열도 후보입니다. 확인한 고정본에서 `grill-me`는 `grilling`을, `grill-with-docs`는 `grilling`과 `domain-modeling`을 참조합니다. 진입 파일 한 개만 가져오면 충분하지 않습니다. 원본의 길게 질문하는 절차가 작업 시간에 맞는지도 판단합니다.

## codexclaw를 사용하는 경우

확인한 버전은 `0.2.46+codex.20261031141000`입니다. 설치 안내의 두 명령은 아래와 같습니다. 명령은 Codex 대화창이 아닌 일반 터미널에서 실행합니다. 먼저 해당 환경의 `codex plugin --help`에 명령이 있는지 확인합니다. 지원되지 않는 환경을 임의로 업데이트하지 않습니다.

```sh
codex plugin marketplace add https://github.com/lidge-jun/codexclaw
codex plugin add codexclaw@codexclaw
codex plugin list
```

기존 작업 상태를 저장하고 Codex를 재시작한 뒤, 승인 요청에 표시되는 훅과 권한을 검토합니다. 연습용 프로젝트에서 작은 변경 하나를 계획부터 검증까지 실행해 보고 필요한 시간과 생성 파일 위치를 확인합니다. 출처: [현재 README](https://github.com/lidge-jun/codexclaw/blob/e413b144ffa0617093d158a0dde101601bcadee9/README.md), [플러그인 명세](https://github.com/lidge-jun/codexclaw/blob/e413b144ffa0617093d158a0dde101601bcadee9/plugins/codexclaw/.codex-plugin/plugin.json).

대화 요청 예시:

```text
codexclaw를 사용해 이 작은 변경의 계획과 검증 근거를 관리해줘.
현재 환경에서 허용된 모델과 도구만 사용해줘.
먼저 미확인 중 결과를 바꾸는 조건을 알려주고,
확인된 범위부터 구현한 뒤 실제 검사 결과와 남은 문제를 정리해줘.
작업 기록은 내가 확인할 수 있는 위치를 알려줘.
```

확인할 기능별 차이:

- 기본 에이전트 정의는 메인 모델을 상속하도록 돼 있다. 별도 역할 설정이나 외부 provider가 있으면 동작이 달라지므로 실제 구성을 확인한다.
- Repo Map은 별도 저장소 체크아웃과 Python 도구 준비가 필요하다. 기본 플러그인 설치만으로 모든 기능이 준비되지는 않는다.
- 기록 저장 위치가 작업 폴더 밖으로 정해질 수 있다. `cxc state path`로 확인한다. 로컬의 다른 폴더에 저장하는 것과 인터넷으로 전송하는 것은 다르다.
- `cxc state sync`는 설정에 따라 원격 저장소에 기록을 전송한다. 외부 전송이 제한된 작업에는 사용하지 않는다.
- provider 연결, 메신저 연결, 자동 승인 설정은 별도 기능이다. 작업에 필요하지 않으면 추가하지 않는다. 제공 환경의 권한·감독 설정을 우회하는 용도로 쓰지 않는다.
- 기록의 존재와 단계 통과는 업무적으로 올바른 결과를 증명하지 않는다. 요구에서 도출한 기대값과 실제 동작의 비교가 여전히 필요하다.

## 모델 평가 MCP를 볼 때

`cofa-loop-graph`의 `luna_mcp.py`는 API 키가 있으면 별도 모델 API를 호출하고, 그렇지 않거나 오류가 나면 `codex exec`를 사용하는 구조입니다. 설치기도 전역 설정과 역할 파일을 변경합니다. 제공된 Codex만 사용할 수 있는 환경이라면 이 구성 전체를 그대로 설치하는 것을 권하지 않습니다. [모델 호출 코드](https://github.com/itssosunny/cofa-loop-graph/blob/3489f1dddea1fae7d076df45374822bfbe33c517/.cofa/luna_mcp.py), [설치기](https://github.com/itssosunny/cofa-loop-graph/blob/3489f1dddea1fae7d076df45374822bfbe33c517/install.sh)

도구가 스스로 매긴 점수는 실제 평가 결과나 정답의 보증이 아닙니다. 별도 모델 평가 없이도 입력·기대값·관찰 결과를 대조하는 검사는 가능하며, 추가 모델 호출은 별도 시간과 사용량을 소모할 수 있습니다.

## 반영 범위와 출처

PROMPTS.md의 추가 요청문은 기존 작업 원칙과 사용 목적에 맞춰 새로 작성했습니다. 외부 키트의 코드·설치기·SKILL.md 원문을 포함하지 않았습니다. 비교 과정에서 아래 관점을 참고했습니다.

- codexclaw: 중요한 가정과 모순을 다시 확인하고 실행 근거를 남기는 흐름.
- cofa-hackathon-kit 및 Matt Pocock Skills: 질문의 선후 관계, 구현과 요구의 연결.
- cofa-harness: 사람이 먼저 설명하고 실제 코드와 대조하는 연습.
- cofa-public-ops-toolkit: 단순한 기준 방법과 개선 방법을 같은 조건에서 비교하고, 유효성과 최적성을 구분하는 관점.

확인한 커밋: codexclaw `e413b14`, cofa-hackathon-kit `41b5da9`, cofa-harness `347ac04`, cofa-public-ops-toolkit `c6c3723`, cofathon-kit `9c41222`, cofa-loop-graph `3489f1d`. Matt 원본은 cofa-hackathon-kit이 보존한 `a496f5513d4a4cf889bc48e189e579f4b0bdf6aa` 고정본을 확인했습니다. 최신 버전에서는 경로·구성·행동이 바뀔 수 있습니다.
