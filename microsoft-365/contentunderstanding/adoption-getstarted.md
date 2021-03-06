---
title: 'Microsoft SharePoint Syntex 채택: 시작'
description: 비즈니스 문제를 해결하는 데 도움이 될 수 있도록 조직에서 SharePoint Syntex를 사용 및 구현하는 방법을 학습합니다.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: e88a7de1c81995b878dbf8a9308fbc774583289e
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597061"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Microsoft SharePoint Syntex 채택: 시작

SharePoint Syntex에서 사용할 수 있는 지능형 콘텐츠 서비스는 다음 세 부분으로 구성됩니다.

- **콘텐츠 이해:** 코드 없는 AI 모델을 만들어 콘텐츠에서 정보를 분류하고 추출하여 지식 검색 및 재사용을 위한 메타데이터를 자동으로 적용합니다. 콘텐츠 [이해에 대해 자세히 알아보겠습니다.](document-understanding-overview.md)
- **콘텐츠 처리:** 콘텐츠 캡처, 수집 및 분류를 자동화하고 Power Automate를 사용하여 콘텐츠 중심 프로세스를 간소화합니다. 콘텐츠 처리에 [대해 자세히 알아보겠습니다.](form-processing-overview.md)
- **콘텐츠 준수:** Microsoft Information Protection에 통합된 보안 및 거버넌스를 개선하기 위해 콘텐츠를 제어하고 관리합니다.

새로운 AI 서비스 및 기능을 사용하여 콘텐츠 이해 및 분류 앱을 SharePoint Syntex를 사용하여 콘텐츠 관리 흐름에 직접 빌드할 수 있습니다. 콘텐츠를 이해하는 방법에는 두 가지가 있습니다. 사용하는 모델 형식은 파일 형식 및 사용 사례를 기반으로 합니다.

| 양식 처리 | 문서 이해 |
|:-------|:-------|
| 문서 라이브러리에서 만들어집니다. | SharePoint Syntex의 일부인 콘텐츠 센터에서 생성됩니다. |
| AI 작성기에서 만든 모델입니다. | 네이티브 인터페이스에서 만든 모델입니다. |
| 반구조적 파일 형식에 사용됩니다. | 구조화되지 않은 파일 형식에 사용됩니다. |
| Settable 분류자입니다. | 선택적 추출기를 사용할 수 있는 학습 가능한 분류자입니다. |
| 단일 라이브러리로 제한됩니다. | 여러 라이브러리에 적용할 수 있습니다. |
| PDF, JPG, PNG 형식 교육 총 50MB/500 pp. | 부정적인 예제를 포함하여 5-10 PDF, Office 또는 전자 메일 파일에 대해 교육합니다. |

기능을 보다 완전한 비교는 문서 이해 모델과 양식 처리 모델 간의 [차이를 참조하세요.](difference-between-document-understanding-and-form-processing-model.md)

## <a name="identify-pilot-business-scenarios-to-optimize"></a>최적화할 파일럿 비즈니스 시나리오 확인

조직에서 SharePoint Syntex 사용을 준비하려면 먼저 유용한 시나리오를 이해해야 합니다. "이유"는 필요한 모델과 모델이 적용되는 위치를 기준으로 조직을 구성하는 방법을 결정하는 데 도움이 됩니다. 다음은 문서 이해가 조직에 도움이 될 수 있는 몇 가지 시나리오입니다.

- **콘텐츠 처리:** 계약서, 작업 설명 및 기타 양식과 같은 문서를 처리합니다. 양식을 조정하고 필드를 이해하고 매핑하기 위해 모델을 교육한 다음 양식을 실행하여 데이터를 자동으로 수집합니다. 자세한 내용은 양식 처리 [개요를 참조하세요.](form-processing-overview.md)
- **송장 분석:** 송장에서 관련 세부 정보를 끌어오고 정책이 준수되고 있는지 또는 적절하게 처리되고 있는지 확인

SharePoint Syntex가 조직에 도움이 될 수 있는 방법에 대해 생각해 보아야 합니다.

- 비즈니스 프로세스 자동화
- 검색 정확도 향상
- 규정 준수 위험 관리

고려할 비즈니스 시나리오를 고려할 때 다음과 같은 질문을 합니다.

- 실제 문제를 해결하나요?
- 광범위하게 사용되거나 광범위한 영향을 미치나요?
- 얻을 수 있나요?
- 성공을 측정할 수 있나요?

영향 및 구현 용이성을 기반으로 시나리오 우선 순위를 지정합니다. 초기 포커스 영역을 쉽게 구현할 수 있는 더 큰 영향 시나리오로 만들어야 합니다. 구현하기 어려운 낮은 영향 시나리오의 우선 순위를 낮게 지정합니다.

다음 예제 시나리오를 사용하여 조직에서 SharePoint Syntex를 사용하는 방법에 대한 아이디어를 묻습니다.

### <a name="scenario-track-data-from-invoices-with-form-processing"></a>시나리오: 양식 처리를 사용하여 송장에서 데이터 추적

예를 들어 SharePoint Syntex 및 Power Automate 기능을 사용하여 송장을 추적하고 모니터링하는 프로세스를 설정할 수 있습니다.

1. 송장 문서를 저장할 라이브러리를 설치합니다.
1. 문서의 필드를 인식하는 모델을 학습합니다.
1. 추적할 필드를 목록으로 추출합니다.
1. 흐름을 설정하여 다음을 통해 특정 이벤트를 알릴 수 있습니다.
    - 새 송장이 추가됩니다.
    - 송장 기한이 지난 경우
    - 송장은 자동 승인 금액보다 큰 금액에 대한 것입니다.

![SharePoint Syntex 및 Power Automate를 통해 송장 추적 및 모니터링](../media/content-understanding/process-invoices-flow.png)

이 시나리오를 자동화할 때 다음을 할 수 있습니다.

- 송장에서 데이터를 수동으로 추출하는 대신 자동으로 추출하여 시간과 비용을 절약할 수 있습니다.
- 워크플로를 사용하여 송장을 확인하고 문제를 알려 잠재적인 오류를 줄이고 규정 준수를 향상합니다.

### <a name="scenario-track-information-from-contracts-with-document-understanding"></a>시나리오: 문서 이해를 통해 계약에서 정보 추적

또 다른 예로, 회사의 다른 회사 또는 개인과의 계약을 식별하는 프로세스를 설정할 수 있습니다. 클라이언트 이름, 수수료, 날짜 또는 기타 중요한 정보와 같은 주요 정보를 해당 계약에서 추출하고 정보를 빠르게 볼 수 있는 필드로 라이브러리에 추가하는 모델을 설정하세요. 문서 라이브러리에 보존 레이블을 적용하여 비즈니스 규정을 적절하게 준수하기 위해 특정 기간 전에 계약을 삭제할 수 없습니다.

1. 콘텐츠 센터에서 시작하여 계약에 대한 새 문서 이해 모델을 만들 수 있습니다.
1. 양성 및 부정적 예제를 위해 샘플 문서를 업로드한 다음 교육을 실행하여 계약 문서를 식별하고 결과를 검토합니다.
1. 추출기에서 클라이언트 이름, 수수료 및 날짜와 같은 계약 필드를 식별하는 교육을 한 다음 추출기 테스트를 합니다.
1. 모델이 완료되면 계약을 업로드할 수 있는 라이브러리에 모델을 적용합니다.
1. 날짜 필드에 보존 레이블을 적용하여 계약이 필요한 기간 동안 라이브러리에 보존됩니다.

![SharePoint Syntex 및 보존 레이블과의 계약 추적 및 모니터링](../media/content-understanding/process-contracts-flow.png)

이 시나리오를 자동화할 때 다음을 할 수 있습니다.

- 수동으로 수행하지 않고 계약에서 데이터를 자동으로 추출하여 시간과 비용을 절약할 수 있습니다.
- 보존 레이블을 사용하여 계약이 적절하게 보존되도록 하여 규정 준수를 향상합니다.

### <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a>시나리오: SharePoint Syntex를 기반으로 하는 레코드 관리, 문서 거버넌스 및 규정 준수 프로세스로 위험을 방지합니다.

대부분의 회사에서 위험을 줄이는 것이 일반적인 목표입니다. 다음이 필요할 수 있습니다.

- 테넌트 전체에서 정보 거버넌스를 제공/적용하는 더 나은 방법
- 문서, 전자 메일 및 프로젝트의 '레코드'로 간주되는 기타 통신 형식의 분류 시스템을 개선하기 위해
- 회사 정책을 준수하기 위해 영수증, 계약 등 감사
- 프로젝트에 규정 준수에 필요한 모든 설명서가 프로젝트에 있도록 합니다.

더 나은 거버넌스가 필요한 문서 및 양식을 캡처하고 적절하게 분류, 감사 및 플래그를 지정하기 위해 SharePoint Syntex 준수를 위한 일부 프로세스를 설정합니다. 최종 사용자가 수동으로 태그를 지정하는 대신 SharePoint Syntex를 사용하여 콘텐츠를 자동 분류하거나 규정 준수 팀에서 거버넌스 규칙 및 보관을 수동으로 적용할 수 있습니다. 또한 간소화된 검색 환경을 사용하도록 설정하고, 데이터 볼륨을 관리하고, 레코드 관리 및 보존 정책을 적용하고, 규정 준수를 보장하고, 모범 사례 보관 및 삭제 방법을 사용할 수 있습니다.

이 시나리오를 자동화하면 다음의 안전을 느낄 수 있습니다.

- 규정 준수를 준수하고 위험을 줄입니다.
- 세분화 및 레코드 관리는 일관되고 정확하게 적용됩니다.
- 콘텐츠 볼륨이 제어됩니다.
- 직원은 올바른 컨텍스트에서 올바른 정보를 쉽게 검색할 수 있습니다.

### <a name="scenario-capture-information-from-previously-inaccessible-documents"></a>시나리오: 이전에는 이 문서에 없는 문서에서 정보 캡처

대부분의 조직에는 법률 문서, 정책, 계약, HR 문서 및 거버넌스 지침이 큰 저장소가 있습니다. 프로젝트, 섹터, 테마, 사람, 지리적 영역 등의 중요한 정보를 추출하기 위해 이러한 데이터 저장소를 마이인드합니다.

예를 들어 HR 감독은 이력서, HR 정책 및 기타 양식을 포함하여 모든 HR 문서에 빠르게 액세스해야 합니다. 또한 문서를 수동으로 제거하지 않고도 이력서 및 기타 HR 관련 문서에서 필요한 정보를 빠르게 식별할 수 있습니다. 수천 개의 이력서, HR 정책 및 여러 사이트에 분산될 수 있는 기타 설명서를 수동으로 살펴보지 않고도 필요한 정보를 빠르게 찾을 수 있는 솔루션을 찾고 있습니다.

이 시나리오를 자동화할 때 다음을 할 수 있습니다.

- 디지털 콘텐츠에서 지식의 잠금을 해제합니다.
- HR 정책, 이력서, 판매 문서, 기술 청사진, 계정 계획 및 정보 추출을 분류합니다.
- 원하는 올바른 정보나 문서를 빠르게 찾을 수 있습니다.
- 최신 정보에 즉시 액세스합니다.
- 검색 시간을 줄입니다.

### <a name="scenario-improve-data-processing-to-provide-insights--analytics"></a>시나리오: 데이터 처리를 개선하여 분석에 대한 & 제공

예를 들어 제약 회사에서 SharePoint Syntex를 사용하여 FDA 문서에서 정보를 추출하여 리더의 질문에 답변할 수 있습니다. 답변에 보다 쉽게 액세스할 수 있도록 하면 이러한 답변을 생성하는 데 필요한 시간을 줄이고 데이터의 가용성을 높이어 리더십 질문에 대한 보다 정확한 답변을 생성할 수 있습니다.

예를 들어 프로젝트 관리자는 리더십 팀의 제품 관련 질문에 대한 답변을 신속하게 제공해야 합니다. 하나의 통합 대시보드에서 쿼리와 관련된 정보 및 메트릭을 찾아야 합니다. 제품 레이블, 제품 팜플릿 및 기타 자료에서 필요한 정보를 추출하고 리더십 팀에 다시 보고할 때 사용할 수 있는 통합 보고서를 생성하는 솔루션을 찾고 있습니다.

이 시나리오를 자동화할 때 다음을 할 수 있습니다.

- 답변을 생성하는 데 필요한 시간을 줄입니다.
- 데이터의 가용성을 향상합니다.
- 보다 정확한 답변을 제공합니다.

### <a name="scenario-automate-order-processing"></a>시나리오: 주문 처리 자동화

SharePoint Syntex를 사용하면 고객 주문을 수동으로 처리하는 시간을 줄일 수 있습니다. 예를 들어 OCR 처리를 사용하여 팩스, 전자 메일 또는 용지의 주문을 SharePoint에 업로드한 다음 자동화된 프로세스를 사용하여 주문을 이행할 수 있도록 해당 주문에서 메타데이터를 추출할 수 있습니다.

예를 들어 공급망 관리자는 수동 데이터 입력으로 인한 오류를 줄이고자 합니다. 비즈니스 시스템으로 들어오는 오류를 줄이기 위해 인바운드 고객 주문(용지, 팩스 또는 전자 메일)의 수동 검토 및 데이터 입력을 방지하려는 경우 AI 및 기계 학습 기술을 적용하여 들어오는 주문 정보의 유효성을 검사하고 핵심 데이터를 추출한 다음 ERP 시스템에 자동으로 푸시하여 주문 이행 및 조정을 위해 솔루션을 원합니다.

이 시나리오를 자동화할 때 다음을 보장할 수 있습니다.

- 주문 및 배송 정확도가 증가합니다.
- 주문 또는 배송 오류와 관련된 수수료 또는 페널티가 감소합니다.
- 송장 송장 또는 지급이 감소하는 경우의 지연
- 직원 비용 절감

### <a name="scenario-simplify-visa-renewal-process"></a>시나리오: Visa 갱신 프로세스 간소화

SharePoint Syntex를 사용하면 주요 계약 정보에 대한 미리 알림 및 갱신을 자동화할 수 있습니다. 예를 들어 HR 감독은 직원의 Visas를 최신으로 유지 및/또는 정시에 갱신해야 합니다. 사람들이 Visas를 업데이트하는 간단하고 직관적인 프로세스를 제공하려는 경우 계약에서 갱신 날짜를 추출하고 갱신 날짜가 다가오면 직원에게 미리 알림을 자동으로 보내는 솔루션이 필요합니다.

이 시나리오를 자동화할 때 다음을 보장할 수 있습니다.

- 비준수 수준이 감소합니다.
- 수동 미리 알림 수가 감소합니다.
- 비준수에 대한 벌금 수가 감소합니다.

## <a name="identify-roles--responsibilities"></a>역할 및 & 식별

조직에서 모델을 빌드하고 관리할 사용자 결정 다음과 같은 역할이 관련될 수 있습니다.

| SharePoint/지식 관리자 | Power Platform 관리자 | 지식 관리자 | 모델 소유자 |
|:-------|:-------|:-------|:-------|
| AAD 역할| AAD 역할 | AAD 역할 | 챔피언 |
| 양식 처리 구성 | 양식 처리를 위한 일반 데이터 서비스 환경 구성 | 사용 사례 수집 | 비즈니스 사용 사례 수집 |
| 콘텐츠 센터 및 사용 권한 관리| AIB 크레딧 구매 및 할당 | 모범 사례 설정 및 모델 분석 검토 | 모델 만들기 및 적용 |

기술 관리자, 비즈니스 프로세스 소유자 및 콘텐츠 모델 소유자는 조직에서 샘플 모델과 챔피언 채택을 생성합니다.
관련이 있을 수 있는 기타: 규정 준수 관리자, 세분화 관리자.

어디에서 모델을 빌드하고 적용할 것인가? 개선할 수 있는 기존 프로세스 또는 리포지토리가 있나요?

- 양식 처리: 양식 처리 작업을 받을 사이트를 결정할 수 있습니다.
- 문서 이해: 서로 다른 비즈니스 영역에 대해 여러 콘텐츠 센터를 만들 수 있습니다.

## <a name="strategic-positioning"></a>전략적 위치

관련자와 협의하여 SharePoint Syntex 사용 전략에 맞춰야 합니다. 이 위치 관리에 도움이 되는 다음 리소스를 조사하고 제공합니다.

- 비즈니스 결과:
  - 잠재적 회계 결과
  - 잠재적인 민첩성 결과
  - 비즈니스 결과 서식 파일
- 이해 관계자/Exec 스폰서 구입/조정
  - 비즈니스 사례 데크
  - 재무 모델
  - 회사 준비 - 문화

## <a name="identify-stakeholders"></a>관련자 파악

프로젝트 관련자를 식별합니다.

|역할 |책임 |부서 |
|:-------|:-------|:--------|
| Executive sponsor(s)   | 회사에 높은 수준의 비전과 가치 전달   |  임원진 리더십   |
| 프로젝트 주도자 | 전체 실행 실행 및 롤아웃 프로세스에 대한 오버시 | 프로젝트 관리 |
| 지식 관리자| 콘텐츠 센터 만들기 및 관리 | IT 또는 기타 부서|
| 콘텐츠 관리자 및 모델 소유자| 사용 사례 수집 및 모델 만들기 및 적용 | 모든 부서|
| 챔피언 | 이의 처리를 전도하고 관리하는 데 도움이 됩니다. | 모든 부서(직원) |
| 테넌트 관리자 | 테넌트 수준 설정 구성 | IT 부서|
| Power Platform 관리자| 일반 데이터 서비스 환경 구성 | IT 부서|

> [!Note]
> 이러한 각 역할을 롤아웃 전체에서 이행하는 것이 까다로우면 식별된 솔루션을 시작하는 데 이러한 역할이 모두 필요하지 않을 수도 있습니다.

## <a name="readiness-checklist"></a>준비 검사 목록

SharePoint Syntex 구현을 준비하려면 다음을 해야 합니다.

![콘텐츠 이해를 위한 준비](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. 종료 상태 계획
    - 문서 이해 모델은 끝이 아니라 수단입니다.
    - 다음을 사용하여 추출된 메타데이터의 값을 사용 계획합니다.
      - 검색
      - 필터링 및 보기 서식
      - 규정 준수
      - 자동화
2. 식별
    - 기존 정보 아키텍처 및 콘텐츠 관리 기능 사용을 이해합니다.
    - 기존 콘텐츠 형식이 모델에 대해 좋은 후보인가요?
    - 메타데이터를 통해 개선할 기존 프로세스는 무엇입니까?
3. 디자인
    - 정보 아키텍처, 관리되는 메타데이터 및 콘텐츠 형식에 대한 접근 방식 디자인
    - 정의, 만들기, 관리 프로세스를 디자인합니다.

## <a name="engage-your-organization"></a>조직 참여

1. 지주를 식별하고 시나리오를 확인하고 프로젝트 계획을 개발합니다.
1. 설정을 구성하고 라이선스를 적용합니다.
1. 인식과 교육 시작 - 챔피언을 모집합니다.
1. 단계적 롤아웃  
1. 피드백을 수집하고 이행합니다.
1. 사용량이 증가함에 따라 필요한 경우 AI 작성기 크레딧에 대한 계획이 커지고 있습니다.
