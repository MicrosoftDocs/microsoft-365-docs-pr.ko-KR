---
title: 관리되지 않는 Windows 10 PC 및 Mac 보호
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365를 통해 관리되지 않는 장치 또는 BYOD(Bring Your Own Devices)를 보호합니다.
ms.openlocfilehash: 5c27b29b5bb4fb445655e671d8c654ad8e9abc6b
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044387"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>관리되지 않는 Windows 10 PC 및 Mac 보호

Microsoft Intune에 등록하여 Windows 10 PC 및 Mac을 관리할 수 있습니다. 이를 통해 환경의 데이터에 액세스하기 전에 정상 및 보안을 보장할 수 있습니다. 그러나 많은 캠페인과 중소기업에는 조직에서 관리하지 않는 BYOD(자체 장치)를 가져오는 직원이 포함되어 있습니다. 이러한 관리되지 않는 PC 및 Mac의 경우 이 문서를 사용하여 최소 보안 기능이 구성되도록 합니다.

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Windows 10 또는 Mac을 실행하는 컴퓨터 보호

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Windows 10 PC 또는 Mac이 조직에서 관리되지 않는 경우 이러한 보안 기능을 구성해야 합니다.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**장치 암호화 켜기**<p>

장치 암호화는 광범위한 Windows 장치에서 사용할 수 있으며 데이터를 암호화하여 보호하는 데 도움이 됩니다. 장치 암호화를 켜면 권한이 부여된 개인만 장치 및 데이터에 액세스할 수 있습니다. 지침은 [장치 암호화](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 켜기 기능을 참조하세요.

 장치에서 장치 암호화를 사용할 수 없는 경우 대신 표준 [BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) 암호화를 켜면 됩니다. (BitLocker는 Windows 10 Home 버전에서는 사용할 수 없습니다.) 

**Windows 보안으로 디바이스 보호**<p>
If you have Windows 10, you'll get the latest antivirus protection with Windows Security. Windows 10을 처음 시작하면 Windows 보안이 설정되어 있으며 맬웨어(악성 소프트웨어), 바이러스 및 보안 위협을 검사하여 PC 보호를 적극적으로 지원하고 있습니다. Windows 보안은 실시간 보호를 사용하여 PC에서 다운로드하거나 실행한 모든 것을 검사합니다.

Windows 업데이트는 Windows 보안에 대한 업데이트를 자동으로 다운로드하여 PC를 안전하게 유지하고 위협으로부터 보호합니다.

이전 버전의 Windows가 있는 경우 Microsoft Security Essentials Windows 보안으로 이동하는 것이 좋습니다. 자세한 내용은 [Windows 보안으로 내 장치를 보호하는 도움말을 참조하세요.](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)

**Windows 방화벽 켜기**<p>
다른 방화벽이 켜져 있는 경우에도 항상 Windows 방화벽을 실행해야 합니다. Windows 방화벽을 끄면 장치(및 네트워크가 있는 경우)가 무단 액세스에 더 취약할 수 있습니다. 지침은 [Windows 방화벽](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) 켜기 또는 끄기 참조

## <a name="mac"></a>[Mac](#tab/Mac)

**FileVault를 사용하여 Mac 디스크 암호화**<p>
디스크 암호화는 장치를 분실하거나 도난당한 경우 데이터를 보호합니다. FileVault 전체 디스크 암호화를 사용하면 시작 디스크의 정보에 무단으로 액세스할 수 없습니다. 지침은 [FileVault를 사용하여 Mac의](https://support.apple.com/HT204837) 시작 디스크를 암호화하세요.

**맬웨어로부터 mac 보호**<p>
Mac에 신뢰할 수 있는 바이러스 백신 소프트웨어를 설치하고 사용하는 것이 좋습니다. 선택 항목 목록은 다음 문서를 [참조하세요. 최상의 Mac 바이러스 백신 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

신뢰할 수 있는 원본에서만 소프트웨어를 사용하여 맬웨어의 위험을 줄일 수 있습니다. 보안 및 개인 정보 & 설정을 사용하면 Mac에 설치된 소프트웨어 원본을 지정할 수 있습니다. 자세한 내용은 [맬웨어로부터 Mac을 보호하세요.](https://support.apple.com/kb/PH25087)

**방화벽 보호 켜기**<p>
방화벽 설정을 사용하여 인터넷 또는 네트워크에 연결할 때 다른 컴퓨터에서 시작한 원치 않는 연락처로부터 Mac을 보호합니다. 이러한 보호가 없는 경우 Mac은 무단 액세스에 더 취약할 수 있습니다. 지침은 [응용 프로그램 방화벽에](https://support.apple.com/HT201642) 대해 참조하세요.
