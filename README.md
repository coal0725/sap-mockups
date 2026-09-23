# SAP 개선안 시안

삼성표준인증원 SAP 인증심사 플랫폼의 **화면 개선안 시안**입니다.

> 삼성표준인증원 장은수 · 2026-09-24
> 문의 ssr@ssr1.co.kr

---

## 이 시안의 성격

**확정안입니다.** 참고안이 아닙니다.

시안은 아래 항목의 기준입니다.

- 화면 구성 · 문구 · 배치
- 필수 여부 — `data-req` · `data-reqgroup` 속성
- 조건부 표시 규칙 — `data-when="필드:값"` 속성
- 네비게이션 약어 — `data-nav` 속성

**스타일은 참고용입니다.** 통째로 복사하지 마시고 프로젝트 구조에 맞게 옮겨 주십시오.

---

## 화면

신청 플로우 순서대로입니다.

| 화면 | 시안 | 현재 화면 |
|---|---|---|
| SC-001 웰컴 · 인증심사 신청 | [SC-001](https://coal0725.github.io/sap-mockups/SC-001-welcome-proposal.html) | `/welcome` |
| SC-002 신청서 작성 | [SC-002](https://coal0725.github.io/sap-mockups/SC-002-application-form-proposal.html) | `/apply/form` |
| SC-003 설문 작성 | [SC-003](https://coal0725.github.io/sap-mockups/SC-003-survey-proposal.html) | `/apply/survey` |
| SC-005 서류 첨부 | [SC-005](https://coal0725.github.io/sap-mockups/SC-005-attach-proposal.html) | `/apply/attach` |
| SC-004 계약서 작성 · 서명 | [SC-004](https://coal0725.github.io/sap-mockups/SC-004-contract-proposal.html) | `/apply/contract` |
| SC-006 최종 확인 · 제출 | [SC-006](https://coal0725.github.io/sap-mockups/SC-006-final-submit-proposal.html) | `/apply/submit` |
| SC-006B 제출 완료 · 접수번호 안내 | [SC-006B](https://coal0725.github.io/sap-mockups/SC-006B-complete-proposal.html) | **신규 화면** |

### 화면 순서에 관하여

**서류 첨부(SC-005)가 계약서 서명(SC-004)보다 앞입니다.**

계약서에 들어가는 심사 범위와 비용 근거가 첨부서류로 확정되기 때문입니다. 기능정의서의 화면 번호는 반대로 되어 있으며 문서 정정 대상입니다. 화면 ID 는 기능정의서를 따르되 진행 순서는 위 표를 따릅니다.

### SC-006B 에 관하여

현재 구현에 없는 화면입니다. 기능정의서 「5. 화면 흐름」에 SC-006 의 이동 가능 화면으로 「접수번호 안내」가 적혀 있으나 화면 ID 가 부여되어 있지 않아 신설하였습니다.

최종 제출 후 웰컴 화면으로 돌아가면 접수번호를 전달할 수 없고 제출 여부도 알 수 없어, 기업이 같은 신청을 다시 하게 됩니다.

---

## assets

| 파일 | 용도 |
|---|---|
| `assets/ssr-logo.svg` | 헤더 로고 |
| `assets/bester-salute.svg` | SC-006B 마스코트 |
| `assets/contract-view.pdf` | **열람용 계약서 원문.** SC-004 의 「계약서 원문 내려받기」가 이 파일을 가리킵니다 |
| `assets/multisite-form.xlsx` | 복수 · 임시사업장 현황 양식 |

### contract-view.pdf 에 관하여

SSR-P-901-05(Rev.2) 의 조항 본문만 담은 파일입니다.

- 신청 조직 정보 · 신청 표준 · 서명란 · 첨부란이 없습니다
- 「열람용」 표시가 들어 있습니다
- 신청 건별로 생성할 필요가 없는 **정적 파일 1개**입니다

SC-004 시안의 계약 조항과 **같은 원문에서 생성하여 문자 단위로 일치**시켰습니다. 한쪽만 수정하면 어긋나므로 함께 관리해 주십시오.

---

## 검수 문서와의 관계

| 문서 | 내용 |
|---|---|
| `docs/review/00_overview.md` | 작업 지시 · 범위 · 분류 기준 |
| `docs/review/01_application.md` | 화면별 반영 항목 149건 |
| `docs/review/02_result.md` | 반영 결과 회신 |
| `docs/reference/SSR_인증원_기준정의서.md` | 인증원 업무 기준. REV 에 한정되지 않습니다 |
| `SAP_검수메모_REV1.xlsx` | 화면 캡처가 포함된 사람용 문서. md 와 내용은 같습니다 |

md 는 Claude 로 작업하실 때, 엑셀은 눈으로 보실 때 쓰시면 됩니다. **어느 쪽을 보셔도 같은 내용입니다.**

---

## 갱신 이력

| 일자 | 내용 |
|---|---|
| 2026-09-21 | SC-001 · SC-002 · SC-003 시안 |
| 2026-09-23 | SC-005 · SC-004 시안 · 열람용 계약서 PDF |
| 2026-09-24 | SC-006 · SC-006B 시안 |
