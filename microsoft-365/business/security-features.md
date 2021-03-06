---
title: Microsoft 365 Business Premium 보안 및 규정 준수 기능
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-security-compliance
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: PC, 휴대폰 및 태블릿에서 데이터를 보호하기 위해 Microsoft 365 Business Premium과 함께 제공된 보안 기능에 대해 자세히 알아보습니다.
ms.openlocfilehash: b7fdd3d7fa25c23ee49ae82aa037588d8fba61a1
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840392"
---
# <a name="microsoft-365-business-premium-security-and-compliance-features"></a>Microsoft 365 Business Premium 보안 및 규정 준수 기능

Microsoft 365 Business Premium은 PC, 휴대폰 및 태블릿에서 데이터를 보호하는 데 도움이 되는 간소화된 보안 기능을 제공합니다.
    
## <a name="microsoft-365-admin-center-security-features"></a>Microsoft 365 관리 센터 보안 기능

관리 센터에서 많은 Microsoft 365 Business Premium 보안 기능을 관리할 수 있습니다. 이 기능을 켜거나 끄는 간단한 방법을 제공합니다. 관리 센터에서 다음을 할 수 있습니다.
  
- [Android 또는 iOS 디바이스에 대한 애플리케이션 관리 설정 지정](app-protection-settings-for-android-and-ios.md). 
    
    이러한 설정에는 설정된 기간 후에 비활성 장치에서 파일을 삭제하고, 작업 파일을 암호화하고, 사용자가 PIN을 설정하도록 요구하는 등입니다.
    
- [Windows 10 디바이스의 애플리케이션 설정 지정](protection-settings-for-windows-10-devices.md) 
    
    이러한 설정은 회사 소유 디바이스 또는 개인 소유 디바이스의 회사 데이터에 모두 적용할 수 있습니다.
    
- [Windows 10 디바이스의 디바이스 보호 설정 지정](protection-settings-for-windows-10-pcs.md). 
    
    [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) 암호화를 사용하도록 설정하여 디바이스를 분실하거나 도난당한 경우 데이터를 보호하고, [Windows Exploit Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection)를 사용하도록 설정하여 랜섬웨어에 대한 고급 보호 기능을 제공할 수 있습니다. 
    
- [장치에서 회사 데이터 제거](remove-company-data.md)
    
    디바이스를 분실하거나 도난당한 경우 또는 직원이 퇴사하는 경우 회사 데이터를 원격으로 지울 수 있습니다.
    
- [Windows 10 디바이스를 공장 설정으로 다시 설정](reset-devices-to-factory-settings.md). 
    
    디바이스 보호가 설정된 Windows 10 디바이스를 다시 설정할 수 있습니다.
    
## <a name="additional-security-features"></a>추가 보안 기능 

Microsoft 365 Business Premium의 고급 기능을 사용하여 사이버 위협으로부터 비즈니스를 보호하고 중요한 정보를 보호할 수 있습니다.
  
- **[Office 365용 Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)**
    
    Office 365용 Microsoft Defender를 사용하면 직원 또는 고객 정보를 손상하도록 설계된 정교한 피싱 및 랜섬웨어 공격을 방지할 수 있습니다. 기능은 다음과 같습니다.
    
  - 위험한 메시지를 감지하고 삭제하기 위한 정교한 첨부 파일 검색 및 AI 기반 분석
    
  - 전자 메일의 링크를 자동으로 검사하여 피싱 스키마에 포함되는지 평가합니다. 따라서 안전하지 않은 웹 사이트에 안전하게 액세스할 수 있습니다.

- **[Azure Portal의 Intune 전체 기능](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Azure Portal에서 Intune 관리 센터에 액세스하면 Microsoft 365 관리 센터를 통해 사용할 수 없는 Windows용 고급 장치 관리와 함께 MacOS 장치, iPhone 및 Android 장치 관리와 같은 추가 보안 기능을 설정할 수 있습니다.
- **Azure [](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) AD Premium P1 계획과 동일한 조건부 액세스**


    조건부 액세스는 로그인 위험으로부터 조직을 보호하고, 예기치 않은 네트워크 또는 로지에서 액세스 시도, 위험한 장치 유형에서 액세스 시도 등에서 조직을 보호하는 데 도움이 될 수 있습니다. 조건부 액세스 정책은 첫 번째 인증이 완료된 후에 적용하며, 첫 번째 인증 이벤트의 신호를 사용하여 시도된 액세스를 승인, 거부 또는 추가 증명(예: 두 번째 ID 형식)이 필요한지 여부를 판단합니다.

    포함된 조건부 액세스 기능은 다음과 같습니다.

    - 사용자 이름, 그룹 및 역할 기반 액세스
    - 앱 [기반 액세스](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [위치에 따라 액세스합니다.](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration)  신뢰할 수 있는 IP 범위 또는 특정 국가에서만 액세스 허용 
    - 액세스에 MFA 필요
    - 레거시 인증을 사용하는 [앱에 대한 액세스 차단](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication)
    - 앱에서 [Intune 앱 보호를 사용해야 합니다.](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - 타사 공급자를 사용하는 MFA(예: DUO)와 같은 사용자 지정 인증
   
    기타 기능:
    - 하이브리드 Azure [AD에 대한](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization) 셀프 서비스 암호 재설정
    
## <a name="compliance-features"></a>준수 기능

Microsoft 365 Business Premium 구독에는 규정 준수 및 규정 표준을 유지 관리하는 데 도움이 되는 기능이 포함되어 있습니다.

- **[데이터 손실 방지 정책 개요](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)**(DLP) 
    
    회사 외부의 부주의한 공유를 방지하기 위해 신용 카드 번호, 주민등에게서 번호와 같은 중요한 정보를 자동으로 검색하는 DLP를 설정할 수 있습니다.
    
- **[Exchange Online Archiving](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online Archiving 라이선스를 사용하면 연속 데이터 백업을 통해 메시지를 쉽게 보관할 수 있습니다. 나중에 검색 또는 복원에 필요한 경우를 위해 삭제된 항목을 포함하여 사용자의 모든 전자 메일이 저장됩니다. 또한 다양한 보존 정책을 사용하여 소송 보존, eDiscovery에 대한 전자 메일 데이터를 보존하거나 규정 준수 요구 사항을 충족할 수 있습니다.
    
- **[민감도 레이블](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)**

   Microsoft 365 Business Premium에는 [Azure Information Protection 계획 1의 모든 기능이 포함되어 있습니다.](https://go.microsoft.com/fwlink/p/?linkid=871407) 이 계획을 사용하면 "전달하지 말 것" 및 "복사 안 하세요."와 같은 컨트롤을 사용하여 전자 메일 및 문서의 중요한 정보에 대한 액세스를 제어할 수 있는 민감도 레이블을 만들 수 있습니다.  또한 중요한 정보를 "기밀"으로 분류하고 기밀 정보를 비즈니스 내부와 외부에서 공유할 수 있는 방법을 지정할 수 있습니다. 엔터프라이즈급 암호화는 전자 메일 및 문서에 쉽게 적용하여 정보를 비공개로 유지할 수 있습니다. Office 앱용 Azure Information Protection 클라이언트 추가 기능을 설치할 수도 있습니다. 자세한 내용은 Azure Information Protection 통합 [레이블 클라이언트를 참조하세요.](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history) 민감도 레이블의 경우 다음 **AzInfoProtection_UL.exe.**

보안 준수 센터 및 Intune 관리 센터에서 이러한 기능을 &amp; 관리할 수 있습니다. 시간이 지날 때 간소화된 컨트롤이 Microsoft 365 관리 센터에 추가됩니다.
  
    
## <a name="faq"></a>FAQ

 ### <a name="are-these-security-features-available-in-all-markets"></a>이러한 보안 기능을 모든 지역/국가에서 사용할 수 있나요?
  
예. 이러한 기능은 Microsoft 365 Business Premium이 판매되는 모든 시장에서 사용할 수 있습니다.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>보안 및 준수 센터는 어떻게 찾을 수 있나요?
  
1. [관리자 자격 증명을 사용하여 Microsoft 365 Business Premium에](https://portal.microsoft.com/) 로그인합니다. 
    
2. 왼쪽 탐색 창에서 **관리 센터** 를 찾아 확장합니다. 
    
    ![Microsoft 365 관리 센터의 왼쪽 탐색 창에서 관리 센터를 선택합니다.](../media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. **보안 및 준수** 를 선택하여 보안 및 준수 센터로 이동합니다.
