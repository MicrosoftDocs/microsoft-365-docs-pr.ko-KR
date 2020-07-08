---
title: GDPR에 따른 Windows 알림용 데이터 프로세서 서비스
description: Windows용 데이터 프로세서 서비스가 개인 데이터 위반으로부터 보호하는 방법 및 Microsoft가 위반 발생 시 대응하고 사용자에게 알리는 방법입니다.
keywords: Windows용 데이터 프로세서 서비스, Microsoft 365, Microsoft 365 문서, GDPR
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: daniha
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: bfadeae0f4f0b01197f58f0610d1040da3080922
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023634"
---
# <a name="data-processor-service-for-windows-breach-notification-under-the-gdpr"></a>GDPR에 따른 Windows 위반 알림용 데이터 프로세서 서비스

>[!NOTE]
>이 항목은 Windows 미리 보기 프로그램용 데이터 프로세서 서비스 참여자를 대상으로 하며 특정 사용 약관을 수락해야 합니다. 프로그램에 대해 자세히 알아보고 사용 조건에 동의하려면 [https://aka.ms/dpswpublicpreview](https://aka.ms/dpswpublicpreview)을(를) 참조하세요.

Windows용 Microsoft 데이터 프로세서 서비스는 GDPR(일반 데이터 보호 규정)에 따라 의무를 다합니다. Windows용 Microsoft 데이터 프로세서 서비스는 데이터 위반 으로부터 보호를 위해 광범위한 보안 조치를 취합니다. 여기에는 악의적 액세스를 사전에 예측, 방지, 완화하는 전담 위협 관리 팀이 포함됩니다.  포트 검색, 경계 취약성 검색, 침입 감지와 같은 내부 보안 조치는 악의적인 액세스를 감지하고 예방하며 자동화된 보안 프로세스, 포괄적인 정보 보안 및 개인 정보 보호 정책, 모든 담당자에 대한 보안 및 개인 정보 보호 교육 등도 포함됩니다. 

보안은 처음부터 끝까지 Windows용 Microsoft 데이터 프로세서 서비스에서 구축되며 설계에 따른 개인 정보 보호 및 기본적인 방법론에 따른 개인 정보 보호를 통합하는 필수 개발 프로세스인 [보안 개발 수명 주기](https://www.microsoft.com/sdl/)부터 시작합니다. Microsoft의 보안 전략의 처리 원칙은 심층 방어 전략의 확장인 "위반 가정"을 하는 것입니다. Microsoft는 Windows용 데이터 프로세서 서비스의 보안 기능에 끊임없이 도전하여 최신 위협에 앞장설 수 있습니다. Windows 보안용 데이터 프로세서 서비스에 대한 자세한 내용은 해당 [리소스](https://www.microsoft.com/TrustCenter/Security/windows10-security)를 참조하세요. Windows용 데이터 프로세서 서비스는 보안 인시던트 대응 프로세스에 따라 잠재적인 데이터 위반에 대해 대응합니다. Windows 보안 인시던트 대응에 대한 데이터 프로세서 서비스는 5단계 프로세스(검색, 평가, 진단, 안정화 및 닫기)를 사용하여 구현됩니다. 보안 인시던트 대응 팀은 조사가 진행되면서 진단 및 안정화 단계를 전환하면서 수행할 수 있습니다. 보안 인시던트 대응 프로세스에 대한 개요는 다음과 같습니다. 

|**단계**|**설명**|
| ------- | ------------- |
| ***1-감지*** | 잠재적인 인시던트의 최초 지표 |
| ***2-평가*** | An on-call incident response team member assesses the impact and severity of the event. Based on evidence, the assessment may or may not result in further escalation to the security response team. |
| ***3-진단*** | 보안 응답 전문가가 해당 기술 또는 법정 조사를 수행하고, 방지, 완화 및 해결 전략을 파악합니다. 보안 팀에서 고객 데이터가 불법적이거나 허가되지 않은 개인에게 노출되었을 수 있다고 판단할 경우 고객 인시던트 알림 프로세스가 동시에 실행될 수 있습니다. |
| ***4 - 안정화 및 복구*** | The incident response team creates a recovery plan to mitigate the issue. Crisis containment steps such as quarantining impacted systems may occur immediately and in parallel with diagnosis. Longer term mitigations may be planned which occur after the immediate risk has passed. |
| ***5 - 종료 및 사후 평가*** | 인시던트 대응 팀은 정책, 절차 및 프로세스를 수정하여 이벤트 재발을 방지하기 위해 인시던트의 세부 정보를 대략적으로 설명하는 사후 평가를 만듭니다. |

Windows용 Microsoft 데이터 프로세서 서비스에서 사용하는 감지 프로세스는 Windows용 데이터 프로세서 서비스의 기밀성, 무결성 및 가용성을 침해하는 이벤트를 검색하도록 고안되었습니다. 다음과 같은 일부 이벤트가 조사를 트리거할 수 있습니다. 

 - 내부 모니터링 및 경고 프레임워크를 통한 자동화된 시스템 알림. 이러한 경고는 맬웨어 방지, 침입 감지와 같은 서명 기반 경보나 비정상 상황 발생 시 예상되는 작업 및 경고를 프로파일링하도록 설계된 알고리즘을 통해 제공됩니다.
 - 첫 번째 파티는 Microsoft Azure 및 Azure Government에서 실행되는 Microsoft 서비스의 첫 번째 파티 보고서입니다.
 - 보안상 취약한 부분은 [secure@microsoft.com] (mailto:secure@microsoft.com)을 통해 [MSRC (Microsoft Security Response Center)](https://technet.microsoft.com/security/dn440717)로 보고됩니다. MSRC는 전 세계의 파트너 및 보안 연구자들과 협력하여 보안 인시던트를 방지하고 Microsoft 제품 보안을 향상시킬 수 있도록 지원합니다.
 - 고객은 고객 지원 포털 또는 Microsoft Azure 및 Azure Government 관리 포털을 통해 보고하며 Azure 인프라에 영향을 주는 의심스러운 작업(고객의 책임 범위 내에서 발생하는 작업과는 반대됨)을 설명합니다.
 - 보안 [Red 팀 및 Blue 팀](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) 활동. 이 전략은 공격적 보안 전문가로 구성된 고도로 훈련된 Red 팀을 사용하여 Azure에서 잠재적인 취약점을 밝히고 공격할 수 있습니다. 보안 응답 Blue 팀은 Red 팀의 활동을 감지하고 방어해야 합니다. Azure 보안 대응 노력으로 보안 문제를 효과적으로 관리하는지 확인하는 데 Red 및 Blue 팀 작업이 모두 사용 됩니다. 보안 Red 팀 및 Blue 팀 활동은 고객 데이터 보호를 보장하기 위해 계약 규칙에 따라 운영됩니다.
 - Azure 서비스의 연산자에 의한 에스컬레이션 Microsoft 직원은 잠재적인 보안 문제를 식별하고 에스컬레이션하도록 교육을 받았습니다.

 ## <a name="data-processor-service-for-windows-data-breach-response"></a>Windows 데이터 위반 대응에 대한 데이터 프로세서 서비스 

 Microsoft는 인시던트가 기능에 미치는 영향, 복구 가능성 및 정보에 미치는 영향을 결정하여 조사의 적절한 우선순위와 심각도 수준을 할당합니다. 우선 순위와 심각도는 새로 확인한 결과 및 결론에 따라, 조사가 진행되는 동안 변경될 수 있습니다. 고객 데이터의 즉각적인 위험이나 확인된 위험과 관련된 보안 이벤트는 높은 심각도로 처리하고 24시간 내내 해결합니다. Windows용 Microsoft 데이터 프로세서 서비스는 다음의 위반 카테고리에 따라 인시던트가 정보에 미치는 영향을 분류합니다. 

| **범주**             | **정의**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| ***없음***               | 정보가 노출, 변경, 삭제 또는 다른 방식으로 손상되지 않았습니다. |
| ***개인 정보 보호 위반***     | 납세자, 직원, 수익자 등의 중요한 개인 데이터가 액세스되었거나 노출되었습니다. |
| ***독점 위반*** | PCII(보호되는 중요한 인프라 정보)와 같은 분류되지 않은 소유 정보가 액세스되었거나 노출되었습니다. |
| ***무결성 손실***     | 중요한 정보 또는 소유 정보가 변경되었거나 삭제되었습니다. |

보안 대응 팀은 Windows용 Microsoft 데이터 프로세서 서비스 보안 엔지니어 및 SME와 공조하여 증거를 통한 실제 데이터를 기준으로 이벤트를 분류합니다. 보안 이벤트를 다음과 같이 분류할 수 있습니다. 

 - **가양성:** 검색 기준을 충족하지만 일반적인 비즈니스 사례에 해당되며 필터링해야 하는 이벤트입니다. 서비스 팀은 가양성의 근본 원인을 파악한 후, 탐지 원본을 활용하고 필요에 따라 미세 조정하는 체계적인 방식을 통해 해결합니다. 
 - **보안 인시던트:** Microsoft 장비 또는 Microsoft 시설에 저장되어 있는 모든 고객 데이터 또는 지원 데이터에 대한 불법 액세스 또는 이러한 장비 또는 시설에 대한 무단 액세스로 인해 고객 데이터 또는 지원 데이터가 손실, 노출 또는 변경되는 인시던트입니다. 
 - **CRSI(고객 보고 가능 보안 인시던트):** Microsoft의 시스템, 장비 또는 시설을 불법적으로 또는 허가 없이 액세스하거나 사용하여 고객 데이터를 공개, 수정 또는 손실하는 경우입니다. 
 - **개인 정보 보호 위반:** 개인 데이터와 관련된 보안 인시던트의 하위 유형입니다. 처리 절차는 보안 인시던트와 다르지 않습니다. 

 For a CRSI to be declared, Microsoft must determine that unauthorized access to customer data has or has very likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSI after the conclusion of the Diagnose stage of a security incident; however, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process. 

Throughout the investigation, the security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers. There are also significant restrictions on system and customer data viewing and handling in various operating environments. Sensitive or confidential data, as well as Customer Data, are not transferred out of the production environment without explicit written approval from the Incident Manager recorded in the corresponding incident ticket. 

Microsoft verifies that customer and business risk is successfully contained, and that corrective measures are implemented. If necessary, emergency mitigation steps to resolve immediate security risks associated with the event are taken. 

Microsoft는 또한 데이터 유출을 위한 내부 사후 평가을 완료합니다. 이 연습의 일환으로 응답 및 운영 절차의 충분성이 평가되고 보안 사고 대응 SOP 또는 관련 프로세스에 필요한 업데이트가 식별되고 구현됩니다. 데이터 유출에 대한 내부 사후 평가는 고객이 이용할 수 없는 극비 기록입니다. 그러나 사후 평가는 요약되어 다른 고객 이벤트 통지에 포함될 수 있습니다. 이 보고서는 Windows 정기 감사 주기에 대한 데이터 프로세서 서비스의 일부로 검토를 위해 외부 감사인에게 제공됩니다. 

## <a name="customer-notice"></a>고객 알림

Windows용 Microsoft 데이터 프로세서 서비스는 필요한 경우 데이터 위반 사실을 고객과 규제 기관에 알립니다. Microsoft는 Windows용 데이터 프로세서 서비스의 운영에 있어서 많은 내부 구획화에 의존합니다. 데이터 흐름 로그 역시 강력합니다. 이 설계에 대한 혜택으로 대부분의 인시던트는 특정 고객으로 범위가 지정될 수 있습니다. 해당 목표는 데이터가 위반되는 경우 영향을 받는 고객에게 제때에 정확하고 조치를 취할 수 있는 알림을 제공하는 것입니다. 

CRSI를 선언한 후에는 빠르게 이동하는 보안 위험을 계속 고려하면서 최대한 신속하게 알림 프로세스가 수행됩니다. 일반적으로 인시던트 조사가 진행되는 동안에 알림 작성 프로세스가 수행됩니다. 고객 알림은 다음 상황을 제외하고 위반을 선언한 시점으로부터 72시간 이내에 전달됩니다. 

 - Microsoft believes the act of performing a notification will increase the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate. 
 - Microsoft의 법률 부서 CELA(회사 외부 업무 및 법률 담당) 및 인시던트 책임 관리자가 기타 비정상적이거나 극단적인 상황을 조사한 경우. 

 Windows용 Microsoft 데이터 프로세서 서비스는 알림 프로세스를 과도하게 지연시키지 않으면서 내부 조사를 수행할 수 있도록 하고 최종 사용자 약정을 충족하도록 지원할 수 있는 자세한 정보를 고객에게 제공합니다. 

개인 데이터 침해에 대한 알림은 전자 메일을 통해 Microsoft를 포함한 모든 방법으로 고객에게 전달됩니다. 데이터 위반 알림은 Azure Security Center에서 제공되는 보안 담당자 목록에 전달되며 [구현 지침](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details)을 따라 구성할 수 있습니다. Azure Security Center에서 연락처 정보가 제공되지 않으면 Azure 구독으로 한 명 이상의 관리자에게 알림이 전송됩니다. 알림이 성공적으로 전달될 수 있도록 해당 구독 및 온라인 서비스 포털에 대한 관리 연락처 정보가 올바른지 확인하는 것은 고객의 책임입니다.

Windows용 데이터 프로세서 서비스 팀은 CSS(고객 서비스) 및 고객 AM(계정 관리자) 또는 TAM(기술 계정 관리자)과 같은 추가 Microsoft 담당자에게도 알리도록 선택할 수 있습니다. 이러한 개인은 고객과 밀접하게 관련되어 있는 경우가 많으며 보다 빠른 수정이 이루어지는 데 도움이 될 수 있습니다. 

Microsoft에서 개인 데이터 위반을 감지하고 대처하는 방법에 대한 자세한 내용은 Service Trust Portal의 [GDPR에서 데이터 위반 알림](https://servicetrust.microsoft.com/ViewPage/GDPRBreach)을 참조하세요.