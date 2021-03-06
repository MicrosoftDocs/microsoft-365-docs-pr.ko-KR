---
title: EOP(Exchange Online Protection) 개요
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: EOP(Exchange Online Protection)가 독립 실행형 및 하이브리드 환경에서 전자 메일 조직을 보호하는 데 어떻게 도움이 될 수 있는지 알아보십시오.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e8e3d44cb39e3569179d4155e32a8c11e0a5be56
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286888"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

EOP(Exchange Online Protection)는 스팸 및 맬웨어로부터 조직을 보호하는 데 도움이 되는 클라우드 기반 필터링 서비스입니다. EOP는 Exchange Online 사서함이 있는 모든 Microsoft 365 조직에 포함되어 있습니다. 그러나 EOP는 다음과 같은 On-premises 시나리오에서도 사용할 수 있습니다.

- **독립 실행형** 시나리오: EOP는 클라우드 기반 전자 메일 보호를 제공합니다. EOP는 다른 모든온-프레미스 SMTP 전자 메일 솔루션에 대해 클라우드 기반 전자 메일 보호 기능을 제공합니다.

- **하이브리드 배포에서**: 전자 메일 환경을 보호하고, 전자 메일 사서함과 클라우드 사서함이 혼합되어 있는 경우 메일 라우팅을 제어하도록 EOP를 구성할 수 있습니다.

이러한 시나리오에서 EOP는 전자 메일 환경의 관리를 간소화하고 온-프레미스 하드웨어 및 소프트웨어 유지 관리 시의 많은 부담을 덜어 줄 수 있습니다.

이 항목의 나머지에서는 EOP가 독립 실행형 및 하이브리드 환경에서 작동하는 방식에 대해 설명합니다.

## <a name="how-eop-works"></a>EOP의 작동 방식

EOP가 받는 전자 메일을 처리하는 방법을 확인하면 EOP의 작동 방식을 이해하는 데 도움이 됩니다.

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="EOP로 전달되는 인터넷 또는 고객 의견 및 연결, 맬웨어 방지, 메일 흐름 규칙-슬래시 정책 필터링 및 콘텐츠 필터링을 통해 정크 메일 또는 차단 또는 최종 사용자 메일 배달이 판결되기 전에 전송되는 전자 메일의 그래픽입니다.":::

- 들어오는 메시지가 EOP에 들어오면 처음에는 연결 필터링을 통해 전달되어 보낸 사람 신뢰도도 확인됩니다. 대부분의 스팸은 이 시점에서 중지된 후 EOP에서 거부됩니다. 자세한 내용은 [연결 필터링 구성](configure-the-connection-filter-policy.md)을 참조하십시오.

- 그런 다음 메시지에서 맬웨어의 징후를 검사합니다. 메시지 또는 첨부 파일에서 맬웨어가 발견된 경우 메시지는 관리자 전용 저장소로 라우팅됩니다. 맬웨어 방지 구성에 대한 자세한 내용은 여기에서 자세히 [알아보십시오.](configure-anti-malware-policies.md)

- 메시지는 정책 필터링을 계속 진행하여 템플릿에서 만들거나 적용하는 사용자 지정 메일 흐름 규칙(전송 규칙)에 대해 평가됩니다. 예를 들어 특정 보낸 사람으로부터 메일이 도착하면 관리자에게 알림을 보내는 규칙을 사용할 수 있습니다. DLP(데이터 손실 방지) 검사도 이 시점에서(Exchange Enterprise CAL with Services)에 있습니다.

- 다음으로 메시지는 콘텐츠 필터링(스팸 방지라고도 알려지기)을 통과합니다. 이 필터에서 스팸 또는 피싱으로 확인되는 메시지는 여러 옵션 중에서 스팸 또는 피싱을 차단하거나 사용자의 정크 메일 폴더로 보낼 수 있습니다.  자세한 내용은 스팸 [방지](configure-your-spam-filter-policies.md) 정책 구성 및 피싱 방지 [정책 구성을 참조하십시오.](configure-anti-phishing-policies-eop.md)

이러한 모든 보호 계층을 성공적으로 전달하는 모든 메시지는 받는 사람에게 배달됩니다.

자세한 내용은 전자 메일 보호의 [순서 및 우선 순위를 참조하세요.](how-policies-and-protections-are-combined.md)

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>EOP 계획 및 기능-프레미스 전자 메일 조직

사용 가능한 EOP 구독 계획은 다음을 제공합니다.

- **EOP 독립 실행형 : EOP에** 등록하여온-프레미스 전자 메일 조직을 보호합니다.

- **Exchange Online의 EOP** 기능: Exchange Online을 포함하는 모든 구독(독립 실행형 또는 Microsoft 365의 일부)은 EOP를 사용하여 Exchange Online 사서함을 보호합니다.

- **Exchange Enterprise CAL with Services:** Exchange Enterprise CAL with Services 라이선스를 추가로 구입한 Exchange 조직이 있는 경우 EOP는 포함된 서비스의 일부입니다.

모든 EOP 구독 계획의 요구 사항, 중요한 제한 및 기능 가용성에 대한 자세한 내용은 Exchange Online Protection 서비스 [설명을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>전자 메일 조직에 대해 EOP 설정

EOP는 간단하게 설정할 수 있으며, 특히 준수 규칙이 많지 않은 소규모 조직의 경우에는 더욱 그렇습니다. 그러나 도메인이 여러 개이거나 사용자 지정 준수 규칙 또는 하이브리드 메일 흐름을 사용하는 대규모 조직의 경우에는 EOP 설정에 더 많은 시간과 계획이 필요할 수 있습니다.

EOP를 이미 구입한 경우 [EOP 서비스 설정](set-up-your-eop-service.md)을 참조하여 메시징 환경을 보호하도록 EOP를 구성하는 데 필요한 모든 단계를 완료하십시오.

### <a name="eop-datacenters"></a>EOP 데이터 센터

EOP는 최고 수준의 사용 가능성을 제공하도록 설계된 전 세계 데이터 센터 네트워크에서 실행됩니다. 예를 들어 데이터 센터를 사용할 수 없더라도 서비스 중단 없이 전자 메일 메시지가 다른 데이터 센터에 자동으로 라우팅됩니다. 각 데이터 센터의 서버는 사용자 대신 메시지를 수락하여 조직과 인터넷을 분리하는 계층을 제공함으로써 서버에 대한 부하를 줄입니다. 이처럼 가용성이 뛰어난 네트워크를 통해 Microsoft는 전자 메일이 제때에 조직으로 배달되도록 할 수 있습니다.

EOP는 특정 지역 내에서만 데이터 센터 간 부하 분산을 수행합니다. 단일 지역에서 프로비전되는 경우에는 해당 영역에 대한 메일 라우팅을 사용하여 모든 메시지가 처리됩니다. 다음 목록에는 EOP 데이터 센터에 대한 영역 메일 라우팅의 작동 방식이 나와 있습니다.

- EMEA(유럽, 중동 및 아프리카)에서는 모든 Exchange Online 사서함이 EMEA 데이터 센터에 있으며 모든 메시지가 EOP 필터링용으로 EMEA 데이터 센터를 통해 라우팅됩니다.

- APAC(Asia-Pacific)에서 모든 Exchange Online 사서함은 APAC 데이터 센터에 있으며 메시지는 현재 EOP 필터링을 위해 APAC 데이터 센터를 통해 라우팅됩니다.

- 미국에서는 서비스가 다음 위치에 배포됩니다.

  - 남미: Exchange Online 사서함은 브라질 및 칠레의 데이터 센터에 있습니다. 모든 메시지는 EOP 필터링을 위해 로컬 데이터 센터를 통해 라우팅됩니다. Quarantined 메시지는 테넌트가 있는 데이터 센터에 저장됩니다.

  - 캐나다: Exchange Online 사서함은 캐나다의 데이터 센터에 있습니다. 모든 메시지는 EOP 필터링을 위해 로컬 데이터 센터를 통해 라우팅됩니다. Quarantined 메시지는 테넌트가 있는 데이터 센터에 저장됩니다.

  - 미국: Exchange Online 사서함은 미국 데이터 센터에 있습니다. 모든 메시지는 EOP 필터링을 위해 로컬 데이터 센터를 통해 라우팅됩니다. Quarantined 메시지는 테넌트가 있는 데이터 센터에 저장됩니다.

- GCC(정부 커뮤니티 클라우드)의 경우에는 모든 Exchange Online 사서함이 미국 데이터 센터에 있으며 모든 메시지는 EOP 필터링용으로 미국 데이터 센터를 통해 라우팅됩니다.

## <a name="eop-help-for-admins"></a>관리자를 위한 EOP 도움말

EOP 관리자의 도움말 내용은 다음과 같은 최상위 범주로 구성되어 있습니다.

- [Microsoft Defender for Office 365 관리자용 EOP 구성: Office 365용 Microsoft Defender의](protect-against-threats.md)핵심에서 EOP 보호 및 검색 도구 구성

- [EOP 기능: EOP에서](eop-features.md)사용할 수 있는 기능 목록을 제공합니다.

- [EOP 서비스](set-up-your-eop-service.md)설정: EOP 서비스를 설정하는 단계와 추가 정보에 대한 링크를 제공합니다.

- [Google Postini, Barracuda Spam and Virus Firewall 또는 Cisco IronPort에서 EOP로](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)전환: 다른 전자 메일 보호 제품에서 EOP로 전환하는 프로세스를 설명

- [독립 실행형 EOP에서](manage-recipients-in-eop.md)받는 사람 관리 : EOP에서 메일 사용자 및 그룹을 관리하는 방법을 설명 합니다.

- [EOP의 메일](mail-flow-in-eop.md)흐름 : 커넥터를 사용하여 사용자 지정 메일 흐름 시나리오를 구성하는 방법, 서비스에 연결된 도메인을 관리하는 방법 및 DBEB(디렉터리 기반 Edge 차단) 기능을 사용하도록 설정하는 방법을 설명합니다.

- [EOP](best-practices-for-configuring-eop.md)구성 모범 사례: 서비스를 설정하고 프로비전한 후의 권장 구성 설정 및 고려 사항을 설명

- [독립 실행형 EOP의](auditing-reports-in-eop.md)감사 보고서: 감사 보고서를 사용하여 서비스에 대한 구성 변경 내용을 추적하는 방법을 설명 합니다.

- [EOP의](anti-spam-and-anti-malware-protection.md)스팸 방지 및 맬웨어 방지 보호 : 스팸 필터링 및 맬웨어 필터링에 대해 설명하고 조직의 요구 사항을 가장 잘 충족할 수 있도록 사용자 지정하는 방법을 보여줍니다. 또한 관리자 및 최종 사용자가 격리된 메시지에 대해 수행할 수 있는 작업도 설명합니다.

- [Exchange Online Protection의](reporting-and-message-trace-in-exchange-online-protection.md)보고 및 메시지 추적: 사용 가능한 보고서 및 문제 해결 도구에 대해 설명

- [독립 실행형 EOP의 Exchange](exchange-admin-center-in-exchange-online-protection-eop.md)관리 센터: EAC(Exchange 관리 센터) 관리 인터페이스를 액세스하고 탐색하여 EOP 서비스를 관리하는 방법을 설명

- [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): 명령줄에서 EOP 서비스를 관리할 수 있는 원격 PowerShell에 대한 정보를 제공합니다.

- [EOP에 대한 도움말 및 지원](help-and-support-for-eop.md) 도움말 및 기술 지원 서비스를 구하는 내용에 대해 설명합니다.
