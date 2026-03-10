# Teams to Excel Sync

Microsoft Teams 채팅 메시지를 분석하여 주간 보고서를 자동 생성하고 Excel에 저장하는 도구입니다.

🔗 **라이브 데모:** https://jskang-fcg.github.io/htmltoexel/

## 주요 기능

- ✅ Microsoft Teams 채팅 메시지 불러오기
- ✅ 날짜 범위 선택 또는 전체 메시지 로드
- ✅ AI 기반 메시지 분석 (OpenAI GPT-4o-mini)
- ✅ 목표/과제/결과/요약 자동 추출
- ✅ OneDrive Excel 파일에 직접 저장

## 사용 방법

### 1단계: 로그인
- Microsoft 계정으로 로그인
- Teams 채팅 읽기 및 OneDrive 파일 접근 권한 필요

### 2단계: 채팅 선택
- 채팅 목록 불러오기 클릭
- 원하는 채팅방 선택

### 3단계: 메시지 불러오기
- 날짜 범위 설정 후 "메시지 불러오기" 또는
- "전체 메시지 불러오기" 클릭
- 체크박스로 분석할 메시지 선택

### 4단계: AI 분석
- OpenAI API Key 입력 (선택사항)
- "🤖 AI로 메시지 분석하여 보고서 생성" 클릭
- AI가 목표/과제/결과/요약 자동 추출
- 필요시 내용 직접 수정

### 5단계: Excel 저장
- OneDrive 파일 경로 입력 (예: `/주간보고.xlsx`)
- 시트 이름 및 컬럼 설정
- "📊 Excel에 보고서 추가" 클릭

## 사전 준비

### Azure AD 앱 등록 (관리자)
1. [Azure Portal](https://portal.azure.com) → 앱 등록
2. 리디렉션 URI 추가 (SPA):
   - `http://localhost:8080/teamstoexel.html` (로컬)
   - `https://jskang-fcg.github.io/htmltoexel/` (배포)
3. API 권한: `Chat.Read`, `Files.ReadWrite`, `User.Read`

### OpenAI API Key (선택)
- [OpenAI Platform](https://platform.openai.com/api-keys)에서 발급
- 처음 가입 시 $5 무료 크레딧 제공
- API Key는 브라우저에만 저장됨 (서버 전송 없음)

### OneDrive Excel 파일
- OneDrive에 Excel 파일 미리 생성 필요
- 예: `주간보고.xlsx`
- 첫 행에 헤더 권장: 월, 주차, 목표, 목표기한, 과제, 과제기한, 결과, 요약

## 기술 스택

- HTML/CSS/JavaScript (단일 파일)
- Microsoft Authentication Library (MSAL.js)
- Microsoft Graph API
- OpenAI API (GPT-4o-mini)

## 보안

- Client ID, Tenant ID는 공개 정보 (SPA 앱)
- 모든 인증은 Azure AD에서 처리
- OpenAI API Key는 브라우저 로컬에서만 사용
- 서버 없이 클라이언트에서만 동작

## 라이선스

MIT License
