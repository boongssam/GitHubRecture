<!--
  ✏️ 수정 규칙 (이 파일은 index.html이 불러와서 화면에 보여 줍니다)
  ## 제목    → 위쪽 목차 버튼에 들어가는 큰 제목
  ### 제목   → 새 카드(흰 상자) 시작
  #### 제목  → 카드 밖 소제목
  ***        → 카드 끊기 (제목 없이 새 카드를 시작할 때)
  > 문장     → 파란 강조 상자
  <p class="lead">문장</p>  → 크게 가운데 정렬
-->

## 시작 전 준비

### 시작 전 준비: Git 설치 확인

터미널(PowerShell)을 열고 아래 명령을 입력해 버전이 나오면 준비 완료입니다.

```bash
git --version
```

버전이 나오지 않으면 [[git-scm.com](https://git-scm.com/install/windows)]((https://git-scm.com/install/windows))에서 설치한 뒤 터미널을 다시 열어 주세요. GitHub 계정도 미리 만들어 두면 좋습니다.

## 1. 깃허브란?

<p class="lead">제작하셨던 수많은 코드들,<br>잘 보관하고 계신가요?</p>

### GitHub = 코드 전용 저장 · 공유 · 공동작업 플랫폼

구글 드라이브, iCloud 같은 클라우드 저장소도 있지만, GitHub는 **코드를 위해 만들어진** 저장소입니다.

- 저장 및 다운로드, 편집이 편리
- **버전 관리** 가능
- 다른 수많은 개발자들의 오픈소스에 접근
- 포트폴리오 등의 공유

### 버전 관리가 왜 필요할까?

수차례 코드를 수정하고 추가하다 보면, 이런 일이 생깁니다.

| 코드 폴더 | 보고서 파일 |
|---|---|
| 📄 버전 14 (2026.11.4) | 📄 프로젝트 결과 보고서_1126 |
| 📄 버전 13 (2026.9.14) | 📄 프로젝트 결과 보고서_1126_수정 |
| 📄 버전 12 (2026.7.25) | 📄 프로젝트 결과 보고서_최종 |
| 📄 버전 11 (2026.7.25) | 📄 프로젝트 결과 보고서_최종_보고용_1127 최종 |
| … 무엇이 바뀌었는지 알 수 없음 | 📄 **…_최종_진짜진짜최종** |

> Git을 쓰면 버전마다 **"내가 무엇을 수정했는지"** 알아볼 수 있는 메모를 남길 수 있습니다.

```
PS> git add .
PS> git commit -m "261107"
[master 374b483] 261107
 1 file changed, 1 insertion(+), 1 deletion(-)
```

### Git과 GitHub는 다릅니다

| git | ⇄ | GitHub |
|---|---|---|
| 버전 입력 시스템 | | 코드 저장소 |
| 내 컴퓨터에서 동작 | | 인터넷(원격)에 있음 |

## 2. 올리고 내려받기

### AI가 다 알아서 해주던데요?

**자동화의 역설**: 영국 심리학자 리잔 베인브리지가 1983년 '자동화의 아이러니'라고 이름 붙인 현상

기계가 일을 잘하게 돼 일상 업무를 자동화할수록 사람은 직접 수행할 기회를 점차 잃는다. 감시 책임은 사람에게 남지만, 바로 그 자동화 때문에 감시 능력은 퇴화한다.

<p class="stat">28.4% <strong>→ 22.4%</strong></p>

<p class="center">폴란드의 관찰 연구: AI 보조 대장내시경 도입 후, <b>AI 없이</b> 검사했을 때의 선종 발견율 하락</p>

> 그래서 AI에게 맡기더라도 **기본 용어와 명령어는 알고 있자!**

#### 필수 용어 — 알고는 있자!

### Repository

**프로젝트 폴더.** 코드 파일과 그 변경 기록이 함께 들어 있는 저장소입니다. 줄여서 "레포"라고도 부릅니다.

### Branch

**수정을 위한 복사본.** main 브랜치는 그대로 두고, 새 브랜치에서 작업한 뒤 검토(Review)를 거쳐 합칩니다(Merge).

### Branch 흐름

<svg viewBox="0 0 640 170" width="100%" role="img" aria-label="main 브랜치에서 feature 브랜치를 만들고 커밋 후 pull request, review를 거쳐 merge하는 흐름">
<g font-family="Noto Sans KR" font-size="13" fill="currentColor">
<line x1="40" y1="40" x2="590" y2="40" stroke="#6fa3e3" stroke-width="3"/>
<line x1="40" y1="40" x2="220" y2="130" stroke="#6fa3e3" stroke-width="3"/>
<line x1="220" y1="130" x2="460" y2="130" stroke="#b07fd8" stroke-width="3"/>
<line x1="460" y1="130" x2="590" y2="40" stroke="#b07fd8" stroke-width="3"/>
<circle cx="40" cy="40" r="14" fill="#a9c9f2" stroke="#6fa3e3" stroke-width="2"/>
<circle cx="590" cy="40" r="14" fill="#94dcbc" stroke="#4bb487" stroke-width="2"/>
<circle cx="220" cy="130" r="13" fill="#d8b3ef" stroke="#b07fd8" stroke-width="2"/>
<circle cx="340" cy="130" r="13" fill="#d8b3ef" stroke="#b07fd8" stroke-width="2"/>
<circle cx="460" cy="130" r="13" fill="#d8b3ef" stroke="#b07fd8" stroke-width="2"/>
<text x="62" y="28">Main branch</text>
<text x="560" y="20">Merge</text>
<text x="150" y="160">Feature branch</text>
<text x="312" y="160">Commits</text>
<text x="500" y="105">Pull request → Review</text>
</g>
</svg>

### 내 컴퓨터 → 저장소까지 3단계

| Working directory | → | Staging area | → | Local repository | → | GitHub |
|---|---|---|---|---|---|---|
| 작업 중인 폴더 | `git add` | 올릴 파일 장바구니 | `git commit` | 버전(스냅샷) 저장 | `git push` | 원격 저장소 (origin) |

#### Git 명령어

### `git init`

**"git 저장소(폴더)를 만들어!"**

현재 폴더를 Git이 관리하는 저장소로 만듭니다. 폴더 안에 숨김 폴더 `.git`이 생깁니다.

### `git add .`

**"현재 폴더에 있는 파일을 선택(스테이징)할게!"**

`.`은 "현재 폴더 전체"라는 뜻입니다.

### `git commit -m "할말"`

**"'할말'로 버전 기록해줘!"**

메시지에는 날짜나 수정 내용을 적어 두면 나중에 찾기 쉽습니다. 예: `git commit -m "로그인 버튼 추가"`

### `git branch -M main`

**"기본 브랜치 이름을 main으로 변경!"**

Git의 기본 브랜치명은 **master**, GitHub의 기본 브랜치명은 **main**이라서 이름을 맞춰 줍니다.

### `git remote add origin GitHub주소`

**"origin이라는 이름으로 GitHub 레포지토리에 연결해줘!"**

내 컴퓨터 🖥️ 🔗 GitHub. 한 번만 연결하면 됩니다.

### `git push -u origin main`

**"origin의 main에 업로드해줘!"**

내 컴퓨터(main) → **push** → GitHub(origin/main). `-u`를 한 번 붙여 두면 다음부터는 `git push`만 입력해도 됩니다.

### 학교 컴퓨터에서 작업하다가, 우리 집에 왔을 때!

GitHub(origin/main) → **pull 또는 clone** → 집 컴퓨터(main)

| | `git clone 레포지토리주소` | `git pull origin main` |
|---|---|---|
| 언제? | **처음** 내려받을 때 | **이미 내려받은 뒤** 업데이트할 때 |
| 결과 | 저장소를 복제해 **새 폴더**를 만듭니다 | 원격 변경 사항을 가져와 **기존 폴더**에 반영합니다 |

### Fork: 레포지토리 복사

다른 사람의 GitHub 저장소 오른쪽 위 **Fork** 버튼을 누르면 내 GitHub 계정으로 사본이 만들어집니다.

| 비교 | Fork | Clone |
|---|---|---|
| 복사 위치 | 내 GitHub 계정 | 내 컴퓨터 |
| 주요 목적 | 기여 · 독립 작업 | 로컬 작업 |
| Push | 내 저장소라 push 쉬움 | 원본 권한 없으면 push 불가 |

- **clone만:** 내 소유 저장소가 아니므로 코드 수정 후 push 불가
- **clone → 새 레포 만들어 push:** 가능하지만, 원본 코드에 pull request 보내기 어려움
- **fork → clone:** 내 소유 사본 생성 → 코드 다운 → push 가능 ✅

> 💡 한 줄 요약: **Fork는 GitHub에 복사, Clone은 컴퓨터에 복사**

### `git switch -c feature`

**"feature라는 브랜치를 만들어 이동해!"**

main은 안전하게 두고, 새 기능은 feature 브랜치에서 실험한 뒤 합칩니다.

### `git status`

**"작업 폴더와 스테이징 영역 상태를 보여줘!"**

| 색 | 뜻 |
|---|---|
| 🟢 초록 | **Changes to be committed**<br>git add로 스테이징 영역(장바구니)에 정상적으로 올라간 파일 |
| 🔴 빨강 | **Changes not staged for commit**<br>Git이 추적하던 파일이지만, 수정 후 아직 git add를 하지 않은 파일 |
| 🔴 빨강 | **Untracked files**<br>새로 생겨서 Git이 한 번도 추적한 적 없는 파일 |

## 실습

<p class="lead">웹페이지를 하나 만들어서<br>GitHub에 직접 업로드해 봅시다.</p>

### 준비

1. 웹페이지 폴더 만들기 (예: `index.html` 한 개)
2. GitHub에서 **New repository**로 빈 저장소 만들고 주소 복사
3. VS Code 등에서 해당 폴더를 열고 터미널 열기

### 명령어 (순서대로)

```bash
# 1. 로컬 저장소 초기화
git init
# 2. 파일 추가 및 첫 커밋
git add .
git commit -m "First commit"
# 3. 기본 브랜치 이름을 main으로 맞춤
git branch -M main
# 4. 방금 만든 GitHub 저장소 주소 등록
git remote add origin 주소
# 5. 원격 저장소로 첫 업로드
git push -u origin main
```

'주소' 자리에 복사한 저장소 주소를 붙여 넣으세요. 처음 push할 때 GitHub 로그인 창이 뜰 수 있습니다.

## 3. GitHub 탐색하기

### 저장소 화면 위쪽 탭

각 탭이 무엇을 하는 곳인지 살펴봅시다.

| 탭 | 하는 일 |
|---|---|
| **Code** | 코드 파일 |
| **Pull requests** | 수정 요청 |
| **Agents** | 이 저장소와 관련된 AI 코딩 에이전트 작업을 보는 곳 |
| **Actions** | 테스트나 빌드 같은 자동 작업의 실행 결과를 보는 곳 |
| **Projects** | 할 일을 표나 보드로 정리하는 곳 |
| **Security and quality** | 보안과 코드 품질 관련 정보 |
| **Insights** | 기여자와 변경 활동 등 통계 확인 |

## 명령어 요약

### 명령어 한눈에 보기

| 명령어 | 뜻 |
|---|---|
| `git init` | 저장소 만들기 |
| `git add .` | 파일 스테이징 |
| `git commit -m "메시지"` | 버전 기록 |
| `git branch -M main` | 기본 브랜치 이름을 main으로 |
| `git remote add origin 주소` | GitHub 저장소 연결 |
| `git push -u origin main` | 업로드 |
| `git clone 주소` | 처음 내려받기 |
| `git pull origin main` | 최신 내용 받아오기 |
| `git switch -c 이름` | 새 브랜치 만들고 이동 |
| `git status` | 현재 상태 확인 |
