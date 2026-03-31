# CLAUDE.md

이 파일은 Claude Code가 이 프로젝트에서 작업할 때 참고하는 지침서입니다.

## 프로젝트 개요

- **프로젝트명**: 레미오 (REMIO)
- **설명**: 홍대입구역 2번 출구 도보 3분 거리의 레트로 미니 오락실 웹사이트
- **운영 서비스**: 인형뽑기, 가챠머신
- **판매 상품**:
  - 12지신 액막이 키링 12종 (15,000원) - 자체 제작
  - 오행음양 팔찌 5종 (25,000원) - 자체 제작
- **주요 기능**:
  - 무료 사주오행 분석
  - 카카오톡 공유 후 순금 1돈 이벤트
  - 제휴브랜드 소개 (별도 페이지)

## 기술 스택

- 순수 HTML / CSS / JavaScript
- 외부 프레임워크 없음
- Vercel 배포 (GitHub 연동 자동 배포)
- 도메인: remio.co.kr (가비아)

## 프로젝트 구조

```
remio-final.html     # 메인 홈페이지 (단일 HTML 파일)
partner.html         # 제휴브랜드 전용 페이지
CLAUDE.md            # 프로젝트 지침서
deploy/              # Vercel 배포 폴더
  ├── index.html     # remio-final.html 복사본 (배포용)
  ├── partner.html   # partner.html 복사본 (배포용)
  ├── sitemap.xml    # 사이트맵
  ├── robots.txt     # 크롤러 설정
  └── .vercel/       # Vercel 설정
```

## 페이지 구성

### 메인 홈페이지 (`remio-final.html`)
- 히어로 배너 + 메뉴
- 12지신 키링 판매 섹션
- 오행팔찌 판매 섹션
- 무료 사주 분석 + 순금 이벤트
- 사주궁합 소개팅
- 오시는 길
- 고객센터

### 제휴브랜드 페이지 (`partner.html`)
- 로고 무한 마퀴 (파트너 브랜드 스크롤)
- 추천맛집 제휴매장 25곳 (럭키카드 리뷰이벤트 포함)
- 사주·타로 제휴매장 24곳 (레미오 인형 판매)
- 탭 UI + 더보기/접기 기능
- 제휴 문의 배너

## 디자인 가이드

- **스타일**: 팝마트(Pop Mart) 스타일
- **배경색**: 흰색 (#FFFFFF)
- **포인트 컬러**: 핑크(#FF6B8A), 스카이블루(#7EC8E3), 코랄(#FFB5A7)
- **폰트**:
  - Gamja Flower (Google Fonts)
  - Do Hyeon (Google Fonts)
  - Jua (Google Fonts)

## 개발 규칙

- 메인 페이지는 `remio-final.html` 단일 파일로 유지
- 별도 기능 페이지(제휴브랜드 등)는 독립 HTML 파일로 분리 가능
- HTML/CSS/JS를 분리하지 않고 각 파일 내에 인라인으로 작성
- 배포 시 `deploy/` 폴더에 복사 후 push
- 커밋 메시지는 한국어로 작성
- 코드 주석은 한국어로 작성
- Claude와의 대화는 항상 한국어로 진행

## 배포 프로세스

1. 소스 파일 수정 (`remio-final.html`, `partner.html` 등)
2. `deploy/` 폴더에 최신 파일 복사 (`index.html` = `remio-final.html`)
3. `git add` → `git commit` → `git push origin main`
4. Vercel이 GitHub 연동으로 자동 배포
