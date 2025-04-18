# 브라우저 확장 프로그램 SAML 설정

이 문서는 GenU 브라우저 확장 프로그램의 SAML 인증 설정 방법을 설명합니다.

## 필수 조건

- GenU가 SAML을 지원하도록 배포되어 있어야 함
- ID 공급자 (IdP) 설정 완료
- 확장 프로그램이 설치되어 있어야 함

## SAML 설정 단계

1. **ID 공급자 설정**
   - IdP 관리 콘솔에 로그인
   - 새 SAML 애플리케이션 추가
   - 다음 정보 입력:
     - ACS URL: `https://<your-genu-domain>/api/auth/saml/callback`
     - 엔티티 ID: `urn:amazon:cognito:sp:<your-user-pool-id>`
     - 이름 ID 형식: 이메일
     - 속성 매핑 설정

2. **메타데이터 다운로드**
   - IdP에서 SAML 메타데이터 XML 파일 다운로드
   - 파일을 안전한 위치에 저장

3. **AWS Cognito 설정**
   - AWS 콘솔에서 Cognito 사용자 풀 접근
   - "외부 ID 공급자" 섹션으로 이동
   - SAML 공급자 추가
   - 다운로드한 메타데이터 XML 파일 업로드
   - 속성 매핑 구성:
     - `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress` -> `email`
     - `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/givenname` -> `firstName`
     - `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/surname` -> `lastName`

4. **확장 프로그램 설정**
   - 브라우저에서 확장 프로그램 옵션 페이지 열기
   - "인증" 섹션으로 이동
   - SAML 설정 활성화
   - 필요한 경우 추가 설정 구성

## 속성 매핑

| IdP 속성 | Cognito 속성 | 설명 |
|----------|--------------|------|
| email | email | 사용자 이메일 주소 |
| givenName | firstName | 사용자 이름 |
| surname | lastName | 사용자 성 |
| groups | custom:groups | 사용자 그룹 정보 |
| department | custom:department | 부서 정보 |

## 보안 고려사항

1. **인증서 관리**
   - SAML 서명 인증서 주기적 갱신
   - 안전한 인증서 저장
   - 비공개 키 보호

2. **접근 제어**
   - 최소 권한 원칙 적용
   - 그룹 기반 접근 제어 설정
   - 세션 타임아웃 구성

3. **감사 및 모니터링**
   - 인증 시도 로깅
   - 비정상 접근 모니터링
   - 정기적인 보안 검토

## 문제 해결

1. **인증 실패**
   - IdP 및 SP 설정 확인
   - 네트워크 연결 확인
   - 인증서 유효성 검증

2. **속성 매핑 문제**
   - IdP에서 전송되는 속성 확인
   - Cognito 매핑 설정 검증
   - 로그 분석

3. **세션 문제**
   - 쿠키 및 캐시 확인
   - 세션 타임아웃 설정 검토
   - 브라우저 설정 확인

## 모범 사례

1. **구성 관리**
   - 설정 변경 문서화
   - 변경 관리 프로세스 준수
   - 백업 구성 유지

2. **보안 강화**
   - 강력한 암호화 사용
   - 정기적인 보안 업데이트
   - 취약점 스캔 수행

3. **사용자 교육**
   - 보안 정책 교육
   - 문제 해결 방법 안내
   - 지원 채널 정보 제공

## 지원 및 리소스

- [공식 문서](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-saml-idp.html)
- [이슈 트래커](https://github.com/aws-samples/generative-ai-use-cases/issues)
- AWS 지원 센터 