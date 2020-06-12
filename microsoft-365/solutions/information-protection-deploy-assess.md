---
title: 데이터 개인 정보 위험 평가 및 Microsoft 365의 중요 한 항목 확인
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Microsoft 365 환경에 있는 데이터 개인 정보 규정, 관련 시나리오, 준비 및 중요 한 정보 유형을 결정 합니다.
ms.openlocfilehash: 532a6764cd1d21eb5eb0402c3451e320d306dc03
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695188"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>데이터 개인 정보 위험 평가 및 Microsoft 365의 중요 한 항목 확인

조직에서 사용 하는 데이터 개인 정보 규정 및 위험을 평가 하는 것은 Microsoft 365 기능 및 서비스를 통해 얻을 수 있는 작업을 포함 하 여 관련 된 개선 조치를 구현 하기 전에 가장 먼저 수행 되는 단계입니다. 

## <a name="potentially-applicable-data-privacy-regulations"></a>잠재적으로 적용 가능한 데이터 개인 정보 규정

데이터 개인 정보 규정에 대 한 보다 광범위 한 규정 프레임 워크에 대 한 자세한 내용은 [Microsoft 서비스 신뢰 포털](https://servicetrust.microsoft.com/) 및 [gdpr (일반 데이터 보호 규정) 규정의 문서 시리즈](../compliance/gdpr.md)및 업계 또는 지역에 적용 될 수 있는 규정에 대 한 기타 자료를 참조 하세요.

### <a name="gdpr"></a>GDPR

데이터 개인 정보 규정에서 가장 잘 알려져 있고 명시 된 GDPR은 유럽 연합 (EU)에 거주 하는 식별 되거나 식별 가능한 자연 당사자와 관련 된 개인 데이터의 수집, 저장, 처리 및 공유를 제어 합니다. 

GDPR 문서 4에 따라: 

- ' 개인 데이터 '는 식별 되거나 식별 가능한 자연 당사자 (' data subject ')와 관련 된 정보를 의미 합니다. 식별 가능한 기본 사람은 이름, 식별 번호, 위치 데이터, 온라인 식별자 또는 해당 자연 당사자의 실제, physiological, 유전자, mental, 경제, 문화 또는 공유 id와 관련 된 하나 이상의 요소와 같은 식별자를 참조 하 여 직접 또는 간접적으로 식별할 수 있습니다.

### <a name="iso-27001"></a>ISO 27001

또한 ISO 27001 같은 다른 표준을 준수 하는 것은 여러 유럽 관리 기관에서 사용자, 프로세스 및 기술 스펙트럼에 대 한 유효한 의도 프록시로 인식 되었습니다. 겹침을 지정 하 고 ISO-27001 기반 보호 메커니즘을 준수 하는 표준은 특정 상황에서 일부 개인 정보 취급 방침을 처리 하는 프록시로 간주 될 수 있습니다.

### <a name="other-data-privacy-regulations"></a>기타 데이터 개인 정보 규정

기타 두드러진 데이터 개인 정보 규정은 개인 데이터 처리에 대 한 요구도 지정 합니다.

미국에는 캘리포니아[CCPA](../compliance/ccpa-faq.md)(소비자 보호 act), HIPAA-HITECH (미국 의료 보험 개인 정보 보호 act) 및 Graham Gramm-leach-bliley gramm-leach-bliley ACT (GLBA)가 포함 됩니다. 추가 상태별 규정이 전체 또는 개발 단계에 있습니다. 

전 세계적으로, 추가 예로는 독일의 국립 GDPR 구현 Act (BDSG), 브라질 LGPD (Data Protection Act) 및 기타 여러 가지 예가 있습니다.

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>Microsoft 365 기술 컨트롤 범주에 대 한 규제 매핑

대부분의 데이터 개인 정보 관련 규정은 요구 사항이 서로 겹치지만, 기술 컨트롤 체계를 개발 하기 전에 이러한 규정을 준수 해야 합니다. 

이 표에는이 전체 솔루션의 문서에 대 한 참조 자료를 제공 하는 데이터 개인 정보 보호 규정의 발췌 한 설명이 나와 있습니다. 

| 조정기 | 문서/섹션 | 인용 | 적용 가능한 기술 컨트롤 범주 |
|:-------|:-----|:-------|:-------|
| GDPR | 문서 5 (1) (f) | 개인 데이터는 개인 데이터에 대 한 적절 한 보안을 보장 하는 방식으로 처리 되며, 적절 한 기술적 또는 조직적 조치 (' 무결성 및 기밀성 ')를 사용 하 여 무단 또는 불법적 처리 및 우발적 손실, 파괴 또는 손상에 대 한 보호를 포함 합니다.  |  모든 <br> ID <br> 디바이스 <br> 위협 방지 <br> 정보 보호 <br> 정보 제어 <br> 검색 및 대응 |
|  | 문서 (32) (1) (a) | 자유의 상태, 구현 비용, 특성, 범위, 컨텍스트 및 처리 목적을 고려 하 여 자연 사용자의 권한 및에 대 한 다양 한 가능성과 심각도를 파악 하 고, 컨트롤러 및 프로세서는 해당 위험에 적합 한 보안 수준을 보장 하기 위해 적절 한 기술 및 조직 조치를 구현 해야 합니다. (a) alia를 적절 하 게 (a) 개인 데이터의 익명화 및 암호화를 포함 합니다. | 정보 보호 |
|  | 문서 (13) (2) (a) | "... 이 컨트롤러는 개인 데이터를 얻은 시점에서 공정 및 투명 처리를 보장 하는 데 필요한 다음과 같은 추가 정보를 제공 합니다 (a). 개인 데이터를 저장할 기간 또는 해당 기간을 결정 하는 데 사용 되는 기준이 될 수 있습니다. | 정보 제어 |
|  | 문서 (15) (1) (e) | 데이터 주체에 대해 컨트롤러 확인에서 가져올 수 있는 권한이 해당 사용자에 대 한 개인 데이터를 처리 중인지 여부에 대 한 정보를 포함 해야 합니다. 그리고 이러한 경우에는 개인 데이터에 액세스 하 고 다음 정보를 확인 합니다. (e) 컨트롤러에서 요청 하거나, 개인 데이터를 수정 하거나, 데이터 주체 또는 개체와 관련 된 개인 데이터를 처리 하는 것을 이러한 처리에 제한 하기 위한 권한이 있는지 여부입니다. | 검색 및 대응 |
| LGPD | 문서 46 | 처리 에이전트는 보안, 기술 및 관리 수단을 채택 하 여 무단 액세스와 실수로 또는 불법적의 손상, 손실, 변경, 통신 또는 모든 유형이 잘못 되거나 불법적 처리 되는 상황 으로부터 개인 데이터를 보호할 수 있습니다. | 정보 보호 <br> 정보 제어 <br> 검색 및 대응|
|  | 문서 48 | 컨트롤러가 국가 및 데이터 주체에 대 한 적절 한 손상을 초래할 수 있는 보안 인시던트가 발생 하는 경우를 위해 국내 기관과 통신 해야 합니다. | 검색 및 대응 |
| HIPPA-HITECH | 45 CFR 164.312 (e) (1) | 전자 통신 네트워크를 통해 전송 되는 전자 보호 상태 정보에 대 한 무단 액세스를 방지 하는 기술 보안 조치를 구현 합니다. | 정보 보호 |
|  | 45 C.F.R. 164.312 (e) (2) (ii) | 적절 한 것으로 간주 될 때마다 전자 보호 된 상태 정보를 암호화 하는 메커니즘을 구현 합니다. | 정보 보호 |
|  | 45 CFR 164.312 (c) (2) | 전자 보호 된 상태 정보가 무단으로 변경 되거나 삭제 되지 않았음을 corroborate 하는 전자 메커니즘을 구현 합니다. | 정보 제어 |
|  | 45 CFR 164.316 (b) (1) (i) | 이 subpart에 대해 작업, 활동 또는 평가를 문서화 해야 하는 경우 작업, 활동 또는 평가의 기록 (전자 일 수 있음) 기록이 유지 관리 됩니다. | 정보 제어 |
|  | 45 CFR 164.316 (b) (1) (ii) | 이 섹션의 단락 (b) (1)은 해당 문서를 만든 날짜 로부터 6 년 동안 또는 나중에 마지막으로 적용 한 날짜 로부터 보존 해야 합니다. | 정보 제어 |
|  | 45 C.F.R. 164.308 (a) (1) (2) (D) | 정기적으로 정보 시스템 활동 (예: 감사 로그, 액세스 보고서 및 보안 인시던트 추적 보고서)의 레코드를 검토 하는 절차를 구현 합니다. | 검색 및 대응 |
|  | 45 C.F.R. 164.308 (a) (6) (ii) | 의심 되거나 알려진 보안 문제를 파악 하 고 대응 합니다. 확장 된 엔터티 또는 비즈니스 연결에 알려진 보안 사고의 위험에 대 한 영향을 practicable으로 완화 합니다. 보안 인시던트 및 해당 결과를 문서화 합니다. | 검색 및 대응 |
|  | 45 C.F.R. 164.312 (b) | 전자 보호 된 상태 정보를 포함 하거나 사용 하는 정보 시스템에서 활동을 기록 및 검사 하는 하드웨어, 소프트웨어 및 절차적 메커니즘을 구현 합니다. | 검색 및 대응 |
| CCPA | 1798.105 (c) | 이 섹션의 세부 정보를 삭제 하기 위해 소비자 로부터 안정형 요청을 수신 하는 회사는 해당 레코드에서 소비자의 개인 정보를 삭제 하 고 모든 서비스 공급자에 게 제공 하 여 레코드에서 소비자의 개인 정보를 삭제 해야 합니다. | 검색 및 대응 |
|  | 1798.105 (d) | (c 1798.105 예외) <br> 비즈니스 또는 서비스 공급자가 소비자의 개인 정보를 삭제 하기 위한 요청을 준수 해야 하는 경우에는 다음에 대 한 고객의 개인 정보를 관리 해야 합니다 (추가 정보에 대 한 현재 규정 참조). | 검색 및 대응 |
|||||

>[!Important]
>이 목록은 목록을 포괄적으로 제공 하기 위한 것이 아닙니다. 나열 된 기술 제어 범주에 설명 된 섹션의 적응성에 대 한 자세한 내용은 [준수 관리자](../compliance/compliance-manager-overview.md) 또는 법률 또는 준수 관리자를 참조 하세요.
>

## <a name="knowing-your-data"></a>데이터 이해

조직의 내부 및 외부에 있는 다양 한 사용자 데이터 형식이 시스템과 상호 작용 하는 모든 중요 한 요소는 전체 개인 데이터 보호 전략에 영향을 줄 수 있는 모든 주요 요소로, 조직에 적용 되는 산업 및 정부 규정에 따라 좌우 됩니다. 여기에는 개인 데이터가 저장 되는 위치, 사용자의 유형, 해당 데이터의 양, 수집 된 상황 등이 포함 됩니다.
 
![데이터 이해:이 개체의 유형, 개체의 양 및 수집한 상황](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>데이터 이식성 

또한 데이터가 처리 되 고 구체화 되 고 다른 버전이 여기에서 파생 되는 시간에 따라 이동 됩니다. 초기 스냅숏은 충분 하지 않습니다. 데이터를 파악 하기 위해 지속적인 프로세스가 필요 합니다. 이는 중요 한 개인 데이터 볼륨을 처리 하는 대규모 조직에 대 한 가장 큰 문제 중 하나를 나타냅니다. "데이터 파악" 문제를 해결 하지 않은 조직은 매우 높은 위험 및 규제 기관 으로부터의 가능한 벌금과 될 수 있습니다.

![데이터 수명 주기](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)
 
### <a name="where-the-personal-data-is"></a>개인 데이터의 위치

데이터 개인 정보 규정을 해결 하기 위해 지금 또는 나중에 개인 데이터가 있을 것으로 생각 되는 일반적인 notions를 사용할 수 없습니다. 데이터 개인 정보 규정을 준수 하려면 조직에서 개인 데이터가 진행 되 고 있는 위치를 확인 해야 합니다. 이를 통해 Microsoft 365 환경을 비롯 하 여 개인 정보를 저장할 수 있는 모든 데이터 원본의 초기 스냅숏을 사용 하 고 지속적인 모니터링 및 검색 메커니즘을 설정할 수 있습니다.

데이터 개인 정보 규정에 관련 된 전반적인 준비 및 위험을 미리 평가 하지 않은 경우 다음 3 단계 프레임 워크를 사용 하 여 시작 합니다. 

>[!Note]
>이 문서와 해당 내용은 법적 자문 서비스의 자리를 차지 하기 위한 것이 아닙니다. 또한 몇 가지 기본 지침과 평가 초기 단계에서 도움이 될 수 있는 도구에 대 한 링크를 제공 합니다.
>
 
## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>1 단계: 조직의 개인 데이터 시나리오에 대 한 기본 이해 개발 

현재 관리 하는 개인 데이터의 유형, 저장 되는 위치, 보관 되는 보호 컨트롤, 수명 주기 관리 방식 및 액세스 권한이 있는 사용자에 따라 데이터 개인 정보 보호 위험에 대 한 노출을 평가 해야 합니다. 

Microsoft 365 환경에 있는 개인 데이터의 유형을 확인 하는 것이 중요 합니다. 다음 범주를 사용 합니다.

- 일상적인 비즈니스 기능을 수행 하는 데 필요한 직원 데이터
- 조직이 B2B (비즈니스 간) 시나리오에서 비즈니스 고객, 파트너 및 기타 관계에 대해 갖고 있는 데이터
- 조직에서 비즈니스 간 (B2C) 시나리오에서 조직이 관리 하는 온라인 서비스에 정보를 제공 하는 소비자에 대 한 데이터를가지고 있습니다.

다음은 조직의 일반적인 부서에 대 한 다양 한 유형의 데이터 예입니다.

![개인 데이터 형식](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

데이터 개인 정보 규정을 따르는 대부분의 개인 데이터는 대개 수집 되어 Microsoft 365 외부에 저장 됩니다. Microsoft 365 내에서 데이터 개인 정보를 검색할 수 있으려면 소비자 연결 웹 또는 모바일 응용 프로그램의 모든 개인 데이터를 Microsoft 365로 내보내야 합니다. 

Microsoft 365의 데이터 개인 정보 노출은 웹 응용 프로그램 및 CRM 시스템 (이 솔루션에서는 해결 되지 않음)에 상대적으로 제한 될 수 있습니다.

또한 위험 프로필 평가 시 다음과 같은 일반적인 데이터 개인 정보 규정 준수 문제에 대해 고려해 야 합니다.

 - **개인 데이터 배포** 특정 주제에 대 한 정보가 분산 되는 방식 적절 한 제어가 적합 하다 고 규정을 파악 하기에 충분 한지 확인 해야 합니다. 필요한 경우 조사 하 고 수정할 수 있습니까?
- **Exfiltration을 보호 합니다.** 특정 형식 또는 원본의 개인 데이터가 손상 되는 것을 방지 하 고, 그렇지 않은 경우에는 어떻게 대응 해야 하나요?
- **보호 및 위험.** 위험에 대해 적절 한 정보 보호 메커니즘 및 최종 사용자 개입이 필요한 경우 비즈니스 연속성 및 생산성을 유지 관리 하 고 최종 사용자의 영향을 최소화 하는 방법 예를 들어 수동 분류 또는 암호화를 사용 해야 하나요?
- **개인 데이터 보존** 유효한 비즈니스 상의 이유로 인해 개인 데이터를 포함 하는 정보를 보관 해야 하는 기간 및, 비즈니스 연속성에 대 한 보존 요구 사항에 맞게 조정 된, 이전의 계속 해 서 계속 실행 되는 모범 사례를 방지 하는 방법
- **데이터 주체 요청 처리** DSRs (데이터 주체 요청)를 처리 하는 데 필요한 메커니즘과 익명화, 교정 및 삭제와 같은 수정 작업을 수행 해야 하는 경우
- **지속적인 모니터링 및 보고** 다양 한 데이터 형식 및 원본에 대해 사용할 수 있는 일상적인 모니터링, 조사 및 보고 기술
- **데이터 처리에 대 한 제한 사항** 이러한 메서드를 통해 수집 되거나 저장 되는 정보에 대 한 데이터 사용에 제한이 있습니까? 조직에서 개인 정보 제어를 반영 해야 하나요? 예를 들어 판매 담당자가 개인 데이터를 사용 하지 않을 경우 조직은 영업 조직과 연결 된 시스템에서 해당 정보의 전송 또는 저장을 차단 하기 위한 메커니즘을 구현 해야 할 수 있습니다.

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>일상적인 비즈니스 기능을 수행 하는 데 필요한 직원 데이터

조직에서는 전자 id 및 HR 목적을 위해 직원 들이 직원 계약에 동의한 사항에 따라 데이터를 수집 해야 합니다. 회사에서 작업 하는 사용자는 일반적으로 문제가 되지 않습니다. 조직은 악의적인 행위자가 exfiltrating에서 직원의 개인 데이터를 누출 하지 못하도록 하기 위한 메커니즘을 마련 하고자 할 수 있습니다. 

한 사람이 회사를 떠나는 경우 조직에는 일반적으로 사용자 계정을 제거 하 고, 사서함과 개인 드라이브를 해제 하 고, 인적 자원 시스템과 같은 직원 상태를 변경 하기 위한 프로세스, 절차 및 보존 및 삭제 일정이 있습니다. 소송에 대 한 법률 조사를 수행 하는 경우 직원이 나 다른 당사자가 조직의 시스템에 저장 된 개인 데이터에 대 한 정보를 얻는 데 유효한 이유가 있을 수 있습니다. 어떤 경우에는 해당 당사자가 해당 데이터를 제거 하거나 익명 것을 요청할 수 있습니다. 

이러한 요구를 해결 하기 위해 조직은 예방, 예방용 인지 및 수정 사항에 대 한 정보를 마련 하기 위해 필요한 프로세스 및 절차를 수행 하 여 직원에 대 한 일부 정보가 비즈니스 연속성에 매우 중요 하 게 고려 될 수 있습니다. 예를 들어 개인이 파일을 작성 했거나 함수를 수행한 정보입니다. 

>[!Note]
>Microsoft 365의 개인 데이터에 대 한 조사 및 재구성 기술에 대 한 자세한 내용은 [monitor and 응답할 문서](information-protection-deploy-monitor-respond.md)를 참조 하십시오. 또한 자동화 된 분류 및 보호 체계를 활용 하 여 조직 내부에서 개인 데이터를 제어 하 고, 악의적인 행위자 상황에서 조직이 벗어나지 않도록 할 수 있습니다. 자세한 내용은 [정보 보호 문서](information-protection-deploy-protect-information.md) 를 참조 하세요.
>
 
### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>B2B 시나리오에서 조직이 비즈니스 고객에 대해 갖는 데이터

조직에서 비즈니스 연속성 목적을 위해 다양 한 시스템에 고객 이름 및 트랜잭션의 기록을 보관 해야 할 수도 있으므로 실수로 또는 악의적인 exfiltration에서 해당 정보를 보호 하는 것도 쉽지 않습니다. 직원 데이터와 마찬가지로 조직에는 이러한 데이터를 보호 하는 데 필요한 정책, 절차 및 기술 컨트롤이 있고, 정의 된 보존 및 삭제 일정에 따라이를 사용 해야 합니다. 

일반적으로 외부 고객, 파트너 및 조직에서 비즈니스를 수행 하는 데 사용 하는 기타 엔터티에는 엔터티가 조직과 관계가 있는 동안/후에 보호, 보존 및 삭제를 비롯 한 이러한 데이터 처리에 대 한 언어를 지정 하는 조직이 제공 됩니다. 

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>B2C 시나리오에서 조직이 관리 하는 온라인 서비스에 정보를 제공 하는 소비자에 게 조직에서 갖는 데이터

이 범주는 고객 데이터 누출의 여러 공용 인스턴스로 인해 데이터 프라이버시에 대해 가장 많이 생각 되는 사람입니다. 이는 공급자에 대 한 계약을 받고 있는 타사와 같은 의도적인 일 수도 있고, 악성 작업자의 노출 되었습니다와 같이 의도 하지 않은 경우에는이 방법을 사용할 수 있습니다. 소비자 데이터 보호는 EU가 이러한 규정을 준수 하는 주된 이유 중 하나입니다. GDPR 및 CCPA와 같은 데이터 개인 정보 규정을 위해서는 다음에 대 한 계획을 세워야 합니다.

- [작업 계획](../compliance/gdpr-action-plan.md) 및 [책임 준비 상태 검사 목록](../compliance/gdpr-arc-office365.md)
- [데이터 보호 영향 평가](../compliance/gdpr-data-protection-impact-assessments.md)
- [위반 알림](../compliance/gdpr-breach-office365.md)
- [데이터 주체 요청](../compliance/gdpr-dsr-office365.md)

조직에서 소비자가 직접 데이터 수집을 수행 하지 않는 경우이 종류에 문제가 적을 수 있습니다. 그러나이 문서에서 설명 하는 프로세스를 계속 진행 하 여 준수 해야 할 수도 있습니다.

### <a name="step-1-summary"></a>1 단계 요약

위험 및 데이터 개인 정보 규정에 대 한 노출을 이해 하는 것은 조직의 개인 데이터 시나리오에 대 한 기본 이해를 기반으로 하는 중요 한 첫 번째 단계입니다.

Microsoft 365 환경에서 소비자의 개인 데이터를 보유 하 고 있지 않거나 해당 환경의 특정 부분으로 제한 되며 소비자 유형 데이터 노출에 대해 기술 컨트롤을 사용 해야 하는 경우에는 해당 기술 제어를 모든 위치에 적용 해야 하는 것이 아니라 환경에서 높은 위험 부분에만 채택 하면 됩니다.

Microsoft 365의 규정 준수 점수와 같은 외부 조직이 나 표준 제어 권장 사항에 따라 제어 전략을 제공 하는 데 도움이 될 수 있지만, 실제 위험 노출을 정량화 하기 위해 데이터 재고 인식이 결정 되도록 구현할 수 있습니다.

대부분의 조직에서는 위의 시나리오 중 하나에 대 한 노출을 일부 합니다. 평가를 전체적으로 사용 하는 것이 중요 합니다.

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>2 단계: 데이터 개인 정보 규정 준수에 대 한 준비 평가

GDPR과 관련 하 여, 무료 [MICROSOFT gdpr 평가 도구](https://www.microsoft.com/cyberassessment/en/gdpr/uso365) 에서 제기 되는 질문은 전반적인 데이터 개인 정보 준비 상태를 이해 하는 데 도움이 됩니다. 

미국 또는 브라질 LGPD의 CCPA과 같은 기타 데이터 개인 정보 규정을 따르는 조직은이 도구의 준비 상태와 GDPR이 서로 겹치는 상황을 활용할 수 있습니다.

GDPR 평가는 다음 섹션으로 구성 됩니다.

| | |
|:-------|:-----|
| 거버넌스 | <ol><li>개인 정보 보호 정책에서 처리 되는 데이터 정보를 명시적으로 명시 합니까? </li><li>개인 정보 보호 영향 평가 (Pia)를 정기적으로 실행 하나요? </li><li> 도구를 사용 하 여 PI (개인 정보)를 관리 하나요? </li><li> 특정 개인이 PI 데이터를 사용 하 여 비즈니스를 수행할 수 있는 법적 기관이 있습니까? 데이터에 대 한 동의를 추적 하나요? </li><li> 감사 컨트롤을 추적, 구현 및 관리 합니까? 데이터 누수를 모니터링 하나요? </li></ol>|
| 삭제 & 알림 | <ol><li>사용자의 데이터에 액세스 하는 방법에 대 한 명시적인 지침을 제공 하나요? </li><li> 옵트아웃 동의를 처리할 수 있도록 프로세스를 문서화 했습니까? </li><li>   데이터에 대 한 자동화 된 삭제 프로세스가 있습니까? </li><li>   고객을 사용할 때 id의 유효성을 검사 하는 프로세스가 있습니까? </li></ol>|
| 위험 완화 및 정보 보안 | <ol><li>도구를 사용 하 여 구조화 되지 않은 데이터를 검사 합니까? </li><li>모든 서버가 최신 상태이 고 방화벽을 활용 하 여 해당 서버를 보호 하나요? </li><li>서버에 대 한 정기적인 백업을 실행 합니까? </li><li>데이터 누수를 적극적으로 모니터링 하 고 계십니까? </li><li>휴지 및 전송 중에 데이터를 암호화 하 고 있습니까? </li></ol>|
| 정책 관리 | <ol><li>BCRs (기업 규칙) 바인딩을 관리 하는 방법은 무엇 인가요? </li><li>데이터에 대 한 동의를 추적 하나요? </li><li> 1 ~ 5, 5의 범위에 포함 된 계약에는 데이터 분류 및 처리 요구 사항이 포함 되어 있나요? </li><li>사건 대응 계획을 정기적으로 테스트 하 고 있는지 여부 </li><li>액세스를 관리 하는 데 사용 하는 정책은 무엇입니까? </li></ol>|
|||
 
## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>3 단계: Microsoft 365 환경에서 발생 하는 중요 한 정보 유형을 식별 합니다. 

이 단계에는 Microsoft 365 환경에서 발생 하는 특정 규제 제어의 영향을 받는 특정 중요 한 정보 유형의 식별이 포함 됩니다. 

개인을 포함 하는 환경의 콘텐츠를 찾는 작업은 이전에 준수 검색, eDiscovery, 고급 eDiscovery DLP 및 감사를 사용 하는 것과 관련 된 formidable 작업이 될 수 있습니다. 

Microsoft 규정 준수 관리 센터의 새 **데이터 분류** 솔루션을 사용 하는 경우에는 개인 데이터와 관련 된 정보를 포함 하 여 기본 제공 또는 사용자 지정 중요 한 정보의 유형에 사용할 수 있는 [콘텐츠 탐색기](../compliance/data-classification-content-explorer.md) 기능을 사용 하는 것이 훨씬 쉬워졌습니다.
 
### <a name="sensitive-information-types"></a>중요한 정보 유형

Microsoft 준수 관리 센터는 개인 데이터를 식별 하 고 찾는 것과 대부분의 100 중요 한 정보 유형을 미리 로드 하 여 제공 합니다. 이러한 기본 제공 중요 한 정보 유형은 정규식 (regex) 또는 함수로 정의 된 패턴에 따라 신용 카드 번호, 은행 계좌 번호, 여권 번호 등을 식별 하 고 보호 하는 데 도움이 될 수 있습니다. 자세한 내용은 [중요한 정보 유형이 찾는 항목](../compliance/what-the-sensitive-information-types-look-for.md)을 참조하십시오.

직원 Id에 대 한 사용자 지정 형식과 같은 중요 한 항목의 조직 관련 또는 지역별 형식을 식별 하 고 보호 해야 하는 경우, 이러한 방법을 사용 하 여 사용자 지정 중요 한 정보 유형을 만들 수 있습니다. 

- PowerShell
- EDM (정확한 데이터 일치)을 사용 하는 사용자 지정 규칙
- 준수 [점수 및 준수 관리자 사용 문서](information-protection-deploy-compliance.md) 에 강조 표시 된 준수 센터 관리 UI를 통해

기존에 기본적으로 제공 되는 중요 한 정보 유형을 사용자 지정할 수도 있습니다.

자세한 내용은 다음 문서를 참조 하세요.

- [기본 제공 중요한 정보 유형 사용자 지정](../compliance/customize-a-built-in-sensitive-information-type.md)
- [사용자 지정 중요한 정보 유형](../compliance/custom-sensitive-info-types.md)
- [보안 및 준수 센터에서 사용자 지정 중요한 정보 유형 만들기](../compliance/create-a-custom-sensitive-information-type.md)
- [보안 및 준수 센터 PowerShell에서 사용자 지정 중요한 정보 유형 만들기](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [정확한 데이터 일치를 기반으로 하는 사용자 지정 중요 한 정보 유형 만들기 분류](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>콘텐츠 탐색기

사용자 환경에서 중요 한 항목의 발생을 확인 하는 데 필요한 중요 한 도구는 Microsoft 365 준수 관리 센터의 새로운 [콘텐츠 탐색기](../compliance/data-classification-content-explorer.md) 입니다. 중요 한 정보 유형 및 결과 표시에 대 한 전체 Microsoft 365 구독을 초기 및 지속적으로 검색 하는 데 사용할 수 있는 자동화 된 도구입니다.
 
새 콘텐츠 탐색기 도구를 사용 하면 기본 제공 중요 한 정보 유형 또는 사용자 지정 기능을 사용 하 여 환경에서 중요 한 항목의 위치를 빠르게 확인할 수 있습니다. 여기에는 중요 한 항목의 현재 상태 및 위치를 정기적으로 조사 하기 위한 프로세스 설정 및 책임 지정이 포함 될 수 있습니다.

이 문서에서 설명 하는 다른 단계와 함께,이는 계획 된 Microsoft 365 구성 및 모니터링을 통해 보호할 중요 한 항목의 전반적인 위험 노출, 준비 및 위치를 식별 하기 위한 출발점을 제공 합니다. 

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>환경에서 개인 데이터를 식별 하는 기타 방법

콘텐츠 탐색기 외에도, 조직은 고급 검색 조건 및 사용자 지정 필터를 사용 하 여 환경에서 개인 데이터를 찾기 위한 사용자 지정 검색 기능을 사용할 수 있습니다.

[이 문서](../compliance/search-for-and-find-personal-data.md)에서는 콘텐츠 검색을 사용 하 여 개인 데이터를 검색 하는 방법에 대 한 자세한 지침을 제공 합니다. [GDPR 및 CCPA](../compliance/gdpr-dsr-office365.md#introduction-to-dsrs)의 경우에도 콘텐츠 검색 및 기타 검색 기술이 dsrs에서 조사 됩니다.

Microsoft 365의 개인 데이터에 대 한 조사 및 업데이트 관리 기술에 대 한 추가 정보는 [monitor (응답) 문서](information-protection-deploy-monitor-respond.md)에 나와 있습니다.