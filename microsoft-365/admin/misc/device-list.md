---
title: 장치 목록 CSV-파일
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: 비즈니스용 Microsoft 365에서 AutoPilot에 대한 CSV 파일을 만드는 방법을 배워야 합니다.
ms.openlocfilehash: 030fb96e9e60c792fb685af57d34eacd6670645a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399365"
---
# <a name="device-list-csv-file"></a>장치 목록 CSV-파일

## <a name="device-list-csv-file-format"></a>장치 목록 .csv 파일 형식

Windows Autopilot을 통해 장치를 관리하고 배포하려면 장치에 대한 특정 정보가 포함된 .csv 파일이 필요합니다.
  
장치 목록 파일의 열에는 지정된 순서로 다음 헤더가 있어야 합니다.
  
- A 열: 장치 일련 번호

- B 열: 비워 두기

- C 열: 하드웨어 해시

하드웨어 공급업체로부터 이 정보를 얻거나 CSV 파일을 생성하는 [Get-WindowsAutoPilotInfo PowerShell 스크립트](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)를 사용할 수 있습니다. 

장치를 추가할 때 프로필에도 추가해야 합니다. 프로필은 장치 또는 장치 그룹에 AutoPilot 배포 프로필을 적용하는 데 사용됩니다.
  
## <a name="related-articles"></a>관련 문서

[비즈니스용 Microsoft 365 설명서 및 리소스](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[비즈니스용 Microsoft 365 시작](https://docs.microsoft.com/microsoft-365/business/microsoft-365-business-overview)
  
[비즈니스용 Microsoft 365 관리](https://docs.microsoft.com/microsoft-365/business/manage)
  
