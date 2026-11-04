# AI Workflow Playbook

제한 시간 안에 AI와 요구사항을 확인하고, 작은 서비스를 구현·검증·설명하기 위한 한국어 작업 지침입니다. 

## 처음 사용할 때

1. [QUICKSTART.md](QUICKSTART.md)의 가져오기 요청을 제공된 개발 환경의 AI에 전달합니다.
2. 공식 과제 설명과 기존 프로젝트 지침을 먼저 확인합니다.
3. [AGENTS.md](AGENTS.md)를 명시적으로 읽힙니다. 하위 폴더에 다운로드한 파일이 다른 폴더의 작업에 자동 적용된다고 가정하지 않습니다.
4. [PROMPTS.md](PROMPTS.md)의 시작 요청을 사용합니다.
5. [CHECKLIST.md](CHECKLIST.md)로 빠진 조건과 실패 사례를 점검합니다.
6. [TEMPLATES.md](TEMPLATES.md)에서 필요한 양식만 작업 폴더에 작성합니다.

## 추천 운영

- 기본: 구현 세션 1개 + 필요할 때만 검토하는 세션 1개.
- 선택: 마감 전에 기록·설명 세션 1개 추가. 상시 감시나 같은 질문 반복은 하지 않습니다.
- 서비스 실행 터미널은 AI 세션과 별개입니다. 터미널 창 수와 AI 수는 같지 않습니다.
- 소스 코드 작성자는 한 명입니다. 검토자는 REVIEW.md만, 기록자는 EXPLAIN.md와 HOW_TO_RUN.md만 작성합니다.
- 세션끼리 대화가 자동 공유된다고 가정하지 않습니다. 같은 작업 폴더의 완성된 체크포인트와 파일을 읽어 이어갑니다.

## 자료 사용 범위

자료 반입·다중 세션·모델 설정은 해당 행사나 작업 환경의 최신 규칙을 따릅니다. 이 저장소가 특정 대회에서 승인되었다는 뜻은 아닙니다.

공개 준비자료를 다운로드하는 것과 작업 결과를 외부에 업로드하는 것은 다릅니다. 외부 전송이 금지된 환경에서는 작업 중 생성된 파일·데이터·대화·결과물을 이 저장소에 올리거나 Git push하지 않습니다. 외부 AI 연결이나 금지된 자동 조작을 추가하지 않습니다. 원격 기능·추가 서비스 없이 제공된 환경 안에서 사용합니다.

## 파일의 역할

| 파일 | 역할 |
|---|---|
| AGENTS.md | AI가 지킬 짧은 작업 원칙 |
| QUICKSTART.md | 가져오기·세션 열기·재개 방법 |
| PROMPTS.md | 시작·구현·검토·이해 확인 요청문 |
| CHECKLIST.md | 질문 누락·데이터·검증·제출 점검 |
| TEMPLATES.md | 명세·계획·인수인계·실행 안내 양식 |

문서 이름이나 문서 개수는 성과가 아닙니다. 실제 요구 충족, 검증 결과, 설명 가능한 구현을 남깁니다.

## 참고 문서

- [OpenAI: 프로젝트 지침과 확장](https://learn.chatgpt.com/docs/customization/overview)
- [OpenAI: Codex CLI 명령](https://learn.chatgpt.com/docs/cli/reference)
- [OpenAI: 추론 강도](https://developers.openai.com/api/docs/guides/reasoning)
- [OpenAI: 실행 속도](https://learn.chatgpt.com/docs/agent-configuration/speed)

작성일: 2026-11-05. CLI 기능은 설치 버전과 관리 정책에 따라 달라집니다.
