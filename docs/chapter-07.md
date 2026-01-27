# 챕터 7. 가계부에 Supabase 연결하기

> 이 챕터에서는 MCP를 설정해서 클로드 코드와 Supabase를 연결합니다.
> 한 번 설정하면 클로드가 직접 데이터베이스를 관리할 수 있습니다.

---

## 7-1. Supabase에서 MCP 연결 명령어 찾기

### Step 1: Supabase 대시보드 접속

[supabase.com](https://supabase.com)에 접속해서 로그인합니다.
챕터 6에서 만든 프로젝트를 클릭합니다.

### Step 2: Project Settings 열기

왼쪽 메뉴 하단에서 **톱니바퀴 아이콘 (Project Settings)**을 클릭합니다.

<!-- 스크린샷: Project Settings 위치 -->
![Project Settings](./images/ch07-project-settings.png)

### Step 3: MCP 연결 정보 찾기

왼쪽 메뉴에서 **Integrations** 또는 **MCP**를 찾습니다.

<!-- 스크린샷: Integrations 메뉴 -->
![Integrations](./images/ch07-integrations.png)

### Step 4: 연결 명령어 복사

Claude Code용 연결 명령어가 있습니다. **Copy** 버튼을 클릭해서 복사합니다.

아래와 비슷한 형태입니다:

```powershell
claude mcp add --scope user --transport http supabase "https://mcp.supabase.com/mcp?project_ref=여러분의프로젝트ID"
```

<!-- 스크린샷: MCP 연결 명령어 -->
![MCP 명령어](./images/ch07-mcp-command.png)

> **project_ref** 부분이 여러분의 프로젝트 ID입니다.
> 각자 다르니까 꼭 본인 대시보드에서 복사하세요!

---

## 7-2. MCP 연결 설정하기

### VS Code 터미널 열기

1. VS Code 실행
2. 챕터 5에서 만든 `budget` 폴더 열기
3. `` Ctrl + ` `` 로 터미널 열기

### 연결 명령어 실행

복사한 명령어를 터미널에 붙여넣고 실행합니다.

```powershell
claude mcp add --scope user --transport http supabase "https://mcp.supabase.com/mcp?project_ref=여러분의프로젝트ID"
```

<!-- 스크린샷: 명령어 실행 -->
![명령어 실행](./images/ch07-run-command.png)

### 설정 완료 확인

아래와 같은 메시지가 나오면 성공입니다.

```
Added http MCP server supabase with url: https://mcp.supabase.com/mcp?project_ref=...
```

### 연결된 MCP 확인하기

제대로 추가되었는지 확인합니다.

```powershell
claude mcp list
```

`supabase`가 목록에 보이면 성공!

---

## 7-3. 클로드 코드 실행 및 인증

### 클로드 코드 실행

터미널에서 클로드 코드를 실행합니다.

```powershell
claude
```

### Supabase 인증

처음 Supabase MCP를 사용하면 인증이 필요합니다.

클로드에게 Supabase 관련 요청을 하면:

```
내 Supabase 프로젝트 정보 보여줘
```

자동으로 브라우저가 열리고 Supabase 로그인 페이지가 나타납니다.

<!-- 스크린샷: 브라우저 인증 화면 -->
![브라우저 인증](./images/ch07-browser-auth.png)

1. **Supabase 계정으로 로그인** (챕터 6에서 가입한 계정)
2. **권한 허용** 버튼 클릭

인증이 완료되면 터미널로 돌아옵니다.

> **이제 클로드가 직접 Supabase에 접속할 수 있습니다!**

---

## 7-4. 가계부를 DB 저장 방식으로 바꾸기

### 현재 상태

지금 가계부는 데이터를 **브라우저 메모리**에만 저장합니다.
새로고침하면 데이터가 사라지죠.

이제 **Supabase 데이터베이스**에 저장하도록 바꿔봅시다!

### 프롬프트 입력

클로드에게 아래와 같이 요청합니다.

```
지금 만든 가계부를 수정해줘.

현재는 데이터가 새로고침하면 사라지는데,
Supabase 데이터베이스에 저장되도록 바꿔줘.

- 수입/지출 추가하면 DB에 저장
- 페이지 열면 DB에서 불러오기
- 삭제하면 DB에서도 삭제
```

### 클로드가 알아서 합니다

MCP가 연결되어 있으니 클로드가 직접 Supabase를 확인하고 작업합니다.

```
네, 가계부를 Supabase와 연결할게요.

1. Supabase에 transactions 테이블을 생성합니다
2. 데이터 추가/조회/삭제 코드를 수정합니다
3. 페이지 로드 시 DB에서 데이터를 불러옵니다

진행해도 될까요?
```

**"응"** 이라고 답하면 클로드가 작업을 시작합니다.

<!-- 스크린샷: 클로드 작업 중 -->
![클로드 작업](./images/ch07-claude-working.png)

### 권한 요청 시

클로드가 파일을 수정하거나 Supabase에 테이블을 만들 때 권한을 요청합니다.

```
Supabase에 테이블을 생성해도 될까요? (Y/n)
```

**Y** 또는 **A**를 눌러 허용합니다.

---

## 7-5. 연결 테스트

### 앱 실행하기

클로드에게 실행을 요청하거나 직접 실행합니다.

```
실행해줘
```

또는 새 터미널에서:

```powershell
npm run dev
```

### 연결 확인

1. 브라우저에서 가계부 열기
2. 수입/지출 몇 개 입력
3. **브라우저 새로고침** (F5)
4. 데이터가 **유지되는지** 확인

<!-- 스크린샷: 새로고침 후 데이터 유지 -->
![데이터 유지](./images/ch07-data-persisted.png)

**데이터가 유지되면 성공입니다!**

---

## 7-6. Supabase에서 데이터 확인하기

### 클로드에게 물어보기

클로드에게 직접 데이터를 확인해달라고 요청할 수 있습니다.

```
Supabase에 저장된 데이터 보여줘
```

클로드가 MCP를 통해 데이터를 조회해서 보여줍니다.

### 대시보드에서 직접 확인

Supabase 대시보드에서도 확인할 수 있습니다.

1. [supabase.com](https://supabase.com) 접속
2. 프로젝트 선택
3. 왼쪽 메뉴에서 **Table Editor** 클릭
4. `transactions` 테이블 클릭
5. 입력한 데이터가 보임

<!-- 스크린샷: Supabase에서 데이터 확인 -->
![Supabase 데이터](./images/ch07-supabase-data.png)

> 엑셀처럼 데이터가 표 형태로 저장되어 있습니다!

---

## 7-7. 문제가 생겼을 때

### MCP 연결 확인

MCP가 제대로 추가되었는지 확인합니다.

```powershell
claude mcp list
```

`supabase`가 목록에 있어야 합니다.

### MCP 삭제 후 다시 추가

문제가 있다면 삭제 후 다시 추가합니다.

```powershell
claude mcp remove supabase
claude mcp add --scope user --transport http supabase "https://mcp.supabase.com/mcp?project_ref=여러분의프로젝트ID"
```

### 클로드에게 에러 보여주기

에러가 발생하면 클로드에게 보여주세요.

```
에러가 났어:
[에러 메시지 복사해서 붙여넣기]
```

클로드가 원인을 분석하고 해결 방법을 알려줍니다.

### 자주 발생하는 문제

**문제 1: 명령어 실행 시 에러**
- 따옴표가 제대로 들어갔는지 확인
- URL을 Supabase 대시보드에서 직접 복사했는지 확인

**문제 2: 인증이 안 됨**
- 브라우저에서 Supabase에 이미 로그인되어 있는지 확인
- 다른 브라우저로 시도

**문제 3: 클로드가 Supabase를 못 찾음**
- `claude mcp list`로 supabase가 있는지 확인
- 클로드 코드를 종료하고 다시 시작

---

## 7-8. 자유 실습: 나만의 앱 만들기

가계부 연결에 성공했다면, 이제 **나만의 앱**을 만들어보세요!
새 폴더를 만들고, 원하는 프로그램을 자유롭게 개발해봅니다.

### 시작하기

1. VS Code → `파일` → `폴더 열기` → `새 폴더` 만들기
2. 터미널에서 `claude` 실행
3. 원하는 프롬프트 입력
4. 개발 완료 후 Supabase 연결까지 도전!

> **Supabase MCP는 이미 설정되어 있으니** 다른 프로젝트에서도 바로 사용할 수 있습니다!

### 아이디어 예시

아래 예시를 참고하거나, **자유롭게 상상해서** 만들어보세요.

---

**예시 1: OX 퀴즈 게임**

```
나는 개발 초보야.
OX 퀴즈 게임을 만들어줘.

- 문제와 정답(O 또는 X) 등록 기능
- 게임 시작하면 랜덤으로 문제 출제
- O, X 버튼으로 정답 선택
- 틀리면 게임오버
- 게임오버 시 맞춘 개수 표시
- 랭킹 저장 (이름, 점수)
- 랭킹 목록 보기
```

> **DB 연결하면**: 랭킹이 저장되어 새로고침해도 유지!

---

**예시 2: 점심 내기 사다리 게임**

```
나는 개발 초보야.
점심 내기 사다리 게임을 만들어줘.

- 참가자 이름 여러 명 입력
- 사다리 타기 시작 버튼
- 당첨자 한 명 크게 표시
- 기록 저장: 날짜, 당첨자 이름
- 지난 기록 목록 보기
```

> **DB 연결하면**: 누가 언제 샀는지 기록이 쌓임!

---

**예시 3: 밸런스 게임**

```
나는 개발 초보야.
밸런스 게임 앱을 만들어줘.

- 질문과 선택지 2개 등록 기능
- 랜덤 출제 버튼
- 등록된 질문 목록 보기
- 삭제 기능
```

> **질문 만들기 팁**: 클로드에게 "밸런스 게임 질문 10개 만들어줘"라고 요청!

---

### 클로드 활용 팁

퀴즈 문제나 질문도 클로드가 만들어줍니다.

```
OX 퀴즈 문제 20개 만들어줘.
주제는 일반 상식으로.
```

```
회사 관련 OX 퀴즈 10개 만들어줘.
```

```
밸런스 게임 질문 15개 만들어줘.
회사 생활 관련으로.
```

### Supabase 연결하기

자유 실습 앱에 DB를 연결하고 싶다면:

```
이 앱 데이터를 Supabase에 저장하고 싶어.
새로고침해도 유지되게 해줘.
```

MCP가 이미 설정되어 있으니 클로드가 바로 연결해줍니다!

---

## 정리

| 단계 | 내용 |
|------|------|
| 1 | Supabase 대시보드 → Settings → MCP 연결 명령어 복사 |
| 2 | 터미널에서 `claude mcp add ...` 명령어 실행 |
| 3 | `claude` 실행 후 Supabase 인증 (브라우저 로그인) |
| 4 | "가계부 데이터를 Supabase에 저장하도록 바꿔줘" 프롬프트 |
| 5 | 클로드가 테이블 생성 & 코드 수정 (Y로 허용) |
| 6 | 실행 후 새로고침해서 데이터 유지 확인 |

**핵심**: MCP 한 번 설정하면 클로드가 알아서 다 해줍니다!

**다음 챕터에서는** Git과 GitHub을 배웁니다.

---

<div style="text-align: center; margin-top: 40px;">

[← 이전: 챕터 6. 데이터베이스와 Supabase](chapter-06.md) | [다음: 챕터 8. GitHub 계정 설치 →](chapter-08.md)

</div>
