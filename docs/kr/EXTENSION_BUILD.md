# 브라우저 확장 프로그램 빌드

이 문서는 GenU 브라우저 확장 프로그램을 빌드하는 방법을 설명합니다.

## 필수 조건

- Node.js 18.x 이상
- npm 9.x 이상
- Git

## 빌드 단계

1. 저장소를 클론합니다:
```bash
git clone https://github.com/aws-samples/generative-ai-use-cases.git
cd generative-ai-use-cases
```

2. 의존성을 설치합니다:
```bash
npm ci
```

3. 확장 프로그램 디렉토리로 이동합니다:
```bash
cd packages/browser-extension
```

4. 빌드를 실행합니다:
```bash
npm run build
```

## 빌드 출력

빌드가 완료되면 `dist` 디렉토리에 다음 파일들이 생성됩니다:

- `manifest.json`: 확장 프로그램 매니페스트
- `background.js`: 백그라운드 스크립트
- `content.js`: 콘텐츠 스크립트
- `popup.html`: 팝업 UI
- 기타 리소스 파일들

## 테스트

1. Chrome/Edge에서 `chrome://extensions`로 이동합니다.
2. "개발자 모드"를 활성화합니다.
3. "압축해제된 확장 프로그램을 로드합니다"를 클릭합니다.
4. `dist` 디렉토리를 선택합니다.

## 문제 해결

- 빌드 실패 시 로그를 확인하세요.
- 의존성 문제가 있는 경우 `node_modules`를 삭제하고 다시 설치하세요.
- 여전히 문제가 있다면 [이슈 트래커](https://github.com/aws-samples/generative-ai-use-cases/issues)에 보고하세요.