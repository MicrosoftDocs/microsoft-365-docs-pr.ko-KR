---
title: Office 스크립트 설정 관리
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
search.appverid: MET150
description: 조직의 사용자에 대한 Office 스크립트 설정을 관리하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058426"
---
# <a name="manage-office-scripts-settings"></a>Office 스크립트 설정 관리

Office 스크립트를 사용하면 웹에서 Excel에서 스크립트를 기록, 편집 및 실행하여 작업을 자동화할 수 있습니다. Office 스크립트는 Power Automate와 함께 작동하며 사용자는 Excel Online(비즈니스) 커넥터를 사용하여 통합 문서에서 스크립트를 실행합니다. Microsoft 365 관리자는 Microsoft 365 관리 센터에서 Office 스크립트 설정을 관리할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

- Office 스크립트 설정을 관리하려면 전역 관리자 되어야 합니다. 자세한 내용은 관리자 [역할에 대한 정보를 참조하세요.](../add-users/about-admin-roles.md)

- 조직의 사용자에게 다음 계획 중 하나와 같은 Office 데스크톱 앱에 대한 액세스가 포함된 Microsoft 365 또는 Office 365 상업용 또는 EDU 요금제에 대한 유효한 라이선스가 있어야 합니다.

    - Microsoft 365 Business Standard
    - 비즈니스용 Microsoft 365 앱
    - 엔터프라이즈용 Microsoft 365 앱
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Office 스크립트의 가용성 및 스크립트 공유 관리

1. Microsoft 365 관리 센터에서 설정  \> **Org 설정** 서비스 \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">탭으로</a> 이동합니다.

2. **Office 스크립트를 선택합니다.**

3. Office 스크립트는 기본적으로 설정되어 있으며 조직의 모든 사람이 해당 기능에 액세스하여 사용하여 스크립트를 공유할 수 있습니다. 조직에 대한 Office 스크립트를 해제하기 위해 사용자가 **웹에서 Excel에서** 작업을 자동화할 수 있도록 선택을 취소합니다.

4. 이전에 조직의 Office 스크립트를 해제한 후 다시 설정하려면 사용자가 **웹에서 Excel에서** 작업을 자동화할 수 있도록 선택한 다음 기능에 액세스하고 사용할 수 있는 사용자를 지정합니다.

    - 조직의 모든 사용자가 Office 스크립트에 액세스하고 사용할  수 있도록 허용하기 위해 모든 사용자(기본값)를 선택된 그대로 두면 됩니다.

    - 특정 그룹의 구성원만 Office 스크립트에 액세스하고 사용할 수 있도록 허용하려면 특정 그룹을 선택한 다음 그룹의 이름 또는 전자 메일 별칭을 입력하여 허용 목록에 추가합니다. 허용 목록에 그룹 하나만 추가할 수 있으며 다음 유형 중 하나에 해당해야 합니다.
        - Microsoft 365 그룹
        - 메일 그룹
        - 보안 그룹
        - 메일 사용 가능 보안 그룹
    
        다양한 유형의 그룹에 대한 자세한 내용은 [그룹 비교를 참조합니다.](../create-groups/compare-groups.md)

5. Office 스크립트에 액세스할 수 있는 사용자가 조직의 다른 사용자와 스크립트를 공유할 수 있도록 허용하려면 Office 스크립트에 액세스할 수 있는 사용자가 조직의 다른 사용자와 스크립트를 공유할 수 있도록 **합니다.** 조직 외부의 스크립트 공유는 허용되지 않습니다.
 
    > [!NOTE]
    > 나중에 조직에 대한 스크립트 공유를 해제하는 경우 사용자는 이전에 공유한 스크립트를 실행할 수 있습니다.
 
6. Office 스크립트에 액세스할 수 있는 사용자를 지정하여 스크립트를 공유할 수 있습니다.
    
    - Office 스크립트에 액세스할 수 있는 모든 사용자가 스크립트를  공유할 수 있도록 허용하기 위해 모든 사용자(기본값)를 선택된 그대로 남겨 두면 됩니다.

    - Office 스크립트에 액세스할 수 있는 특정 그룹의 구성원만 스크립트를 공유할 수 있도록 허용하려면 특정 그룹을 선택한 다음 그룹의 이름 또는 전자 메일 별칭을 입력하여 허용 목록에 추가합니다. 허용 목록에 그룹 하나만 추가할 수 있으며 다음 유형 중 하나에 해당해야 합니다.
        - Microsoft 365 그룹
        - 메일 그룹
        - 보안 그룹
        - 메일 사용 가능 보안 그룹
    
        다양한 유형의 그룹에 대한 자세한 내용은 [그룹 비교를 참조합니다.](../create-groups/compare-groups.md)

7. 사용자가 Power Automate 흐름 내에서 Office 스크립트를 실행할 수 있도록 허용하려면 Office 스크립트에 액세스할 수 있는 사용자가 Power Automate를 사용하여 스크립트를 실행하도록 **허용을 선택합니다.** 이를 통해 사용자는 [Excel Online(비즈니스) 커넥터의](/connectors/excelonlinebusiness) 실행 스크립트 옵션을 사용하여 흐름 단계를 추가할 **수** 있습니다.

    - Office 스크립트에 액세스할 수 있는 모든 사용자가 흐름에서 스크립트를  사용할 수 있도록 허용하기 위해 모든 사용자(기본값)를 선택된 그대로 남겨 두면 됩니다.

    - Office 스크립트에 액세스할 수 있는 특정 그룹의 구성원만 흐름에서 스크립트를 사용할 수 있도록 허용하려면 특정 그룹을 선택한 다음 그룹의 이름 또는 전자 메일 별칭을 입력하여 허용 목록에 추가합니다. 허용 목록에 그룹 하나만 추가할 수 있으며 다음 유형 중 하나에 해당해야 합니다.
        - Microsoft 365 그룹
        - 메일 그룹
        - 보안 그룹
        - 메일 사용 가능 보안 그룹

        다양한 유형의 그룹에 대한 자세한 내용은 [그룹 비교를 참조합니다.](../create-groups/compare-groups.md)

    - 데이터 손실 방지 정책이 영향을 미칠 수 있는 방법을 포함하여 Power Automate에서 Office 스크립트를 사용하는 방법에 대한 자세한 내용은 [Power Automate를](/office/dev/scripts/develop/power-automate-integration)사용하여 Office 스크립트 실행을 참조합니다.

8. **저장** 을 선택합니다.

    Office 스크립트 설정 변경 내용을 적용하는 데 최대 48시간이 걸릴 수 있습니다.

## <a name="next-steps"></a>다음 단계

Office 스크립트는 Power Automate와 함께 작동하기 때문에 사용자가 Office 스크립트를 사용하는 동안 조직의 데이터가 보호되도록 기존 DLP(데이터 손실 방지) 정책을 검토하는 것이 좋습니다. 자세한 내용은 [DLP(데이터 손실 방지) 정책을 참조하세요.](/power-automate/prevent-data-loss)

## <a name="related-content"></a>관련 콘텐츠

[Office 스크립트 기술 설명서(링크](/office/dev/scripts/) 페이지)\
[Excel의 Office 스크립트](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) 소개(문서)\
[Excel에서 웹용 Office 스크립트](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) 공유(문서)\
[웹에서 Excel에서 Office 스크립트 기록,](/office/dev/scripts/tutorials/excel-tutorial) 편집 및 만들기(문서)
