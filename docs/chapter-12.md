# 챕터 12. Vercel로 배포하기

> 이 챕터에서는 Vercel을 사용해서 고구마마켓을 인터넷에 배포합니다.
> 누구나 접속할 수 있는 실제 웹사이트가 됩니다.

---

## 12-1. Vercel이란?

### 웹사이트 호스팅 서비스

**Vercel**은 웹사이트를 인터넷에 올려주는 서비스입니다.

| 로컬 개발 | Vercel 배포 후 |
|-----------|---------------|
| `localhost:3000`으로만 접속 | `xxx.vercel.app`으로 누구나 접속 |
| 내 컴퓨터 켜야 함 | 24시간 접속 가능 |
| 나만 볼 수 있음 | 전 세계에서 접속 가능 |

### 왜 Vercel인가?

- **무료**: 개인 프로젝트는 무료
- **쉬움**: GitHub 연결만 하면 자동 배포
- **빠름**: 전 세계 CDN으로 빠른 속도

---

## 12-2. Vercel 가입하기

### Step 1: Vercel 접속

```
https://vercel.com
```

### Step 2: Sign Up

오른쪽 상단 **Sign Up** 클릭

### Step 3: GitHub로 가입

**Continue with GitHub** 클릭

> 이미 GitHub 계정이 있으니 그걸로 가입하면 편합니다.

### Step 4: 권한 허용

GitHub 연결 권한을 요청하면 **Authorize** 클릭

### Step 5: 완료

Vercel 대시보드가 나타나면 가입 완료!

---

## 12-3. GitHub 연결 & 배포

### Step 1: 새 프로젝트 만들기

Vercel 대시보드에서 **Add New...** → **Project** 클릭

### Step 2: GitHub 저장소 선택

**Import Git Repository** 섹션에서 `goguma-market` 저장소를 찾아 **Import** 클릭

> 저장소가 안 보이면 **Adjust GitHub App Permissions**를 클릭해서 권한을 추가합니다.

### Step 3: 프로젝트 설정

대부분 자동으로 설정됩니다. 확인할 것:

| 항목 | 값 |
|------|-----|
| Project Name | goguma-market (또는 원하는 이름) |
| Framework Preset | 자동 감지됨 (React, Next.js 등) |
| Root Directory | ./ (기본값) |

### Step 4: 환경변수 설정

Supabase 연결 정보를 추가합니다.

**Environment Variables** 섹션 펼치기:

| Name | Value |
|------|-------|
| VITE_SUPABASE_URL | 본인 Supabase URL |
| VITE_SUPABASE_ANON_KEY | 본인 anon key |

> 변수명은 프로젝트 코드에서 사용한 것과 동일해야 합니다.
> 클로드에게 "환경변수 뭐 써야 해?" 라고 물어보면 알려줍니다.

### Step 5: 배포

**Deploy** 버튼 클릭

배포가 진행됩니다. 1~2분 정도 걸립니다.

---

## 12-4. 배포된 사이트 확인

### 배포 완료

배포가 완료되면 축하 화면이 나타납니다!

### 사이트 주소

배포된 주소가 표시됩니다:

```
https://goguma-market.vercel.app
```

또는

```
https://goguma-market-username.vercel.app
```

### 접속 테스트

1. 주소를 클릭해서 사이트 접속
2. 상품 목록이 보이는지 확인
3. 등록, 수정, 삭제가 되는지 확인
4. 휴대폰에서도 접속해보기

---

## 12-5. 코드 수정 → 자동 재배포

Vercel의 강력한 기능: **GitHub에 푸시하면 자동으로 재배포!**

### 테스트해보기

1. 클로드에게 수정 요청

```
헤더 색상 바꿔줘
```

2. 커밋 + 푸시

3. Vercel 대시보드 확인
   - **Deployments** 탭에서 새 배포가 자동으로 진행됨

4. 배포 완료 후 사이트 접속
   - 변경사항이 반영됨!

### 자동 배포 흐름

```
코드 수정 → 커밋 → 푸시 → Vercel 자동 감지 → 재배포 → 사이트 업데이트
```

개발자가 따로 할 일이 없습니다!

---

## 배포 완료!

🎉 축하합니다!

| 항목 | 상태 |
|------|------|
| 고구마마켓 개발 | ✅ 완료 |
| CRUD 기능 | ✅ 완료 |
| Supabase 연결 | ✅ 완료 |
| Git 커밋 관리 | ✅ 완료 |
| Vercel 배포 | ✅ 완료 |

**실제로 동작하는 웹서비스**를 만들었습니다!

---

## 정리

| 단계 | 내용 |
|------|------|
| 1. Vercel 가입 | GitHub로 가입 |
| 2. 프로젝트 연결 | GitHub 저장소 Import |
| 3. 환경변수 | Supabase URL, Key 추가 |
| 4. 배포 | Deploy 버튼 클릭 |
| 5. 자동 배포 | 푸시하면 자동으로 재배포 |

**다음 챕터에서는** AI 챗봇을 만들어봅니다.

---

<div style="text-align: center; margin-top: 40px;">

[← 이전: 챕터 11. 고구마마켓 만들기 (3)](chapter-11.md) | [다음: 챕터 13. 간단 챗봇 만들기 →](chapter-13.md)

</div>
