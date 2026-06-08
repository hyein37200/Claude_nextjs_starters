Analyze and optimize the Next.js project in the `my-app` directory. Work through the following steps in order:

## 1. TypeScript & Lint 검사
Run type checking and linting, then fix any issues found:
```
cd my-app && npx tsc --noEmit
cd my-app && npm run lint
```

## 2. 코드 품질 분석
Review all source files under `my-app/app/` and `my-app/components/` (if exists) for:
- **불필요한 re-render** — missing `key` props, inline object/function creation in JSX
- **미사용 import/변수** — dead code that should be removed
- **타입 안전성** — `any` 타입 사용, 누락된 타입 선언
- **접근성(a11y)** — `alt` 누락, 시맨틱 HTML 미사용

## 3. Next.js 성능 최적화
Check and fix Next.js-specific patterns:
- `<Image>` 컴포넌트 사용 여부 (`<img>` 태그 대체)
- `<Link>` 컴포넌트 사용 여부 (`<a>` 태그 대체)
- `'use client'` 불필요한 사용 — Server Component로 전환 가능한지 확인
- 동적 import (`next/dynamic`) 로 분리할 수 있는 큰 컴포넌트 확인

## 4. Tailwind CSS 정리
- 중복/충돌 클래스 제거
- 반응형 클래스 누락 확인 (모바일 퍼스트)
- 다크모드 클래스 일관성 확인

## 5. 빌드 검증
After applying fixes, confirm the project builds successfully:
```
cd my-app && npm run build
```

## 보고서
After completing all steps, provide a summary with:
- 발견된 문제 목록 (수정 완료 표시 포함)
- 수동으로 확인이 필요한 항목
- 빌드 성공/실패 