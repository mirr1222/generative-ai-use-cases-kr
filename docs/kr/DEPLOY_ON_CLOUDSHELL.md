# AWS CloudShell로 배포하기

이 문서는 AWS CloudShell을 사용하여 GenU를 배포하는 방법을 설명합니다.

## 전제 조건

- AWS 계정이 있어야 합니다.
- CloudShell에 접근할 수 있어야 합니다.

## 배포 단계

1. AWS 콘솔에 로그인하고 CloudShell을 엽니다.

2. 다음 명령으로 저장소를 클론합니다:
```bash
git clone https://github.com/aws-samples/generative-ai-use-cases.git
cd generative-ai-use-cases
```

3. 의존성을 설치합니다:
```bash
npm ci
```

4. CDK 부트스트랩을 실행합니다 (처음 한 번만):
```bash
npx -w packages/cdk cdk bootstrap
```

5. 배포를 실행합니다:
```bash
npm run cdk:deploy
```

## 주의사항

- CloudShell 세션은 20분 동안 활동이 없으면 종료됩니다.
- CloudShell의 저장 공간은 제한되어 있습니다.
- 배포가 완료될 때까지 기다려야 합니다 (약 20분 소요).

## 문제 해결

- CloudShell 세션이 종료된 경우, 다시 시작하고 마지막 단계부터 진행하세요.
- 메모리 부족 오류가 발생하면 CloudShell을 재시작하세요.
- 배포 실패 시 로그를 확인하고 필요한 조치를 취하세요.