---
title: 추가 기능의 중앙 집중식 배포가 조직에 적합한지 확인
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: 중앙 집중식 배포를 사용하여 Office 추가 기능을 배포할 수 있도록 테넌트와 사용자가 요구 사항을 충족하는지 확인합니다.
ms.openlocfilehash: 04c5f9090ca788f00f2d17d3af59e8022195e9be
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519368"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>추가 기능의 중앙 집중식 배포가 조직에 적합한지 확인

중앙 집중식 배포는 대부분의 고객이 조직 내의 사용자 및 그룹에 Office 추가 기능을 배포하는 데 권장되는 가장 다양한 기능입니다. 관리자인 경우 이 지침을 사용하여 조직 및 사용자가 중앙 집중식 배포를 사용할 수 있도록 요구 사항을 충족하는지 확인합니다.

중앙 집중식 배포는 다음과 같은 이점을 제공합니다.
  
- 전역 관리자는 추가 기능을 사용자, 그룹을 통해 여러 사용자 또는 조직의 모든 사용자에게 직접 할당할 수 있습니다.
    
- 관련 Office 응용 프로그램이 시작되면 추가 기능에서 자동으로 다운로드됩니다. 추가 기능에서 추가 기능 명령을 지원하는 경우 Office 응용 프로그램 내의 리본 메뉴에 추가 기능도 자동으로 나타납니다.
    
- 관리자가 추가 기능을 해제하거나 삭제하거나 사용자가 Azure Active Directory 또는 추가 기능을 할당된 그룹에서 제거한 경우 더 이상 추가 기능을 사용자에게 나타나지 않습니다.

중앙 집중식 배포는 세 가지 데스크톱 플랫폼 Windows, Mac 및 Online Office 앱을 지원합니다. 중앙 집중식 배포는 iOS 및 Android도 지원됩니다(Outlook 모바일 추가 기능만 해당).

추가 기능을 모든 사용자의 클라이언트에 표시하는 데 최대 24시간이 걸릴 수 있습니다.
  
## <a name="requirements"></a>요구 사항

추가 기능을 중앙 집중식으로 배포하려면 사용자가 Microsoft 365 Enterprise SKUS( E3/E5/F3 또는 Business SKUS: Business Basic, Business Standard, Business Premium 및 조직 ID를 사용하여 Office에 로그인)를 사용하고 Exchange Online 및 활성 Exchange Online 사서함을 사용해야 합니다. 구독 디렉터리가 Azure Active Directory에 들어 있어야 합니다.
아래에서 Office 및 Exchange에 대한 특정 요구 사항을 보거나 중앙 집중식 배포 호환성 [검사를 사용할 수 있습니다.](#centralized-deployment-compatibility-checker)

중앙 집중식 배포는 다음을 지원하지 않습니다.
  
- Office 2013에서 Word, Excel 또는 PowerPoint를 대상으로 하는 추가 기능 
- 온-프레미스 디렉터리 서비스
- Exchange On-Prem 사서함에 대한 추가 기능 배포
- SharePoint에 대한 추가 기능 배포  
- Teams 앱
- COM(구성 요소 개체 모델) 또는 VSTO(Visual Studio 도구) 추가 기능 배포.
- SKUS와 같은 Exchange Online을 포함하지 않는 Microsoft 365 배포: 비즈니스용 Microsoft 365 앱 및 엔터프라이즈용 Microsoft 365 앱.

### <a name="office-requirements"></a>Office 요구 사항

- Word, Excel 및 PowerPoint 추가 기능의 경우 사용자가 다음 중 하나를 사용하고 있어야 합니다.
  - Windows 디바이스, Microsoft 365 Enterprise SKUS 버전 1704 이상: E3/E5/F3 또는 Business SKUS: Business Basic, Business Standard, Business Premium
  - Mac 버전 15.34 이상

- Outlook의 경우 사용자가 다음 중 하나를 사용하고 있어야 합니다. 
  - Microsoft 365 Enterprise SKUS 버전 1701 이상: E3/E5/F3 또는 Business SKUS: Business Basic, Business Standard, Business Premium
  - 2019 또는 Office Standard 2019 Office Professional Plus 버전 1808 이상
  - 버전 16.0.4494.1000 이상 Office Professional Plus 2016(MSI) 또는 Office Standard 2016(MSI)\*
  - 버전 15.0.4937.1000 이상 Office Professional Plus 2013(MSI) 또는 Office Standard 2013(MSI)\*
  - Mac용 Office 2016 버전 16.0.9318.1000 이상 
- iOS용 Outlook 모바일 버전 2.75.0 이상 
- Android용 Outlook 모바일 버전 2.2.145 이상 
    
    *MSI 버전의 Outlook에는 "내 추가 기능" 섹션이 아니라 적절한 Outlook 리본에 관리자가 설치한 추가 기능을 볼 수 있습니다.

### <a name="exchange-online-requirements"></a>Exchange Online 요구 사항

Microsoft Exchange는 조직 테넌트 내의 매니페스트에 추가 기능을 저장합니다. 추가 기능을 배포하는 관리자와 해당 추가 기능을 받는 사용자는 OAuth 인증을 지원하는 Exchange Online 버전에 있어야 합니다.
  
조직의 Exchange 관리자에게 문의하여 사용 중인 구성을 확인합니다. 사용자당 OAuth 연결은 [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet을 사용하여 확인할 수 있습니다. 


### <a name="centralized-deployment-compatibility-checker"></a>중앙 집중식 배포 호환성 검사

중앙 집중식 배포 호환성 검사를 사용하여 테넌트의 사용자가 Word, Excel 및 PowerPoint에 대해 중앙 집중식 배포를 사용할 수 있도록 설정되어 있는지 확인할 수 있습니다. Outlook 지원에는 호환성 검사가 필요하지 않습니다. [여기](https://aka.ms/officeaddindeploymentorgcompatibilitychecker)에서 호환성 검사를 다운로드하세요.
  
#### <a name="run-the-compatibility-checker"></a>호환성 검사 실행
  
1. 승격된 창을 PowerShell.exe 합니다.
    
2. 다음 명령을 실행합니다.

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. **Invoke-CompatabilityCheck 명령을 실행합니다.**

   ```powershell
   Invoke-CompatibilityCheck
   ```
   이 명령은  *_TenantDomain(예:_* *TailspinToysIncorporated.onmicrosoft)을 묻는 메시지를 제공합니다. </span> com)* 및  *_TenantAdmin_* 자격 증명(전역 관리자 자격 증명 사용)에 동의를 요청합니다.
    
   > [!NOTE]
   > 테넌트의 사용자 수에 따라 검사를 완료하는 데 몇 분 또는 몇 시간이 걸릴 수 있습니다. 
  
도구 실행이 완료되면 쉼표로 구분된(.csv) 형식으로 출력 파일이 생성됩니다. 파일은 기본적으로 **C:\windows\system32에** 저장됩니다. 출력 파일에는 다음 정보가 포함되어 있습니다.
  
- 사용자 이름
    
- 사용자 ID(사용자의 전자 메일 주소)
    
- 중앙 집중식 배포 준비 - 나머지 항목이 충족된 경우
    
- Office 요금제 - 사용이 허가된 Office 계획
    
- 활성화된 Office - Office를 활성화한 경우
    
- 지원되는 사서함 - OAuth 지원 사서함을 사용 중인 경우

> [!NOTE]
> 다단계 인증은 중앙 배포 PowerShell 모듈을 사용할 때 지원되지 않습니다.
  
## <a name="user-and-group-assignments"></a>사용자 및 그룹 할당

중앙 집중식 배포 기능은 현재 Microsoft 365 그룹, 메일 그룹 및 보안 그룹을 포함하여 Azure Active Directory에서 지원하는 대부분의 그룹을 지원합니다.
  
> [!NOTE]
> 비 메일 사용 가능 보안 그룹은 현재 지원되지 않습니다. 
  
중앙 집중식 배포는 테넌트의 개별 사용자, 그룹 및 모든 사용자에게 할당을 지원합니다. 중앙 집중식 배포는 최상위 그룹 또는 부모 그룹이 없는 그룹의 사용자를 지원하지만, 중첩된 그룹 또는 부모 그룹이 있는 그룹의 사용자는 지원하지 않습니다.
   
지민, 서연 및 영업부 그룹이 추가 기능에 할당된 다음 예제를 살펴봅니다. 서해안 영업부는 중첩된 그룹이므로 현준 및 배식은 추가 기능에 할당되지 않습니다.
  
![영업 부서 다이어그램](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>그룹이 중첩된 그룹을 포함하는지 확인

그룹이 중첩된 그룹을 포함하는지를 검색하는 가장 쉬운 방법은 Outlook 내에서 그룹 연락처 카드를 확인하는 것입니다. 전자 메일의 To 필드에 그룹 이름을 입력한 다음 그룹 이름을 확인하면 그룹 이름이 사용자 또는 중첩된 그룹이 포함되어 있는 경우 표시됩니다.  아래 예에서 테스트 그룹에 대한 Outlook 연락처 카드의 **구성원** 탭에는 사용자는 표시되지 않고 하위 그룹 두 개만 표시됩니다. 
  
![Outlook 연락처 카드의 구성원 탭](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
그룹이 어떤 그룹의 구성원인지 확인하기 위해 그룹을 확인하여 반대 쿼리를 수행할 수 있습니다. 아래 예에서 하위 그룹 1이 테스트 그룹의 구성원인 Outlook 연락처 카드의 **구성원 자격** 탭 아래에서 확인할 수 있습니다. 
  
![Outlook 연락처 카드의 구성원 자격 탭](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
또는 Azure Active Directory Graph API를 사용하여 그룹 내의 그룹 목록을 찾기 위한 쿼리를 실행할 수 있습니다. 자세한 내용은 [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342)(그룹에 대한 작업 | Graph API 참조)를 참조하세요.
  
### <a name="contacting-microsoft-for-support"></a>Microsoft에 지원 요청

중앙에서 배포된 웹용 Office 앱(Word, Excel 등)을 사용하는 동안 추가 기능을 로드하는 데 문제가 발생하는 경우 Microsoft 지원에 문의해야 할 수 있습니다(방법[학습).](../contact-support-for-business-products.md) 지원 티켓의 Microsoft 365 환경에 대한 다음 정보를 제공합니다.
  
|**플랫폼**|**디버그 정보**|
|:-----|:-----|
|사무실  <br/> | Charles/Fiddler 로그  <br/>  테넌트 ID( [방법 알아보기](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))  <br/>  CorrelationID. 사무실 페이지 중 하나의 원본을 보고 상관 관계 ID 값을 찾아서 다음을 지원하기 위해 전송합니다.  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|리치 클라이언트(Windows, Mac)  <br/> | Charles/Fiddler 로그  <br/>  클라이언트 앱의 빌드 번호(파일/계정의 스크린샷으로 **가급적)**  <br/> |
   
