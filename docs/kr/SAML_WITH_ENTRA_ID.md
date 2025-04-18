# Microsoft Entra ID와 SAML 연동

이 문서는 GenU를 Microsoft Entra ID(이전 Azure AD)와 SAML을 통해 통합하는 방법을 설명합니다.

## 필수 조건

- Microsoft Entra ID 테넌트 관리자 권한
- AWS 계정
- GenU가 배포된 상태

## 설정 단계

1. **Microsoft Entra ID에서 엔터프라이즈 애플리케이션 추가**
   - Microsoft Entra ID 관리 센터에 로그인
   - "엔터프라이즈 애플리케이션" > "새 애플리케이션" 선택
   - "비갤러리 애플리케이션" 선택
   - 애플리케이션 이름: "GenU"

2. **SAML 설정 구성**
   - "단일 사인온" > "SAML" 선택
   - 다음 정보 입력:
     - 식별자(엔티티 ID): `urn:amazon:cognito:sp:<your-user-pool-id>`
     - 회신 URL(ACS URL): `https://<your-genu-domain>/api/auth/saml/callback`
     - 로그아웃 URL: `https://<your-genu-domain>/logout`
     - 릴레이 상태: `https://<your-genu-domain>`

3. **사용자 특성 및 클레임 구성**
   - "사용자 특성 및 클레임" 섹션에서 다음 매핑 추가:
     - `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress` -> `user.mail`
     - `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/givenname` -> `user.givenname`
     - `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/surname` -> `user.surname`
     - `http://schemas.microsoft.com/ws/2008/06/identity/claims/groups` -> `user.groups`

4. **SAML 서명 인증서 관리**
   - "SAML 서명 인증서" 섹션에서 인증서 다운로드
   - 인증서 만료일 확인 및 갱신 계획 수립

5. **AWS Cognito 설정**
   - AWS 콘솔에서 Cognito 사용자 풀 접근
   - "외부 ID 공급자" 섹션에서 "SAML" 선택
   - Microsoft Entra ID 메타데이터 URL 입력:
     `https://login.microsoftonline.com/<tenant-id>/federationmetadata/2007-06/federationmetadata.xml?appid=<app-id>`
   - 속성 매핑 구성:
     - `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress` -> `email`
     - `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/givenname` -> `firstName`
     - `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/surname` -> `lastName`
     - `http://schemas.microsoft.com/ws/2008/06/identity/claims/groups` -> `custom:groups`

6. **사용자 및 그룹 할당**
   - Microsoft Entra ID에서 사용자 또는 그룹 선택
   - "할당" 버튼을 클릭하여 액세스 권한 부여
   - 필요한 경우 조건부 액세스 정책 구성

## 테스트

1. **Microsoft Entra ID 테스트**
   - 테스트 사용자로 로그인 시도
   - SAML 응답 확인
   - 속성 매핑 검증

2. **GenU 테스트**
   - "Microsoft로 로그인" 선택
   - Microsoft 계정으로 로그인
   - 성공적인 리디렉션 확인
   - 사용자 정보가 올바르게 표시되는지 확인

## 문제 해결

1. **인증 실패**
   - Microsoft Entra ID 로그 확인
   - SAML 추적 사용
   - 네트워크 연결 확인

2. **속성 매핑 문제**
   - Microsoft Entra ID에서 전송되는 클레임 확인
   - Cognito 매핑 설정 검증
   - 디버그 로그 분석

3. **세션 문제**
   - 쿠키 설정 확인
   - 세션 타임아웃 구성 검토
   - 브라우저 캐시 확인

## 보안 고려사항

1. **인증서 관리**
   - 정기적인 인증서 갱신
   - 안전한 인증서 저장
   - 비공개 키 보호

2. **접근 제어**
   - 최소 권한 원칙 적용
   - 그룹 기반 접근 제어 사용
   - 조건부 액세스 정책 구성

3. **모니터링**
   - 로그인 시도 모니터링
   - 비정상 접근 감지
   - 정기적인 보안 검토

## 모범 사례

1. **구성 관리**
   - 설정 변경 문서화
   - 변경 관리 프로세스 준수
   - 백업 구성 유지

2. **보안 강화**
   - MFA 활성화
   - 강력한 암호 정책 적용
   - 정기적인 보안 업데이트

3. **사용자 교육**
   - 보안 정책 교육
   - 문제 해결 방법 안내
   - 지원 채널 정보 제공

## 지원 및 리소스

- [Microsoft Entra ID 문서](https://docs.microsoft.com/azure/active-directory/)
- [AWS Cognito 문서](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-saml-idp.html)
- [이슈 트래커](https://github.com/aws-samples/generative-ai-use-cases/issues) 