# 챕터 8. Git과 GitHub

> 이 챕터에서는 Git을 설치하고 GitHub에 가입합니다.
> 코드를 저장하고 관리하는 도구를 준비합니다.

---

## 8-1. Git이란?

### 코드의 타임머신

**Git**은 코드의 변경 이력을 저장하는 프로그램입니다.

| 상황 | Git 없이 | Git 있으면 |
|------|----------|-----------|
| 어제 코드가 더 좋았는데... | 기억에 의존 | 어제 버전으로 되돌리기 |
| 뭘 바꿨더니 갑자기 에러 | 뭘 바꿨는지 모름 | 변경 내역 확인 가능 |
| 실험적인 기능 추가하고 싶음 | 원본 망칠까봐 걱정 | 브랜치로 안전하게 실험 |

### 쉽게 말하면

- **저장**: `Ctrl + S`는 현재 상태만 저장
- **Git**: 모든 저장 시점을 기억 → 언제든 과거로 돌아갈 수 있음

---

## 8-2. GitHub이란?

### 코드 저장소

**GitHub**은 Git으로 관리하는 코드를 인터넷에 저장하는 서비스입니다.

| Git | GitHub |
|-----|--------|
| 내 컴퓨터에서 버전 관리 | 인터넷에 코드 저장 |
| 프로그램 | 웹사이트/서비스 |
| 혼자 사용 | 팀원과 공유 가능 |

### 왜 필요한가?

1. **백업**: 컴퓨터가 고장나도 코드가 안전
2. **공유**: 팀원들과 같은 코드로 작업
3. **배포**: Vercel 같은 서비스와 연결해서 자동 배포

---

## 8-3. Git 설치하기 (Windows)

> **Mac 사용자**: Mac에는 Git이 기본 설치되어 있습니다. 8-4로 건너뛰세요.

### Step 1: 설치 여부 확인

VS Code 터미널(WSL)에서 확인합니다.

```bash
git --version
```

버전이 나오면 이미 설치된 것입니다 → **8-4로 건너뛰세요**

### Step 2: Git 설치 (WSL)

버전이 안 나오면 설치합니다.

```bash
sudo apt update
sudo apt install git -y
```

비밀번호를 물어보면 WSL 설치할 때 설정한 비밀번호를 입력합니다.
(입력할 때 화면에 안 보이는 게 정상입니다)

### Step 3: 설치 확인

```bash
git --version
```

버전이 나오면 성공입니다.

---

## 8-4. GitHub 가입하기

### Step 1: GitHub 접속

브라우저에서 아래 주소로 접속합니다.

```
https://github.com
```

### Step 2: Sign up 클릭

오른쪽 상단의 **Sign up** 버튼을 클릭합니다.

### Step 3: 정보 입력

| 항목 | 입력 내용 |
|------|----------|
| **Email** | 본인 이메일 |
| **Password** | 비밀번호 (15자 이상 또는 숫자+소문자 8자 이상) |
| **Username** | 영어로 아이디 (예: `honggildong`, `myname123`) |

> **Username**은 나중에 바꿀 수 있지만, 가급적 기억하기 쉬운 걸로 정하세요.

### Step 4: 이메일 인증

입력한 이메일로 인증 코드가 옵니다.
코드를 입력해서 인증을 완료합니다.

### Step 5: 가입 완료

가입이 완료되면 GitHub 대시보드로 이동합니다.

---

## 8-5. Git 사용자 설정

GitHub 가입이 끝났으면, Git에 사용자 정보를 설정합니다.

### Step 1: VS Code 터미널 열기

VS Code에서 터미널을 엽니다.

### Step 2: 이름 설정

아래 명령어에서 `"본인 이름"`을 GitHub에서 가입한 이름 또는 본인 이름으로 바꿔서 실행합니다.

```bash
git config --global user.name "본인 이름"
```

예시:
```bash
git config --global user.name "Hong Gildong"
```

### Step 3: 이메일 설정

GitHub 가입할 때 사용한 이메일로 설정합니다.

```bash
git config --global user.email "본인이메일@example.com"
```

예시:
```bash
git config --global user.email "hong@gmail.com"
```

### Step 4: 설정 확인

```bash
git config --global --list
```

`user.name`과 `user.email`이 나오면 성공입니다.

---

## 8-6. Git 용어 미리보기

다음 챕터에서 사용할 Git 용어들입니다. 지금 외울 필요 없고, "이런 게 있구나" 정도만 알아두세요.

| 용어 | 쉬운 설명 |
|------|----------|
| **Repository (레포)** | 프로젝트 저장소. 폴더 하나라고 생각하면 됨 |
| **Commit (커밋)** | 현재 상태를 저장하는 것. 게임의 세이브 포인트 |
| **Push (푸시)** | 내 컴퓨터의 커밋을 GitHub에 올리는 것 |
| **Pull (풀)** | GitHub의 코드를 내 컴퓨터로 가져오는 것 |
| **Clone (클론)** | GitHub의 레포를 내 컴퓨터에 복사하는 것 |
| **Branch (브랜치)** | 독립적인 작업 공간. 원본 안 건드리고 실험 가능 |

> **걱정 마세요!** 클로드 코드에게 "커밋해줘", "푸시해줘"라고 하면 알아서 해줍니다.

---

## 정리

| 항목 | 내용 |
|------|------|
| Git | 코드 버전 관리 프로그램 |
| GitHub | 코드를 인터넷에 저장하는 서비스 |
| Git 설치 | WSL: `sudo apt install git -y` |
| GitHub 가입 | github.com에서 Sign up |
| Git 설정 | `git config --global user.name/email` |

**다음 챕터에서는** 고구마마켓 클론을 만들면서 Git을 실제로 사용해봅니다.

---

<div style="text-align: center; margin-top: 40px;">

[← 이전: 챕터 7. 가계부에 Supabase 연결하기](chapter-07.md) | [다음: 챕터 9. 고구마마켓 클론 - 시연 →](chapter-09.md)

</div>
