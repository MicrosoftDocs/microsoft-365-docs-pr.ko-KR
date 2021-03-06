---
title: Microsoft 365 그룹에 대한 Azure Active Directory 분류 및 민감도 레이블
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
description: 이 문서에서는 클래식 Azure Active Directory 분류 및 민감도 레이블에 대해 설명합니다.
ms.openlocfilehash: 2506e7f467a485878f1e26a23ee1071907b41614
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545662"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Microsoft 365 그룹에 대한 Azure Active Directory 분류 및 민감도 레이블

이 문서에서는 클래식 Azure Active Directory 분류 및 민감도 레이블에 대해 설명합니다.

민감도 레이블은 이러한 [서비스에서 지원됩니다.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#support-for-the-sensitivity-labels)

민감도 레이블에 대한 자세한 내용은 민감도 [레이블에 대한 자세한 정보를 참조하세요.](sensitivity-labels.md)

사이트 및 Microsoft 365 그룹의 민감도 레이블 및 해당 동작에 대한 자세한 내용은 민감도 레이블을 사용하여 [Microsoft Teams, Microsoft 365](sensitivity-labels-teams-groups-sites.md)그룹 및 SharePoint 사이트의 콘텐츠를 보호하세요.

클래식 AAD 분류에서 민감도 레이블로 마이그레이션할 때 모범 사례에 대한 다음 시나리오를 참조합니다.

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>시나리오 1: 테넌트가 문서 및 전자 메일에 대해 클래식 AAD 분류 또는 민감도 레이블을 사용한 적이 없습니다.

- 테넌트 관리자는 AAD powershell cmdlet을 통해 테넌트 플래그 "EnableMIPLabels"를 true로 설정하여 그룹에 대해 민감도 레이블을 사용하도록 설정할 수 있습니다.
- 테넌트 관리자는 Microsoft 365 규정 준수 센터에서 [민감도 레이블을 만듭니다.](https://compliance.microsoft.com)
    - 테넌트 관리자는 암호화 및 워터마크와 같은 파일 및 전자 메일 관련 작업을 선택할 수 있습니다.
    - 테넌트 관리자는 민감도 레이블에 대한 Microsoft 365 그룹 및 SharePoint Online 사이트 관련 작업을 선택할 수 있습니다.
- 테넌트 관리자가 정책을 게시합니다.
- **호환 가능한 워크로드에는** 민감도 레이블이 표시됩니다. 민감도 레이블을 사용하여 그룹을 만들 수 있습니다. 호환 가능한 워크로드는 민감도 레이블을 지원하는 서비스입니다.
- **호환되지 않는 워크로드는** 민감도 레이블을 아직 지원하지 않는 서비스입니다. 그룹은 만들 수 있습니다. 그러나 호환되지 않는 워크로드를 통해 민감도 레이블과 연결될 수는 없습니다. 이러한 그룹을 민감도 레이블과 연결하기 위해 테넌트 관리자는 PowerShell cmdlet을 실행할 수 있습니다.

표 1. 호환 및 호환되지 않는 작업의 동작 - 그룹 만들기, 편집 또는 삭제

|워크로드|그룹 창에 사용자에게 어떤 레이블 목록이 표시하나요?|새 그룹 만들기 |그룹 편집 |그룹 삭제 |
|:-------|:-------|:--------|:--------|:--------|   
|호환   |민감도 레이블. |동작이 변경되지 않습니다. |동작이 변경되지 않습니다. |동작이 변경되지 않습니다. |
|호환되지 않습니다. |민감도 레이블이 표시되지 않습니다. |사용자는 민감도 레이블을 선택하지 않고 그룹을 만들 수 있습니다. <br><br> 관리자는 cmdlet을 실행하여 백그라운드에서 민감도 레이블을 적용할 수 있습니다. |**사례 1:** 이전에 민감도 레이블을 선택하지 않았습니다. 사용자는 그룹을 편집할 수 있습니다.<br><br> **사례 2:** 이전에 cmdlet을 사용하여 백그라운드에서 적용된 민감도 레이블입니다. 사용자는 레이블과 관련한 개인 정보 설정의 잘못된 조합을 선택하는 경우를 제외한 그룹을 성공적으로 편집할 수 있습니다. |동작이 변경되지 않습니다.|

> [!NOTE]
> Outlook 데스크톱 클라이언트(Win 32)의 경우 관리자가 테넌트에서 민감도 레이블을 사용할 수 있도록 설정한 후 사용자가 이전 버전의 Outlook 데스크톱 클라이언트(Win 32)에 있습니다.
>
> - 이전 버전의 Outlook 데스크톱 클라이언트에 민감도 레이블이 표시됩니다.
> - 그러나 사용자가 그룹을 편집하고 민감도 레이블을 사용하여 그룹을 저장하면 선택한 개인 정보 설정이 적용된 민감도 레이블의 개인 정보 설정에 의해 재배치됩니다.
>
> 이전 버전의 Outlook 클라이언트 사용자는 최신 버전으로 업그레이드하는 것이 좋습니다.

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>시나리오 2: 테넌트가 이미 클래식 AAD 분류를 [사용하고 있습니다.](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>사례 A: 테넌트가 문서 및 전자 메일에 대해 민감도 레이블을 사용한 적이 없습니다.

1. Microsoft [365](https://compliance.microsoft.com)규정 준수 센터에서 기존 클래식 Azure AD 레이블과 동일한 이름으로 민감도 레이블을 만드는 것이 좋습니다.
2. PowerShell cmdlet을 사용하여 이름 매핑을 사용하여 이러한 민감도 레이블을 기존 Microsoft 365 그룹 및 SharePoint 사이트에 적용합니다.
3. 관리자는 클래식 Azure AD 레이블을 삭제할 수 있습니다.
    - 호환 가능한 워크로드는 이러한 민감도 레이블 및 그룹이 생성되는 모습을 보여 주며, 이러한 레이블을 통해 생성됩니다.
    - 호환되지 않는 워크로드는 그룹을 만들 때 작동하지만 민감도 레이블이 연결되지 않습니다.
4. 관리자는 PowerShell cmdlet을 실행하여 레이블이 없는 이러한 그룹에 민감도 레이블을 적용할 수 있습니다.
    - 또는 관리자는 클래식 Azure AD 레이블을 유지할 수 있습니다.
        - 호환 가능한 워크로드는 이러한 민감도 레이블을 표시하고 그룹이 함께 만들어집니다. 호환 가능한 워크로드는 민감도 레이블을 지원하는 서비스입니다.
        - 호환되지 않는 워크로드는 그룹을 만들 때 작동하며 클래식 Azure AD 레이블을 표시합니다. 이러한 클래식 Azure AD 레이블은 호환되지 않는 워크로드를 사용하여 만든 이러한 그룹에 연결됩니다.
5. 관리자는 PowerShell cmdlet을 실행하여 클래식 Azure AD 레이블을 사용하여 이러한 그룹에 민감도 레이블을 적용하는 것이 좋습니다.

표 2. 호환 및 호환되지 않는 작업의 동작 - 그룹 만들기, 편집 또는 삭제

|워크로드|그룹 창에 사용자에게 어떤 레이블 목록이 표시하나요?|새 그룹 만들기 |그룹 편집 |그룹 삭제 |
|:-------|:-------|:--------|:--------|:--------|   
|호환   |민감도 레이블. |동작이 변경되지 않습니다. |동작이 변경되지 않습니다. |동작이 변경되지 않습니다. |
|호환되지 않습니다. |이전 클래식 AAD 레이블 |사용자는 클래식 Azure AD 레이블이 선택된 그룹을 만들 수 있습니다. <br><br>관리자는 cmdlet을 실행하여 백그라운드에서 민감도 레이블을 적용할 수 있습니다. |**사례 1:** 이전에 민감도 레이블을 선택하지 않았습니다. 사용자는 그룹을 편집할 수 있습니다.<br><br> **사례 2:** 이전에 선택한 클래식 AAD 레이블입니다. 사용자는 그룹을 편집할 수 있습니다.<br><br> **사례 3:** 이전에 cmdlet을 사용하여 백그라운드에서 적용된 민감도 레이블입니다. 사용자가 레이블과 관련한 개인 정보 설정의 잘못된 조합을 선택하는 경우를 제외한 그룹을 편집할 수 있습니다. |사용자는 그룹을 삭제할 수 있습니다. |

> [!NOTE]
> Outlook 데스크톱 클라이언트(Win 32)의 경우 관리자가 테넌트에서 민감도 레이블을 사용할 수 있도록 설정한 후 사용자가 이전 버전의 Outlook 데스크톱 클라이언트(Win 32)에 있습니다.
>
> - 이전 버전의 Outlook 데스크톱 클라이언트에 민감도 레이블이 표시됩니다.
> - 그러나 사용자가 그룹을 편집하고 민감도 레이블을 사용하여 그룹을 저장하면 선택한 개인 정보 설정이 적용된 민감도 레이블의 개인 정보 설정에 의해 재배치됩니다.
>
> 이전 버전의 Outlook 클라이언트 사용자는 최신 버전으로 업그레이드하는 것이 좋습니다.

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>사례 B: 테넌트가 문서 및 전자 메일에 민감도 레이블을 사용함

1. 관리자가 테넌트 플래그 'EnableMIPLabels'를 true로 설정하여 테넌트에서 민감도 레이블 기능을 사용하도록 설정하는 즉시 그룹/사이트/팀에서 문서 및 전자 메일 민감도 레이블을 만들고 편집하는 대화 상자가 나타납니다.
2. 관리자는 동일한 문서 및 전자 메일 민감도 레이블을 사용하여 그룹/사이트/팀에 대해 관련 그룹 설정을 지정하여 개인 정보 및 외부 사용자 액세스를 적용할 수 있습니다.
    1. Microsoft [365 규정 준수](https://compliance.microsoft.com)센터에서 사이트 및 **그룹 탭을** 선택합니다.
    2. 문서 또는 전자 메일 민감도 레이블을 편집합니다.

## <a name="sample-script"></a>예제 스크립트

클래식 AAD 레이블이 있는 그룹을 민감도 레이블로 마이그레이션하는 샘플 스크립트는 클래식 Azure AD 그룹 분류를 [참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)
