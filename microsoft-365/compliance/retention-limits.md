---
title: 보존 정책 및 보존 레이블 정책에 대한 제한 사항
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 보존 정책 및 보존 레이블 정책에 대한 정책당 최대 정책 및 항목 수 이해
ms.openlocfilehash: 547c6396fa9bfcba6dbd271f09a7ea59f9acf170
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261593"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a>보존 정책 및 보존 레이블 정책에 대한 제한 사항

>*[보안 및 규정 준수에 대한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

[보존 정책 및 보존 레이블 정책](retention.md#retention-policies-and-retention-labels)을 사용하여 조직의 데이터를 자동으로 보존하거나 삭제하는 경우 알아야 할 최대 수가 있습니다.

## <a name="maximum-number-of-policies-per-tenant"></a>테넌트당 최대 정책 수

단일 테넌트의 경우 최대 10,000개 정책(모든 구성)을 사용할 수 있습니다. 이 최대 수에는 DLP 정책과 같은 다양한 보존 정책과 기타 규정 준수 정책이 포함됩니다.

워크로드당 최대 보존 정책 수:

- Exchange Online(모든 구성): 1,800
- SharePoint 또는 OneDrive: (모든 사이트가 자동으로 포함됨): 13
- SharePoint 또는 OneDrive(특정 위치 포함 또는 제외): 2,600

## <a name="maximum-number-of-items-per-policy"></a>정책당 최대 항목 수

선택적 구성을 사용하여 특정 사용자, 특정 Microsoft 365 그룹 또는 특정 사이트에 대한 보존 설정의 범위를 지정하는 경우 다음의 정책별 몇 가지 제한 사항을 고려해야 합니다. 

보존 정책당 최대 항목 수:

  - 1,000개의 사서함(사용자 사서함 또는 그룹 사서함)
  - 1,000개의 Microsoft 365 그룹
  - Teams 비공개 채팅에 참여하는 1,000명의 사용자
  - 100개의 사이트(OneDrive 또는 SharePoint)

이러한 제한 사항은 정책당로 적용되므로 특정 포함 또는 제외를 사용하여 이러한 수를 검토해야 하는 경우 동일한 보존 설정을 가진 추가 정책을 생성할 수 있습니다. 이러한 이유로 여러 보존 정책을 사용하는 일부 [예제 시나리오 및 솔루션](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers)은 다음 섹션을 참조하십시오.

그러나 여러 정책으로 인해 관리 오버헤드가 증가하므로 포함 및 제외가 정말 필요한지 확인해야 합니다. 전체 위치에 적용되는 기본 구성에는 제한이 없으며, 이 구성 선택은 여러 정책을 만들고 유지하는 것보다 더 나은 솔루션이 될 수 있습니다.

> [!TIP]
> 이 시나리오에 대해 여러 정책을 생성하고 유지 관리해야하는 경우 보다 효율적인 구성을 위해 [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels)을 사용하는 것이 좋습니다.

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a>최대 수 초과를 방지하는 여러 정책을 사용하는 예

다음 예제는 보존 정책의 위치만 지정할 수 없는 경우에 대한 몇 가지 설계 솔루션을 제공하며, 이전 섹션에서 설명한 최대 항목 수를 고려해야 합니다.

Exchange 예제:

- **요구 사항**: 사용자 사서함이 40,000개 이상인 조직에서 대부분의 사용자는 7년 동안 전자 메일을 보존해야 하지만 식별된 사용자(425명)의 하위 집합은 5년 동안만 전자 메일을 보존해야 합니다.

- **솔루션**: 보존 기간이 7년인 Exchange 전자 메일에 대해 하나의 보존 정책을 생성하고 사용자 하위 집합을 제외합니다. 그런 다음 보존 기간이 5년인 Exchange 전자 메일에 대한 두 번째 보존 정책을 생성하고 사용자 하위 집합을 포함합니다. 
    
    두 경우 모두 포함 및 제외된 수는 단일 정책에 대해 지정된 최대 사서함 수보다 적으며, 두 번째 정책보다 [보존 기간이 길기 때문에](retention.md#the-principles-of-retention-or-what-takes-precedence) 사용자 하위 집합은 첫 번째 정책에서 명시적으로 제외되어야 합니다. 사용자 하위 집합에서 더 긴 보존 정책이 필요한 경우 첫 번째 정책에서 제외할 필요가 없습니다.
     
    이 솔루션을 사용하면 새로 참가한 사람이 있으면 해당 우편함이 7년 동안 자동으로 첫 번째 정책에 포함되며 지원되는 최대 수에 영향을 미치지 않습니다. 그러나 5년 보존 기간이 필요한 새 사용자는 포함 및 제외 수에 추가되며 이 제한은 1,000에 도달하게 됩니다.

SharePoint 예제

- **요구 사항**: 한 조직에서 SharePoint 사이트는 수천 개이지만 2,000개 사이트만 10년 보존 기간이 필요하며 8,000개 사이트에서는 4년 보존 기간이 필요합니다.

- **솔루션**: 100개의 특정 사이트를 포함하는 10년의 보존 기간으로 SharePoint용 20개 보존 정책을 생성하고, 100개의 특정 사이트를 포함하는 4년의 보존 기간으로 SharePoint용 80개 보존 정책을 생성합니다.
    
    모든 SharePoint 사이트를 보유할 필요는 없으므로 특정 사이트를 지정하는 보존 정책을 생성해야 합니다. 보존 정책은 100개 이상의 지정된 사이트를 지원하지 않으므로 두 보존 기간에 대해 여러 정책을 생성해야 합니다. 이러한 보존 정책에는 최대 개수의 사이트가 포함되므로 보존해야 하는 다음 새 사이트에는 보존 기간에 관계없이 새 보존 정책이 필요합니다.

