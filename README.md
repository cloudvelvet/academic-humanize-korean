# Academic Humanize Korean

한국어 학술 논문·학위논문·학술 초록을 명료하게 윤문하는 Codex 스킬입니다. 문장을 자연스럽게 다듬되 주장, 인용, 수치, 전문용어, 인과관계와 불확실성의 강도를 보존합니다. 심리학 원고에서는 연구설계, 통계 결과, 구성개념·척도명과 진단 용어를 추가로 보호합니다.

## 주요 원칙

- 인용, DOI, URL, 수치, 단위, 수식과 표·그림 참조 보존
- 가능성, 추정, 한계 등 연구의 확신 수준 보존
- 상관관계를 인과관계로 바꾸거나 새 근거·출처를 만드는 편집 금지
- 심리학 연구설계, 표집·할당 방식, 통계적 유의성과 임상적 중요성의 구분 유지
- 척도명·버전·하위척도·채점 방향과 증상·선별·진단의 구분 보존
- 초록, 서론, 선행연구, 방법, 결과, 논의·결론별 편집 기준 적용
- AI 탐지 우회는 하지 않으며, 요청 시 AI 문체 위험 신호를 근거와 함께 점검

## 설치

저장소의 `academic-humanize-korean` 폴더 자체가 스킬입니다. 이 저장소를 사용자 스킬 경로 아래에 클론합니다.

### Windows PowerShell

```powershell
git clone https://github.com/cloudvelvet/academic-humanize-korean.git "$env:USERPROFILE\.agents\skills\academic-humanize-korean"
```

설치 후 Codex가 스킬을 찾지 못하면 Codex를 다시 시작합니다.

## 사용

Codex 프롬프트에서 스킬 이름을 명시하고 원고 또는 파일을 전달합니다.

```text
$academic-humanize-korean

아래 논문의 논의 절을 학술 문체로 윤문해줘.
인용, 수치, 전문용어와 주장의 확신 수준은 유지해줘.

[논문 내용]
```

심리학 원고는 연구 유형과 원하는 양식을 함께 알려주면 더 정확하게 처리할 수 있습니다.

```text
$academic-humanize-korean

아래 심리학 연구보고서의 결과와 논의 절을 윤문해줘.
횡단 상관연구이며, 통계값·척도명·인용은 그대로 유지해줘.

[원고 내용]
```

AI 문체 점검을 함께 요청할 수 있습니다. 이 기능은 원고의 작성 주체를 판정하거나 확률을 산출하지 않고, 기계적 반복·모호한 귀속·근거 없는 단정·인용 이상처럼 학술적으로 검토할 신호를 제시합니다.

```text
$academic-humanize-korean

아래 원고를 윤문하고 AI 문체 위험 신호도 점검해줘.
AI 작성 여부를 단정하지 말고 문제가 되는 원문과 학술적 영향만 알려줘.

[원고 내용]
```

파일을 사용할 때는 원본 보존 여부와 편집할 절을 함께 지정하는 편이 안전합니다.

```text
$academic-humanize-korean

C:\논문\paper.md의 결과 절만 윤문해줘.
원본을 덮어쓰지 말고 별도 파일로 저장해줘.
```

## 범위

이 스킬은 기존 원고의 표현을 편집합니다. 연구 결과·논증·문헌을 새로 만들거나, 표절을 숨기거나, AI 탐지기를 우회하는 용도로 설계되지 않았습니다. 연구윤리와 AI 사용 공개 기준은 소속 기관 및 투고처 지침을 확인해야 합니다.

## 구성

- `SKILL.md` — 스킬 진입점과 핵심 편집 원칙
- `references/academic-editing-rules.md` — 학술 절별 세부 규칙과 최종 충실성 점검
- `references/psychology-editing-rules.md` — 심리학 연구설계·통계·척도·임상 용어 윤문 규칙
- `references/ai-writing-review.md` — 요청 시 적용하는 AI 문체 위험 신호와 출력 기준
- `agents/openai.yaml` — Codex UI 표시 및 호출 메타데이터

## 출처와 라이선스

이 스킬은 [Humanize KR](https://github.com/epoko77-ai/im-not-ai)의 의미 보존 원칙을 학술 원고에 맞게 변형했습니다. 원 프로젝트의 MIT 라이선스 고지는 `LICENSE`와 `NOTICE`에 포함되어 있습니다.
