---
title: NAT 지원(Office 365)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: 이 문서에서는 NAT를 사용하여 조직의 IP 주소당 사용할 수 있는 클라이언트 수를 대략화하는 방법에 대해 자세히 제공합니다.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692284"
---
# <a name="nat-support-with-office-365"></a>NAT 지원(Office 365)

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

이전에는 Office 365에 연결하는 데 IP 주소당 사용해야 하는 최대 Exchange 클라이언트 수가 네트워크 포트당 약 2,000개 클라이언트인 것이 제시되었습니다.
  
## <a name="why-use-nat"></a>NAT를 사용하는 이유

NAT를 사용하여 수천 명의 회사 네트워크에서 공개적으로 라우팅 가능한 몇 개의 IP 주소를 "공유"할 수 있습니다.
  
대부분의 회사 네트워크는 개인(RFC1918) IP 주소 공간을 사용합니다. 개인 주소 공간은 IANA(인터넷 할당 번호 기관)에서 할당하며 전역 인터넷을 통해 직접 라우팅되지 않는 네트워크 전용입니다.
  
조직은 개인 IP 주소 공간의 장치에 인터넷에 액세스할 수 있도록 NAT(Network Address Translation) 또는 PAT(포트 주소 변환) 서비스를 제공하는 방화벽 및 Proxies와 같은 게이트웨이 기술을 사용하고 있습니다. 이러한 게이트웨이는 내부 장치에서 인터넷으로(Office 365 포함) 트래픽이 공개적으로 라우팅 가능한 IP 주소에서 온 것으로 나타납니다. 내부 장치의 각 아웃바운드 연결은 공용 IP 주소의 다른 원본 TCP 포트로 변환됩니다. 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a>Office 365에 동시에 많은 연결을 열 필요가 있는 이유는 무엇입니까?

Outlook에서 8개 이상의 연결을 열 수 있습니다(추가 기능, 공유 일정, 사서함 등이 있는 경우). Windows 기반 NAT 장치에서는 최대 64,000개 포트를 사용할 수 있기 때문에 포트가 소진되기 전에 IP 주소 뒤에 최대 8,000명이 있을 수 있습니다. 고객이 NAT에 Windows OS 기반이 아닌 장치를 사용하는 경우 사용 가능한 총 포트는 사용 가능한 NAT 장치 또는 소프트웨어에 따라 달라집니다. 이 시나리오에서는 최대 포트 수가 64,000개 미만일 수 있습니다. 또한 포트 가용성은 Windows에서 자체적으로 사용할 수 있도록 포트 4,000개 제한과 같은 다른 요인의 영향을 받기 때문에 사용 가능한 총 포트 수를 60,000개로 줄입니다. 다른 응용 프로그램(예: Internet Explorer 포트가 필요)이 동시에 연결될 수 있습니다.
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a>Office 365에서 단일 공용 IP 주소 뒤에 지원되는 최대 장치 계산

단일 공용 IP 주소 뒤에 있는 최대 장치 수를 결정하기 위해 네트워크 트래픽을 모니터링하여 클라이언트당 최대 포트 사용량을 결정해야 합니다. 또한 포트 사용에 최대 요인(최소 4)을 사용해야 합니다. 
  
 **다음 수식을 사용하여 IP 주소당 지원되는 장치 수를 계산합니다.**
  
단일 공용 IP 주소 뒤에 지원되는 최대 장치 = (64,000 - 제한된 포트)/(최대 포트 사용 + 최대 비율)
  
 **예를 들어 다음에 해당하면 다음과 같습니다.**
  
- **제한된 포트:** 운영 체제의 경우 4,000개

- **최대 포트 소비:** 장치당 6개

- **최대 계수:** 4

그런 다음 단일 공용 IP 주소 뒤에 지원되는 최대 장치 = (64,000 - 4,000)/(6 + 4) = 6,000
  
Office 365 호스팅 팩이 릴리스되어 2011년 9월 Microsoft Office Outlook 2007년 9월 또는 Microsoft Outlook 2010용 2011년 11월 업데이트 또는 이후 업데이트에 포함되어 있는 Outlook(Office Outlook 2007 서비스 팩 2 및 Outlook 2010)에서 Exchange로의 연결 수는 2개 정도가 될 수 있습니다. 네트워크에서 최대 사용 가능한 최대 포트 수를 결정하려면 여러 운영 체제, 사용자 동작 등에서 요소를 고려해야 합니다.
  
단일 공용 IP 주소 뒤에 더 많은 장치를 지원하려는 경우 지원할 수 있는 최대 장치 수를 평가하기 위해 설명된 단계에 따라 다음을 수행합니다.
  
네트워크 트래픽을 모니터링하여 클라이언트당 최대 포트 사용량을 확인합니다. 다음 데이터를 수집해야 합니다.
  
- 여러 위치에서
    
- 여러 디바이스에서
    
- 여러 번
    
앞의 수식을 사용하여 해당 환경에서 지원할 수 있는 IP 주소당 최대 사용자 수를 계산합니다.
  
추가 공용 IP 주소에 클라이언트 부하를 분산하는 다양한 방법이 있습니다. 사용 가능한 전략은 회사 게이트웨이 솔루션의 기능에 따라 달라 습니다. 가장 간단한 해결 방법은 사용자 주소 공간을 분할하고 각 게이트웨이에 여러 IP 주소를 정적으로 "할당"하는 것입니다. 많은 게이트웨이 장치에서 제공하는 또 다른 대안은 IP 주소 풀을 사용하는 것입니다. 주소 풀의 이점은 사용자 기반이 커질수록 훨씬 더 동적이며 조정이 필요하지 않는다는 것입니다.
  
## <a name="see-also"></a>참고 항목

[Office 365 끝점 관리](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Office 365 끝점 FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
