name: Pull Request
description: Submit changes to the project, with an option to provide a detailed explanation.
labels: ["PR", "pull request"]
body:

- type: input
  id: pr-title
  validations:
  required: true
  attributes:
  label: "🏷️ 제목"
  description: "PR의 간단한 제목을 작성해주세요."
  placeholder: "예: 로그인 기능 개선"

- type: textarea
  id: pr-summary
  validations:
  required: true
  attributes:
  label: "📝 요약"
  description: "PR의 주요 내용을 간단히 요약해주세요."
  placeholder: "예: 로그인 기능에서 사용자 세션 관리 개선..."

- type: markdown
  attributes:
  value: "### 필수 정보 (옵션 사항)"

- type: checkboxes
  id: pr-checklist
  attributes:
  label: "✔️ 확인 사항"
  description: "PR 제출 전에 확인해야 할 사항들입니다."
  options: - label: "관련 이슈가 명시되어 있습니다." - label: "테스트가 완료되었습니다." - label: "문서 업데이트가 포함되었습니다." - label: "코드 리뷰를 위한 사전 검토를 완료했습니다."

- type: textarea
  id: issue-links
  validations:
  required: false
  attributes:
  label: "🔗 관련 이슈"
  description: "이 PR과 관련된 이슈나 기존 PR이 있다면 번호를 언급하고, 필요 시 close할 이슈도 명시해주세요."
  placeholder: "예: 관련 이슈 - #45, close #50"

- type: textarea
  id: changes-detailed
  validations:
  required: false
  attributes:
  label: "📄 변경 사항 (세부)"
  description: "PR의 변경 사항을 자세히 설명하고 싶은 경우 작성해주세요."
  placeholder: "예: 이번 변경 사항에는 로그인 세션 시간 연장 및 오류 메시지 개선이 포함됩니다..."

- type: textarea
  id: testing-instructions
  validations:
  required: false
  attributes:
  label: "🔬 테스트 방법"
  description: "이 PR을 테스트하는 방법이나 테스트 환경을 설명해주세요. 필요한 경우 시나리오를 포함할 수도 있습니다."
  placeholder: "예: 1. 로그인 시도를 한 후 2. 로그아웃 버튼이 정상 동작하는지 확인."

- type: textarea
  id: additional-notes
  validations:
  required: false
  attributes:
  label: "🗒️ 추가 참고 사항"
  description: "리뷰어가 알아야 할 추가적인 사항이나 주의점이 있다면 작성해주세요."
  placeholder: "예: 이 기능은 인증 모듈과 호환성을 고려해야 합니다."

- type: dropdown
  id: pr-impact
  attributes:
  label: "💥 영향도"
  description: "이 PR이 프로젝트에 미칠 영향도를 설정해주세요."
  options: - Minor - Moderate - Major
