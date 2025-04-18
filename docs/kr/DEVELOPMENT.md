# 로컬 개발 환경 설정

이 문서는 GenU의 로컬 개발 환경을 설정하는 방법을 설명합니다.

## 필수 조건

- Node.js 18.x 이상
- npm 9.x 이상
- AWS CLI가 설치되어 있고 구성되어 있어야 함
- AWS CDK가 설치되어 있어야 함

## 개발 환경 설정

1. 저장소를 클론합니다:
```bash
git clone https://github.com/aws-samples/generative-ai-use-cases.git
cd generative-ai-use-cases
```

2. 의존성을 설치합니다:
```bash
npm ci
```

3. 개발 서버를 시작합니다:
```bash
npm run dev
```

4. 브라우저에서 `http://localhost:5173`에 접속합니다.

## 개발 시 주의사항

- `.env` 파일을 생성하여 필요한 환경 변수를 설정해야 합니다.
- AWS 자격 증명이 올바르게 구성되어 있어야 합니다.
- 개발 중에는 실제 AWS 리소스가 아닌 로컬 스택을 사용하는 것이 좋습니다.

## 테스트 실행

다음 명령으로 테스트를 실행할 수 있습니다:

```bash
npm test
```

## 린트 실행

다음 명령으로 코드 린트를 실행할 수 있습니다:

```bash
npm run lint
```

## 빌드

다음 명령으로 프로덕션 빌드를 생성할 수 있습니다:

```bash
npm run build
```