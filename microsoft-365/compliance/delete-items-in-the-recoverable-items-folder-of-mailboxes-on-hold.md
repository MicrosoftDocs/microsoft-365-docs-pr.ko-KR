---
title: 클라우드 사서함 보류의 복구 가능한 항목 폴더에서 항목 삭제
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 사서함이 법적 보유 상태인 경우에도 관리자가 Exchange Online 사서함에 대한 사용자의 복구 가능한 항목 폴더에 있는 항목을 삭제하는 방법을 확인합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7a51a78280885a8a7aa7c65a0c04110b46ed7f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919958"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a>보류 중인 클라우드 기반 사서함의 복구 가능한 항목 폴더에서 항목 삭제

Exchange Online 사서함의 복구 가능한 항목 폴더는 실수로 또는 악의적인 삭제로부터 보호하기 위해 존재합니다. 또한 보존 및 eDiscovery 검색과 같은 준수 기능에서 보존 및 액세스하는 항목을 저장하는 데도 사용됩니다. 그러나 경우에 따라 조직에서 복구 가능한 항목 폴더에 의도하지 않은 보존된 데이터를 삭제해야 할 수 있습니다. 예를 들어 사용자는 업무상 심각한 결과를 초래할 수 있는 중요한 정보나 정보가 포함된 전자 메일 메시지를 무의미하게 보내거나 전달할 수 있습니다. 메시지가 영구적으로 삭제된 경우에도 사서함에 법적 보존이 설정되면 메시지가 무기한 보존될 수 있습니다. 이 시나리오는  데이터가 의도하지 않은 Office 365로 유출된 것이기 때문에 데이터 유출로 알려져 있습니다.  이러한 경우 Office 365의 다른 보류 기능 중 하나를 사용하여 해당 사서함을 보류한 경우에도 Exchange Online 사서함에 대한 사용자의 복구 가능한 항목 폴더에 있는 항목을 삭제할 수 있습니다. 이러한 유형의 보류에는 Office 365 또는 Microsoft 365의 보안 및 준수 센터에서 만든 소송 보존, In-Place 보류, eDiscovery 보존 및 보존 정책이 포함됩니다.
  
 이 문서에서는 관리자가 보류된 클라우드 기반 사서함의 복구 가능한 항목 폴더에서 항목을 삭제하는 방법을 설명합니다. 이 절차에는 사서함에 대한 액세스를 사용할 수 없는 경우와 단일 항목 복구를 사용할 수 없습니다. 관리되는 폴더 도우미가 사서함을 처리하지 못하게 설정하고, 보류를 일시적으로 제거하고, 복구 가능한 항목 폴더에서 항목을 삭제한 다음 사서함을 이전 구성으로 되돌리면 됩니다. 프로세스는 다음과 같습니다.
  
[1단계: 사서함에 대한 정보 수집](#step-1-collect-information-about-the-mailbox)

[2단계: 사서함 준비](#step-2-prepare-the-mailbox)

[3단계: 사서함에서 모든 보류 제거](#step-3-remove-all-holds-from-the-mailbox)

[4단계: 사서함에서 지연 보류 제거](#step-4-remove-the-delay-hold-from-the-mailbox)

[5단계: 복구 가능한 항목 폴더의 항목 삭제](#step-5-delete-items-in-the-recoverable-items-folder)

[6단계: 사서함을 이전 상태로 되걸기](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> 이 문서에 설명된 절차에 따라 데이터가 Exchange Online 사서함에서 영구적으로 삭제(제거)됩니다. 즉, 복구 가능한 항목 폴더에서 삭제한 메시지는 복구할 수 없습니다. 법적 검색 또는 기타 준수 목적으로 사용할 수 없습니다. 보안 및 준수 센터에서 만든 소송 보존, In-Place 보류, eDiscovery 보류 또는 보존 정책의 일부로 보류된 사서함에서 메시지를 삭제하려면 보류를 제거하기 전에 레코드 관리 또는 법률 부서에 문의하십시오. 조직에 보류된 사서함 또는 데이터 유출 인시던트가 우선적으로 적용될지 여부를 정의하는 정책이 있을 수 있습니다.
  
## <a name="before-you-delete-items"></a>항목을 삭제하기 전에

- 콘텐츠 검색을 만들고 실행하려면 eDiscovery 관리자 역할 그룹의 구성원이거나 준수 검색 관리 역할을 할당 받아야 합니다. 메시지를 삭제하려면 조직 관리 역할 그룹의 구성원이거나 검색 및 제거 관리 역할을 할당 받아야 합니다. 역할 그룹에 사용자를 추가하는 방법에 대한 자세한 내용은 [보안 및 준수 센터의 eDiscovery 권한 부여](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions)를 참조하세요.

- 이 문서에 설명된 절차는 비활성 사서함에 대해 지원되지 않습니다. 제거한 후 비활성 사서함에 보류(또는 보존 정책)를 다시 적용할 수 없습니다. 비활성 사서함에서 보류를 제거하면 해당 사서함이 일반 소프트 삭제 사서함으로 변경되고 관리되는 폴더 도우미가 처리한 후 조직에서 영구적으로 삭제됩니다.

- 보존 잠금을 사용하여 잠긴 정책으로 보존 설정이 할당된 사서함에는 이 절차를 수행할 수 없습니다. 이 잠금으로 인해 사서함을 제거하거나 정책에서 제외하고 사서함의 관리되는 폴더 도우미를 해제할 수 없습니다. 보존 정책 잠금에 대한 자세한 내용은 보존 잠금을 사용하여 보존 정책 및 보존 레이블 정책에 대한 변경 내용을 [제한하세요.](retention-preservation-lock.md)

- 사서함이 보류 중이 아니거나 단일 항목 복구를 사용하도록 설정하지 않은 경우 복구할 수 있는 항목 폴더에서 항목을 삭제할 수 있습니다. 이 작업을 하는 방법에 대한 자세한 내용은 조직에서 전자 메일 메시지 검색 및 삭제를 [참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)
  
## <a name="step-1-collect-information-about-the-mailbox"></a>1단계: 사서함에 대한 정보 수집

이 첫 번째 단계는 이 절차에 영향을 줄 대상 사서함에서 선택한 속성을 수집하는 것입니다. 이러한 설정을 적어 두거나 텍스트 파일에 저장해야 합니다. 이러한 속성 중 일부를 변경한 다음 복구 가능한 항목 폴더에서 항목을 삭제한 후 6단계에서 원래 값으로 되돌리게 됩니다. 다음은 수집해야 하는 사서함 속성의 목록입니다.
  
- *SingleItemRecoveryEnabled* 및 *RetainDeletedItemsFor.* 필요한 경우 단일 복구를 사용하지 않도록 설정하고 3단계에서 삭제된 항목 보존 기간을 늘리게 됩니다.

- *LitigationHoldEnabled*  및  *InPlaceHolds*. 3단계에서 일시적으로 제거할 수 있도록 사서함에 배치된 모든 보류를 식별해야 합니다. 사서함에 [배치될](#more-information) 수 있는 형식 보류를 식별하는 방법에 대한 팁은 추가 정보 섹션을 참조하세요.

또한 이 절차 중에 소유자(또는 다른 사용자)가 사서함에 액세스할 수 있도록 사서함 클라이언트 액세스 설정을 일시적으로 사용하지 않도록 설정해야 합니다. 마지막으로 복구 가능한 항목 폴더의 현재 크기와 항목 수를 얻을 수 있습니다. 5단계에서 복구할 수 있는 항목 폴더의 항목을 삭제한 후 이 정보를 사용하여 항목이 제거된 것을 확인합니다.
  
1. [Exchange Online PowerShell에 연결합니다](https://go.microsoft.com/fwlink/?linkid=396554). Exchange Online에서 적절한 관리 역할이 할당된 관리자 계정에 사용자 이름과 암호를 사용하세요.

2. 다음 명령을 실행하여 단일 항목 복구 및 삭제된 항목 보존 기간에 대한 정보를 얻습니다.

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   단일 항목 복구를 사용하도록 설정한 경우 2단계에서 사용하지 않도록 설정해야 합니다. 삭제된 항목 보존 기간이 30일(Exchange Online의 최대값)으로 설정되지 않은 경우 2단계에서 늘 수 있습니다.

3. 다음 명령을 실행하여 사서함에 대한 사서함 액세스 설정을 확인합니다.

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   2단계에서 이러한 모든 액세스 방법을 사용하지 않도록 설정하게 됩니다.

4. 다음 명령을 실행하여 사서함에 적용된 보류 및 보존 정책에 대한 정보를 얻습니다.

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

   > [!TIP]
    > *InPlaceHolds* 속성에 값이 너무 많고 모든 값이 표시되지 않는 경우 명령을 실행하여 각 값을 별도의 줄에 표시할 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` 수 있습니다.
  
5. 다음 명령을 실행하여 조직 전체 보존 정책에 대한 정보를 얻습니다. 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   조직에 조직 전체 보존 정책이 있는 경우 3단계에서 이러한 정책에서 사서함을 제외해야 합니다.

   > [!TIP]
    > *InPlaceHolds* 속성에 값이 너무 많고 모든 값이 표시되지 않는 경우 명령을 실행하여 각 값을 별도의 줄에 표시할 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` 수 있습니다. 
  
6. 다음 명령을 실행하여 사용자의 기본 사서함에 있는 복구 가능한 항목 폴더에 있는 폴더 및 하위 폴더의 현재 크기와 총 항목 수를 확인합니다.

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   사용자의 보관 사서함을 사용하도록 설정한 경우 다음 명령을 실행하여 보관 사서함의 복구 가능한 항목 폴더에 있는 폴더 및 하위 폴더의 총 항목 수와 크기를 확인합니다. 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   5단계에서 항목을 삭제할 때 사용자의 기본 보관 사서함에 있는 복구 가능한 항목 폴더의 항목을 삭제하거나 삭제하지 않을 수 있습니다. 사서함에 대해 자동 확장 보관을 사용하도록 설정하면 보조 보관 사서함의 항목이 삭제되지 않습니다.
  
## <a name="step-2-prepare-the-mailbox"></a>2단계: 사서함 준비

사서함에 대한 정보를 수집하고 저장한 후 다음 작업은 다음 작업을 수행하여 사서함을 준비하는 것입니다.
  
- **이 절차 동안** 사서함 소유자가 사서함에 액세스할 수 없는 경우 사서함 데이터를 변경할 수 있도록 사서함에 대한 클라이언트 액세스를 사용하지 않도록 설정하십시오.

- **삭제된** 항목 보존 기간을 30일(Exchange Online의 최대값)으로 늘리면 5단계에서 항목을 삭제하기 전에 복구 가능한 항목 폴더에서 항목이 제거되지 않습니다.

- **5단계의** 복구 가능한 항목 폴더에서 항목을 삭제한 후 삭제된 항목 보존 기간 동안 항목이 보존되지 않도록 단일 항목 복구를 사용하지 않도록 설정합니다.

- **관리되는 폴더 도우미가** 사서함을 처리하지 않도록 설정하고 5단계에서 삭제한 항목을 보존합니다.

Exchange Online PowerShell에서 다음 단계를 수행합니다.
  
1. 다음 명령을 실행하여 사서함에 대한 모든 클라이언트 액세스를 사용하지 않도록 설정합니다. 명령 구문은 모든 클라이언트 액세스 방법이 사서함에서 사용하도록 설정되어 있는 것으로 가정합니다.

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > 사서함에 대한 모든 클라이언트 액세스 방법을 사용하지 않도록 설정하는 데 최대 60분이 걸릴 수 있습니다. 이러한 액세스 방법을 해제하면 현재 로그인한 사서함 소유자의 연결이 끊어지지 않습니다. 소유자가 로그인되지 않은 경우 이러한 액세스 방법을 사용하지 않도록 설정한 후에도 사서함에 액세스할 수 없습니다.
  
2. 삭제된 항목 보존 기간을 최대 30일로 늘리기 위해 다음 명령을 실행합니다. 이 경우 현재 설정이 30일 미만으로 가정합니다.

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. 다음 명령을 실행하여 단일 항목 복구를 사용하지 않도록 설정할 수 있습니다.

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > 단일 항목 복구를 사용하지 않도록 설정하는 데 최대 60분이 걸릴 수 있습니다. 이 기간이 경과할 때까지 복구 가능한 항목 폴더의 항목을 삭제하지 않습니다. 
  
4. 다음 명령을 실행하여 관리되는 폴더 도우미가 사서함을 처리하지 못하게 합니다. 앞서 설명한처럼 보존 잠금이 있는 보존 정책이 사서함에 적용되지 않은 경우 관리되는 폴더 도우미를 사용하지 않도록 설정할 수 있습니다. 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>3단계: 사서함에서 모든 보류 제거

복구 가능한 항목 폴더에서 항목을 삭제할 수 있는 마지막 단계는 사서함에 배치된 모든 보류(1단계에서 식별)를 제거하는 것입니다. 복구 가능한 항목 폴더에서 항목을 삭제한 후 항목이 보존되지 못하게 모든 보류를 제거해야 합니다. 다음 섹션에는 사서함의 다양한 보류 유형 제거에 대한 정보가 포함되어 있습니다. 사서함에 [배치될](#more-information) 수 있는 형식 보류를 식별하는 방법에 대한 팁은 추가 정보 섹션을 참조하세요. 자세한 내용은 Exchange Online 사서함에 배치된 보류 유형을 [식별하는 방법을 참조하십시오.](identify-a-hold-on-an-exchange-online-mailbox.md)
  
> [!CAUTION]
> 앞서 설명한 것 처럼 사서함에서 보류를 제거 하기 전에 레코드 관리 또는 법률 부서에 확인 합니다. 
  
### <a name="litigation-hold"></a>소송 대기
  
Exchange Online PowerShell에서 다음 명령을 실행하여 사서함에서 소송 보류를 제거합니다.

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> 클라이언트 액세스 방법 및 단일 항목 복구를 사용할 수 있도록 설정하는 경우와 마찬가지로 소송 보류를 제거하는 데 최대 60분이 걸릴 수 있습니다. 이 기간이 경과할 때까지 복구 가능한 항목 폴더에서 항목을 삭제하지 않습니다. 
  
### <a name="in-place-hold"></a>원본 위치 유지
  
Exchange Online PowerShell에서 다음 명령을 실행하여 사서함에 In-Place 보류를 식별합니다. 1단계에서 식별한 In-Place 보류의 GUID를 사용 합니다.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

보류를 In-Place EAC(Exchange 관리 센터) 또는 Exchange Online PowerShell을 사용하여 사서함을 보류에서 제거할 수 있습니다. 자세한 내용은 [만들기 또는 In-place Hold 제거](https://go.microsoft.com/fwlink/?linkid=852668) 항목을 참조하십시오.
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a>특정 사서함에 적용된 보존 정책
  
Security & 준수 센터 [PowerShell에서](https://go.microsoft.com/fwlink/?linkid=627084) 다음 명령을 실행하여 사서함에 적용되는 보존 정책을 식별합니다. 이 명령은 사서함에 적용된 Teams 대화 보존 정책도 반환합니다. 1단계에서 식별한 보존 정책의 GUID(또는 prefix 포함 안 `mbx` `skp` )를 사용 합니다.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

보존 정책을 식별한 후 보안 & 준수 센터의 정보 거버넌스 보존 페이지로 이동하여 이전 단계에서 식별한 보존 정책을 편집한 다음 보존 정책에 포함된 받는 사람 목록에서 사서함을  >   제거합니다.
  
### <a name="organization-wide-retention-policies"></a>조직 전체 보존 정책
  
조직 전체, Exchange 전체 및 Teams 전체 보존 정책은 조직의 모든 사서함에 적용됩니다. 이러한 Cmdlet은 사서함 수준이 아닌 조직 수준에서 적용되고 1단계에서 **Get-OrganizationConfig** cmdlet을 실행할 때 반환됩니다. Security & 준수 센터 [PowerShell에서](https://go.microsoft.com/fwlink/?linkid=627084) 다음 명령을 실행하여 조직 전체 보존 정책을 식별합니다. 1단계에서 식별한 조직 전체 보존 정책에 대한 GUID(즉, 전제는 포함하지  `mbx` 않습니다)를 사용 합니다.

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

조직 전체 보존 정책을 식별한 후 보안 & 준수 센터의 정보 거버넌스 보존 페이지로 이동하여 이전 단계에서 식별한 각 조직 전체 보존 정책을 편집하고 사서함을 제외된 받는 사람 목록에  >   추가합니다. 이렇게 하면 보존 정책에서 사용자의 사서함이 제거됩니다.

### <a name="retention-labels"></a>보존 레이블

사용자가 콘텐츠를 보존하거나 콘텐츠를 보존한 다음 사서함의 폴더 또는 항목에 콘텐츠를 삭제하도록 구성된 레이블을 적용하면 *ComplianceTagHoldApplied* 사서함 속성이 **True로** 설정됩니다. 이 경우 사서함은 소송 보존에 배치되거나 보존 정책에 할당된 경우처럼 보류된 것으로 간주됩니다.

*ComplianceTagHoldApplied* 속성의 값을 보고 Exchange Online PowerShell에서 다음 명령을 실행합니다.

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

보존 레이블이 폴더 또는 항목에 적용되어 사서함이 보류 중으로 확인되면 보안 및 준수 센터의 콘텐츠 검색 도구를 사용하여 ComplianceTag 검색 조건을 사용하여 레이블이 지정된 항목을 검색할 수 있습니다. 자세한 내용은 콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건의 "검색 조건" [섹션을 참조하세요.](keyword-queries-and-search-conditions.md#conditions-for-common-properties)

레이블에 대한 자세한 내용은 보존 정책 및 보존 레이블에 [대한 자세한 내용을 참조하세요.](retention.md)

### <a name="ediscovery-holds"></a>eDiscovery 보존
  
Security & Compliance [Center PowerShell에서](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 다음 명령을 실행하여 사서함에 적용된 *eDiscovery 사례(eDiscovery* 보류라고도 하는 보류)와 연결된 보류를 식별합니다. 1단계에서 식별한 eDiscovery 보류에 대한  `UniH` GUID(prefix를 포함하지 않습니다)를 사용 합니다. 두 번째 명령은 보류가 연결된 eDiscovery 사례의 이름을 표시합니다. 세 번째 명령은 보류의 이름을 표시합니다.
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

eDiscovery 사례의 이름과 보류를 확인한 후 준수 센터의 **eDiscovery** \> **eDiscovery** 페이지로 이동하여 사례를 열고 보류에서 사서함을 제거합니다. eDiscovery 보류를 식별하는 방법에 대한 자세한 내용은 Exchange Online 사서함에 배치된 보류 유형을 식별하는 방법의 "eDiscovery 보류" 섹션을 [참조하세요.](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>4단계: 사서함에서 지연 보류 제거

사서함에서 모든 유형의 보류를 제거한 후 *DelayHoldApplied* 또는 *DelayReleaseHoldApplied* 사서함 속성의 값이 **True로 설정됩니다.** 이 오류는 다음에 관리되는 폴더 도우미가 사서함을 처리하고 보류가 제거된 경우를 감지할 때 발생합니다. 이를 지연  보류라고 부르며, 사서함에서 데이터가 영구적으로 삭제되지 않도록 보류의 실제 제거가 30일 동안 지연됩니다. 지연 보류의 목적은 관리자에게 보류가 제거된 후 제거될 사서함 항목을 검색하거나 복구할 수 있는 기회를 제공하기 위한 것입니다.  사서함에 대해 지연 보류가 설정되는 경우 사서함은 사서함이 소송 보류에 있는 경우처럼 무제한 기간 동안 보류된 것으로 간주됩니다. 30일이 지난 후 지연 보류가 만료되고 Microsoft 365는 지연 보류를 제거하기 위해 지연 보류를 자동으로 *시도합니다(DelayHoldApplied* 또는 *DelayReleaseHoldApplied* 속성을 **False로** 설정). 지연 보류에 대한 자세한 내용은 Exchange Online 사서함에 배치된 보류 유형을 식별하는 방법의 "보류된 사서함 관리" 섹션을 [참조하십시오.](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)

5단계에서 항목을 삭제하려면 먼저 사서함에서 지연 보류를 제거해야 합니다. 먼저 Exchange Online PowerShell에서 다음 명령을 실행하여 지연 보류가 사서함에 적용되는지 여부를 판단합니다.

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

*DelayHoldApplied* 또는 *DelayReleaseHoldApplied* 속성의 값이 **False로** 설정된 경우 사서함에 지연 보류가 배치되지 않습니다. 5단계로 이동하여 복구 가능한 항목 폴더의 항목을 삭제할 수 있습니다.

*DelayHoldApplied* 또는 *DelayReleaseHoldApplied* 속성 값이 **True로** 설정된 경우 다음 명령 중 하나를 실행하여 지연 보류를 제거합니다.

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

또는

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

*RemoveDelayHoldApplied* 또는 *RemoveDelayReleaseHoldApplied* 매개 변수를 사용하려면 Exchange Online에서 법적 보유 역할이 할당되어야 합니다.

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>5단계: 복구 가능한 항목 폴더의 항목 삭제

이제 Security & 준수 센터 PowerShell에서 [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch) 및 [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction) cmdlet을 사용하여 복구할 수 있는 항목 폴더의 항목을 실제로 삭제할 수 있습니다.

복구 가능한 항목 폴더에 있는 항목을 검색하기 위해 대상 컬렉션을 수행하는 *것이 좋습니다.* 즉, 검색 범위를 복구 가능한 항목 폴더에 있는 항목으로만 좁힐 수 있습니다. 이 작업을 위해 대상 컬렉션에 대한 콘텐츠 검색 사용 문서에서 [스크립트를 실행하면](use-content-search-for-targeted-collections.md) 됩니다. 이 스크립트는 대상 복구 가능한 항목 폴더의 모든 하위 폴더에 대한 폴더 ID 속성 값을 반환합니다. 그런 다음 검색 쿼리의 폴더 ID를 사용하여 해당 폴더에 있는 항목을 반환합니다.

사용자의 복구 가능한 항목 폴더에서 항목을 검색하고 삭제하는 프로세스에 대한 개요는 다음과 같습니다.

1. 대상 사용자의 사서함에 있는 모든 폴더의 폴더 ID를 반환하는 대상 컬렉션 스크립트를 실행합니다. 스크립트는 동일한 PowerShell 세션에서 Exchange Online PowerShell 및 & 준수 PowerShell에 연결합니다. 자세한 내용은 스크립트 실행을 참조하여 사서함의 폴더 [목록을 확인합니다.](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site)

2. 복구 가능한 항목 폴더에 있는 모든 하위 폴더의 폴더를 복사합니다. 또는 스크립트의 출력을 텍스트 파일로 리디렉션할 수 있습니다.

   다음은 항목을 검색하고 삭제할 수 있는 복구 가능한 항목 폴더의 하위 폴더 목록 및 설명입니다.

   - **삭제:** 삭제된 항목 보존 기간이 만료되지 않은 소프트 삭제된 항목을 포함 사용자는 Outlook에서 지워진 항목 복구 도구를 사용하여 이 하위 모음에서 소프트 삭제된 항목을 복구할 수 있습니다.

   - **제거:** 삭제된 항목 보존 기간이 만료된 영구 삭제된 항목을 포함 사용자는 복구 가능한 항목 폴더에서 항목을 제거하여 항목을 영구 삭제할 수도 있습니다. 사서함이 보류 중이면 영구 삭제된 항목이 보존됩니다. 이 하위폴더는 최종 사용자에게 표시되지 않습니다.

   - **DiscoveryHolds**: eDiscovery 보류 또는 보존 정책에 의해 보존된 영구 삭제된 항목을 포함 이 하위폴더는 최종 사용자에게 표시되지 않습니다.

   - **SubstrateHolds**: 보존 정책 또는 다른 유형의 보류에 의해 보존된 Teams 및 기타 클라우드 기반 앱에서 영구 삭제된 항목을 포함 이 하위폴더는 최종 사용자에게 표시되지 않습니다.

3. **New-ComplianceSearch** cmdlet(보안 & 준수 센터 PowerShell에서) 또는 준수 센터의 콘텐츠 검색 도구를 사용하여 대상 사용자의 복구 가능한 항목 폴더에서 항목을 반환하는 콘텐츠 검색을 만들 수 있습니다. 검색할 모든 하위 폴더의 FolderId를 검색 쿼리에 포함하면 됩니다. 예를 들어 다음 쿼리는 제거 및 eDiscoveryHolds 하위폴더의 모든 메시지를 반환합니다.

   ```text
   folderid:<folder ID of Purges subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   폴더 ID 속성을 사용하는 콘텐츠 검색을 실행하는 데 대한 자세한 내용 및 예제는 폴더 ID 사용 또는 대상 컬렉션 [수행을 참조하십시오.](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection)

   > [!NOTE]
   > **New-ComplianceSearch** cmdlet을 사용하여 복구 가능한 항목 폴더를 검색하는 경우 **Start-ComplianceSearch** cmdlet을 사용하여 검색을 실행해야 합니다.

4. 콘텐츠 검색을 만든 후 삭제할 항목을 반환하는지 확인한 후 명령(보안 & 준수 센터 PowerShell)을 사용하여 이전 단계에서 만든 콘텐츠 검색에서 반환된 항목을 영구적으로 `New-ComplianceSearchAction -Purge -PurgeType HardDelete` 삭제합니다. 예를 들어 다음 명령과 유사한 명령을 실행할 수 있습니다.

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. 이전 명령을 실행하면 사서함당 최대 10개 항목이 삭제됩니다. 즉, 복구 가능한 항목 폴더에서 삭제할 모든 항목을 삭제하기 위해 명령을 여러 번 `New-ComplianceSearchAction -Purge` 실행해야 할 수 있습니다. 추가 항목을 삭제하려면 먼저 이전 준수 검색 삭제 작업을 제거해야 합니다. 이 작업을 위해 `Remove-ComplianceSearchAction` cmdlet을 실행합니다. 예를 들어 이전 단계에서 실행된 제거 작업을 삭제하려면 다음 명령을 실행합니다.

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   이 작업을 수행한 후 새 준수 검색 삭제 작업을 만들어 더 많은 항목을 삭제할 수 있습니다. 새 제거 작업을 만들기 전에 각 제거 작업을 삭제해야 합니다.

   준수 검색 작업 목록을 표시하기 위해 `Get-ComplianceSearchAction` cmdlet을 실행하면 됩니다. 제거 작업은 검색 이름에 `_Purge` 추가하여 식별됩니다.

### <a name="verify-that-items-were-deleted"></a>항목이 삭제된지 확인

사서함의 복구 가능한 항목 폴더에서 항목이 성공적으로 삭제된지 확인하려면 Exchange Online PowerShell에서 **Get-MailboxFolderStatistics** cmdlet을 사용하여 복구 가능한 항목 폴더의 항목 수와 크기를 확인합니다. 이러한 통계를 1단계에서 수집한 통계와 비교할 수 있습니다.
  
다음 명령을 실행하여 사용자의 기본 사서함에 있는 복구 가능한 항목 폴더에 있는 폴더 및 하위 폴더의 현재 크기와 총 항목 수를 확인합니다.
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

다음 명령을 실행하여 사용자의 보관 사서함에 있는 복구 가능한 항목 폴더의 폴더 및 하위 폴더에 있는 항목의 크기와 총 개수를 확인합니다.

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>6단계: 사서함을 이전 상태로 되걸기

마지막 단계는 사서함을 이전 구성으로 되돌리는 것입니다. 즉, 2단계에서 변경한 속성을 다시 설정하고 3단계에서 제거한 보류를 다시 지정합니다. 여기에는 다음이 포함됩니다.
  
- 삭제된 항목 보존 기간을 이전 값으로 변경합니다. 또는 이 집합을 Exchange Online의 최대값인 30일로 남겨두면 됩니다.

- 단일 항목 복구를 다시 사용하도록 설정

- 소유자가 자신의 사서함에 액세스할 수 있도록 클라이언트 액세스 방법을 다시 사용하도록 설정

- 제거한 보존 및 보존 정책을 다시 적용합니다.

- 사서함을 처리하기 위해 관리되는 폴더 도우미를 다시 사용하도록 설정

> [!IMPORTANT]
> 사서함을 처리하도록 관리되는 폴더 도우미를 다시 사용하도록 설정하기 전에 보류 또는 보존 정책을 다시 적용하고 현재 보존 정책이 있는지 확인한 후 24시간을 기다리는 것이 좋습니다.
  
Exchange Online PowerShell에서 다음 단계를 지정된 순서로 수행합니다.
  
1. 다음 명령을 실행하여 삭제된 항목 보존 기간을 원래 값으로 변경합니다. 이 경우 이전 설정이 30일 미만으로 가정합니다. 예를 들어 14일입니다.

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. 다음 명령을 실행하여 단일 항목 복구를 다시 사용하도록 설정하십시오.

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. 다음 명령을 실행하여 모든 클라이언트 액세스 방법을 사서함에 다시 사용하도록 설정할 수 있습니다.

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. 3단계에서 제거한 보류를 다시합니다. 보류 유형에 따라 다음 절차 중 하나를 사용 합니다.

    **소송 대기**

    사서함에 대해 소송 보류를 다시 사용하도록 설정하려면 다음 명령을 실행합니다.

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **원본 위치 유지**

    EAC(또는 Exchange Online PowerShell)를 사용하여 사서함을 In-Place 보류합니다.

    **특정 사서함에 적용된 보존 정책**

    보안 & 준수 센터를 사용하여 사서함을 보존 정책에 다시 추가합니다. Security **&** 준수 센터의 정보 거버넌스 보존 페이지로 이동하여 보존 정책을 편집한 다음 보존 정책이 적용되는 받는 사람 목록에 사서함을 다시  >   추가합니다.

    **조직 전체 보존 정책**

    조직 전체 또는 Exchange 전체 보존 정책을 정책에서 제외하여 제거한 경우 보안 & 준수 센터를 사용하여 제외된 사용자 목록에서 사서함을 제거합니다. Security **&** 준수 센터의 정보 거버넌스 보존 페이지로 이동하여 조직 전체 보존 정책을 편집하고 제외된 받는 사람 목록에서 사서함을  >   제거합니다. 이렇게 하면 보존 정책이 사용자 사서함에 다시 적용됩니다.

    **eDiscovery 사례 보류**

    Security & 준수 센터를 사용하여 eDiscovery 사례와 연결된 사서함을 다시 보류합니다. **eDiscovery**  >  **eDiscovery** 페이지로 이동하여 사례를 열고 사서함을 보류에 다시 추가합니다. 

5. 다음 명령을 실행하여 관리되는 폴더 도우미가 사서함을 다시 처리하도록 허용합니다. 앞서 언급했듯이 관리되는 폴더 도우미를 다시 사용하도록 설정하기 전에 보류 또는 보존 정책을 다시 적용하고 현재 상태가 확인된 후 24시간 동안 기다리는 것이 좋습니다.

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. 사서함이 이전 구성으로 되돌아 났는지 확인하려면 다음 명령을 실행한 다음 설정을 1단계에서 수집한 설정과 비교하면 됩니다.

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a>추가 정보

**다음은 Get-Mailbox** 또는 **Get-OrganizationConfig** cmdlet을 실행할 때 *InPlaceHolds* 속성의 값에 따라 다양한 유형의 보류를 식별하는 방법을 설명하는 표입니다. 자세한 내용은 Exchange Online 사서함에 배치된 보류 유형을 식별하는 [방법을 참조하십시오.](identify-a-hold-on-an-exchange-online-mailbox.md)

앞서 설명한 경우 복구 가능한 항목 폴더의 항목을 성공적으로 삭제하려면 먼저 사서함에서 모든 보류 및 보존 정책을 제거해야 합니다.
  
| 보류 유형 | 예제 값 | 보류를 식별하는 방법 |
|:-----|:-----|:-----|
|소송 대기  <br/> | `True` <br/> |*LitigationHoldEnabled 속성이 LitigationHoldEnabled로* `True` 설정됩니다.  <br/> |
|원본 위치 유지  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |*InPlaceHolds* 속성에는 사서함에 In-Place Hold의 GUID가 포함되어 있습니다. GUID가 In-Place 시작하지 않는 경우 이 보류를 알 수 있습니다.  <br/> Exchange Online PowerShell의 명령을 사용하여 사서함의 보류 In-Place  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` 정보를 얻을 수 있습니다.  <br/> |
| 특정 사서함에 적용된 보안 & 준수 센터의 보존 정책  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> 또는  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |**Get-Mailbox** cmdlet을 실행할 때 *InPlaceHolds* 속성에는 사서함에 적용된 보존 정책의 GUID도 포함되어 있습니다. GUID가 prefix로 시작하기 때문에 보존 정책을 식별할  `mbx` 수 있습니다. 보존 정책의 GUID가 사전으로 시작하는 경우 보존 정책이 비즈니스용 Skype 대화에 적용된  `skp` 것입니다.  <br/> 사서함에 적용되는 보존 정책을 ID로 확인하기 위해 보안 및 준수 센터 PowerShell에서 & 실행합니다. <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>이 명령을 실행할 때 이 또는 사전을  `mbx`  `skp` 제거해야 합니다.  <br/> |
|보안 및 준수 센터의 & 보존 정책  <br/> |값 없음  <br/> 또는  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696` (사서함이 조직 전체 정책에서 제외된 것)  <br/> |**Get-Mailbox** cmdlet을 실행할 때 *InPlaceHolds* 속성이 비어 있는 경우에도 사서함에 하나 이상의 조직 전체 보존 정책이 적용될 수 있습니다.  <br/> 이를 확인하기 위해 Exchange Online PowerShell에서 명령을 실행하여 조직 전체 보존 정책에 대한 GUID 목록을 얻을  `Get-OrganizationConfig | FL InPlaceHolds` 수 있습니다. Exchange 사서함에 적용된 조직 전체 보존 정책의 GUID는 다음과 같은 사전으로  `mbx`  `mbxa3056bb15562480fadb46ce523ff7b02` 시작합니다.  <br/> 사서함에 적용된 조직 전체 보존 정책을 ID로 확인하기 위해 Security & 준수 센터 PowerShell에서 다음 명령을 실행합니다. <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>사서함이 조직 전체 보존 정책에서 제외된 경우 **Get-Mailbox** cmdlet을 실행할 때 보존 정책의 GUID가 사용자 사서함의 *InPlaceHolds* 속성에 표시됩니다. 예를 들어, `-mbx``-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|보안 및 준수 센터의 eDiscovery & 보류  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |*InPlaceHolds* 속성에는 사서함에 배치될 수 있는 보안 & 준수 센터의 eDiscovery 사례와 연결된 모든 보류의 GUID도 포함되어 있습니다. GUID가 prefix로 시작하기 때문에 eDiscovery 케이스 보류라고 알  `UniH` 수 있습니다.  <br/> Security & Compliance Center PowerShell의 cmdlet을 사용하여 사서함의 보류가 연결된 eDiscovery 사례에 대한 정보를 얻을  `Get-CaseHoldPolicy` 수 있습니다. 예를 들어 명령을 실행하여 사서함에 있는 케이스 보류의  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 이름을 표시할 수 있습니다. 이 명령을 실행할 때 반드시 이 명령을  `UniH` 제거해야 합니다.  <br/><br/> 사서함의 보류가 연결된 eDiscovery 사례를 ID로 확인하기 위해 다음 명령을 실행합니다.<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`
