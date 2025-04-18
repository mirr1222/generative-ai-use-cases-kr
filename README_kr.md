<div markdown="1" align="center">
  <h1>생성형 AI 유스케이스 (GenU)</h1>

[![](https://img.shields.io/badge/Documentation-Latest-blue)](https://aws-samples.github.io/generative-ai-use-cases/index.html) [![](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/aws-samples/generative-ai-use-cases/blob/main/LICENSE) [![](https://github.com/aws-samples/generative-ai-use-cases/actions/workflows/node.js.yml/badge.svg)](https://github.com/aws-samples/generative-ai-use-cases/actions/workflows/node.js.yml) [![](https://github.com/aws-samples/generative-ai-use-cases/actions/workflows/browser-extension.yml/badge.svg)](https://github.com/aws-samples/generative-ai-use-cases/actions/workflows/browser-extension.yml)

[English](./README.md) | [日本語](./README_ja.md) | 한국어

비즈니스 운영에서 생성형 AI를 안전하게 활용하기 위한 비즈니스 유스케이스 애플리케이션 구현

  <img src="./docs/assets/images/sc_lp_en.png" alt="비즈니스 운영에서 생성형 AI를 안전하게 활용하기 위한 비즈니스 유스케이스 애플리케이션 구현" width="68%">
</div>

> [!IMPORTANT]
> GenU는 v4부터 다국어를 지원합니다.
>
> GenU supports multiple languages since v4. English documentation is [here](./README.md)

## GenU 사용 패턴

여기서는 사용 패턴별로 GenU의 기능과 옵션을 소개합니다. 전체적인 배포 옵션은 [이 문서](docs/en/DEPLOY_OPTION.md)를 참조하세요.

> [!TIP]
> 사용 패턴을 클릭하면 자세한 내용을 볼 수 있습니다.

<details markdown="1">
  <summary><strong><ins>생성형 AI 유스케이스를 경험하고 싶습니다</ins></strong></summary>

GenU는 생성형 AI를 활용한 다양한 표준 유스케이스를 제공합니다. 이러한 유스케이스는 비즈니스 운영에서 생성형 AI를 활용하는 방법에 대한 아이디어의 씨앗이 되거나, 그대로 비즈니스에 적용할 수 있습니다. 앞으로도 더욱 정교한 유스케이스를 지속적으로 추가할 예정입니다. 필요하지 않은 경우 옵션으로 [특정 유스케이스를 숨길](docs/en/DEPLOY_OPTION.md#hiding-specific-use-cases) 수도 있습니다. 기본적으로 제공되는 유스케이스는 다음과 같습니다.

  <br/>
  <br/>
  <table width="100%">
    <thead>
      <tr>
        <td width="20%">유스케이스</td>
        <td width="80%">설명</td>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>채팅</td>
        <td>대형 언어 모델(LLM)과 채팅 형식으로 대화할 수 있습니다. LLM과 직접 대화할 수 있는 플랫폼의 존재는 특정하고 새로운 유스케이스에 대한 신속한 대응을 가능하게 합니다. 또한 프롬프트 엔지니어링의 테스트 환경으로도 효과적입니다.</td>
      </tr>
      <tr>
        <td>텍스트 생성</td>
        <td>어떤 맥락에서든 텍스트를 생성하는 것은 LLM이 잘하는 작업 중 하나입니다. 기사, 보고서, 이메일 등 모든 종류의 텍스트를 생성합니다.</td>
      </tr>
      <tr>
        <td>요약</td>
        <td>LLM은 대량의 텍스트를 요약하는 데 능숙합니다. 단순한 요약을 넘어, 텍스트를 컨텍스트로 제공한 후 대화 형식으로 필요한 정보를 추출할 수도 있습니다. 예를 들어, 계약서를 읽은 후 "XXX의 조건은 무엇인가요?" 또는 "YYY의 금액은 얼마인가요?"와 같은 질문을 할 수 있습니다.</td>
      </tr>
      <tr>
        <td>작문</td>
        <td>LLM은 오타뿐만 아니라 텍스트의 흐름과 내용까지 고려하여 더 객관적인 관점에서 개선 사항을 제안할 수 있습니다. 다른 사람에게 보여주기 전에 LLM이 객관적으로 확인하여 놓칠 수 있는 부분을 점검함으로써 품질 향상을 기대할 수 있습니다.</td>
      </tr>
      <tr>
        <td>번역</td>
        <td>여러 언어로 훈련된 LLM은 번역을 수행할 수 있습니다. 단순한 번역을 넘어, 캐주얼함과 대상 독자와 같은 다양한 지정된 컨텍스트 정보를 번역에 통합할 수 있습니다.</td>
      </tr>
      <tr>
        <td>웹 콘텐츠 추출</td>
        <td>블로그와 문서와 같은 웹 콘텐츠에서 필요한 정보를 추출합니다. LLM은 불필요한 정보를 제거하고 잘 구조화된 텍스트로 포맷팅합니다. 추출된 콘텐츠는 요약 및 번역과 같은 다른 유스케이스에서 사용할 수 있습니다.</td>
      </tr>
      <tr>
        <td>이미지 생성</td>
        <td>이미지 생성 AI는 텍스트나 기존 이미지를 기반으로 새로운 이미지를 생성할 수 있습니다. 아이디어를 즉시 시각화할 수 있어 디자인 작업의 효율성 향상에 도움이 될 수 있습니다. 이 기능에서는 LLM이 프롬프트 작성에 도움을 줄 수 있습니다.</td>
      </tr>
      <tr>
        <td>비디오 생성</td>
        <td>비디오 생성 AI는 텍스트에서 짧은 비디오를 생성합니다. 생성된 비디오는 다양한 시나리오에서 자료로 사용할 수 있습니다.</td>
      </tr>
      <tr>
        <td>비디오 분석</td>
        <td>멀티모달 모델을 사용하면 텍스트뿐만 아니라 이미지도 입력할 수 있습니다. 이 기능에서는 비디오 프레임과 텍스트 입력을 LLM이 분석하도록 요청할 수 있습니다.</td>
      </tr>
      <tr>
        <td>다이어그램 생성</td>
        <td>다이어그램 생성은 모든 주제에 대한 텍스트와 콘텐츠를 최적의 다이어그램으로 시각화합니다. 텍스트 기반의 다이어그램을 쉽게 생성할 수 있어 비프로그래머와 비디자이너도 효율적으로 플로우차트 등의 다이어그램을 만들 수 있습니다.</td>
      </tr>
    </tbody>
  </table>
</details>

<details markdown="1">
  <summary><strong><ins>RAG를 사용하고 싶습니다</ins></strong></summary>

RAG는 LLM이 일반적으로 어려워하는 최신 정보나 도메인 지식과 같은 외부 정보를 제공하여, LLM이 일반적으로 답변할 수 없는 질문에 답변할 수 있게 하는 기술입니다.
조직 내에 축적된 PDF, Word, Excel 등의 파일이 정보 소스로 활용될 수 있습니다.
RAG는 또한 "그럴듯하지만 잘못된 정보"를 제공하는 것을 방지하는 효과도 있습니다.

GenU는 RAG 채팅 유스케이스를 제공합니다.
RAG 채팅에는 [Amazon Kendra](docs/en/DEPLOY_OPTION.md)와 [Knowledge Base](docs/en/DEPLOY_OPTION.md#enabling-rag-chat-knowledge-base-use-case) 두 가지 유형의 정보 소스가 있습니다.
Amazon Kendra를 사용할 때는 [수동으로 생성한 S3 버킷이나 Kendra 인덱스를 그대로 사용](docs/en/DEPLOY_OPTION.md#using-an-existing-amazon-kendra-index)할 수 있습니다.
Knowledge Base를 사용할 때는 [고급 파싱](docs/en/DEPLOY_OPTION.md#enabling-advanced-parsing), [청크 전략 선택](docs/en/DEPLOY_OPTION.md#changing-chunking-strategy), [쿼리 분해](docs/en/DEPLOY_OPTION.md#enabling-rag-chat-knowledge-base-use-case), [재순위화](docs/en/DEPLOY_OPTION.md#enabling-rag-chat-knowledge-base-use-case)와 같은 고급 RAG 기능을 사용할 수 있습니다.
Knowledge Base는 [메타데이터 필터 설정](docs/en/DEPLOY_OPTION.md#metadata-filter-configuration)도 가능합니다.
예를 들어, "조직별로 접근 가능한 데이터 소스를 전환"하거나 "사용자가 UI에서 필터를 설정할 수 있도록 허용"하는 등의 요구사항을 충족할 수 있습니다.

</details>

<details markdown="1">
  <summary><strong><ins>조직 내에서 커스텀 AI 에이전트나 Bedrock Flows를 사용하고 싶습니다</ins></strong></summary>

GenU에서 [에이전트를 활성화](docs/en/DEPLOY_OPTION.md#enabling-agent-chat-use-case)하면 웹 검색 에이전트와 코드 인터프리터 에이전트가 생성됩니다.
웹 검색 에이전트는 사용자의 질문에 답하기 위해 웹에서 정보를 검색합니다. 예를 들어, "AWS GenU가 무엇인가요?"와 같은 질문에 답변할 수 있습니다.
코드 인터프리터 에이전트는 사용자의 요청에 응답하기 위해 코드를 실행할 수 있습니다. 예를 들어, "더미 데이터로 산점도를 그려주세요"와 같은 요청에 응답할 수 있습니다.

웹 검색 에이전트와 코드 인터프리터 에이전트는 기본적인 에이전트이지만, 비즈니스 요구에 맞는 더 실용적인 에이전트를 사용하고 싶을 수 있습니다.
GenU는 수동으로 또는 다른 자산으로 생성한 에이전트를 [가져오는](docs/en/DEPLOY_OPTION.md#adding-manually-created-agents) 기능을 제공합니다.

GenU를 에이전트 활용 플랫폼으로 사용하면 GenU의 [풍부한 보안 옵션](docs/en/DEPLOY_OPTION.md#security-related-settings)과 [SAML 인증](docs/en/DEPLOY_OPTION.md#saml-authentication)을 활용하여 조직 내에서 실용적인 에이전트를 확산시킬 수 있습니다.
또한 [불필요한 표준 유스케이스를 숨기거나](docs/en/DEPLOY_OPTION.md#hiding-specific-use-cases) [에이전트를 인라인으로 표시](docs/en/DEPLOY_OPTION.md#displaying-agents-inline)하여 GenU를 더욱 에이전트 중심의 플랫폼으로 사용할 수 있습니다.

마찬가지로 Bedrock Flows에 대한 [가져오기 기능](docs/en/DEPLOY_OPTION.md#enabling-flow-chat-use-case)도 있으니 활용해 보세요.

</details>

<details markdown="1">
  <summary><strong><ins>커스텀 유스케이스를 만들고 싶습니다</ins></strong></summary>

GenU는 자연어로 프롬프트 템플릿을 설명하여 커스텀 유스케이스를 만들 수 있는 "유스케이스 빌더" 기능을 제공합니다.
커스텀 유스케이스 화면은 프롬프트 템플릿만으로 자동 생성되므로 GenU 자체의 코드 변경이 필요하지 않습니다.
생성된 유스케이스는 개인용으로만 사용할 수 있는 것이 아니라 애플리케이션에 로그인할 수 있는 모든 사용자와 공유할 수 있습니다.
유스케이스 빌더는 필요하지 않은 경우 [비활성화](docs/en/DEPLOY_OPTION.md#use-case-builder-configuration)할 수 있습니다.
유스케이스 빌더에 대한 자세한 내용은 <a href="https://aws.amazon.com/jp/blogs/news/genu-use-cases-builder/">이 블로그</a>를 확인하세요.
<br/>
<br/>
유스케이스 빌더는 폼에 텍스트를 입력하거나 파일을 첨부하는 유스케이스를 만들 수 있지만, 요구사항에 따라 채팅 UI가 더 적합할 수 있습니다.
이러한 경우 "채팅" 유스케이스의 시스템 프롬프트 저장 기능을 활용하세요.
시스템 프롬프트를 저장하면 한 번의 클릭으로 비즈니스에 필요한 "봇"을 만들 수 있습니다.
예를 들어, "소스 코드를 입력하면 철저히 검토하는 봇"이나 "입력 내용에서 이메일 주소를 추출하는 봇"을 만들 수 있습니다.
또한 채팅 대화 기록은 로그인한 사용자와 공유할 수 있으며, 공유된 대화 기록에서 시스템 프롬프트를 가져올 수 있습니다.
<br/>
<br/>
GenU는 OSS이므로 커스텀 유스케이스를 추가하기 위해 커스터마이징할 수도 있습니다.
이 경우 GenU의 메인 브랜치와의 충돌에 주의하세요.

</details>

## 배포

> [!IMPORTANT]
> [`/packages/cdk/cdk.json`](/packages/cdk/cdk.json)에 나열된 `modelRegion` 지역에서 `modelIds`(텍스트 생성), `imageGenerationModelIds`(이미지 생성), `videoGenerationModelIds`(비디오 생성)를 활성화하세요. ([Amazon Bedrock Model access screen](https://us-east-1.console.aws.amazon.com/bedrock/home?region=us-east-1#/modelaccess))

GenU 배포는 [AWS Cloud Development Kit](https://aws.amazon.com/jp/cdk/) (CDK)를 사용합니다. CDK 실행 환경을 준비할 수 없는 경우 다음 배포 방법을 참조하세요:

- [AWS CloudShell을 사용한 배포 방법 (자신의 환경을 준비하기 어려운 경우)](docs/en/DEPLOY_ON_CLOUDSHELL.md)
- [워크샵](https://catalog.workshops.aws/generative-ai-use-cases-jp)

먼저 다음 명령을 실행하세요. 모든 명령은 저장소 루트에서 실행해야 합니다.

```bash
npm ci
```

CDK를 처음 사용하는 경우, 처음 한 번만 [Bootstrap](https://docs.aws.amazon.com/ja_jp/cdk/v2/guide/bootstrapping.html)이 필요합니다. 환경이 이미 부트스트랩된 경우 다음 명령은 필요하지 않습니다.

```bash
npx -w packages/cdk cdk bootstrap
```

다음으로 다음 명령으로 AWS 리소스를 배포하세요. 배포가 완료될 때까지 기다리세요 (약 20분 정도 소요될 수 있습니다).

```bash
# 일반 배포
npm run cdk:deploy

# 빠른 배포 (생성된 리소스를 사전 확인하지 않고 빠르게 배포)
npm run cdk:deploy:quick
```

## 아키텍처

![arch.drawio.png](./docs/assets/images/arch.drawio.png)

## 기타 정보

- [배포 옵션](docs/en/DEPLOY_OPTION.md)
- [업데이트 방법](docs/en/UPDATE.md)
- [로컬 개발 환경 설정](docs/en/DEVELOPMENT.md)
- [리소스 삭제 방법](docs/en/DESTROY.md)
- [네이티브 앱으로 사용하는 방법](docs/en/PWA.md)
- [브라우저 확장 프로그램 사용](docs/en/EXTENSION.md)

## 비용 추정

GenU 사용에 대한 구성 및 비용 추정 예시를 게시했습니다. (서비스는 종량제이며, 실제 비용은 사용량에 따라 달라집니다.)

- [간단한 버전 (RAG 없음) 추정](https://aws.amazon.com/jp/cdp/ai-chatbot/)
- [RAG (Amazon Kendra) 포함 추정](https://aws.amazon.com/jp/cdp/ai-chatapp/)
- [RAG (Knowledge Base) 포함 추정](https://aws.amazon.com/jp/cdp/genai-chat-app/)

## 고객 사례 연구

| 고객                                                                                                                          | 인용                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| :-------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <a href="https://www.yasashiite.com/" target="_blank"><img src="./docs/assets/images/cases/yasashiite_logo.png"></a>              | **Yasashiite Co., Ltd.** <br/> _GenU 덕분에 사용자에게 부가가치를 제공하고 직원의 업무 효율성을 향상시킬 수 있었습니다. 직원들의 "이전 업무"가 즐거운 업무로 변화하면서 "원활한 운영"에서 "흥미로운 업무"로 계속 진화하고 있습니다!_ <br/> ・[사례 상세 보기](./docs/assets/images/cases/yasashiite_case.png) <br/> ・[사례 페이지 보기](https://aws.amazon.com/jp/solutions/case-studies/yasashii-te/)                                |
| <a href="https://www.takihyo.co.jp/" target="_blank"><img src="./docs/assets/images/cases/TAKIHYO_logo.png"></a>                  | **TAKIHYO Co., Ltd.** <br/> _생성형 AI 활용으로 내부 업무 효율화 및 450시간 이상의 업무 감소를 달성했습니다. Amazon Bedrock을 의류 디자인 등에 적용하고 디지털 인재 육성을 추진했습니다._ <br/> ・[사례 페이지 보기](https://aws.amazon.com/jp/solutions/case-studies/takihyo/)                                                                                                                                                     |
| <a href="https://salsonido.com/" target="_blank"><img src="./docs/assets/images/cases/salsonido_logo.png"></a>                    | **Salsonido Inc.** <br/> _솔루션으로 제공되는 GenU를 활용하여 생성형 AI를 통한 업무 프로세스 개선을 빠르게 시작할 수 있었습니다._ <br/> ・[사례 상세 보기](./docs/assets/images/cases/salsonido_case.png) <br/> ・[적용 서비스](https://kirei.ai/)                                                                                                                                                                                |
| <a href="https://www.tamura-ss.co.jp/jp/index.html" target="_blank"><img src="./docs/assets/images/cases/tamura-ss_logo.png"></a> | **TAMURA CORPORATION** <br/> _AWS가 Github에 게시하는 애플리케이션 샘플은 즉시 테스트 가능한 기능이 풍부하며, 이를 그대로 사용하여 우리에게 적합한 기능을 쉽게 선택하고 최종 시스템의 개발 시간을 단축할 수 있었습니다._<br/> ・[사례 상세 보기](./docs/assets/images/cases/tamura-ss_case.png)<br/>                                                                                                      |
| <a href="https://jdsc.ai/" target="_blank"><img src="./docs/assets/images/cases/jdsc_logo.png"></a>                               | **JDSC Inc.** <br/> _Amazon Bedrock을 통해 데이터와 함께 LLM을 안전하게 사용할 수 있습니다. 또한 목적에 따라 최적의 모델로 전환할 수 있어 비용을 절감하면서 속도와 정확도를 향상시킬 수 있습니다._ <br/> ・[사례 상세 보기](./docs/assets/images/cases/jdsc_case.png)                                                                                                                                                                      |
| <a href="https://www.iret.co.jp/" target="_blank"><img src="./docs/assets/images/cases/iret_logo.png"></a>                        | **iret, Inc.** <br/> _BANDAI NAMCO Amusement Inc.의 생성형 AI 활용을 위한 내부 지식 축적 및 체계화를 위해 AWS가 제공하는 Generative AI Use Cases JP를 사용하여 유스케이스 사이트를 개발했습니다. iret, Inc.는 이 프로젝트의 설계, 구축 및 개발을 지원했습니다._ <br/> ・[BANDAI NAMCO Amusement Inc.의 클라우드 활용 사례 연구](https://cloudpack.jp/casestudy/302.html?_gl=1*17hkazh*_gcl_au*ODA5MDk3NzI0LjE3MTM0MTQ2MDU) |
| <a href="https://idealog.co.jp" target="_blank"><img src="./docs/assets/images/cases/idealog_logo.jpg"></a>                       | **IDEALOG Inc.** <br/> _기존 생성형 AI 도구보다 더 큰 업무 효율성을 달성할 수 있다고 느낍니다. 입력/출력 데이터를 모델 훈련에 사용하지 않는 Amazon Bedrock을 사용하면 보안에 대해 안심할 수 있습니다._ <br/> ・[사례 상세 보기](./docs/assets/images/cases/idealog_case.png) <br/> ・[적용 서비스](https://kaijosearch.com/)                                                                                   |
| <a href="https://estyle.co.jp/" target="_blank"><img src="./docs/assets/images/cases/estyle_logo.png"></a>                        | **eStyle Inc.** <br/> _GenU를 활용하여 단기간에 생성형 AI 환경을 구축하고 회사 내 지식 공유를 촉진할 수 있었습니다._ <br/> ・[사례 상세 보기](./docs/assets/images/cases/estyle_case.png)                                                                                                                                                                                                                             |
| <a href="https://meidensha.co.jp/" target="_blank"><img src="./docs/assets/images/cases/meidensha_logo.svg"></a>                  | **Meidensha Corporation** <br/> _Amazon Bedrock과 Amazon Kendra와 같은 AWS 서비스를 사용하여 신속하고 안전하게 생성형 AI 사용 환경을 구축할 수 있었습니다. 회의록 자동 생성 및 내부 정보 검색을 통해 직원의 업무 효율성 향상에 기여합니다._ <br/> ・[사례 상세 보기](./docs/assets/images/cases/meidensha_case.png)                                                                            |
| <a href="https://www.st-grp.co.jp/" target="_blank"><img src="./docs/assets/images/cases/st-grp_logo.jpg"></a>                    | **Sankyo Tateyama, Inc.** <br/> _Amazon Kendra를 통해 회사 내에 묻혀있던 정보를 빠르게 검색할 수 있게 되었습니다. GenU를 참조하여 회의록 생성과 같은 필요한 기능을 신속하게 제공할 수 있었습니다._ <br/> ・[사례 상세 보기](./docs/assets/images/cases/st-grp_case.png)                                                                                                                                                    |
| <a href="https://www.oisixradaichi.co.jp/" target="_blank"><img src="./docs/assets/images/cases/oisixradaichi_logo.png"></a>      | **Oisix ra daichi Inc.** <br/> _GenU를 사용한 유스케이스 개발 프로젝트를 통해 필요한 리소스, 프로젝트 구조, 외부 지원 및 인재 육성을 파악할 수 있었고, 이는 생성형 AI의 내부 배포에 대한 우리의 이미지를 명확히 하는 데 도움이 되었습니다._ <br/> ・[사례 페이지 보기](https://aws.amazon.com/jp/solutions/case-studies/oisix/)                                                                                                  |
| <a href="https://www.san-a.co.jp/" target="_blank"><img src="./docs/assets/images/cases/san-a_logo.png"></a>                      | **SAN-A CO., LTD.** <br/> _Amazon Bedrock을 활용하여 엔지니어의 생산성이 극적으로 향상되어 자체적으로 구축한 회사 특화 환경의 클라우드로의 마이그레이션이 가속화되었습니다._ <br/> ・[사례 상세 보기](./docs/assets/images/cases/san-a_case.png)<br/> ・[사례 페이지 보기](https://aws.amazon.com/jp/solutions/case-studies/san-a/)                                                                                    |

사용 사례를 소개하고 싶으시면 [Issue](https://github.com/aws-samples/generative-ai-use-cases/issues)를 통해 문의해 주세요.

## 참고 자료

- [블로그 (일본어): 코드 없이 생성형 AI 앱을 만들고 배포하는 GenU 유스케이스 빌더](https://aws.amazon.com/jp/blogs/news/genu-use-cases-builder/)
- [블로그 (일본어): RAG 프로젝트를 성공시키는 방법 #1 ~ 또는 빠르게 실패하는 방법 ~](https://aws.amazon.com/jp/builders-flash/202502/way-to-succeed-rag-project/)
- [블로그 (일본어): RAG 채팅의 정확도를 높이는 디버깅 방법](https://qiita.com/sugimount-a/items/7ed3c5fc1eb867e28566)
- [블로그 (일본어): Amazon Q Developer CLI를 사용하여 코드 없이 GenU 커스터마이징하기](https://qiita.com/wadabee/items/659e189018ad1a08e152)
- [블로그 (일본어): Generative AI Use Cases JP 커스터마이징 방법](https://aws.amazon.com/jp/blogs/news/how-to-generative-ai-use-cases-jp/)
- [블로그 (일본어): Generative AI Use Cases JP ~ 첫 기여 가이드 ~](https://aws.amazon.com/jp/builders-flash/202504/genu-development-guide/)
- [블로그 (일본어): 생성형 AI로 불합리한 요청을 거절하자 ~ 브라우저에 생성형 AI 통합하기 ~](https://aws.amazon.com/jp/builders-flash/202405/genai-sorry-message/)
- [블로그 (일본어): Amazon Bedrock으로 인터프리터 개발하기!](https://aws.amazon.com/jp/builders-flash/202311/bedrock-interpreter/)
- [비디오 (일본어): 생성형 AI 유스케이스를 철저히 고려하는 Generative AI Use Cases JP (GenU)의 매력과 사용법](https://www.youtube.com/live/s1P5A2SIWgc?si=PBQ4ZHQXU4pDhL8A)

## 보안

자세한 내용은 [CONTRIBUTING](/CONTRIBUTING.md#security-issue-notifications)을 참조하세요.

## 라이선스

이 라이브러리는 MIT-0 라이선스에 따라 라이선스가 부여됩니다. LICENSE 파일을 참조하세요. 