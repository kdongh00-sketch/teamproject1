# 오픈소스 팀 프로젝트 1팀

> 오픈소스SW 및 협업실무 수업에서 GitHub 협업 흐름을 4주 동안 실습하기 위한 팀 저장소입니다.

## 소개

이 저장소는 6명이 한 팀으로 GitHub 협업 과정을 직접 연습하기 위해 만든 저장소입니다.  
팀원들은 개인 branch에서 작업하고, commit을 남긴 뒤 GitHub에 push하고, Pull Request와 review를 거쳐 main branch에 merge합니다.

이 미션의 핵심은 Git 명령어를 단순히 외우는 것이 아니라 실제 협업 상황에서 다음 흐름을 반복해 보는 것입니다.

- branch 생성
- commit 작성
- push 수행
- Pull Request 생성
- review comment 작성
- merge 수행
- conflict 확인 및 해결
- 오류와 해결 과정 기록

## 팀원

| 이름 | GitHub ID | 팀 내 역할 | 담당 파일/작업 |
|---|---|---|---|
| [김동혁] | [kdongh00-sketch] | Repository Owner / 팀장 | 저장소 생성, collaborator 초대 |
| [김민기] | [ffdddda-s] | Branch Manager | branch 이름 규칙 확인 |
| [문재후] | [psjoa] | Issue Manager | issue 생성 및 담당자 지정 |
| [이종원] | [iambingbing] | PR Manager | PR 제목, 설명, issue 연결 확인 |
| [정예서] | [GomgukXD] | Reviewer | PR review 및 comment 작성 |
| [홍준기] | [hongjungi2004] | Recorder | conflict/error log 정리 |

> 역할은 고정하지 않고 주차별로 바꾸어도 됩니다.

## 저장소 구조

```text
.
├── README.md
├── TEAM.md
├── CONTRIBUTING.md
├── GIT-MISSION-REPORT.md
├── docs/
│   ├── git-convention.md
│   ├── conflict-log.md
│   ├── error-log.md
│   └── command-note.md
├── members/
│   ├── member1.md
│   ├── member2.md
│   ├── member3.md
│   ├── member4.md
│   ├── member5.md
│   └── member6.md
└── weekly/
    ├── week1.md
    ├── week2.md
    ├── week3.md
    └── week4.md
```

| 경로 | 설명 |
|---|---|
| `README.md` | 저장소 소개, 팀원, 구조, 협업 흐름 정리 |
| `TEAM.md` | 팀 정보와 팀원 정보 정리 |
| `CONTRIBUTING.md` | branch, commit, PR, review 규칙 정리 |
| `GIT-MISSION-REPORT.md` | 4주 Git 미션 최종 보고서 |
| `docs/git-convention.md` | Git 사용 규칙과 convention 정리 |
| `docs/conflict-log.md` | conflict 발생 원인과 해결 과정 기록 |
| `docs/error-log.md` | 실습 중 만난 오류와 해결 방법 기록 |
| `docs/command-note.md` | Git 명령어와 의미 정리 |
| `members/` | 팀원별 자기소개 및 개인 Git 활동 기록 |
| `weekly/` | 주차별 미션 수행 기록 |

## Git 협업 흐름

1. GitHub Issue를 만든다.
2. 작업 담당자를 정한다.
3. main branch를 최신 상태로 가져온다.
4. 개인 branch를 만든다.
5. 작업 후 의미 있는 단위로 commit한다.
6. GitHub에 branch를 push한다.
7. Pull Request를 만든다.
8. 팀원에게 review를 받는다.
9. 필요한 수정 후 main branch에 merge한다.
10. issue를 닫고 작업 내용을 기록한다.

## 기본 작업 명령어

```bash
git clone <저장소주소>
cd <저장소이름>
git pull origin main --no-rebase
git checkout -b docs/이름-profile
```

작업 후에는 다음 순서로 commit과 push를 수행합니다.

```bash
git status
git add <파일명>
git commit -m "docs: add member profile"
git push origin <branch-name>
```

## Branch 이름 규칙

Issue 번호와 작업 내용을 branch 이름에 포함합니다.

```text
docs/3-readme-intro
feature/4-team-rule
fix/5-readme-typo
```

| prefix | 의미 | 예시 |
|---|---|---|
| `docs` | 문서 추가 또는 수정 | `docs/3-readme-intro` |
| `feature` | 새 내용 또는 기능 추가 | `feature/4-team-rule` |
| `fix` | 오타, 오류, 잘못된 내용 수정 | `fix/5-readme-typo` |

## Commit message 규칙

commit message는 변경 내용을 알 수 있게 작성합니다.

| type | 의미 | 예시 |
|---|---|---|
| `docs` | 문서 추가 또는 수정 | `docs: add README usage section` |
| `feat` | 새 기능 또는 새 내용 추가 | `feat: add team project idea` |
| `fix` | 오타, 오류, 잘못된 내용 수정 | `fix: correct team member name` |
| `refactor` | 내용 구조 정리 | `refactor: reorganize README sections` |
| `chore` | 기타 관리 작업 | `chore: create weekly folders` |

좋지 않은 commit message 예시는 다음과 같습니다.

```text
update
test
aaa
```

## Pull Request 작성 규칙

PR 제목은 issue 번호와 작업 내용을 함께 적습니다.

```text
[#3] docs: add README intro
```

PR 설명에는 다음 내용을 포함합니다.

```markdown
## 작업 내용
- README.md에 프로젝트 소개를 추가했습니다.
- 팀 미션 저장소의 목적을 한 문장으로 정리했습니다.

## 확인한 내용
- [ ] 개인 branch에서 작업했습니다.
- [ ] commit message를 의미 있게 작성했습니다.
- [ ] 관련 issue 번호를 연결했습니다.

Closes #3
```

## Review 규칙

Pull Request는 최소 1명 이상의 팀원에게 review를 받은 뒤 merge합니다.

좋은 review comment 예시는 다음과 같습니다.

```text
README 첫 문장이 프로젝트 목적을 잘 설명합니다.
처음 보는 사람이 따라 하기 쉽도록 사용 방법을 한 줄 추가하면 좋겠습니다.
branch 이름이 규칙과 다르므로 다음부터 docs/번호-작업내용 형식으로 맞추면 좋겠습니다.
```

다음과 같은 comment만 남기는 것은 피합니다.

```text
굿
확인
ㅇㅇ
```

## Conflict 해결 원칙

conflict가 발생하면 바로 파일을 지우지 않고 먼저 현재 상태를 확인합니다.

```bash
git status
```

conflict marker는 다음과 같은 형태입니다.

```text
<<<<<<< HEAD
현재 branch 또는 main 쪽 내용
=======
병합하려는 branch 쪽 내용
>>>>>>> branch-name
```

해결 절차는 다음과 같습니다.

1. `git status`로 충돌 파일을 확인한다.
2. 충돌 파일을 열어 `<<<<<<<`, `=======`, `>>>>>>>` 표시를 확인한다.
3. 팀에서 최종으로 남길 내용을 결정한다.
4. conflict marker를 모두 삭제한다.
5. 수정한 파일을 `git add`한다.
6. conflict 해결 commit을 남긴다.
7. `docs/conflict-log.md`에 원인과 해결 과정을 기록한다.

예시 명령어:

```bash
git add docs/conflict-practice.md
git commit -m "resolve team project intro conflict"
git push origin main
```

## 4주 미션 로드맵

| 주차 | 핵심 미션 | 팀 산출물 | 개인별 필수 경험 |
|---|---|---|---|
| 1주차 | 팀 저장소 생성, clone, 개인 branch, 첫 commit, 첫 PR | `README.md`, `TEAM.md`, `members/` | 개인 branch 1개, commit 1개 이상, PR 1개 이상 |
| 2주차 | Issue 기반 작업 분배, README 보강, PR review | Issue 6개 이상, `README.md`, `CONTRIBUTING.md` | Issue 1개 담당, PR 1개, review comment 1개 이상 |
| 3주차 | 자동 병합과 conflict 차이 확인, conflict 해결 | `docs/conflict-log.md`, `docs/error-log.md` | conflict 해결 과정 관찰 또는 참여, `git status/log` 해석 |
| 4주차 | 저장소 최종 정리, Git 명령어 노트, 시험 대비 기록 | `GIT-MISSION-REPORT.md`, `docs/command-note.md` | 자신이 한 Git 작업 설명, 상황별 명령어 정리 |

## 완료 체크리스트

### 팀 저장소

- [X] 팀별 GitHub 저장소가 있다.
- [X] 팀원 6명이 collaborator로 참여했다.
- [X] main branch에 직접 작업하지 않았다.

### 개인 작업

- [X] 모든 팀원이 개인 branch를 만들었다.
- [X] 모든 팀원이 의미 있는 commit을 남겼다.
- [X] 모든 팀원이 Pull Request를 1개 이상 만들었다.
- [X] 모든 팀원이 다른 팀원의 PR에 review comment를 남겼다.

### Issue / PR

- [X] GitHub Issue로 작업을 나누었다.
- [X] PR에서 관련 issue를 연결했다.
- [X] PR 설명에 작업 내용과 확인 항목을 작성했다.

### Conflict

- [X] 자동 병합 사례를 확인했다.
- [X] 같은 줄 conflict를 만들고 해결했다.
- [X] 삭제/수정 conflict를 관찰하거나 해결했다.
- [X] `docs/conflict-log.md`에 원인, 해결 방법, 사용 명령어를 기록했다.

### 문서 정리

- [X] `README.md`가 프로젝트 소개, 팀원, 저장소 구조, 협업 흐름을 설명한다.
- [X] `TEAM.md`에 팀원 정보가 정리되어 있다.
- [X] `CONTRIBUTING.md`에 branch, commit, PR, review 규칙이 있다.
- [X] `docs/command-note.md`에 주요 Git 명령어와 의미가 정리되어 있다.
- [X] `GIT-MISSION-REPORT.md`에 4주 미션 요약이 있다.

## 주요 Git 명령어

| 명령어 | 의미 | 사용 상황 |
|---|---|---|
| `git clone <주소>` | 원격 저장소를 내 컴퓨터로 가져온다 | 처음 저장소를 받을 때 |
| `git pull origin main --no-rebase` | 원격 main의 최신 변경을 가져온다 | 작업 전, push 거절 후 |
| `git checkout -b <branch>` | 새 branch를 만들고 이동한다 | 새 작업을 시작할 때 |
| `git branch` | branch 목록과 현재 위치를 확인한다 | 현재 branch 확인 |
| `git status` | 변경 파일, 충돌 여부, commit 준비 상태를 확인한다 | 문제가 생겼을 때 가장 먼저 확인 |
| `git add <파일>` | 변경 파일을 commit 대상으로 올린다 | commit 전 |
| `git commit -m "메시지"` | 변경 내용을 하나의 기록으로 저장한다 | 작업 단위 기록 |
| `git push origin <branch>` | 내 branch를 GitHub에 올린다 | PR 생성 전 |
| `git merge <branch>` | 다른 branch의 변경을 현재 branch에 합친다 | 작업 내용을 합칠 때 |
| `git log --oneline --graph --all` | commit과 branch 흐름을 그래프로 확인한다 | 작업 이력 해석 |
| `git merge --abort` | 진행 중인 merge를 취소한다 | 충돌 해결 전 상태로 되돌릴 때 |
| `git rm <파일>` | 파일 삭제를 Git 변경 이력으로 기록한다 | 삭제/수정 conflict 해결 |

## 자주 하는 실수

| 실수 | 문제점 | 권장 행동 |
|---|---|---|
| main에서 바로 작업한다 | 팀원의 작업과 섞여 추적이 어렵다 | 항상 branch를 먼저 만든다 |
| commit message를 `update`로만 쓴다 | 나중에 무엇을 바꿨는지 알 수 없다 | `docs: add README intro`처럼 작성한다 |
| pull하지 않고 작업한다 | 원격 저장소가 더 최신이면 push가 거절될 수 있다 | 작업 전 `git pull origin main --no-rebase`를 실행한다 |
| conflict marker를 그대로 둔다 | 최종 파일에 Git 충돌 표시가 남는다 | 최종 내용을 정하고 marker를 모두 삭제한다 |
| 한 명이 모든 작업을 대신한다 | 팀 Git 협업 경험이 쌓이지 않는다 | 모든 팀원이 branch, commit, PR, review를 직접 수행한다 |
| GitHub 웹에서만 수정한다 | 명령어 기반 Git 사용 능력이 늘지 않는다 | 가능한 한 로컬 명령어로 작업한다 |

## 학습 목표

이 저장소를 통해 팀원들은 다음 질문에 답할 수 있어야 합니다.

- 현재 내가 어느 branch에 있는지 어떻게 확인하는가?
- 작업 전에 왜 pull을 해야 하는가?
- push가 거절되면 가장 먼저 무엇을 확인해야 하는가?
- conflict marker에서 현재 branch 내용과 병합하려는 branch 내용을 어떻게 구분하는가?
- conflict 해결 후 왜 `git add`와 `git commit`을 다시 해야 하는가?
- `git log --oneline --graph --all` 결과에서 branch와 merge 흐름을 어떻게 읽는가?
- 좋은 commit message와 좋지 않은 commit message의 차이는 무엇인가?
- Pull Request와 review가 왜 필요한가?
- README가 왜 저장소의 첫인상인가?
- 팀 프로젝트에서 Git을 쓰지 않으면 어떤 문제가 생기는가?
