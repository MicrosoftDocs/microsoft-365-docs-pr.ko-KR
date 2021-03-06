---
title: 고객 키 관리
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 고객 키를 설정한 후 AKV 키를 복원하고 사용 권한 및 데이터 암호화 정책을 관리하여 키 관리 방법을 배워야 합니다.
ms.openlocfilehash: de85edd5c53fc2b76be4361575e1a85655c0f297
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547088"
---
# <a name="manage-customer-key"></a>고객 키 관리

Office 365에 대한 고객 키를 설정한 후 이 문서에 설명된 바와 같이 키를 관리할 수 있습니다. 관련 항목에서 고객 키에 대한 자세한 내용을 참조하세요.

## <a name="restore-azure-key-vault-keys"></a>Azure Key Vault 키 복원

복원을 수행하기 전에 소프트 삭제에서 제공하는 복구 기능을 사용 합니다. 고객 키와 함께 사용되는 모든 키는 소프트 삭제를 사용하도록 설정해야 합니다. 소프트 삭제는 재활용란처럼 사용하며 복원할 필요 없이 최대 90일 동안 복구할 수 있습니다. 복원은 키 또는 키 자격 증명 모음이 손실되는 경우와 같은 극단적인 상황이나 비정상적인 상황에서만 필요합니다. 고객 키와 함께 사용할 키를 복원해야 하는 경우 Azure PowerShell에서 다음과 Restore-AzureKeyVaultKey cmdlet을 실행합니다.
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

예시:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

키 자격 증명 모음에 이름이 같은 키가 이미 포함되어 있는 경우 복원 작업이 실패합니다. Restore-AzKeyVaultKey 이름을 포함하여 키의 모든 키 버전 및 모든 메타데이터를 복원합니다.
  
## <a name="manage-key-vault-permissions"></a>주요 자격 증명 모음 사용 권한 관리

필요한 경우 키 자격 증명 모음 권한을 제거할 수 있는 몇 가지 cmdlet을 사용할 수 있습니다. 예를 들어 직원이 팀을 떠날 때 사용 권한을 제거해야 할 수 있습니다. 이러한 각 작업에 대해 Azure PowerShell을 사용합니다. Azure Powershell에 대한 자세한 내용은 [Azure PowerShell 개요를 참조하세요.](https://docs.microsoft.com/powershell/azure/)

키 자격 증명 모음 사용 권한을 보시다가 자격 증명 Get-AzKeyVault 실행합니다.

```powershell
Get-AzKeyVault -VaultName <vault name>
```

예시:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

관리자의 사용 권한을 제거하려면 다음 Remove-AzKeyVaultAccessPolicy 실행합니다.
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

예시:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>고객 키를 사용하여 DEP(데이터 암호화 정책) 관리

고객 키는 서비스마다 다르게 DEP를 처리합니다. 예를 들어 각 서비스에 대해 다른 수의 DEP를 만들 수 있습니다.

**Exchange Online 및 비즈니스용 Skype:** 최대 50개 DEP를 만들 수 있습니다. 자세한 내용은 Exchange Online 및 비즈니스용 Skype에서 사용할 DEP(데이터 암호화 정책 [만들기)를 참조하세요.](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

**SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일:** DEP는 지리적 위치(지리적 위치)의 데이터에 _적용됩니다._ Office 365의 Multi-Geo 기능을 사용하는 경우 지역당 하나의 DEP를 만들 수 있습니다. Multi-Geo를 사용하지 않는 경우 DEP를 하나 만들 수 있습니다. 일반적으로 고객 키를 설정할 때 DEP를 생성합니다. 자세한 내용은 각 SharePoint Online 및 비즈니스용 [OneDrive 지리적으로 DEP(데이터](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)암호화 정책) 만들기를 참조하세요.

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype에 대해 만든 DEP 보기

Get-DataEncryptionPolicy PowerShell cmdlet을 사용하여 Exchange Online 및 비즈니스용 Skype에 대해 만든 모든 DEP 목록을 보시고 다음 단계를 완료합니다.

1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [Exchange Online PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. 조직의 모든 DEP를 반환하기 위해 매개 변수 없이 Get-DataEncryptionPolicy cmdlet을 실행합니다.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   cmdlet에 대한 Get-DataEncryptionPolicy [Get-DataEncryptionPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy)

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>클라우드로 사서함을 마이그레이션하기 전에 DEP 할당

DEP를 할당하면 Microsoft 365는 마이그레이션 중에 할당된 DEP를 사용하여 사서함의 콘텐츠를 암호화합니다. 이 프로세스는 사서함을 마이그레이션하고 DEP를 할당한 다음 암호화가 진행될 때까지 기다리는 것보다 더 효율적이며, 이 작업에는 몇 시간 또는 며칠이 걸릴 수 있습니다.

OFFICE 365로 마이그레이션하기 전에 사서함에 DEP를 할당하려면 Exchange Online PowerShell에서 Set-MailUser cmdlet을 실행합니다.

1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [Exchange Online PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. cmdlet을 Set-MailUser 실행합니다.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   여기서 *GeneralMailboxOrMailUserIdParameter는* 사서함을 지정하고 *DataEncryptionPolicyIdParameter는* DEP의 ID입니다. 이 cmdlet에 대한 Set-MailUser [Set-MailUser를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>사서함에 할당된 DEP 확인

사서함에 할당된 DEP를 확인하기 위해 Get-MailboxStatistics cmdlet을 사용 합니다. 이 cmdlet은 GUID(고유 식별자)를 반환합니다.
  
1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [Exchange Online PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   *GeneralMailboxOrMailUserIdParameter는* 사서함을 지정하고 DataEncryptionPolicyID는 DEP의 GUID를 반환합니다. 이 cmdlet에 대한 Get-MailboxStatistics [Get-MailboxStatistics를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics)
  
2. Get-DataEncryptionPolicy cmdlet을 실행하여 사서함이 할당된 DEP의 이름을 찾을 수 있습니다.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   여기서 *GUID는* 이전 단계에서 Get-MailboxStatistics cmdlet에서 반환된 GUID입니다.

## <a name="verify-that-customer-key-has-finished-encryption"></a>고객 키가 암호화를 완료한지 확인

고객 키를 롤링하거나 새 DEP를 할당하거나 사서함을 마이그레이션한 경우 이 섹션의 단계를 사용하여 암호화가 완료되도록 합니다.

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype에 대한 암호화 완료 확인

사서함 암호화에는 시간이 걸릴 수 있습니다. DEP를 변경하거나 사서함에 DEP를 처음 할당할 때 암호화 유효성을 검사하기 전에 72시간을 기다리는 것이 좋습니다.
  
이 Get-MailboxStatistics cmdlet을 사용하여 사서함이 암호화되어 있는지 확인할 수 있습니다.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

사서함이 암호화된 경우 IsEncrypted 속성은 **true** 값을 반환하고 사서함이 암호화되지 않은 경우 **false** 값을 반환합니다.

사서함 이동을 완료하는 데 시간은 사서함의 크기에 따라 다를 수 있습니다. 새 DEP를 할당한 후 72시간이 지난 후에 고객 키가 사서함을 완전히 암호화하지 않은 경우 Microsoft 지원에 도움을 요청합니다. 로컬 New-MoveRequest 더 이상 이 cmdlet을 사용할 수 없습니다. 추가 [정보는 이 공지 사항을](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) 참조하십시오.

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 암호화 완료 확인

다음과 같이 Get-SPODataEncryptionPolicy cmdlet을 실행하여 암호화 상태를 검사합니다.

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

이 cmdlet의 출력에는 다음이 포함됩니다.
  
- 기본 키의 URI입니다.

- 보조 키의 URI입니다.

- 지리적 암호화 상태입니다. 가능한 상태는 다음과 같습니다.

  - **등록이 등록되지 않은 경우:** 고객 키 암호화가 아직 적용되지 않았습니다.

  - **등록:** 고객 키 암호화가 적용되고 파일이 암호화 중입니다. 지리적 키가 등록되는 경우 암호화 진행률을 모니터링할 수 있도록 지리적으로 완료된 사이트의 백분율에 대한 정보도 표시됩니다.

  - **등록된:** 고객 키 암호화가 적용되고 모든 사이트의 모든 파일이 암호화되었습니다.

  - **롤링:** 키 롤이 진행 중입니다. 지리적 키가 롤링되는 경우 진행 상황을 모니터링할 수 있도록 키 롤 작업을 완료한 사이트의 비율에 대한 정보도 표시됩니다.

## <a name="unassign-a-dep-from-a-mailbox"></a>사서함에서 DEP의 제거

Set-mailbox PowerShell cmdlet을 사용하여 사서함에서 DEP를 제거하고 를 으로 `DataEncryptionPolicy` 설정하면 `$NULL` 됩니다. 이 cmdlet을 실행하면 현재 할당된 DEP의 할당을 해제하고 기본 Microsoft 관리 키와 연결된 DEP를 사용하여 사서함을 다시 암호화합니다. Microsoft 관리 키에 사용되는 DEP의 사용은 Unassignign을 unassignens(Microsoft 관리 키)할 수 없습니다. Microsoft 관리 키를 사용하지 않는 경우 사서함에 다른 DEP를 할당할 수 있습니다.

PowerShell cmdlet을 사용하여 사서함에서 DEP를 Set-Mailbox 다음 단계를 완료합니다.

1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [Exchange Online PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. cmdlet을 Set-Mailbox 실행합니다.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>키를 해지하고 데이터 제거 경로 프로세스 시작

가용성 키를 포함하여 모든 루트 키의 해지 제어 고객 키는 규정 요구 사항의 종료 계획 측면을 제어할 수 있도록 합니다. 데이터를 삭제하고 서비스를 종료하기 위해 키를 해지하기로 결정한 경우 데이터 삭제 프로세스가 완료되면 서비스에서 가용성 키를 삭제합니다.

Microsoft 365는 데이터 제거 경로를 감사하고 유효성을 검사합니다. 자세한 내용은 Service Trust Portal에서 사용할 수 있는 SSAE 18 SOC 2 [보고서를 참조하세요.](https://servicetrust.microsoft.com/) 또한 Microsoft는 다음 문서를 권장합니다.

- [Microsoft 클라우드의 금융 기관에 대한 위험 평가 및 규정 준수 가이드](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [O365 종료 계획 고려 사항](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

데이터 제거 경로는 서비스마다 약간 다릅니다.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype에 대한 고객 키 및 가용성 키 해지

Exchange Online 및 비즈니스용 Skype에 대한 데이터 삭제 경로를 시작할 때 DEP에 대해 영구 데이터 삭제 요청을 설정할 수 있습니다. 이렇게 하면 DEP가 할당된 사서함 내에서 암호화된 데이터가 영구적으로 삭제됩니다.

한 번의 DEP에 대해 PowerShell cmdlet을 실행할 수만 있는 경우 데이터 삭제 경로를 시작하기 전에 모든 사서함에 단일 DEP를 다시 배정할 수 있습니다.

> [!WARNING]
> 데이터 삭제 경로를 사용하여 사서함의 하위 집합을 삭제하지 않습니다. 이 프로세스는 서비스를 종료하는 고객에게만 사용할 수 있습니다.

데이터 제거 경로를 시작하고 다음 단계를 완료합니다.

1. Azure Key Vaults에서 "O365 Exchange Online"에 대한 래핑 및 래핑 제거

2. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [Exchange Online PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

3. 삭제할 사서함이 포함된 각 DEP에 대해 다음과 같이 [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) cmdlet을 실행합니다.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   명령이 실패하면 이 작업의 앞부분에서 지정한 대로 Azure Key Vault의 두 키에서 Exchange Online 사용 권한을 제거해야 합니다.Set-DataEncryptionPolicy cmdlet을 사용하여 PermanentDataPurgeRequested 스위치를 설정하면 더 이상 이 DEP를 사서함에 할당할 수 없습니다.

4. Microsoft 지원에 문의하여 데이터 제거 eDocument를 요청합니다.

    요청 시 Microsoft는 데이터 선택을 승인하고 승인하기 위해 법적 문서를 전송합니다. 등록하는 동안 FastTrack 제품에서 승인자로 등록한 조직의 사람이 이 문서에 서명해야 합니다. 일반적으로 이 임원 또는 다른 지정된 사람은 조직을 대신하여 문서에 서명할 수 있는 법적 권한이 있는 임원 또는 기타 지정된 사람입니다.

5. 담당자가 법적 문서에 서명한 후 Microsoft에 반환합니다(일반적으로 eDoc 서명을 통해).

    Microsoft가 법적 문서를 받으면 Microsoft는 cmdlet을 실행하여 정책을 먼저 삭제하는 데이터 삭제를 트리거하고 사서함을 영구 삭제로 표시한 다음 가용성 키를 삭제합니다. 데이터 삭제 프로세스가 완료되면 데이터가 제거되고 Exchange Online에 액세스하지 못하며 복구할 수 없습니다.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 고객 키 및 가용성 키 해지

SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 데이터 삭제 경로를 시작하려면 다음 단계를 완료합니다.

1. Azure Key Vault 액세스를 해지합니다. 모든 주요 자격 증명 모음 관리자는 액세스를 해지하는 데 동의해야 합니다.

   SharePoint Online용 Azure Key Vault는 삭제하지 않습니다. 주요 자격 증명 모음은 여러 SharePoint Online 테넌트 및 DEP에서 공유할 수 있습니다.

2. 가용성 키를 삭제하려면 Microsoft에 문의하십시오.

    가용성 키를 삭제하기 위해 Microsoft에 문의하면 법적 문서가 전송됩니다. 등록하는 동안 FastTrack 제품에서 승인자로 등록한 조직의 사람이 이 문서에 서명해야 합니다. 일반적으로 이 임원 또는 다른 지정된 사람이 조직을 대신하여 문서에 서명할 수 있는 법적 권한을 가집니다.

3. 담당자가 법적 문서에 서명하면 Microsoft에 반환합니다(일반적으로 eDoc 서명을 통해).

   Microsoft에서 법적 문서를 받으면 cmdlet을 실행하여 테넌트 키, 사이트 키 및 문서별 모든 개별 키의 암호화 삭제를 수행하여 키 계층 구조가 끊어지는 것을 트리거합니다. 데이터 삭제 cmdlet이 완료되면 데이터가 삭제됩니다.

## <a name="related-articles"></a>관련 문서

- [고객 키를 사용한 서비스 암호화](customer-key-overview.md)

- [가용성 키에 대해 자세히](customer-key-availability-key-understand.md)

- [고객 키 설정](customer-key-set-up.md)

- [고객 키 또는 가용성 키 롤 또는 회전](customer-key-availability-key-roll.md)

- [고객 Lockbox](customer-lockbox-requests.md)

- [서비스 암호화](office-365-service-encryption.md)
