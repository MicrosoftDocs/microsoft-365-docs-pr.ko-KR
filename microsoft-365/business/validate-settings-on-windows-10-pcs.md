---
title: Windows 10 PC에서 앱 보호 설정 유효성 검사
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
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: 비즈니스용 Microsoft 365 앱 보호 설정이 사용자의 Windows 10 디바이스에 적용된 것을 확인하는 방법을 확인합니다.
ms.openlocfilehash: 39aee3bc811cb0090d58f9a282de7a8162c097b3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403593"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Windows 10 PC에서 장치 보호 설정 유효성 검사

## <a name="verify-that-windows-10-device-policies-are-set"></a>Windows 10 장치 정책이 설정되어 있는지 확인

장치 [정책을](protection-settings-for-windows-10-pcs.md)설정한 후 정책이 사용자의 장치에 적용되는 데 최대 몇 시간이 걸릴 수 있습니다. 사용자 장치에서 다양한 Windows 설정 화면을 확인하여 정책이 적용된지 확인할 수 있습니다. 사용자가 Windows 10 장치에서 Windows 업데이트 및 Windows Defender 바이러스 백신 설정을 수정할 수 없는 경우 많은 옵션이 회색으로 표시됩니다.
  
1. 설정 **업데이트 보안** Windows 업데이트 다시 시작 옵션으로 이동하여 모든 설정이 \> **&amp;** \>  \>  회색으로 표시되어 있는지 확인합니다. 
    
    ![모든 다시 시작 옵션은 회색으로 표시됩니다.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. 설정 업데이트 **보안** Windows 업데이트 고급 옵션으로 이동하여 모든 설정이 \> **&amp;** \>  \>  회색으로 표시되어 있는지 확인합니다. 
    
    ![Windows 고급 업데이트 옵션은 모두 회색으로 표시됩니다.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** Advanced \> **options** Choose how \> **updates are delivered.**
    
    일부 설정이 조직에서 숨겨지거나 관리되는 메시지가 빨간색으로 표시되고 모든 옵션이 회색으로 표시될 수 있습니다.
    
    ![업데이트가 배달되는 방법을 선택하면 조직에서 설정을 숨기거나 관리할 수 있습니다.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Windows Defender 보안 센터를 열려면 설정  업데이트 보안으로 이동하여 Windows Defender 보안 센터 바이러스 스레드 보호 바이러스 Windows Defender 설정 \> **&amp;** \>  \>  \> **&amp;** \> **&amp; 열기를 클릭합니다.** 
    
5. 모든 옵션이 회색으로 표시 지어 있는지 확인 합니다. 
    
    ![바이러스 및 위협 방지 설정은 회색으로 표시됩니다.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>관련 항목

[비즈니스용 Microsoft 365 설명서 및 리소스](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[비즈니스용 Microsoft 365 시작](microsoft-365-business-overview.md)
  
[비즈니스용 Microsoft 365 관리](manage.md)
  
[Windows 10 PC용 장치 구성 설정](protection-settings-for-windows-10-pcs.md)
  

