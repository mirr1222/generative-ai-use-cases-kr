# AWS에 배포하기

이 문서는 AWS에 GenU를 배포하는 방법을 설명합니다.

## 전제 조건

- AWS 계정이 있어야 합니다.
- AWS CLI가 설치되어 있고 구성되어 있어야 합니다.
- Node.js와 npm이 설치되어 있어야 합니다.
- AWS CDK가 설치되어 있어야 합니다.

## 배포 단계

1. 저장소를 클론합니다:
```bash
git clone https://github.com/aws-samples/generative-ai-use-cases.git
cd generative-ai-use-cases
```

2. 의존성을 설치합니다:
```bash
npm ci
```

3. CDK 부트스트랩을 실행합니다 (처음 한 번만):
```bash
npx -w packages/cdk cdk bootstrap
```

4. 배포를 실행합니다:
```bash
npm run cdk:deploy
```

## 구성 옵션

배포 전에 `packages/cdk/cdk.json` 파일에서 다음 설정을 확인하세요:

- `modelRegion`: 모델이 활성화된 리전
- `modelIds`: 텍스트 생성에 사용할 모델 ID
- `imageGenerationModelIds`: 이미지 생성에 사용할 모델 ID
- `videoGenerationModelIds`: 비디오 생성에 사용할 모델 ID

## 비용 고려사항

- 사용하는 AWS 서비스에 따라 비용이 발생합니다.
- 모델 사용량에 따라 추가 비용이 발생할 수 있습니다.
- 비용 추정은 [비용 추정 페이지](https://aws.amazon.com/jp/cdp/ai-chatbot/)를 참조하세요.

## 모니터링

배포 후 AWS 콘솔에서 다음 서비스를 모니터링할 수 있습니다:

- CloudWatch: 로그 및 메트릭
- CloudTrail: API 호출 기록
- Cost Explorer: 비용 모니터링