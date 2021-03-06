---
title: Microsoft 365 용 PowerShell을 사용해야 하는 이유
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: '요약: PowerShell을 사용하여 Microsoft 365를 관리해야 하는 이유를 이해합니다. 경우에 따라 더 효율적일 수도 있으며, 필요한 경우도 있습니다.'
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754109"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>Microsoft 365 용 PowerShell을 사용해야 하는 이유

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 관리 센터를 사용하여 Microsoft 365 사용자 계정 및 라이선스를 관리할 수 있습니다. Exchange Online, Teams 및 SharePoint Online과 같은 Microsoft 365 서비스를 관리할 수도 있습니다. 대신 PowerShell을 사용하여 이러한 서비스를 관리하는 경우 명령줄 및 스크립팅 언어 환경을 사용하여 속도, 자동화 및 추가 기능을 활용할 수 있습니다.
  
이 문서에서는 PowerShell을 사용하여 Microsoft 365를 관리하는 방법을 보여 주며,
  
- Microsoft 365 관리 센터에서 볼 수 없는 추가 정보 표시
    
- PowerShell에서만 가능한 기능 및 설정 구성
    
- 대량 작업 수행
    
- 데이터 필터링
    
- 데이터 인쇄 또는 저장
    
- 여러 서비스 관리
    
Microsoft 365용 PowerShell은 Windows 기반 서비스 및 플랫폼을 위한 명령줄 환경인 Windows PowerShell 모듈 집합입니다. 이 환경에서는 추가 모듈을 사용하여 확장할 수 있는 명령 셸 언어를 만듭니다. 간단한 명령이나 복잡한 명령이나 스크립트를 실행할 수 있는 방법을 제공합니다. 예를 들어 Microsoft 365 모듈용 PowerShell을 설치하고 Microsoft 365 구독에 연결한 후 다음 명령을 실행하여 해당 모듈의 모든 사용자 사서함을 Microsoft Exchange Online.
  
```powershell
Get-Mailbox
```

Microsoft 365 관리 센터를 사용하여 사서함 목록을 얻을 수도 있지만 모든 웹앱에 대한 모든 사이트의 모든 목록에서 항목을 계산하는 것은 쉽지 않습니다.
  
Microsoft 365용 PowerShell은 Microsoft 365 관리 센터를 대체하지 말고 Microsoft 365를 관리하는 데 도움이 하도록 디자인됩니다. Microsoft 365 명령에 대해 PowerShell을 통해서만 수행될 수 있는 몇 가지 구성 절차가 있기 때문에 관리자는 Microsoft 365용 PowerShell을 사용할 수 있습니다. 이러한 경우 다음 방법을 알아야 합니다.
  
- Microsoft 365 모듈용 PowerShell을 설치합니다(각 관리자 컴퓨터에 대해 한 번만 수행).
    
- Microsoft 365 구독에 연결합니다(각 PowerShell 세션에 대해 한 번).
    
- Microsoft 365 명령에 필요한 PowerShell을 실행하는 데 필요한 정보를 수집합니다.
    
- Microsoft 365 명령에 대해 PowerShell을 실행합니다.
    
이러한 기본 기술을 학습한 후 **Get-Mailbox** 명령을 사용하여 사서함 사용자를 나열할 수 없습니다. 또한 모든 웹앱에 대한 모든 사이트의 모든 목록에 있는 모든 항목의 개수를 계산하기 위해 이전에 인용한 명령과 같은 새 명령을 만드는 방법을 이해할 수 없습니다. Microsoft와 관리자 커뮤니티는 필요한 경우 이러한 작업을 지원할 수 있습니다.
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a>Microsoft 365용 PowerShell은 Microsoft 365 관리 센터에서 볼 수 없는 정보를 공개할 수 있습니다.

Microsoft 365 관리 센터에는 많은 유용한 정보가 표시됩니다. 그러나 Microsoft 365에서 사용자, 라이선스, 사서함 및 사이트에 대해 저장하는 가능한 모든 정보는 표시되지 않습니다. Microsoft 365  관리 센터의 사용자 및 그룹에 대한 예는 다음과 같습니다.
  
![Microsoft 365 관리 센터의 사용자 및 그룹 표시 예](../media/o365-powershell-users-and-groups.png)
  
이 보기는 많은 경우에 필요한 정보를 제공합니다. 그러나 더 많은 정보가 필요한 경우도 있습니다. 예를 들어 Microsoft 365 라이선싱(및 사용자가 사용할 수 있는 Microsoft 365 기능)은 사용자의 지리적 위치에 따라 부분적으로 의존합니다. 미국에 거주하는 사용자에게 확장할 수 있는 정책 및 기능은 인도나 벨기에의 사용자로 확장할 수 있는 정책과 다를 수 있습니다. Microsoft 365 관리 센터에서 다음 단계에 따라 사용자의 지리적 위치를 확인할 수 있습니다.
  
1. 사용자의 **표시 이름** 을 두 번 클릭합니다.
    
2. 사용자 속성 표시 창에서 세부 **정보를 선택합니다.**
    
3. 세부 정보 표시에서 추가 **세부 정보를 선택합니다.**
    
4. 제목 국가 또는 지역을 찾을 때까지 **스크롤합니다.**
    
     ![Microsoft 365 관리 센터의 사용자에 대한 지역 정보의 예](../media/o365-powershell-usage-location.png)
  
5. 사용자의 표시 이름과 지역을 종이에 적어 두거나 복사한 다음 메모장에 붙여 넣습니다.
    
각 사용자에 대해 이 절차를 반복해야 합니다. 사용자가 많은 경우 이 프로세스는 지저분할 수 있습니다. Microsoft 365용 PowerShell을 사용하면 다음 명령을 사용하여 모든 사용자에 대해 이 정보를 표시할 수 있습니다.
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>PowerShell Core는 이름에 *Msol이* 있는 Windows PowerShell 및 cmdlet용 Microsoft Azure Active Directory 모듈을 지원하지 않습니다. 이러한 cmdlet은 해당 cmdlet에서 실행해야 Windows PowerShell.
>

결과의 예는 다음과 같습니다.
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

이 PowerShell 명령을 해석하면 다음이 있습니다. 현재 Microsoft 365 구독의 모든 사용자를 **다운로드(Get-AzureADUser)하지만** 각 사용자의 이름과 위치만 **표시합니다(DisplayName 선택, UsageLocation** 선택).
  
Microsoft 365용 PowerShell은 명령 셸 언어를 지원하기 때문에 **Get-AzureADUser** 명령으로 얻은 정보를 추가로 조작할 수 있습니다. 예를 들어 이러한 사용자를 위치별로 정렬하여 모든 브라질 사용자, 모든 미국 사용자를 함께 그룹화할 수 있습니다. 명령은 다음과 같습니다.
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

결과의 예는 다음과 같습니다.
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

이 PowerShell 명령을 해석하면: 현재 Microsoft 365 구독의 모든 사용자를 되지만 각 사용자의 이름과 위치만 표시하고 먼저 위치별로 정렬한 다음 **이름(Sort UsageLocation, DisplayName)을** 정렬합니다.
  
추가 필터링을 사용할 수도 있습니다. 예를 들어 브라질 사용자에 대한 정보만 표시하려면 다음 명령을 사용합니다.
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

결과의 예는 다음과 같습니다.
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

이 PowerShell 명령을 해석하면 다음이 있습니다. 현재 Microsoft 365 구독의 모든 사용자를 해당 위치가 **브라질(Where {$ ) 으로 해석합니다. \_ UsageLocation -eq "BR"}**)을 입력한 다음 각 사용자의 이름과 위치를 표시합니다.
  
 **큰 도메인에 대한 참고 사항**
  
사용자가 수만 명인 큰 도메인이 있는 경우 이 문서에 설명된 예제 중 일부를 시도하면 스로틀이 발생할 수 있습니다. 컴퓨팅 전원 및 사용 가능한 네트워크 대역폭과 같은 요인에 따라 한 때 너무 많은 작업을 시도할 수 있습니다. 대규모 조직에서는 이러한 PowerShell 작업 중 일부를 두 개의 명령으로 분할할 수 있습니다.

예를 들어 다음 명령은 모든 사용자 계정을 반환하고 각 계정의 이름과 위치를 보여줄 수 있습니다.
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

소규모 도메인에서는 이 명령을 사용해도 아무런 문제가 없습니다. 그러나 대규모 조직에서는 해당 작업을 두 개의 명령, 즉 사용자 계정 정보를 변수에 저장하는 명령과 필요한 정보를 표시하는 명령으로 분할할 수 있습니다. 예를 들면 다음과 같습니다.
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

이 PowerShell 명령 집합을 해석하는 것은 다음입니다.
1. 현재 Microsoft 365 구독의 모든 사용자를 다운로드하고 정보를 $x($x **= Get-AzureADUser)라는 변수에 저장합니다.**
1.  변수의 내용을 $x 각 사용자의 이름과 위치만 **포함합니다($x | DisplayName, UsageLocation을 선택합니다.**
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>Microsoft 365에는 Microsoft 365용 PowerShell로만 구성할 수 있는 기능이 있습니다.

Microsoft 365 관리 센터는 대부분의 환경에 적용되는 일반적이고 유용한 관리 작업에 액세스할 수 있도록 합니다. 즉, Microsoft 365 관리 센터는 일반적인 관리자가 가장 일반적인 관리 작업을 수행할 수 있도록 디자인된 것입니다. 그러나 관리 센터에서 수행할 수 없는 몇 가지 작업이 있습니다.
  
예를 들어 비즈니스용 Skype Online 관리 센터에서는 사용자 지정 모임 초대를 만들기 위한 몇 가지 옵션을 제공합니다.
  
![비즈니스용 Skype Online 관리 센터에 표시된 사용자 지정 모임 초대 예제입니다.](../media/o365-powershell-meeting-invitation.png)
  
이러한 설정을 사용하여 모임 초대를 전문적으로 개인 설정할 수 있습니다. 그러나 모임 구성 설정에는 단순히 사용자 지정 모임 초대를 만드는 것 이상이 있습니다. 예를 들어 모임에서는 기본적으로 다음과 같은 설정이 가능합니다.
  
- 익명 사용자가 각 모임에 자동으로 입장할 수 있도록 설정
    
- 참석자가 모임을 기록하도록 설정
    
- 조직의 모든 사용자가 모임 참가 시 발표자로 지정되도록 설정
    
이러한 설정은 비즈니스용 Skype Online 관리 센터에서 사용할 수 없습니다. Microsoft 365용 PowerShell에서 제어할 수 있습니다. 다음은 이러한 세 가지 설정을 사용하지 않도록 설정하는 명령입니다.
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> 이 명령을 실행하려면 비즈니스용 [Skype Online PowerShell 모듈을 설치해야 합니다. ](https://www.microsoft.com/download/details.aspx?id=39366)
  
이 PowerShell 명령을 해석하는 것은 다음입니다.
 
1. 새 비즈니스용 Skype Online 모임 **설정(Set-CsMeetingConfiguration)에서** 익명 사용자가 모임에 자동 입장할 수 있도록 허용하지 않도록 **설정(-AdmitAnonymousUsersByDefault $False).**
2.  참석자에 모임을 기록할 수 있는 기능을 사용하지 않도록 **설정(-AllowConferenceRecording $False).**
3. 조직의 모든 사용자를 **발표자(-DesignateAsPresenter "없음")로 지정하지 않습니다.**
  
이러한 기본 설정을 복원하려면(옵션을 사용하도록 설정) 다음 명령을 실행합니다.
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

다른 유사한 시나리오도 있습니다. 따라서 관리자가 Microsoft 365 명령에 대해 PowerShell을 실행하는 방법을 알아야 합니다.
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a>Microsoft 365용 PowerShell은 대량 작업에 매우 잘 사용

Microsoft 365 관리 센터와 같은 시각적 인터페이스는 단일 작업을 할 때 가장 유용한 기능입니다. 예를 들어 사용자 계정 하나를 사용하지 않도록 설정해야 하는 경우 관리 센터를 사용하여 확인란을 빠르게 찾아 선택을 취소할 수 있습니다. 이 작업은 PowerShell에서 유사한 작업을 수행하는 것보다 더 쉬워집니다.
  
그러나 대규모 작업 내에서 많은 것 또는 일부 선택된 것을 변경해야 하는 경우 Microsoft 365 관리 센터가 최상의 도구가 아 않을 수 있습니다. 예를 들어 수천 개의 전화 번호에 대한 prefix를 변경하거나 모든 SharePoint Online 사이트에서 특정 사용자 *Ken Myer를* 제거해야 합니다. Microsoft 365 관리 센터에서는 어떻게 해야 합니까?
  
마지막 예제에서는 SharePoint Online 사이트가 수백 개 있으며 Ken Meyer가 구성원으로 있는 사이트를 모르는 경우를 예로 들 수 있습니다. Microsoft 365 관리 센터에서 시작한 다음 각 사이트에 대해 다음 절차를 수행해야 합니다.
  
1. 사이트의 **URL을** 선택합니다.
    
2. 사이트 **모음 속성 상자에서** 사이트를 **열 웹** 사이트 주소 링크를 선택합니다.
    
3. 사이트에서 공유를 **선택합니다.**
    
4. 공유 **대화** 상자에서 사이트에 대한 사용 권한이 있는 모든 사용자를 표시하는 링크를 선택합니다.
    
     ![SharePoint Online 관리 센터에서 SharePoint Online 사이트의 구성원을 보는 예제입니다.](../media/o365-powershell-view-permissions.png)
  
5. 공유 대상 **대화** 상자에서 고급을 **선택합니다.**
    
6. 사용자 목록을 아래로 스크롤하여 Ken Myer를 찾아 선택한 다음(사이트에 대한 사용 권한이 있는 경우) 사용자 권한 **제거를 선택합니다.**
    
수백 개의 *사이트에는* 시간이 오래 걸릴 수 있습니다.
  
또는 Microsoft 365용 PowerShell에서 다음 명령을 실행하여 모든 사이트에서 Ken Myer를 제거하는 것입니다.
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> 이 명령을 사용하려면 [SharePoint Online PowerShell 모듈을 설치해야 합니다.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) 
  
이 PowerShell 명령을 해석하면: 현재 Microsoft 365 **구독(Get-SPOSite)의** 모든 SharePoint 사이트를 다운로드하고 각 사이트에 대해 액세스할 수 있는 사용자 목록에서 Ken **Meyer를 제거합니다(ForEach {Remove-SPOUser -Site $ \_ ). Url -LoginName "kenmyer \@ litwareinc.com"}**).
  
Microsoft 365에 액세스 권한이 없는 사이트를 포함하여 모든 사이트에서 Ken Meyer를 제거합니다. 따라서 결과에는 액세스 권한이 없는 사이트에 대한 오류가 표시됩니다. 이 명령에서 추가 조건을 사용하여 로그인 목록에 Ken Meyer가 있는 사이트에서만 Ken Meyer를 제거할 수 있습니다. 그러나 반환되는 오류는 사이트 자체에 해를 입히지 않습니다. 이 명령은 Microsoft 365 관리 센터를 통해 작업하는 시간이 아니라 수백 개의 사이트에 대해 실행하는 데 몇 분 정도 걸릴 수 있습니다.
  
다음은 다른 대량 작업 예제입니다. 다음 명령을 사용하여 새 SharePoint 관리자인 *Bonnie Kearney를* 조직의 모든 사이트에 추가합니다.
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

이 PowerShell 명령을 해석하면: 현재 Microsoft 365 구독의 모든 SharePoint 사이트를 다운로드하고 각 사이트에 대해 사이트의 구성원 그룹에 로그인 이름을 추가하여 Bonnie Kearney 액세스를 **허용합니다(ForEach {Add-SPOUser -Site $ \_ ). Url -LoginName "bkearney \@ litwareinc.com" -Group "Members"}**).
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>Microsoft 365용 PowerShell은 데이터를 필터링하는 데 매우 능동적입니다.

Microsoft 365 관리 센터에서는 데이터를 필터링하여 대상 정보 하위 집합을 쉽게 찾을 수 있는 여러 가지 방법을 제공합니다. 예를 들어 Exchange에서는 사용자 사서함의 사실상 모든 속성을 기준으로 쉽게 필터링을 할 수 있습니다. 예를 들어 Bloomington에 거주하는 모든 사용자의 사서함 목록은 다음과 같습니다.
  
![Microsoft 365 관리 센터에서 Bloomington에 거주하는 모든 사용자의 사서함 목록에 대한 고급 검색을 수행한 예입니다.](../media/o365-powershell-advanced-search.png)
  
Exchange 관리 센터에서도 필터 기준을 조합할 수 있습니다. 예를 들어 Bloomington에 거주하고 Finance 부서에서 일하는 모든 사용자에 대한 사서함을 찾을 수 있습니다.
  
그러나 Exchange 관리 센터에서 할 수 있는 작업을 제한할 수 있습니다. 예를 들어 Bloomington이나 San Diego에 거주하는 사용자 사서함이나  Bloomington에 거주하지 않는 모든 사용자에 대한 사서함을 쉽게 찾을 수 없습니다.
  
다음 Microsoft 365용 PowerShell 명령을 사용하여 Bloomington 또는 San Diego에 거주하는 모든 사용자에 대한 사서함 목록을 얻을 수 있습니다.
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

결과의 예는 다음과 같습니다.
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

이 PowerShell 명령을 해석하면 다음이 적용됩니다. San Diego 또는 Bloomington(Where **{$ . \_ RecipientTypeDetails -eq "UserMailbox" -and ($ \_ . City -eq "San Diego" -or $ \_ . City -eq "Bloomington")}** 을 입력한 다음 각 구/시의 이름과 구/시(Select **DisplayName, City)를 표시합니다.**
  
Bloomington을 제외한 모든 곳에 거주하는 사람에 대한 모든 사서함을 나열하는 명령은 다음과 같습니다.
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

결과의 예는 다음과 같습니다.
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

이 PowerShell 명령을 해석하면 다음이 적용됩니다. Bloomington에 사서함이 없는 현재 Microsoft 365 구독의 모든 **사용자(Where {$ \_ ). RecipientTypeDetails -eq "UserMailbox" -and $ \_ . City -ne "Bloomington"}**) 각 구/시의 이름과 구/시를 표시합니다.
  
### <a name="use-wildcards"></a>와일드카드 사용

PowerShell 필터에서 와일드카드 문자를 사용하여 이름의 일부와 일치할 수도 있습니다. 예를 들어 사용자 계정을 찾고 있는 경우를 가정해 보겠습니다. 사용자의 성은 *Anderson* 또는 *Henderson* 또는 *Jorgenson입니다.*
  
검색 도구를 사용하고 세 가지 다른 검색을 수행하여 Microsoft 365 관리 센터에서 해당 사용자를 추적할 수 있습니다.
  
- *Anderson*  에 대해, 
    
- *Henderson*  에 대해, 
    
- *Jorgenson*  에 대해 
    
이 세 이름은 모두 "son"으로 끝나기 때문에 PowerShell에 이름이 "son"으로 끝나는 모든 사용자를 표시하게 할 수 있습니다. 명령은 다음과 같습니다.
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

이 PowerShell 명령을 해석하면: 현재 Microsoft 365 구독의 모든 사용자를 되지만 성으로 끝나는 사용자만 나열하는 필터를 **사용하세요(-Filter '{LastName -like " \* son"}'**). 이 문자는 모든 문자 집합을 대칭합니다. 이 문자는 사용자의 \* 성에 있는 문자입니다.
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>Microsoft 365용 PowerShell을 사용하면 데이터를 쉽게 인쇄하거나 저장할 수 있습니다.

Microsoft 365 관리 센터에서는 데이터 목록을 볼 수 있습니다. 비즈니스용 Skype Online에 대해 사용하도록 설정된 사용자 목록을 표시하는 비즈니스용 Skype Online 관리 센터의 예는 다음과 같습니다.
  
![비즈니스용 Skype Online을 사용하도록 설정된 사용자 목록을 표시하는 비즈니스용 Skype Online 관리 센터 예제입니다.](../media/o365-powershell-lync-users.png)
  
이 정보를 파일에 저장하려면 문서나 Microsoft Excel 워크시트에 붙여 넣아야 합니다. 두 경우 모두 추가 서식이 필요할 수 있습니다. 또한 Microsoft 365 관리 센터에서는 표시된 목록을 직접 인쇄할 수 있는 방법을 제공하지 않습니다.
  
다행히 PowerShell을 사용하여 목록을 표시할 뿐만 아니라 Excel로 쉽게 가져올 수 있는 파일에 저장할 수도 있습니다. 다음은 비즈니스용 Skype Online 사용자 데이터를 콤보로 구분된 값(CSV) 파일에 저장하는 예제 명령으로, Excel 워크시트의 표로 쉽게 가져올 수 있습니다.
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

결과의 예는 다음과 같습니다.
  
![콤보로 구분된 값 파일에 저장된 비즈니스용 Skype Online 사용자 데이터에 대한 Excel 워크시트로 가져온 테이블의 예입니다.](../media/o365-powershell-data-in-excel.png)
  
이 PowerShell 명령을 해석하면 다음을 실행합니다. 현재 Microsoft 365 구독의 모든 비즈니스용 Skype Online 사용자 **다운로드(Get-CsOnlineUser**); 사용자 이름, UPN 및 **위치(Select DisplayName, UserPrincipalName, UsageLocation**); 그런 다음 C: \\ Logs \\ **SfBUsers.csv(Export-Csv -Path "C: \\ Logs \\SfBUsers.csv" -NoTypeInformation)라는** CSV 파일에 해당 정보를 저장합니다.
  
옵션을 사용하여 이 목록을 XML 파일 또는 HTML 페이지로 저장할 수도 있습니다. 실제로 추가 PowerShell 명령을 사용하면 원하는 사용자 지정 서식을 사용하여 Excel 파일로 직접 저장할 수 있습니다.
  
Windows의 기본 프린터에 직접 목록을 표시하는 PowerShell 명령의 출력을 보낼 수도 있습니다. 명령의 예는 다음과 같습니다.
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

인쇄된 문서의 모양은 다음과 같습니다.
  
![PowerShell 명령의 출력이 Windows의 기본 프린터로 직접 전송된 인쇄 문서의 예입니다.](../media/o365-powershell-printed-data.png)
  
이 PowerShell 명령을 해석하면 다음을 실행합니다. 현재 Microsoft 365 구독의 모든 비즈니스용 Skype Online 사용자를 다운로드합니다. 사용자 이름, UPN 및 위치만 얻습니다. 그런 다음 기본 Windows 프린터(Out-Printer)로 해당 **정보를 전송합니다.**
  
인쇄된 문서의 서식은 PowerShell 명령 창의 표시 서식과 동일합니다. 하드 카피를 얻기 위해 해당 복사본을 **추가하기만 | 명령 끝에서** 프린터로 나타났습니다.
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>Microsoft 365용 PowerShell을 사용하여 여러 서버 제품을 관리할 수 있습니다.

Microsoft 365를 구성하는 구성 요소는 함께 작동하도록 디자인되었습니다. 예를 들어 Microsoft 365에 새 사용자를 추가하고 사용자의 부서 및 전화 번호와 같은 정보를 지정하는 경우를 가정해 보겠습니다. 이 정보는 비즈니스용 Skype Online, Exchange 또는 SharePoint와 같은 Microsoft 365 서비스에서 사용자 정보에 액세스하는 경우 사용할 수 있습니다.
  
그러나 이러한 방식은 제품군 전체에 적용되는 일반적인 정보에만 해당됩니다. 사용자의 Exchange 사서함에 대한 정보와 같은 제품별 정보는 일반적으로 제품군 전체에서 사용할 수 없습니다. 예를 들어 사용자의 사서함을 사용할 수 있는지 여부에 대한 정보는 Exchange 관리 센터에서만 사용할 수 있습니다.
  
모든 사용자에 대해 다음 정보를 표시하는 보고서를 만들려는 경우를 가정해 보겠습니다.
  
- 사용자의 표시 이름
    
- 사용자에게 Microsoft 365 라이선스가 있는지 여부
    
- 사용자의 Exchange 사서함이 사용하도록 설정되었는지 여부
    
- 사용자가 비즈니스용 Skype 온라인을 사용할 수 있도록 설정되었는지 여부
    
Microsoft 365 관리 센터에서는 이러한 보고서를 쉽게 만들 수 없습니다. 대신 Excel 워크시트와 같은 정보를 저장할 별도의 문서를 만들어야 합니다. 그런 다음 Microsoft 365 관리 센터에서 모든 사용자 이름 및 라이선스 정보를 다운로드하고, Exchange 관리 센터에서 사서함 정보를 다운로드하고, 비즈니스용 Skype Online 관리 센터에서 비즈니스용 Skype Online 정보를 확인한 다음 해당 정보를 결합합니다.
  
대신 PowerShell 스크립트를 사용하여 보고서를 컴파일할 수 있습니다.
  
다음 예제 스크립트는 이 문서에서 지금까지 설명한 명령보다 더 복잡합니다. 그러나 PowerShell을 사용하여 다른 보기를 만들기 어려운 정보 보기를 만들 수 있는 가능성을 보여 주게 됩니다. 다음은 필요한 목록을 컴파일하고 표시하는 스크립트입니다.
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

결과의 예는 다음과 같습니다.
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

이 PowerShell 스크립트를 해석하는 것은 다음입니다.  

1. 현재 Microsoft 365 구독의 모든 사용자를 다운로드하고 정보를 $x($x  **= Get-AzureADUser)라는 변수에 저장합니다.**
1. 변수의 모든 사용자에 대해 실행되는 루프를 **$x(foreach($i)$x).**  
1. 이름이 $y  변수를 정의하고 사용자의 사서함 정보를 해당 변수에 저장합니다(**$y = Get-Mailbox -Identity $i.UserPrincipalName).**
1. *IsMailBoxEnabled라는* 사용자 정보에 새 속성을 추가합니다. 사용자 사서함의 IsMailBoxEnabled 속성 **값($i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled)으로** 설정하십시오.
1. $y 변수를 정의하고 사용자의 비즈니스용 Skype Online 정보를 저장합니다($y **= Get-CsOnlineUser -Identity $i.UserPrincipalName).**
1. *EnabledForSfB라는* 사용자 정보에 새 속성을 추가합니다. 사용자의 비즈니스용 Skype Online **정보($i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled)의** Enabled 속성 값으로 설정합니다.
1. 사용자 목록을 표시하지만 이름, 사용이 허가 여부, 사서함을 사용할 수 있는지 여부와 비즈니스용 Skype Online을 사용할 수 있는지 여부를 나타내는 두 가지 새 속성만 포함합니다($x |**DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB를 선택합니다.**
  
## <a name="see-also"></a>참고 항목

[Microsoft 365용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Microsoft 365에서 Windows PowerShell을 사용하여 보고서 만들기](use-windows-powershell-to-create-reports-in-microsoft-365.md)
