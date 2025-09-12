# Contribution Guide

이 문서는 **Sticker Diary** 프로젝트의 브랜치 전략, 커밋 규칙, PR 규칙 등을 정리한 가이드입니다.  
(1인 개발 기준으로 작성되었습니다.)


## 1. Branch Strategy

- **main**
  - 배포 가능한 안정 브랜치
  - Force push 및 삭제 금지

- **feature/***
  - 신규 기능 개발
  - 예: `feature/fe-canvas-stage`, `feature/be-auth-login`

- **fix/***
  - 버그 수정
  - 예: `fix/fe-image-upload`

- **chore/***
  - 설정, 빌드, 문서 등 비기능 작업
  - 예: `chore/eslint-config`

- **release/x.y.z** 
  - 배포 준비용 브랜치

**흐름**
1. 작업 단위별 브랜치 생성
2. 작업 후 `main`으로 머지 (Squash & Merge 사용 예정)


</br>

## 2. Commit Convention

**형식**

**types**
- `feat`: 기능 추가
- `fix`: 버그 수정
- `docs`: 문서 수정
- `style`: 코드 포맷 (기능 변화 없음)
- `refactor`: 리팩토링
- `test`: 테스트 관련
- `chore`: 빌드, 배포, 설정 등

**예시**
- `feat(fe): 브러시 그리기 및 색/두께 옵션 추가`
- `fix(be): JWT 만료 시 401 처리 추가`
- `chore: Husky + lint-staged 설정`

</br>

## 3. Pull Request 규칙

```
✨ 변경 내용
- (이 PR에서 구현/수정한 주요 기능을 bullet 형식으로 작성해주세요)

❔ 배경/맥락
- (이 작업을 하게 된 이유, 관련된 이슈나 배경을 간단히 작성해주세요)

🔬 테스트 방법
- (어떻게 테스트했는지, 재현 단계가 있으면 작성해주세요)
- 예시:
  1. 로그인 후 `/page/:id` 접속
  2. 브러시로 그림을 그린 후 PNG 다운로드 확인

✅ 체크리스트
- [ ] 코드 스타일(ESLint/Prettier) 통과
- [ ] 타입 오류 없음
- [ ] 주요 기능 수동 테스트 완료
- [ ] 관련 문서/주석 업데이트 완료 

📎 참고 이슈
- #이슈번호 (있으면 연결)
```

**머지 방식**
- Squash & Merge 권장 → 히스토리 간결 유지

</br>

## 4. Release & Tag

- MVP/프로토타입 배포: `v0.1.0`
- 기능 묶음/배포 단위: `v0.2.0`, `v0.3.0` 식으로 태깅

</br>


## 5. Issue Label 

- `type:feat`, `type:fix`, `type:chore`, `type:docs`
- `priority:high`, `priority:low`
- `status:blocked`, `status:ready`
- `good first issue`

</br>

## 6. 디렉토리 구조 (초안)
(작성 예정)


</br>

## 7. 코드 규칙

- TypeScript strict 모드 사용
- ESLint + Prettier 적용 (자동 포맷)
- 모듈/함수는 단일 책임 원칙 유지
- API 응답 DTO는 zod 스키마로 검증
