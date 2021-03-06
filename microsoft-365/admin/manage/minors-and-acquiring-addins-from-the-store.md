---
title: 미성년자 및 스토어에서 추가 기능 다운로드
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 미성년자 개인 데이터를 규제하는 GDPR(일반 데이터 보호 규정) 규정에 대해 자세히 알아보고
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306554"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>미성년자 및 스토어에서 추가 기능 다운로드

GDPR(일반 데이터 보호 규정)은 2018년 5월 25일 시행되는 유럽 연합 규정입니다. 사용자에게 데이터에 대한 권한 및 보호 권한을 제공합니다. GDPR의 측면 중 하나는 미성년자가 부모 또는 보호자가 승인하지 않은 당사자에게 개인 데이터를 전송할 수 없다는 점입니다. 부로 정의된 특정 연령은 개인이 있는 지역에 따라 다를 수 있습니다.
  
부모 동의에 대한 법률 규정이 있는 지역은 미국, 대한민국, 영국 및 유럽 연합입니다. 이러한 지역의 경우 미성년자는(Azure Active Directory를 통해) 스토어에서 새 Office 추가 기능을 다운로드하고 이전에 취득한 추가 기능을 실행하지 못하게 차단됩니다. 법률 규정이 없는 국가의 경우 다운로드 제한이 없습니다.
  
사용자는 Azure Active Directory에 지정된 데이터에 따라 부 사용자로 결정됩니다. 조직 관리자는 법적 연령 그룹 및 해당 사용자의 부모 동의를 선언해야 합니다.
  
부모/보호자가 특정 추가 기능을 사용하는 미성년자에 동의하는 경우 조직 관리자는 중앙 집중식 배포를 사용하여 동의한 모든 미성년자에 해당 추가 기능을 배포할 수 있습니다.
  
미성년자에 대한 GDPR을 준수하려면 다음 Office 빌드 중 하나를 학교/조직에 배포해야 합니다.
 
 **Word, Excel, PowerPoint 및 Project의 경우:** 

|**플랫폼** <br/> |**빌드 번호** <br/> |
|:-----|:-----|
|엔터프라이즈용 Microsoft 365 앱(현재 채널)  <br/> |9001.2138   <br/> |
|엔터프라이즈용 Microsoft 365 앱(반기 엔터프라이즈 채널)  <br/> |8431.2159  <br/> |
|Windows용 Office 2016  <br/> |16.0.4672.1000  <br/> |
|Windows용 Office 2013  <br/> |15.0.5023.1000  <br/> |
|Office 2016 for Mac  <br/> |16.11.18020200  <br/> |
|웹용 Office  <br/> |해당 없음  <br/> |
   
 **Outlook의 경우:** 
  
|**플랫폼** <br/> |**빌드 번호** <br/> |
|:-----|:-----|
|Windows용 Outlook 2016(MSI)  <br/> |TBD 빌드 안  <br/> |
|Windows용 Outlook 2016(C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 for Mac  <br/> |16.0.9318.1000  <br/> |
|iOS용 Outlook 모바일  <br/> |2.75.0  <br/> |
|Android용 Outlook 모바일  <br/> |2.2.145  <br/> |
|outlook.com  <br/> |해당 없음  <br/> |

 **Office 2013 요구 사항**
  
Windows용 Word, Excel 및 PowerPoint 2013에서는 ADAL(Active Directory 인증 라이브러리)이 활성화되어 있는 경우 동일한 부 버전 검사를 지원합니다. 다음에 설명된 규정 준수에 대한 두 가지 옵션이 있습니다.
  
- **ADAL을 사용하도록 설정.** 이 문서에서는 Office 2013용 ADAL을 사용하도록 설정하는 방법: Office 클라이언트에서 Microsoft 365 최신 인증 [사용에 대해 설명합니다.](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)<br/>Windows 장치에서 [Office 2013에](../security-and-compliance/enable-modern-authentication.md)대한 최신 인증 사용에 설명된 따라 ADAL을 사용하도록 레지스트리 키를 설정해야 합니다.<br/>또한 Office 2013에 대한 다음 4월 업데이트를 설치해야 합니다.
    
  - [Office 2013의 보안 업데이트에 대한 설명: 2018년 4월 10일](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [2018년 4월 3일, Office 2013에 대한 업데이트(KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **ADAL을 사용하도록 설정하지 않습니다.** Office 2013에서 ADAL을 사용하도록 설정할 수 없는 경우 그룹 정책을 사용하여 Office 클라이언트에 대한 스토어를 해제하는 것이 좋습니다. Office 설정용 앱을 끄는 방법에 대한 정보는 여기에 [있습니다.](https://technet.microsoft.com/library/cc178992.aspx)

## <a name="related-articles"></a>관련 문서

[관리 센터에서 추가 기능 배포](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[관리 센터에서 추가 기능 관리](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
