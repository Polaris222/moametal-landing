# cluade.md

## 프로젝트 개요
- 프로젝트명: MOA METAL 랜딩 페이지
- 메인 파일: `index.html` (HTML, CSS, JavaScript가 한 파일에 포함된 구조)
- 언어 구성: 한국어 중심 + 다국어 지원
- 목적: 금 산업, 천연자원, 무역 서비스를 소개하는 기업 랜딩 페이지

## 페이지 구조
- `#hdr`: 로고, 내비게이션, 언어 선택, 모바일 메뉴 버튼이 있는 고정 헤더
- `#hero`: 메인 브랜딩 영역(헤드라인/설명)
- `#business`: 비즈니스 카드 3종(Gold Industry, Natural Resources, Trading Service)
- `#cv`: 핵심 가치(Core Value) 카드 4개 섹션
- `#cta`: 문의 섹션으로 연결되는 콜투액션 영역
- `#contact`: 회사 정보(주소/전화/이메일)와 구글 지도 임베드
- `#footer`: 회사 정보, 메뉴 링크, 저작권 정보

## 스타일링 메모
- 모든 스타일은 `index.html` 내부 단일 `<style>` 블록에 포함
- 디자인 토큰은 `:root`에 정의(색상, 간격, 타이포그래피, 트랜지션)
- 반응형 처리는 미디어 쿼리로 구성
- 그라디언트 텍스트, 리빌 애니메이션, 글래스모피즘 계열 시각 효과 사용

## 스크립트 동작
인라인 스크립트 2개를 사용합니다.

1. i18n 언어 전환기
   - 번역 객체 `T`에 `ko`, `en`, `zh-CN`, `zh-TW` 포함
   - `applyLang(lang)`가 각 섹션의 텍스트를 갱신
   - 선택 언어는 `localStorage`의 `moametal-lang` 키에 저장
   - 헤더 언어 메뉴 클릭으로 언어 전환 실행

2. 핵심 UI 인터랙션
   - 스크롤 시 헤더 축소 효과(`#hdr.s`)
   - `IntersectionObserver` 기반 `.rv` 리빌 애니메이션
   - 모바일 내비게이션 열기/닫기(`.nav-btn`, `.hdr-nav`)
   - 모바일 언어 단축 메뉴를 동적으로 생성

## 수정 가이드
- 스크립트가 셀렉터에 의존하므로 ID/class를 안정적으로 유지
  - 예: `.hero-h1`, `.biz-card`, `.cv-card`
- 텍스트 변경 시 아래 2가지를 함께 수정
  - 기본 HTML 텍스트
  - `T` 객체의 번역 항목
- 섹션 추가 시 반응형 CSS 및 리빌 애니메이션 클래스 동작 확인
- 일관성을 위해 `localStorage` 언어 키(`moametal-lang`) 유지

## 빠른 점검 체크리스트
- 데스크톱/모바일 레이아웃 확인
- 4개 언어 전환이 모두 정상 동작하는지 확인
- 앵커 링크 확인: Home / Business / Core Value / Contact
- 연락처 링크(`tel:`, `mailto:`) 정상 동작 확인
