# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 프로젝트 개요

비개발자를 위한 클로드 코드 교육 교재 (Docsify 기반 문서 사이트)

- **대상**: 비개발자
- **목표**: 바이브 코딩으로 웹앱 개발 + DB 연결 + Git 협업 + 배포 경험
- **프로젝트**: 가계부, 당근마켓 클론, AI 챗봇

## 문서 구조

```
docs/
├── README.md          # 메인 페이지
├── _sidebar.md        # 사이드바 네비게이션
├── chapter-01.md ~ chapter-17.md  # 각 챕터
└── *.png              # 스크린샷 이미지
```

- `claudecode.md`: 원래 교육 커리큘럼 계획서 (참고용)

## 로컬 실행

```bash
# Docsify CLI로 실행
npx docsify-cli serve docs

# 또는 Python 간이 서버
cd docs && python -m http.server 3000
```

브라우저에서 `http://localhost:3000` 접속

## 작성 가이드

- 챕터 파일명: `chapter-XX.md` 형식
- 스크린샷: `docs/` 폴더에 직접 저장 (images 하위 폴더 없이)
- 언어: 한국어, 비개발자 눈높이의 쉬운 설명
- 각 챕터 하단에 이전/다음 네비게이션 링크 포함
- 새 챕터 추가 시 `_sidebar.md`도 함께 수정
