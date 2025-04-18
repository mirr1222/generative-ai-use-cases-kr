# 배포 옵션

GenU는 다양한 방식으로 배포할 수 있습니다. 각 배포 옵션의 특징과 사용 사례를 설명합니다.

## 배포 옵션 비교

| 옵션 | 설명 | 장점 | 단점 | 추천 사용 사례 |
|------|------|------|------|---------------|
| AWS 직접 배포 | AWS 계정에 직접 배포 | - 완전한 제어권<br>- 커스터마이징 가능<br>- 확장성 | - 설정 복잡<br>- 관리 부담 | - 대규모 배포<br>- 엔터프라이즈 사용 |
| AWS CloudShell | AWS CloudShell을 통한 배포 | - 설정 간소화<br>- 빠른 시작<br>- AWS 콘솔 통합 | - 세션 제한<br>- 저장 공간 제한 | - 빠른 테스트<br>- 개념 증명 |
| 로컬 개발 | 로컬 환경에서 개발 | - 빠른 반복<br>- 디버깅 용이<br>- 오프라인 개발 | - 프로덕션과 차이<br>- 리소스 제한 | - 개발<br>- 테스트 |

## 배포 옵션 선택 가이드

### AWS 직접 배포를 선택하는 경우
- 완벽한 제어가 필요한 경우
- 대규모 사용자 기반을 예상하는 경우
- 커스텀 설정이 필요한 경우
- 보안 요구사항이 엄격한 경우

### AWS CloudShell을 선택하는 경우
- 빠른 시작이 필요한 경우
- AWS 콘솔에서 직접 작업하고 싶은 경우
- 간단한 테스트나 개념 증명이 필요한 경우
- 제한된 리소스로 시작하고 싶은 경우

### 로컬 개발을 선택하는 경우
- 개발 및 테스트 목적인 경우
- 오프라인에서 작업이 필요한 경우
- 빠른 반복이 필요한 경우
- AWS 리소스 사용을 최소화하고 싶은 경우

## 비용 고려사항

각 배포 옵션별 예상 비용:

1. **AWS 직접 배포**
   - AWS 서비스 사용량에 따른 비용
   - 모델 사용량에 따른 추가 비용
   - 스토리지 및 네트워크 비용

2. **AWS CloudShell**
   - 기본적으로 무료
   - 배포된 리소스에 대한 비용만 발생

3. **로컬 개발**
   - 로컬 리소스 사용 비용만 발생
   - AWS 서비스 사용 시 해당 비용 발생

## 보안 고려사항

각 배포 옵션별 보안 측면:

1. **AWS 직접 배포**
   - IAM 역할 및 정책 설정 가능
   - VPC 및 보안 그룹 구성 가능
   - 암호화 설정 가능

2. **AWS CloudShell**
   - AWS 계정 보안 설정 적용
   - 세션 기반 접근 제어
   - 임시 자격 증명 사용

3. **로컬 개발**
   - 로컬 보안 설정 필요
   - 개발용 자격 증명 관리 필요
   - 로컬 네트워크 보안 고려

## 다음 단계

선택한 배포 옵션에 따라 다음 문서를 참조하세요:

- [AWS에 배포하기](DEPLOY_ON_AWS.md)
- [AWS CloudShell로 배포하기](DEPLOY_ON_CLOUDSHELL.md)
- [로컬 개발 환경 설정](DEVELOPMENT.md) 