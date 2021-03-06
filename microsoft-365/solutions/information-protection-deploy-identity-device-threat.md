---
title: 데이터 개인 정보 보호 규정에 ID, 장치 및 위협 방지 사용
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
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Microsoft 365의 ID, 장치 및 위협 방지 서비스를 사용하여 개인 데이터 위반을 방지합니다.
ms.openlocfilehash: 321b60efbdabe62b14502df4a16dd2dcec4b9cef
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847181"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>데이터 개인 정보 보호 규정에 ID, 장치 및 위협 방지 사용

Microsoft 365는 조직이 데이터 개인 정보 관련 규정 준수 규정 준수를 위해 사용할 수 있는 다양한 ID, 장치 및 위협 방지 기능을 제공합니다. 이 문서에서는 이러한 영역에 필요한 데이터 개인 정보 규정에 대해 설명하고 구현 요구 사항을 충족하는 데 도움이 되는 추가 정보 링크와 관련된 Microsoft 365 기능 및 서비스의 목록을 제공합니다.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>ID, 장치 및 위협 방지와 데이터 개인 정보 보호 규정의 관계

데이터 개인 정보 규정은 특정성에 따라 다르지만, 이러한 규정의 본질은 다음을 규정하는 GDPR의 제5조(1)(f)에 구체화되어 있습니다. 

- 개인 데이터는 적절한 기술 또는 조직적 조치('무결성 및 기밀성')를 사용하여 무단 또는 불법 처리 및 우발적인 손실, 파기 또는 손상으로부터 보호를 포함하여 개인 데이터의 적절한 보안을 보장하는 방식으로 처리되어야 합니다.

개인 데이터 침해는 관리 또는 최종 사용자 계정 손상 및 악의적인 시스템 액세스로 인해 자주 발생하기 때문에 예를 들어 관리자 계정 해킹으로 인해 고객 신용 카드 번호 또는 기타 개인 정보가 유출될 수 있습니다. Microsoft 365에서 일반적으로 사용할 수 있는 모든 ID, 장치 및 위협 방지를 구현해야 합니다. 이는 준수 관리자에 있는 준수 점수에 반영됩니다.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>평가 작업 및 준수 관리자의 결과 사용

준수 관리자에는 다음 범주를 사용하는 ID, 장치 및 위협 방지가 포함됩니다.

- ID가 컨트롤 액세스 **범주에 해당합니다.**
- 디바이스 관리 **범주에 해당합니다.**
- 위협 방지는 위협으로부터 보호 **범주에 해당합니다.**
 
4개의 주요 데이터 개인 정보 보호 규정 샘플 집합에서 이러한 규정을 선택한 경우 준수 관리자는 90개의 개선 작업을 지정합니다. 이 중 대부분은 "27"으로 점수가 지정됩니다. 이러한 범주에 대해 준수 관리자가 이러한 많은 수를 호출하기 때문에 참조를 위해 몇 가지 일반적인 범주가 여기에 나열됩니다.

ID 및 제어 [액세스 범주에 Azure AD(Azure Active Directory)를](https://azure.microsoft.com/services/active-directory/) 사용하여 다음을 할 수 있습니다. 

- 재생 방지 인증 구현("중간에 있는 사람" 공격을 방지)
- 레거시 인증을 차단합니다.
- 사용자 위험 및 사용자 로그인 위험 정책을 구성합니다.
- 관리자 및 비 관리자에 대해 조건부 액세스 및 MFA(다단계 인증)를 사용하도록 설정할 수 있습니다.
- 암호 정책을 구성하고 적용합니다.
- Azure AD Privileged Identity Management를 사용하여 권한 있는 계정에 대한 액세스를 제한합니다.
- 종료 시 액세스를 사용하지 않도록 설정
- 사용자 계정 및 상태 변경 감사
- 역할 그룹 및 관리 변경 내용을 검토합니다.

장치 및 장치 관리 범주에 [대해 Microsoft Endpoint Manager를](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) 사용하여 다음을 할 수 있습니다. 

- 끊어지고 루팅된 모바일 장치를 차단합니다.
- 모바일 장치 관리를 위해 Intune을 구성합니다.
- Android, iOS, macOS 및 Windows 장치에 대한 준수 정책을 만들 수 있습니다.
- Android, iOS, macOS 및 Windows 장치에 대한 장치 구성 프로필을 생성합니다.
- iOS 및 Windows에 대한 앱 보호 정책을 만들 수 있습니다.
- 잠금 화면으로 정보를 은신합니다.
- 모바일 장치에 대한 암호 정책을 구현합니다.
- 모바일 장치가 비활성에 잠겨야 합니다.
- 모바일 장치가 여러 로그인 실패 시 지워야 합니다.

위협으로부터 보호 범주에 Exchange Online Protection 및  [Microsoft Defender for Office 365를](../security/office-365-security/office-365-atp.md) 사용하여 다음을 할 수 있습니다.

- 보낸 사람 인증(SPF, DMARC 및 DKIM)을 사용하도록 설정
- Office 365 피싱 방지 정책을 위한 Microsoft Defender를 설치합니다.
- 안전한 첨부 파일을 구현합니다.
- 안전한 링크를 구현합니다.
- 맬웨어 검색 및 응답 정책을 구현합니다.
- 아웃바운드 및 인바운드 스팸 정책을 구현합니다.

### <a name="references"></a>참조:

- [일반 ID 및 장치 액세스 정책](../security/office-365-security/identity-access-policies.md)
- [Office 365의 위협으로부터 보호](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [안전한 첨부 파일](../security/office-365-security/atp-safe-attachments.md)
- [안전한 링크](../security/office-365-security/atp-safe-links.md)
- [안전한 문서](../security/office-365-security/safe-docs.md)
