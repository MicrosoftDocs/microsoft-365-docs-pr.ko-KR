---
title: Office 365 GCC High 및 DoD에 대한 추가 네트워크 보안 요구 사항
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: '요약: Office 365 GCC High 및 DoD에 추가 네트워크 보안 요구 사항이 있습니다.'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692579"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Office 365 GCC High 및 DOD에 대한 추가 네트워크 보안 요구 사항

*이 문서는 Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High 및 Microsoft 365 DOD에 적용됩니다.*

Office 365 GCC High 및 DOD는 미국 정부 및 해당 공급자 및 계약자 요구를 충족하는 안전한 클라우드 환경입니다.  이러한 클라우드 환경에는 서비스가 액세스할 수 있는 외부 끝점에 대한 추가 네트워크 제한이 있습니다.

페더러티 ID 또는 하이브리드 동시 사용을 계획하는 GCC High 및 DOD 고객은 Microsoft가 기존온-프레미스 배포에 대한 인바운드 및/또는 아웃바운드 액세스를 허용해야 할 수 있습니다.  이러한 활동의 예는 다음과 같습니다.

* 페더링 ID 사용(Active Directory Federation Services 또는 유사한 지원 STS 사용)
* 비즈니스용 Skype 배포 또는 Exchange Server 하이브리드 공존성
* On-premises 시스템에서 기존 사용자 콘텐츠 마이그레이션

서비스가 Office 365 끝점과 통신할 수  있도록 허용하려면 네트워크 변경을 위해 Office 365 엔지니어링으로 전자 메일을 보내야 합니다.

> [!WARNING]
> 모든 요청은 **3주** SLA를 가지며 필요한 보안 및 준수 제어 및 배포 파이프라인으로 인해 처리될 수 없습니다.  여기에는 초기 온보더링 네트워크 요청과 서비스로 마이그레이션한 후의 변경 내용이 포함됩니다.  네트워크 팀이 이 타임라인을 인식하고 계획 주기에 포함하세요.

다음 정보가 있는 전자 메일을 [Office 365 Government Network 화이트리스트로](mailto:o365gwlt@microsoft.com) 보내 주세요.

* **To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)
* **보낸** 사람 : 테넌트 관리자 - 전자 메일 **보내기가** 테넌트의 전역 관리자 연락처와 일치해야 합니다.
* **전자 메일 제목:** Office 365 GCC High Network Request - contoso.onmicrosoft.us(테넌트 이름으로 바꾸기)

메시지 본문에는 다음 데이터가 포함되어야 합니다.

* 사용자 Microsoft Online Services 이름(예: contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* Microsoft가 네트워크 변경 및/또는 잘못된 서브넷에 대한 후속 조치를 위해 통신할 전자 메일 메일 목록
* Microsoft Teams 하이브리드 공동 사용을 계획할지 여부를 지정합니다.
* CIDR 상의 외부에서 액세스할 수 있는 URL(예: sts.contoso.com) 및 IP 주소 범위(예: 10.1.1.0/28)
* CIDR 표시의 On-Premises PKI 인증서 해지 목록 URL 및 IP 주소 범위
* CIDR로 Exchange Server 배포를 위한 외부에서 액세스할 수 있는 URL 및 IP 주소 범위
* CIDR(비즈니스용 Skype) On-premises 배포를 위한 외부에서 액세스할 수 있는 URL 및 IP 주소 범위

보안 및 규정 준수를 위해 요청에 대한 다음 제한 사항을 염두에 두어 주세요.

* 테넌트당 네 개의 서브넷 제한이 있습니다.
* 서브넷은 CIDR Notation(예: 10.1.1.0/28)에 있어야 합니다.
* 서브넷 범위는 서브넷 범위보다 클 수 /24
* 상업용 클라우드 **서비스(상업용** Office 365, Google G-Suite, Amazon Web Services 등)에 대한 액세스를 허용하는 요청을 수용할 수 없습니다.

Microsoft에서 요청을 수신하고 승인하면 구현을 위한 3주 SLA가 있으며, 이 SLA는 처리되지 않습니다.  요청이 수신되고 완료된 후 최종 확인이 완료되면 초기 인정을 받게 됩니다.
