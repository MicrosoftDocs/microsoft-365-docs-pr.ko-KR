---
title: PowerShell을 사용 하 여 Microsoft 365 사용자 계정에 역할 할당
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: 이 문서에서는 Microsoft 365 용 PowerShell을 빠르고 쉽게 사용 하 여 사용자 계정에 역할을 할당 하는 방법을 알아봅니다.
ms.openlocfilehash: 4726dcea109490ff28299002bc5263aa15dca949
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692332"
---
# <a name="assign-roles-to-microsoft-365-user-accounts-with-powershell"></a>PowerShell을 사용 하 여 Microsoft 365 사용자 계정에 역할 할당

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft 365 용 PowerShell을 사용 하 여 사용자 계정에 쉽고 빠르게 역할을 할당할 수 있습니다.

>[!Note]
>Microsoft 365 관리 센터를 사용 하 여 사용자 계정에 역할을 할당 하려면 [다음 지침](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)을 참조 하세요.
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 모듈용 Azure Active Directory PowerShell 사용하기

먼저 전역 관리자 계정을 사용 하 여 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) 합니다.
  
다음으로, 역할에 추가 하려는 사용자 계정의 로그인 이름 (예: fredsm@contoso.com)을 확인 합니다. 이를 UPN (사용자 계정 이름)이 라고도 합니다.

다음으로, 역할 이름을 확인 합니다. 이 [관리자 역할 권한 목록을 Azure Active Directory에서](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)사용 합니다.

>[!Note]
>이 문서의 참고 사항에 주의 하십시오. 일부 역할 이름은 Azure AD PowerShell에 따라 다릅니다. 예를 들어 Microsoft 365 관리 센터의 "SharePoint 관리자" 역할에는 Azure AD PowerShell에 대 한 "SharePoint Service 관리자" 라는 이름이 지정 됩니다.
>

다음으로, 로그인 및 역할 이름을 입력 하 고 다음 명령을 실행 합니다.
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

다음은 belindan@contoso.com 계정에 SharePoint 서비스 관리자 역할을 할당 하는 완성 된 명령 집합의 예입니다.
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

특정 역할에 대 한 사용자 이름 목록을 표시 하려면 다음 명령을 사용 합니다.

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell용 Microsoft Azure Active Directory 모듈 사용하기

먼저 전역 관리자 계정을 사용 하 여 [Microsoft 365 테 넌 트에 연결](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) 합니다.
  
### <a name="for-a-single-role-change"></a>단일 역할 변경의 경우

특정 사용자 계정에 대 한 가장 일반적인 방법은 해당 표시 이름 또는 전자 메일 이름 (로그인 이름 또는 UPN (사용자 계정 이름))을 사용 하는 것입니다.

#### <a name="display-names-of-user-accounts"></a>사용자 계정의 표시 이름

사용자 계정의 표시 이름으로 작업 하는 데 사용 되는 경우 다음 사항을 결정 합니다.
  
- 구성 하려는 사용자 계정입니다.
    
    사용자 계정을 지정 하려면 해당 표시 이름을 결정 해야 합니다. 전체 목록 계정을 가져오려면 다음 명령을 사용 합니다.
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    이 명령은 표시 이름별로 정렬 된 사용자 계정의 표시 이름을 한 번에 하나씩 나열 합니다. **Where** cmdlet을 사용 하 여 목록을 더 작은 집합으로 필터링 할 수 있습니다. 예를 들면 다음과 같습니다.

   >[!Note]
   >PowerShell Core는 Windows PowerShell용 Microsoft Azure Active Directory 모듈 및 이름에 **Msol**이 있는 cmdlet을 지원하지 않습니다. 이러한 cmdlet을 계속 사용하려면 Windows PowerShell에서 이를 실행해야 합니다.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    이 명령은 표시 이름이 "John"으로 시작 하는 사용자 계정만 나열 합니다.
    
- 할당 하려는 역할입니다.
    
    사용자 계정에 할당할 수 있는 사용 가능한 역할 목록을 표시 하려면 다음 명령을 사용 합니다.
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

계정의 표시 이름과 역할 이름을 확인 한 후에는 다음 명령을 사용 하 여 계정에 역할을 할당 합니다.
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

명령을 복사 하 여 메모장에 붙여 넣습니다. **$DispName** 및 **$roleName** 변수의 경우 설명 텍스트를 해당 값으로 바꾸고, 문자를 제거 \< and > 하 고, 따옴표를 남겨 두어야 합니다. 수정 된 줄을 복사 하 여 Windows PowerShell 용 Windows Azure Active Directory 모듈 창에 붙여 넣어 실행 합니다. 또는 Windows PowerShell ISE (통합 스크립트 환경)를 사용할 수 있습니다.
  
다음은 완성 된 명령 집합의 예입니다.
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>사용자 계정의 로그인 이름

사용자 계정의 로그인 이름 또는 Upn으로 작업 하는 데 사용 되는 경우 다음 사항을 확인 합니다.
  
- 사용자 계정의 UPN입니다.
    
    아직 UPN을 모르는 경우에는 다음 명령을 사용 합니다.
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    이 명령은 UPN을 기준으로 한 번에 한 화면씩 정렬 하 여 사용자 계정의 UPN을 나열 합니다. **Where** cmdlet을 사용 하 여 목록을 더 작은 집합으로 필터링 할 수 있습니다. 예를 들면 다음과 같습니다.
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    이 명령은 표시 이름이 "John"으로 시작 하는 사용자 계정만 나열 합니다.
    
- 할당 하려는 역할입니다.
    
    사용자 계정에 할당할 수 있는 사용 가능한 역할 목록을 표시 하려면 다음 명령을 사용 합니다.
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

계정의 UPN과 역할 이름을 한 후에는 다음 명령을 사용 하 여 계정에 역할을 할당 합니다.
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

명령을 복사 하 여 메모장에 붙여 넣습니다. **$UpnName** 및 **$roleName** 변수의 경우 설명 텍스트를 해당 값으로 바꾸고, 문자를 제거 \< and > 하 고, 따옴표를 남겨 두어야 합니다. 수정 된 줄을 복사 하 여 Windows PowerShell 용 Windows Azure Active Directory 모듈 창에 붙여 넣어 실행 합니다. 또는 Windows PowerShell ISE를 사용할 수 있습니다.
  
다음은 완성 된 명령 집합의 예입니다.
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>여러 역할 변경

여러 역할 변경의 경우 다음 사항을 확인 합니다.
  
- 구성 하려는 사용자 계정 이전 섹션의 방법을 사용 하 여 표시 이름 또는 Upn 집합을 수집할 수 있습니다.
    
- 각 사용자 계정에 할당 하려는 역할
    
    사용자 계정에 할당할 수 있는 사용 가능한 역할 목록을 표시 하려면 다음 명령을 사용 합니다.
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

다음으로 표시 이름이 나 UPN 및 role name 필드가 있는 CSV (쉼표로 구분 된 값) 텍스트 파일을 만듭니다. Microsoft Excel에서 쉽게이 작업을 수행할 수 있습니다.

다음은 표시 이름에 대 한 예입니다.
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

다음으로, CSV 파일의 위치를 입력 하 고 PowerShell 명령 프롬프트에서 결과 명령을 실행 합니다.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

Upn의 예는 다음과 같습니다.
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

다음으로, CSV 파일의 위치를 입력 하 고 PowerShell 명령 프롬프트에서 결과 명령을 실행 합니다.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a>참고 항목

- [PowerShell로 Microsoft 365 사용자 계정, 라이선스 및 그룹 관리](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [PowerShell로 Microsoft 365 관리](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Microsoft 365 용 PowerShell 시작](getting-started-with-microsoft-365-powershell.md)