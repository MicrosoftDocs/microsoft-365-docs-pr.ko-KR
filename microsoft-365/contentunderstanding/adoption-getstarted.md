---
title: 'Microsoft SharePoint Syntex 채택: 시작'
description: 비즈니스 문제를 해결 하는 데 도움이 되도록 조직에서 SharePoint Syntex를 사용 하 고 구현 하는 방법을 알아봅니다.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: f6bb4f5e09adcb1be6323a5d3d182cc3d1bc6017
ms.sourcegitcommit: 3f8e573244bc082518125e339a385c41ef6ee800
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337232"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Microsoft SharePoint Syntex 채택: 시작

SharePoint Syntex에서 사용할 수 있는 지능형 콘텐츠 서비스는 다음과 같은 세 가지 부분으로 생각 하면 됩니다.

- **콘텐츠 이해:** 콘텐츠의 정보를 분류 및 추출 하 여 기술 자료 검색 및 다시 사용을 위한 메타 데이터를 자동으로 적용 하는 코드 없는 AI 모델을 만듭니다. 자세한 내용은 [콘텐츠 이해](document-understanding-overview.md)를 참고 하세요.
- **콘텐츠 처리:** 파워 자동화를 사용 하 여 콘텐츠 캡처, 수집 및 분류를 자동화 하 고 콘텐츠 중심 프로세스를 간소화 합니다. [콘텐츠 처리](form-processing-overview.md)에 대해 자세히 알아보세요.
- **콘텐츠 준수:** 콘텐츠를 제어 및 관리 하 여 Microsoft 정보 보호와의 통합을 통해 보안 및 관리 효율성을 향상 시킵니다.

새 인공 지능 서비스와 기능을 사용 하 여 SharePoint Syntex을 사용 하 여 콘텐츠 관리 흐름에 직접 콘텐츠와 분류 앱을 작성할 수 있습니다.

|수동 입력| 양식 처리 | 문서 이해 |
|:-------|:--------|:--------|
| 모든 콘텐츠에 대 한 데이터 입력 및 노동 집약적 | 디지털 콘텐츠 처리-사진, 스캔, 영수증, 명함, 비디오에서 OCR & 텍스트 |  계약, 이력서 및 기타 구조화 된 문서에서 콘텐츠 형식 및 메타 데이터 캡처 |
| 들은   | 미리 작성 된 자동화 된   | 사용자 지정, 보조   | 사용자 지정, 준수 |
| 작업을 수행 하는 사용자 | 주제별 전문가 (SMEs)의 배울 사항입니다. 계약, 다시 시작, 기타 구조화 되지 않은 문서에서 콘텐츠 형식 및 메타 데이터를 캡처합니다. | SMEs은 덜 복잡 합니다. 구매 주문, 응용 프로그램, 기타 반구조적 및 구조화 된 문서 |

다음 표에서는 SharePoint Syntex을 사용할 때 얻을 수 있는 결과에 대해 설명 합니다.

| 양식 처리 | 문서 이해 |
|:-------|:-------|
| APAC, 오스트레일리아, 캐나다, EU, JP, 라틴 아메리카, 영국, US에서 사용 가능 | 모든 지역에서 사용 가능 |
| AI Builder 제작진-1M 제작진 = 2000 페이지를 사용 합니다. 소비량은 약 2000 송장 = 2 단위입니다. 전원 자동화가 필요 하며 더 필요한 경우 추가할 수 있습니다. 1M에 게 할당 된 라이선스 300 개 또한 제작진을 별도로 구입할 수도 있습니다. | 모델은 모든 라틴어 알파벳 언어에서 작동 합니다. 영어 (독일어, 스웨덴어, 프랑스어, 스페인어, 이탈리아어, 포르투갈어)가 추가 되었습니다. |
| 기본 일반 데이터 서비스 환경에 대해 프로 비전 됨| 용량 제한이 없습니다. |

콘텐츠를 이해 하는 방법은 두 가지입니다. 사용 하는 모델 유형은 파일 형식과 사용 사례를 기반으로 합니다.

| 양식 처리 | 문서 이해 |
|:-------|:-------|
| 문서 라이브러리에서 만들어짐 | 콘텐츠 센터에서 만들어지고 SharePoint Syntex의 일부 |
| AI builder에서 생성 되는 모델 | 네이티브 인터페이스에서 만든 모델 |
| 반구조적 파일 형식에 사용 됨 | 구조화 되지 않은 파일 형식에 사용 됨 |
| 설정 가능한 분류자 | 선택적 추출기가 포함 된 Trainable 분류자 |
| 단일 라이브러리로 제한 | 여러 라이브러리에 적용할 수 있음 |
| PDF, JPG, PNG 형식, 총 50 MB/500 페이지를 교육 합니다. | 부정적 예를 포함 하 여 5-10 PDF, Office 또는 전자 메일 파일에 대해 교육 합니다. |

SharePoint Syntex는 다음과 같은 Microsoft 365 규정 준수 기능을 통합 합니다.

- 문서 보존 기간 또는 외부 이벤트를 기반으로 하는 레코드 정책을 정의 하는 보존 레이블입니다.
- 민감도 레이블-DLP, 암호화, 공유 및 조건부 액세스 정책을 설정 합니다.

사용자는 레이블을 적용 하거나 SharePoint Syntex AI 모델에서 자동으로 적용할 수 있습니다. 분석 및 파일 계획은 레이블 사용 및 정책에 대 한 확장 된 관리를 제공 합니다.

## <a name="identify-pilot-business-scenarios-to-optimize"></a>최적화할 파일럿 비즈니스 시나리오 식별

조직에서 SharePoint Syntex 사용을 준비 하려면 먼저 it가 도움이 되는 시나리오를 이해 해야 합니다. 필요한 모델을 결정 하는 이유와 모델이 적용 되는 위치를 기반으로 하 여 조직 구조를 구성 하는 방법을 설명 합니다. 다음은 문서를 이해 하는 것이 조직에 도움이 될 수 있는 몇 가지 시나리오입니다.

- 콘텐츠 처리: 프로세스 계약, 작업 문서 및 기타 양식 등의 문서입니다. 양식을 흡입구로 만들고 필드를 이해 하 고 매핑한 다음 양식을 실행 하 여 데이터를 자동으로 수집 하는 모델을 학습 합니다. 자세한 내용은 [양식 처리 개요](form-processing-overview.md)를 참조 하세요.
- 송장 분석: 청구서에서 관련 세부 정보를 추출 하 여 정책에 대 한 준수 여부 또는 적절 하 게 처리 중인지 확인 합니다.

SharePoint Syntex가 조직에 도움을 주는 방식에 대해 생각해 보십시오.

- 비즈니스 프로세스 자동화
- 검색 정확도 향상
- 규정 준수 위험 관리

### <a name="form-processing-scenario-example"></a>양식 처리 시나리오 예

예를 들어 SharePoint Syntex 및 Power 자동화 기능을 사용 하 여 송장을 추적 하 고 모니터링 하는 프로세스를 설정할 수 있습니다.

1. 송장 문서를 저장할 라이브러리를 설정 합니다.
1. 모델을 학습 하 여 문서의 필드를 인식 하도록 합니다.
1. 목록으로 추적 하려는 필드의 압축을 풉니다.
1. 다음과 같은 특정 이벤트를 알리도록 흐름을 설정 합니다.
    - 새 송장이 추가 됩니다.
    - 송장 기한이 만료 되었습니다.
    - 송장에서 자동 승인 금액 보다 큰 경우

![SharePoint Syntex 및 Power 자동화를 사용 하 여 송장을 추적 및 모니터링](../media/content-understanding/process-invoices-flow.png)

이 시나리오를 자동화 하는 경우 다음을 수행할 수 있습니다.

- 수동으로 작업을 수행 하는 대신 송장에서 데이터를 자동으로 추출 하 여 시간과 비용을 절약할 수 있습니다.
- 잠재적 오류를 줄이고 송장을 사용 하 여 송장에 대 한 작업을 수행 하 고 문제를 사용자에 게 알릴 수 있습니다.

### <a name="document-understanding-scenario-example"></a>시나리오 이해 문서 예

또 다른 예로 회사의 다른 회사나 개인이 가진 계약을 식별 하는 프로세스를 설정할 수 있습니다. 이러한 계약에서 클라이언트 이름, 수수료, 날짜 또는 기타 중요 한 정보와 같은 주요 정보를 추출 하는 모델을 설정 하 고 라이브러리에 빠르게 확인할 수 있는 필드로 추가할 수 있습니다. 그리고 문서 라이브러리에 보존 레이블을 적용 하 여 비즈니스 규정을 준수 하기 위해 특정 기간 이전에 계약을 삭제할 수 없도록 할 수 있습니다.

1. 콘텐츠 센터에서 시작 하 고 계약에 대 한 새 문서 이해 모델을 만듭니다.
1. 긍정적인 및 부정적 예제에 대 한 샘플 문서를 업로드 한 다음 교육을 실행 하 여 계약 문서를 식별 하 고 결과를 검토 합니다.
1. 추출기를 교육 하 여 클라이언트 이름, 비용, 날짜 등 계약의 필드를 식별 한 다음 추출기를 테스트 합니다.
1. 모델이 완료 되 면 계약을 업로드할 수 있는 라이브러리에 모델을 적용 합니다.
1. 조직에서 계약에 대해 요구 하는 기간 동안 계약이 라이브러리에 보존 되도록 날짜 필드에 보존 레이블을 적용 합니다.

![SharePoint Syntex 및 보존 레이블로 계약 추적 및 모니터링](../media/content-understanding/process-contracts-flow.png)

이 시나리오를 자동화 하는 경우 다음을 수행할 수 있습니다.

- 수동으로 작업을 수행 하는 대신 계약에서 데이터를 자동으로 추출 하 여 시간과 비용을 절약할 수 있습니다.
- 보존 레이블을 사용 하 여 계약이 적절 하 게 보존 되도록 하 여 규정 준수를 개선 해야 합니다.

### <a name="tips-for-identifying-scenarios"></a>시나리오 식별 팁

고려해 야 하는 비즈니스 시나리오를 고려할 때는 다음 사항을 확인 하십시오.

- 실제 문제가 해결 되었습니까?
- 광범위 하 게 사용 되거나 광범위 한 영향을 줍니까?
- 해당 기능을 얻을 수 있나요?
- 성공을 측정할 수 있나요?

영향 및 구현 용이성에 따라 시나리오 우선 순위 지정 초기 포커스 영역이 더 높은 영향을 받을 수 있도록 쉽게 구현할 수도 있습니다. 구현 하기 어려운 낮은 영향 시나리오의 우선 순위를 해제 합니다.

## <a name="identify-roles--responsibilities"></a>역할 & 책임 식별

조직의 누가 모델을 빌드하고 관리할 지 결정 다음과 같은 역할이 포함 될 수 있습니다.

| SharePoint/기술 자료 관리자 | 전원 플랫폼 관리자 | 기술 자료 관리자 | 모델 소유자 |
|:-------|:-------|:-------|:-------|
| AAD 역할| 역할 추가 | AAD 역할 | 챔피언 |
| 양식 처리 구성 | 양식 처리를 위해 일반 데이터 서비스 환경 구성 | 사용 사례 수집 | 비즈니스 사용 사례 수집 |
| 콘텐츠 센터 및 사용 권한 관리| AIB 제작진 구입 및 할당 | 모범 사례 설정 및 검토 모델 분석 | 모델 만들기 및 적용 |

지식 관리자, 비즈니스 프로세스 소유자 및 콘텐츠 모델 소유자 조직에 샘플 모델 및 챔피언 채택을 만듭니다.
관련 된 다른 사용자: 준수 관리자, 분류 관리자

모델을 빌드하고 적용할 위치 향상 시킬 수 있는 기존 프로세스나 리포지토리가 있습니까?

- 양식 처리: 양식 처리 작업을 가져올 사이트를 결정 합니다.
- 문서 이해: 각 비즈니스 영역에 대해 콘텐츠 센터를 여러 개 만들 수 있습니다.

## <a name="strategic-positioning"></a>전략적 포지셔닝

관련자와 협력 하 여 SharePoint Syntex 사용 전략에 부합 되는지 확인 합니다. 이 위치 지정에 도움이 되는 다음 리소스를 조사 하 고 제공 합니다.

- 비즈니스 결과:
  - 잠재적 회계 결과
  - 잠재적인 민첩성 결과
  - 비즈니스 결과 서식 파일
- 관련자/Exec 스폰서 구매/맞춤
  - 비즈니스 사례 데크
  - 재무 모델
  - 회사 준비-문화권

## <a name="identify-stakeholders"></a>관련자 파악

프로젝트에 대 한 관련자를 식별 합니다.

|역할 |업무 |부서 |
|:-------|:-------|:--------|
| 경영 간부   | 회사에 높은 수준의 비전 및 가치 전달   |  임원 리더십   |
| 프로젝트 책임자 | 전체 시작 실행 및 롤아웃 프로세스 감독 | 프로젝트 관리 |
| 지식 관리자| 콘텐츠 센터 만들기 및 관리 | IT 또는 기타 부서|
| 콘텐츠 관리자 및 모델 소유자| 사용 사례 수집 및 모델 만들기 및 적용 | 모든 부서|
| 챔피언 | Objection 처리 evangelize 및 관리 지원 | 모든 부서 (직원) |
| 테넌트 관리자 | 테 넌 트 수준 설정 구성 | IT 부서|
| 전원 플랫폼 관리자| Common data services 환경 구성 | IT 부서|

> [!Note]
> 롤아웃 전체에서 이러한 각 역할을 수행 하는 것이 좋지만 확인 된 솔루션을 시작 하기 위해 이러한 각 역할이 모두 필요 하지 않을 수 있습니다.

## <a name="readiness-checklist"></a>준비 상태 검사 목록

SharePoint Syntex 구현을 준비 하려면 다음을 수행 해야 합니다.

![콘텐츠 이해 준비](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. 최종 상태 계획
    - 문서 이해 모델은 종료를 의미 하지 않습니다.
    - 압축을 푼 메타 데이터의 값을 harnessing에 대 한 계획:
      - 검색
      - 서식 필터링 및 보기
      - 규정 준수
      - 자동화
2. 신원을
    - 기존 정보 아키텍처 및 콘텐츠 관리 기능 사용을 이해 합니다.
    - 기존 콘텐츠 형식이 모델에 적합 한 후보 입니까?
    - 메타 데이터로 향상 된 기존 프로세스는 무엇 인가요?
3. Design
    - 정보 아키텍처, 관리 되는 메타 데이터 및 콘텐츠 형식에 대 한 접근 방식 디자인
    - 정의, 생성, 관리에 대 한 프로세스를 디자인 합니다.

## <a name="engage-your-organization"></a>조직에 참여

1. Stake 소유자 확인, 시나리오 확인 및 프로젝트 계획 개발
1. 설정을 구성 하 고 라이선스를 적용 합니다.
1. 인식 및 교육 시작-Champions.
1. 단계를 롤아웃 합니다.  
1. 의견을 수집 하 고 반복 합니다.
1. 사용량은 필요한 경우 모든 AI Builder 제작진을 계획 하는 것입니다.