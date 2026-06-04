# 🤝 Team Git Collaboration Guide

## Branch Strategy

### Main Branch
- main 브랜치는 항상 배포 가능한 상태를 유지합니다.
- 직접 커밋 및 Push를 금지합니다.
- 모든 변경 사항은 Pull Request(PR)를 통해 병합합니다.

### Feature Branch

새로운 기능 개발 시 다음 규칙을 따릅니다.

bash git checkout main git pull origin main git checkout -b feature/feature-name 

예시

text feature/login feature/signup feature/payment 

### Bug Fix Branch

버그 수정 시 다음 규칙을 따릅니다.

text bugfix/login-error bugfix/api-error 

---

## Workflow

### 1. 최신 코드 가져오기

bash git checkout main git pull origin main 

### 2. 작업 브랜치 생성

bash git checkout -b feature/feature-name 

### 3. 개발 진행

필요한 기능을 구현합니다.

### 4. 커밋

bash git add . git commit -m "feat: 로그인 기능 추가" 

### 5. 원격 저장소에 Push

bash git push origin feature/feature-name 

### 6. Pull Request 생성

GitHub에서 Pull Request를 생성합니다.

### 7. 코드 리뷰

최소 1명 이상의 승인을 받은 후 Merge합니다.

### 8. Merge

Squash Merge를 사용합니다.

### 9. 브랜치 삭제

bash git branch -d feature/feature-name git push origin --delete feature/feature-name 

---

## Commit Convention

### Format

text <type>: <description> 

### Types

| Type | Description |
|--------|--------|
| feat | 새로운 기능 추가 |
| fix | 버그 수정 |
| docs | 문서 수정 |
| style | 코드 스타일 수정 |
| refactor | 리팩토링 |
| test | 테스트 코드 |
| chore | 설정 및 기타 작업 |

### Examples

bash git commit -m "feat: 회원가입 기능 구현" git commit -m "fix: 로그인 오류 수정" git commit -m "docs: README 업데이트" 

---

## Pull Request Rules

### PR Title

text [FEAT] 회원가입 기능 구현 [FIX] 로그인 오류 수정 [DOCS] README 수정 

### PR Description

markdown ## 작업 내용 - 회원가입 API 구현 - JWT 인증 적용  ## 테스트 결과 - 회원가입 성공 확인 - 로그인 성공 확인  ## 관련 이슈 #1 

---

## Merge Rules

- 직접 main 브랜치에 Push 금지
- 최소 1명 이상의 코드 리뷰 승인 필요
- Squash Merge 사용
- Merge 전 최신 main 반영 필수

bash git checkout main git pull origin main  git checkout feature/feature-name git rebase main 

---

## Prohibited Actions

❌ main 브랜치 직접 개발

❌ main 브랜치 직접 Push

❌ 승인 없는 Merge

❌ API Key, Password, Secret Key 커밋

❌ .env 파일 커밋

---

## Recommended .gitignore

gitignore .env node_modules/ dist/ build/ target/ .idea/ .vscode/ *.log 

---

## Quick Start

bash # 최신 코드 가져오기 git checkout main git pull origin main  # 브랜치 생성 git checkout -b feature/login  # 개발 후 커밋 git add . git commit -m "feat: 로그인 기능 추가"  # Push git push origin feature/login  # Pull Request 생성  # 리뷰 승인 후 Merge  # 브랜치 삭제 git branch -d feature/login git push origin --delete feature/login 