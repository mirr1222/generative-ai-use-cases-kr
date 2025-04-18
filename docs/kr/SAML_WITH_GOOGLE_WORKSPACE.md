# Google Workspace와 SAML 통합

이 문서는 GenU를 Google Workspace와 SAML을 통해 통합하는 방법을 설명합니다.

## 필수 조건

- Google Workspace 관리자 계정
- AWS 계정
- GenU가 배포된 상태

## 설정 단계

1. Google Workspace 관리 콘솔에서:
   - 앱 > 웹 및 모바일 앱으로 이동
   - "앱 추가" > "앱 및 사용자 정의 앱 추가" 선택
   - "SAML 앱 추가" 선택

2. 앱 정보 입력:
   - 앱 이름: "GenU"
   - 설명: "Generative AI Use Cases"
   - 로고: 선택 사항

3. SAML 설정:
   - ACS URL: `https://<your-genu-domain>/api/auth/saml/callback`
   - 엔티티 ID: `urn:amazon:cognito:sp:<your-user-pool-id>`
   - 이름 ID 형식: "이메일"
   - 이름 ID: "기본 이메일"

4. 속성 매핑:
   - `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress` -> `email`
   - `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/givenname` -> `firstName`
   - `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/surname` -> `lastName`

5. Google Workspace에서 메타데이터 다운로드:
   - "메타데이터 다운로드" 버튼 클릭
   - 다운로드된 XML 파일을 저장

6. AWS 콘솔에서:
   - Cognito 사용자 풀 설정
   - "외부 ID 공급자" 섹션에서 "SAML" 선택
   - Google Workspace 메타데이터 XML 파일 업로드
   - 속성 매핑 설정 저장

## 테스트

1. Google Workspace에서 테스트 사용자에게 앱 액세스 권한 부여
2. GenU 로그인 페이지에서 "Google로 로그인" 선택
3. Google 계정으로 로그인
4. 성공적으로 리디렉션되는지 확인

## 문제 해결

- 로그인 실패 시 CloudWatch 로그 확인
- SAML 응답이 올바른 형식인지 확인
- 속성 매핑이 정확한지 확인
- 필요한 경우 [이슈 트래커](https://github.com/aws-samples/generative-ai-use-cases/issues)에 보고