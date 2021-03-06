---
title: Windows 장치에서 Office 2013에 대해 최신 인증 사용
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: 2013이 설치된 장치에 대해 최신 인증을 사용하도록 레지스트리 Microsoft Office 방법을 학습합니다.
ms.openlocfilehash: 2a4be82328d391db7808cb9197ce259275b567c6
ms.sourcegitcommit: bf9e0091e5bdc78d9b23be64583eb816bb059eb2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2021
ms.locfileid: "50758931"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Windows 장치에서 Office 2013에 대해 최신 인증 사용

Office 2013이 설치되어 있는 Windows 장치에 대해 최신 인증을 사용하려면 특정 레지스트리 키를 설정해야 합니다.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Office 2013 클라이언트에 대해 최신 인증 사용

> [!NOTE]
> Office 2016 클라이언트에 대해 이미 최신 인증이 사용되고 있는 경우 Office 2016에 대해 레지스트리 키를 설정할 필요가 없습니다. 
  
Microsoft Office 2013이 설치되었고 Windows를 실행 중인 장치(예: 노트북 및 태블릿)에 대해 최신 인증을 사용하려면 다음 레지스트리 키를 설정해야 합니다. 최신 인증을 사용할 각 장치에서 키를 설정해야 합니다.
  
|**레지스트리 키**|**유형**|**값** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
   
레지스트리 키를 설정한 후 Office 2013 장치 앱이 Microsoft 365에서 [MFA(다단계](set-up-multi-factor-authentication.md) 인증)를 사용하도록 설정할 수 있습니다. 
  
현재 클라이언트 앱에 로그인한 경우 변경 내용을 적용하려면 로그아웃 후 다시 로그인해야 합니다. 그러지 않으면 ADAL ID가 설정될 때까지 MRU 및 로밍 설정을 사용할 수 없습니다.
  
## <a name="disable-modern-authentication-on-devices"></a>장치에서 최신 인증을 사용하지 않음

장치에서 최신 인증을 사용하지 않으려면 장치의 다음 레지스트리 키를 설정합니다.
  
|**레지스트리 키**|**유형**|**값**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |REG_DWORD|0|
   
## <a name="related-articles"></a>관련 문서
[두 번째 확인 방법으로 Office 2013에 로그인](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

[Outlook에 암호를 입력하라는 메시지가 표시되어 최신 인증을 사용하여 Office 365에 연결하지 않습니다.](https://docs.microsoft.com/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)

  
