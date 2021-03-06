---
title: Microsoft 365 관리 센터에서 전자 메일 앱 액세스 관리
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: d00b6b83-1f14-4e9c-a2c5-dbd9a92816f4
ROBOTS: NOINDEX, NOFOLLOW
description: 전자 메일, 일정 및 연락처에 액세스하는 데 사용할 수 있는 모바일 앱을 선택하는 방법을 배워야 합니다.
ms.openlocfilehash: f114aa43b4bbade09d53f415aae4c5c033c20694
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400055"
---
# <a name="manage-email-app-access-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 전자 메일 앱 액세스 관리

모바일 전자 메일 액세스 설정을 사용하여 조직의 사용자들이 직장 또는 학교 계정에 액세스하여 전자 메일, 일정 및 연락처에 액세스하는 데 사용할 수 있는 모바일 앱을 선택합니다.
  
> [!IMPORTANT]
> Microsoft Intune을 사용 중이거나 Exchange 관리 센터에서 모바일 장치 관리 설정을 구성하지 않는 한 조직에서 이 설정에 액세스할 수 있습니다. 
  
## <a name="manage-email-app-options"></a>전자 메일 앱 옵션 관리

> [!IMPORTANT]
>  이 기능을 사용하지 않는 경우 사용자 환경이 변경되지 않습니다. 모바일 전자 메일 앱을 사용하여 모바일 장치에서 전자 메일, 일정 및 연락처에 대한 직장 또는 학교 계정에 액세스할 수 있습니다. 
    
1. 관리 센터 미리 보기에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">서비스 &amp; 추가 기능</a> 페이지로 이동합니다. 

2. 모바일 전자 **메일 액세스 옵션** 페이지에서 확인란을 선택한 다음 조직의 사용자가 장치에서 전자 메일 앱을 사용하는 방법을 선택합니다.
  
조직의 사용자가 모바일 장치에서 직장 또는 학교 계정에 액세스하는 방법을 설정하는 옵션을 선택합니다.
  
- **Outlook만** - 조직의 사용자는 모바일 장치에서 Android용 Outlook 또는 iOS용 Outlook 앱을 사용해야 합니다. 
    
- **모든 전자 메일 앱** - 조직의 모든 사용자에게 Outlook을 사용할지 묻는 메시지가 표시되지만 전자 메일 앱을 사용하기로 선택할 수 있습니다. 
    
- **모든 전자 메일** 앱 - 조직의 새 사용자 또는 장치에 Outlook을 사용할지 묻는 메시지가 한 번 표시되지만 전자 메일 앱을 사용할 수 있습니다. 
    
자세한 내용은 모바일 장치에서 전자 메일에 액세스하기 위한 옵션을 [확인합니다.](access-email-from-a-mobile-device.md)
  
## <a name="new-user-or-device-is-activated-in-your-organization"></a>조직에서 새 사용자 또는 장치가 활성화됩니다.

조직의 사용자가 타사 전자 메일 앱 또는 새 장치에 직장 또는 학교 전자 메일을 추가하는 즉시 조직을 대신하여 Microsoft로부터 전자 메일을 **받게 됩니다.** 이 전자 메일을 통해 Outlook 모바일 앱을 사용할 경우의 이점을 알 수 있으며 다운로드 위치에 대한 링크를 제공합니다. 그러면 사용자는 타사 앱을 계속 사용할지 아니면 Outlook 모바일 앱을 사용할지 선택할 수 있습니다. 사용자가 이 전자 메일을 처음 수신한 후 24시간 동안 디바이스가 무단으로 전송됩니다. 전자 메일, 일정 및 연락처 데이터는 업데이트되지 않습니다. Outlook 모바일 앱을 사용하기로 선택한 경우 타사 앱은 계속 에지된 상태로 유지하며 데이터는 Outlook 모바일 앱과만 동기화됩니다. 타사 앱을 계속 사용하기로 결정하면 데이터가 즉시 동기화됩니다. 처음 24시간 동안 아무 작업도 수행되지 않았다면 받은 편지함에서 전자 메일이 제거되고 데이터가 서버에서 자동으로 동기화하기 시작됩니다.
  
## <a name="previously-configured-users-in-your-organization"></a>이전에 조직에서 구성된 사용자

조직의 모든 사용자에게 Outlook을 권장하기로 결정한 경우 새 사용자에 대해 위에서 설명한 환경 외에도 이전에 직장 또는 학교 전자 메일 계정을 타사 앱에 연결한 사용자는 이 설정을 사용하도록 설정한 후 48시간 이내에 조직을 대신하여 **Microsoft로부터** 전자 메일을 받게 됩니다. 이 전자 메일을 통해 Outlook 모바일 앱을 사용할 경우의 이점을 알 수 있으며 다운로드 위치에 대한 링크를 제공합니다. 그러면 사용자는 타사 앱을 계속 사용할지 아니면 Outlook 모바일 앱을 사용할지 선택할 수 있습니다. 사용자가 이 전자 메일을 처음 수신한 후 24시간 동안 디바이스가 무단으로 전송됩니다. 전자 메일, 일정 및 연락처 데이터는 업데이트되지 않습니다. Outlook 모바일 앱을 사용하기로 선택한 경우 타사 앱은 계속 고지된 상태로 유지하며 데이터는 Outlook 모바일 앱과만 동기화됩니다. 타사 앱을 계속 사용하기로 결정하면 데이터가 즉시 동기화됩니다. 처음 24시간 동안 아무 작업도 수행되지 않았다면 받은 편지함에서 전자 메일이 제거되고 데이터가 서버에서 자동으로 동기화하기 시작됩니다. 
  

