# 챕터 2. 환경 설치

> 이 챕터에서는 클로드 코드를 사용하기 위한 프로그램들을 설치합니다.
> 순서대로 따라하면 누구나 설치할 수 있습니다.

---

## 설치할 프로그램 목록

| 프로그램 | 용도 |
|----------|------|
| **Node.js** | 웹앱을 실행하는 데 필요한 프로그램 |
| **VS Code** | 코드를 작성하고 터미널을 사용하는 프로그램 |
| **WSL** | Windows에서 리눅스 터미널을 사용하게 해주는 프로그램 |
| **클로드 코드** | AI와 대화하며 개발하는 프로그램 |

> **Mac 사용자**: WSL 설치는 건너뛰세요. Mac은 기본 터미널을 사용하면 됩니다.

---

## 2-1. Node.js 설치

### Node.js란?

Node.js는 웹앱을 실행하는 데 필요한 프로그램입니다.
클로드 코드가 만들어주는 웹앱은 대부분 Node.js가 있어야 실행됩니다.

### Step 1: 다운로드 페이지 접속

브라우저에서 아래 주소로 접속합니다.

```
https://nodejs.org/ko/download
```

<!-- 스크린샷: Node.js 공식 사이트 메인 -->
![Node.js 사이트](./images/ch02-nodejs-site.png)

### Step 2: LTS 버전 다운로드

설치 버튼을 클릭해서 다운로드 합니다. 

<!-- 스크린샷: LTS 다운로드 버튼 -->

![LTS 다운로드](iShot_2026-01-28_00.29.39.png)

### Step 3: 설치 파일 실행

다운로드된 파일을 더블클릭해서 실행합니다.

<!-- 스크린샷: 다운로드된 설치 파일 -->

![alt text](iShot_2026-01-28_00.31.09.png)

### Step 4: 설치 진행

설치 마법사가 나타나면 **Next**를 계속 클릭합니다.

1. **Welcome** 화면 → `Next`
2. **License Agreement** → 체크박스 선택 → `Next`
3. **Destination Folder** → 기본값 그대로 → `Next`
4. **Custom Setup** → 기본값 그대로 → `Next`
5. **Ready to install** → `Install`

### Step 5: 설치 완료

**Finish** 버튼을 클릭하면 설치가 완료됩니다.

### Step 6: 설치 확인

설치가 잘 되었는지 확인합니다.

1. `Windows 키 + R` 을 누릅니다
2. `cmd` 입력 후 Enter
3. 아래 명령어 입력 후 Enter

```
node --v
```

버전 번호가 나오면 성공입니다. (예: `v20.x.x`)

<!-- 스크린샷: node --version 결과 -->
![alt text](image.png)

---

## 2-2. VS Code 설치

### VS Code란?

VS Code(Visual Studio Code)는 코드를 작성하는 프로그램입니다.
메모장의 고급 버전이라고 생각하면 됩니다.

클로드 코드도 VS Code의 터미널에서 실행합니다.

### Step 1: 다운로드 페이지 접속

브라우저에서 아래 주소로 접속합니다.

```
https://code.visualstudio.com/download
```


### Step 2: 다운로드

**Download for Windows** 버튼을 클릭합니다.

<!-- 스크린샷: 다운로드 버튼 -->
![alt text](image-1.png)

### Step 3: 설치 파일 실행

다운로드된 파일을 더블클릭해서 실행합니다.

### Step 4: 설치 진행

설치 마법사가 나타나면 진행합니다. 다 Next를 누르시고, 체크박스가 많이 나와있는 곳에서만 체크박스를 확인해주세요.

1. **License Agreement** → "I accept" 선택 → `Next`
2. **Select Destination** → 기본값 그대로 → `Next`
3. **Select Start Menu** → 기본값 그대로 → `Next`
4. **Select Additional Tasks** → 아래 항목들 체크 권장
   - ✅ Add "Open with Code" action to Windows Explorer file context menu
   - ✅ Add "Open with Code" action to Windows Explorer directory context menu
   - ✅ Add to PATH
5. **Ready to Install** → `Install`

<!-- 스크린샷: Additional Tasks 체크 화면 -->
![alt text](iShot_2026-01-27_23.24.08.png)

> **Add to PATH**는 꼭 체크하세요! 터미널에서 VS Code를 실행할 때 필요합니다.

### Step 5: 설치 완료

**Finish** 버튼을 클릭하면 설치가 완료됩니다.
"Launch Visual Studio Code" 체크박스가 선택되어 있으면 바로 VS Code가 실행됩니다.

<!-- 스크린샷: 설치 완료 -->
![alt text](iShot_2026-01-27_23.27.11.png)

### Step 6: VS Code 

보통 3분할, 4분할로 사용합니다. 메인인 가운데는 메모장처럼 코드를 직접 작성하는 곳이고, 왼쪽은 폴더, 오른쪽은 채팅(우리는 사용하지 않음), 그리고 아래쪽은 터미널입니다. x표시로 각 분할창을 끌수있고, VS Code의 우측상단의 아이콘들을 통해 다시 키고 끄고 할 수 있습니다. 

메모장 파일을 생성하고 수정해보세요.


---

## 2-3. WSL 설치 (Windows만)

> **Mac 사용자는 이 섹션을 건너뛰세요.**
> Mac은 기본 터미널을 사용하면 됩니다.

### WSL이란?

WSL(Windows Subsystem for Linux)은 Windows에서 리눅스를 사용할 수 있게 해주는 프로그램입니다.

클로드 코드는 리눅스/Mac 환경에서 더 잘 작동하기 때문에, Windows에서는 WSL을 사용합니다.

### Step 1: VS Code 터미널 열기

VS Code에서 터미널을 엽니다.

단축키: `` Ctrl + ` ``

터미널이 열리면 기본적으로 **PowerShell**이 실행됩니다.

<!-- 스크린샷: VS Code PowerShell 터미널 -->
![PowerShell 터미널](./images/ch02-vscode-powershell.png)

### Step 2: WSL 설치 여부 확인

아래 명령어를 입력해서 WSL이 이미 설치되어 있는지 확인합니다.

```powershell
wsl --version
```

**결과에 따라 다음 단계가 달라집니다:**

| 결과 | 의미 | 다음 단계 |
|------|------|----------|
| 버전 번호가 나옴 | 이미 설치됨 | → Step 5로 이동 |
| 에러 메시지 | 설치 안 됨 | → Step 3 진행 |

<!-- 스크린샷: wsl --version 결과 (설치됨/안됨 둘 다) -->
![alt text](image-2.png)

### Step 3: WSL 설치 (설치 안 된 경우만)

WSL이 설치되어 있지 않다면, 아래 명령어를 입력합니다.

```powershell
wsl --install
```

설치가 완료되면 **컴퓨터를 재시작**합니다.

### Step 4: 재시작 후 Ubuntu 설정 (설치 안 된 경우만)

> 이미 WSL이 설치되어 있었다면 이 단계를 건너뛰세요.

컴퓨터를 재시작하면 Ubuntu 설정 창이 자동으로 나타납니다.

1. **사용자 이름** 입력 (영어, 소문자, 공백 없이)
   - 예: `huhsame`, `myname`
2. **비밀번호** 입력
   - 입력할 때 화면에 안 보이는 게 정상입니다
   - 비밀번호를 입력하고 Enter
3. **비밀번호 확인** - 다시 한번 입력


> **비밀번호가 안 보여요!**
> 리눅스에서는 비밀번호 입력 시 화면에 아무것도 표시되지 않습니다.
> 그냥 입력하고 Enter를 누르면 됩니다.

### Step 5: 설치 확인

설정이 완료되면 아래와 같은 화면이 나타납니다.

```
사용자이름@컴퓨터이름:~$
```


`exit` 를 입력하고 Enter를 눌러 창을 닫습니다.

---

## 2-4. VS Code에서 WSL 터미널 설정

VS Code의 기본 터미널을 WSL(Ubuntu)로 변경합니다.

### Step 1: VS Code 실행

VS Code를 실행합니다.

### Step 2: 터미널 열기

상단 메뉴에서 분할창 아이콘을 통해 터미널을 엽니다.

또는 단축키: `` Ctrl + ` ``

<!-- 스크린샷: 터미널 열기 -->
![alt text](image-3.png)
### Step 3: 기본 터미널 변경

터미널 오른쪽 상단의 **∨ (아래 화살표)** 버튼을 클릭합니다.

<!-- 스크린샷: 터미널 드롭다운 -->

![alt text](iShot_2026-01-27_23.43.18.png)

### Step 4: Select Default Profile 클릭

**Select Default Profile** 을 클릭합니다.

<!-- 스크린샷: Select Default Profile -->

![alt text](iShot_2026-01-27_23.47.53.png)

### Step 5: Ubuntu (WSL) 선택

목록에서 **Ubuntu (WSL)** 또는 **WSL** 을 선택합니다.

<!-- 스크린샷: Ubuntu 선택 -->
![alt text](iShot_2026-01-27_23.48.14.png)

### Step 6: 새 터미널로 확인

기존 터미널을 닫고 새 터미널을 엽니다.
![alt text](iShot_2026-01-27_23.49.18.png)
1. 터미널 창의 **휴지통 아이콘** 클릭 (터미널 닫기)
2. `` Ctrl + ` `` 로 새 터미널 열기

터미널에 아래와 같이 표시되면 성공입니다.

```
사용자이름@컴퓨터이름:~$
```

<!-- 스크린샷: WSL 터미널 확인 -->

![alt text](iShot_2026-01-27_23.50.20.png)

> **PowerShell이 아닌 Ubuntu가 기본 터미널이 되었습니다!**


터미널의 저 표시는 폴더를 나타냅니다.
![alt text](image-4.png)

---

## 2-5. 클로드 코드 설치

이제 클로드 코드를 설치합니다.

> **공식 설치 가이드**: https://code.claude.com/docs/en/setup#installation

![alt text](iShot_2026-01-28_00.00.45.png)
윈도우말고 WSL로 보아야 합니다.


### Step 1: VS Code 터미널 열기

VS Code에서 터미널을 엽니다.



### Step 2: 클로드 코드 설치 명령어 실행

**터미널에서** 아까 복사한 명령어를 입력하고 Enter를 누릅니다.

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

<!-- 스크린샷: 설치 스크립트 실행 -->
![alt text](iShot_2026-01-28_00.04.35.png)
![alt text](iShot_2026-01-28_00.05.00.png)

설치가 진행되고, 완료되면 안내 메시지가 나타납니다.
![alt text](iShot_2026-01-28_00.08.22.png)
![alt text](iShot_2026-01-28_00.08.48.png)

### Step 3: 설치 확인

새 터미널에서 아래 명령어로 확인합니다.

```bash
claude --version
```

버전 번호가 나오면 설치 성공입니다.


> **자동 업데이트**: 이 방식으로 설치하면 클로드 코드가 자동으로 최신 버전을 유지합니다.

---

## 2-6. 클로드 코드 실행 및 계정 연결

### Step 1: 클로드 코드 실행

터미널에서 아래 명령어를 입력합니다.

```bash
claude
```

<!-- 스크린샷: claude 실행 -->
![alt text](iShot_2026-01-28_00.09.20.png)
![alt text](iShot_2026-01-28_00.12.48.png)
![alt text](iShot_2026-01-28_00.13.26.png)

### Step 2: 로그인 진행

처음 실행하면 로그인이 필요합니다.

화면에 나오는 안내에 따라 진행합니다.

![](iShot_2026-01-28_00.17.14.png)
1. Enter를 누르면 브라우저가 열립니다
2. Claude 계정으로 로그인합니다 (없으면 회원가입)
3. 권한 허용 화면에서 **Allow** 클릭

![alt text](iShot_2026-01-28_00.21.31.png)
![alt text](iShot_2026-01-28_00.18.38.png)
### Step 3: 로그인 완료

Login Successful 이라고 나오면 성공입니다.

<!-- 스크린샷: 로그인 완료 -->

![alt text](iShot_2026-01-28_00.19.47.png)
![alt text](iShot_2026-01-28_00.20.35.png)

### Step 4: 클로드코드 확인

 클로드 코드가 드디어 실행되었습니다. 앞으로는 지금까지 했던 설치나 세팅 작업 없이, 클로드를 실행하면 바로 이 화면이 나옵니다.


<!-- 스크린샷: 클로드 코드 실행 화면 -->

![alt text](iShot_2026-01-28_00.22.07.png)


### Step 5: 테스트 대화

간단한 테스트를 해봅시다. 아래 내용을 입력하고 Enter:

```
안녕, 나는 클로드 코드를 처음 써보는 사람이야!
```

클로드가 답변하였습니다 축하합니다.



### Step 6: 종료하기

테스트가 끝나면 아래 명령어로 종료합니다.

```
/exit
```
![alt text](iShot_2026-01-28_00.25.19.png)
![alt text](iShot_2026-01-28_00.25.46.png)
![alt text](iShot_2026-01-28_00.26.15.png)
---

## 트러블슈팅

### Node.js 설치 문제

**문제: `node --version`이 안 됨**

→ 컴퓨터를 재시작하고 다시 시도하세요.

→ 환경 변수에 Node.js가 추가되지 않았을 수 있습니다. Node.js를 다시 설치하세요.

### WSL 설치 문제

**문제: `wsl --install` 에러**

→ Windows 버전이 낮을 수 있습니다. Windows 업데이트를 먼저 진행하세요.

→ 가상화 기능이 꺼져 있을 수 있습니다. BIOS에서 가상화를 활성화하세요.

**문제: Ubuntu 설정 창이 안 나옴**

→ 시작 메뉴에서 "Ubuntu"를 검색해서 직접 실행하세요.


**문제: `claude` 명령어가 안 됨**

→ 터미널을 닫고 새로 열어보세요.

→ VS Code를 완전히 종료하고 다시 실행해보세요.

### 로그인 문제

**문제: 브라우저가 안 열림**

→ 터미널에 표시된 URL을 직접 복사해서 브라우저에 붙여넣으세요.

**문제: 로그인 후 터미널에서 아무 반응이 없음**

→ 잠시 기다려보세요. 연결에 시간이 걸릴 수 있습니다.

→ `Ctrl + C`로 종료 후 `claude`를 다시 실행하세요.

---

## 설치 완료 체크리스트

모든 항목이 완료되었는지 확인하세요.

- [ ] Node.js 설치됨 (`node --version` 작동)
- [ ] VS Code 설치됨
- [ ] WSL 설치됨 (Windows만)
- [ ] VS Code 기본 터미널이 Ubuntu로 설정됨 (Windows만)
- [ ] 클로드 코드 설치됨 (`claude --version` 작동)
- [ ] 클로드 계정 연결됨 (`claude` 실행 후 대화 가능)

---

## 정리

| 프로그램 | 설치 방법 |
|----------|----------|
| Node.js | nodejs.org/ko/download → 다운로드 → 설치 |
| VS Code | code.visualstudio.com → 다운로드 → 설치 |
| WSL | PowerShell 관리자 → `wsl --install` → 재시작 |
| 클로드 코드 | 터미널에서 `curl -fsSL https://claude.ai/install.sh \| bash` |

**다음 챕터에서는** 클로드 코드의 기본 사용법을 배웁니다.

---

<div style="text-align: center; margin-top: 40px;">

[← 이전: 챕터 1. 오프닝](chapter-01.md) | [다음: 챕터 3. 클로드 코드 기본 사용법 →](chapter-03.md)

</div>
