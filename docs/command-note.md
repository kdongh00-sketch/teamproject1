# Git 명령어 모음집

## 저장소 초기 설정

### 저장소 복제(Clone)

bash git clone <repository-url> 

예시

bash git clone git@github.com:team/project.git 

### 원격 저장소 확인

bash git remote -v 

### 원격 저장소 변경

bash git remote set-url origin <repository-url> 

---

# 브랜치 관리

### 현재 브랜치 확인

bash git branch 

### 모든 브랜치 확인

bash git branch -a 

### 브랜치 생성

bash git branch feature/login 

### 브랜치 생성 후 이동

bash git checkout -b feature/login 

### 브랜치 이동

bash git checkout feature/login 

### 브랜치 삭제

bash git branch -d feature/login 

### 강제 삭제

bash git branch -D feature/login 

---

# 변경 사항 확인

### 현재 상태 확인

bash git status 

### 변경 파일 확인

bash git diff 

### Staging 영역 포함 변경 사항 확인

bash git diff --cached 

### 커밋 기록 확인

bash git log 

### 한 줄로 확인

bash git log --oneline 

### 브랜치 그래프 확인

bash git log --oneline --graph --all 

---

# 파일 추가 및 커밋

### 특정 파일 추가

bash git add filename 

### 전체 파일 추가

bash git add . 

### 커밋

bash git commit -m "feat: 로그인 기능 추가" 

### 마지막 커밋 수정

bash git commit --amend 

---

# 원격 저장소 사용

### Push

bash git push origin 브랜치명 

예시

bash git push origin feature/login 

### 최초 Push

bash git push -u origin feature/login 

### Pull

bash git pull origin main 

### Fetch

bash git fetch origin 

---

# 협업 시 자주 사용하는 명령어

### 최신 main 가져오기

bash git checkout main git pull origin main 

### 작업 브랜치 생성

bash git checkout -b feature/login 

### 개발 후 커밋

bash git add . git commit -m "feat: 로그인 구현" 

### 원격 저장소 업로드

bash git push origin feature/login 

### 최신 main 반영

bash git checkout main git pull origin main  git checkout feature/login git rebase main 

---

# Merge

### 브랜치 병합

bash git checkout main git merge feature/login 

### Rebase

bash git rebase main 

### 충돌 해결 후 계속 진행

bash git add . git rebase --continue 

### Rebase 취소

bash git rebase --abort 

---

# Undo (되돌리기)

### Staging 취소

bash git restore --staged . 

### 파일 수정 취소

bash git restore 파일명 

### 마지막 커밋 취소 (파일 유지)

bash git reset --soft HEAD~1 

### 마지막 커밋 취소 (Staging 해제)

bash git reset --mixed HEAD~1 

### 마지막 커밋 완전 삭제

bash git reset --hard HEAD~1 

---

# 원격 브랜치 삭제

bash git push origin --delete feature/login 

---

# Stash

### 임시 저장

bash git stash 

### 목록 확인

bash git stash list 

### 복구

bash git stash pop 

### 특정 Stash 복구

bash git stash apply stash@{0} 

---

# SSH 관련

### SSH 연결 확인

bash ssh -T git@github.com 

정상 출력 예시

text Hi username! You've successfully authenticated, but GitHub does not provide shell access. 

### SSH 키 생성

bash ssh-keygen -t ed25519 -C "your_email@example.com" 

### 공개키 출력

bash cat ~/.ssh/id_ed25519.pub 

---

# 유용한 설정

### Pull 시 Rebase 사용

bash git config --global pull.rebase true 

### 사용자 이름 설정

bash git config --global user.name "홍길동" 

### 이메일 설정

bash git config --global user.email "example@email.com" 

### 설정 확인

bash git config --list 

---

# 팀 프로젝트 기본 작업 흐름

bash # 최신 코드 받기 git checkout main git pull origin main  # 작업 브랜치 생성 git checkout -b feature/기능명  # 작업 git add . git commit -m "feat: 기능 구현"  # 업로드 git push origin feature/기능명  # Pull Request 생성  # Merge 후 정리 git checkout main git pull origin main git branch -d feature/기능명 git push origin --delete feature/기능명 