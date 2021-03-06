---
title: PowerShell을 사용하여 Microsoft 365 사용자 계정 속성 구성
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Microsoft 365용 PowerShell을 사용하여 Microsoft 365 테넌트에서 개별 또는 여러 사용자 계정의 속성을 구성합니다.
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754331"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>PowerShell을 사용하여 Microsoft 365 사용자 계정 속성 구성

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 관리 센터를 사용하여 Microsoft 365 테넌트의 사용자 계정에 대한 속성을 구성할 수 있습니다. PowerShell에서 이 작업을 할 수도 있습니다. 또한 관리 센터에서 할 수 없는 다른 작업을 할 수 있습니다.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

Azure Active Directory PowerShell for Graph 모듈에서 사용자 계정에 대한 속성을 구성하기 위해 [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet을 사용하여 설정하거나 변경할 속성을 지정합니다.

먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   
### <a name="change-properties-for-a-specific-user-account"></a>특정 사용자 계정의 속성 변경

*-ObjectID* 매개 변수를 사용하여 계정을 식별하고 추가 매개 변수를 사용하여 특정 속성을 설정하거나 변경합니다. 다음은 가장 일반적인 매개 변수 목록입니다.
  
- -Department \<department name> "
    
- -DisplayName " \<full user name> "
    
- -FacsimilieTelephoneNumber \<fax number> "
    
- -GivenName " \<user first name> "
    
- -Surname " \<user last name> "
    
- -Mobile \<mobile phone number> "
    
- -JobTitle \<job title> "
    
- -PreferredLanguage \<language> "
    
- -StreetAddress " \<street address> "
    
- -City \<city name> "
    
- -State \<state name> "
    
- -PostalCode " \<postal code> "
    
- -Country \<country name> "
    
- -TelephoneNumber \<office phone number> "
    
- -UsageLocation \<2-character country or region code> "
    
    ISO 3166-1 알파-2(A2) 두 글자 국가 또는 지역 코드입니다.
    
추가 매개 변수는 [Set-AzureADUser를 참조하세요.](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0)

>[!Note]
>사용자 계정에 라이선스를 할당하려면 먼저 사용 위치를 할당해야 합니다.
>

사용자 계정에 대한 사용자 계정 이름을 표시하기 위해 다음 명령을 실행합니다.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

이 명령은 PowerShell에 지시합니다.
  
1. 사용자 **계정(Get-AzureADUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.
    
1. 사용자 계정 이름 목록을 사전순으로 **정렬(Sort UserPrincipalName)한** 후 다음 명령()으로 **|** 전송합니다.
    
1. 각 계정에 대한 사용자 계정 이름 속성만 **표시합니다(UserPrincipalName 선택).**

1. 한 화면으로 한 화면 **표시(추가)합니다.**
    
표시 이름(이름 및 성)을 기준으로 계정의 사용자 계정 이름을 표시하려면 다음 명령을 실행합니다. $userName *입력하고* 문자를 \< and > 제거합니다.
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

이 예에서는 표시 이름이 *Caleb Sills인* 사용자 계정의 사용자 계정 이름을 표시합니다.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

이 $upn  사용하여 표시 이름에 따라 개별 계정을 변경할 수 있습니다. 다음은 *Belinda Newman의* 사용 위치를 프랑스로 설정하는 예제입니다. 그러나 사용자 계정 이름이 아닌 표시 이름을 지정합니다.
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>모든 사용자 계정의 속성 변경

모든 사용자에 대한 속성을 변경하기 위해 **Get-AzureADUser** 및 **Set-AzureADUser** cmdlet의 조합을 사용할 수 있습니다. 다음 예에서는 모든 사용자의 사용 위치를 *프랑스로 변경합니다.*
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

이 명령은 PowerShell에 지시합니다.
  
1. 사용자 **계정(Get-AzureADUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.
    
1. 사용자 위치를 **프랑스(Set-AzureADUser -UsageLocation "FR")로 설정**
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>특정 사용자 계정 집합의 속성 변경

특정 사용자 계정 집합의 속성을 변경하기 위해 **Get-AzureADUser,** **Where** 및 **Set-AzureADUser** cmdlet의 조합을 사용할 수 있습니다. 다음 예에서는 회계 부서의 모든 사용자의 사용 위치를 *프랑스로 변경합니다.*
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

이 명령은 PowerShell에 지시합니다.
  
1. 사용자 **계정(Get-AzureADUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.
    
1.  Department 속성이 "Accounting"(Where {$_)으로 설정된 모든 사용자 계정을  **찾아야 합니다. Department -eq "Accounting"}**) 및 결과 정보를 다음 명령()으로 **|** 전송합니다.
    
1. 사용자 위치를 **프랑스(Set-AzureADUser -UsageLocation "FR")로 설정**
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

Microsoft Azure Active Directory 모듈을 사용하여 사용자 계정에 대한 속성을 구성 Windows PowerShell **Set-MsolUser** cmdlet을 사용하여 설정하거나 변경할 속성을 지정합니다.

먼저 [Microsoft 365 테넌트에 연결합니다.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
  
>[!Note]
>PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 *Msol* 이 있는 cmdlet을 지원하지 않습니다. Windows PowerShell에서 이러한 cmdlet을 실행합니다.
>

### <a name="change-properties-for-a-specific-user-account"></a>특정 사용자 계정의 속성 변경

특정 사용자 계정에 대한 속성을 구성하려면 [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet을 사용하여 설정하거나 변경할 속성을 지정합니다. 

*-UserPrincipalName* 매개 변수를 사용하여 계정을 식별하고 추가 매개 변수를 사용하여 특정 속성을 설정하거나 변경합니다. 다음은 가장 일반적인 매개 변수의 목록입니다.
  
- -City \<city name> "
    
- -Country \<country name> "
    
- -Department \<department name> "
    
- -DisplayName " \<full user name> "
    
- -Fax \<fax number> "
    
- -FirstName " \<user first name> "
    
- -LastName " \<user last name> "
    
- -MobilePhone \<mobile phone number> "
    
- -Office \<office location> "
    
- -PhoneNumber \<office phone number> "
    
- -PostalCode " \<postal code> "
    
- -PreferredLanguage \<language> "
    
- -State \<state name> "
    
- -StreetAddress " \<street address> "
    
- -Title " \<title name> "
    
- -UsageLocation \<2-character country or region code> "
    
    ISO 3166-1 알파-2(A2) 두 글자 국가 또는 지역 코드입니다.
    
추가 매개 변수는 [Set-MsolUser를 참조합니다.](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100))

모든 사용자의 사용자 계정 이름을 확인하도록 다음 명령을 실행합니다.
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

이 명령은 PowerShell에 지시합니다.
  
1. 사용자 **계정(Get-MsolUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.
    
1. 사용자 계정 이름 목록을 사전순으로 **정렬(Sort UserPrincipalName)한** 후 다음 명령()으로 **|** 전송합니다.
    
1. 각 계정에 대한 사용자 계정 이름 속성만 **표시합니다(UserPrincipalName 선택).**
    
1. 한 화면으로 한 화면 **표시(추가)합니다.**
    
표시 이름(이름 및 성)을 기준으로 계정의 사용자 계정 이름을 표시하려면 다음 명령을 실행합니다. $userName *입력하고* 문자를 \< and > 제거합니다.
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

이 예에서는 Caleb Sills라는 사용자의 사용자 계정 이름을 표시합니다.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

이 $upn  사용하여 표시 이름에 따라 개별 계정을 변경할 수 있습니다. 다음은 *Belinda Newman의* 사용 위치를 프랑스로 설정하지만 사용자 계정 이름이 아닌 표시 이름을 지정하는 예제입니다.
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>모든 사용자 계정의 속성 변경

모든 사용자에 대한 속성을 변경하기 위해 **Get-MsolUser** 및 **Set-MsolUser** cmdlet의 조합을 사용 합니다. 다음 예에서는 모든 사용자의 사용 위치를 *프랑스로 변경합니다.*
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

이 명령은 PowerShell에 지시합니다.
  
1. 사용자 **계정(Get-MsolUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.
    
1. 사용자 위치를 **프랑스(Set-MsolUser -UsageLocation "FR")로 설정**
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>특정 사용자 계정 집합의 속성 변경

특정 사용자 계정 집합의 속성을 변경하기 위해 **Get-MsolUser,** **Where** 및 **Set-MsolUser** cmdlet의 조합을 사용할 수 있습니다. 다음 예에서는 회계 부서의 모든 사용자의 사용 위치를 *프랑스로 변경합니다.*
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

이 명령은 PowerShell에 지시합니다.
  
1. 사용자 **계정(Get-MsolUser)에** 대한 모든 정보를 확인하여 다음 명령()으로 **|** 전송합니다.
    
1. Department 속성이 "Accounting"(Where {$_)으로 설정된 모든 사용자 계정을  **찾아야 합니다. Department -eq "Accounting"}**)을 사용하여 다음 명령()에 결과 정보를 **|** 전송합니다.
    
1. 사용자 위치를 **프랑스(Set-MsolUser -UsageLocation "FR")로 설정**

## <a name="see-also"></a>참고 항목

[PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)
