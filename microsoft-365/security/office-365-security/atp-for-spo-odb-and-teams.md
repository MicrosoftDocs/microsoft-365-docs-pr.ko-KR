---
title: SharePoint, OneDrive 및 Microsoft Teams를 위한 안전한 첨부 파일
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams의 파일에 대한 Microsoft Defender for Office 365에 대해 자세히 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce73e1fd5c8ecb63bee1db2e9e64aade305b37e9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287056"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint, OneDrive 및 Microsoft Teams를 위한 안전한 첨부 파일

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Office [365용 Microsoft Defender의](office-365-atp.md) SharePoint, OneDrive 및 Microsoft Teams에 대한 안전한 첨부 파일은 [Microsoft 365의](virus-detection-in-spo.md)일반적인 바이러스 검색 엔진에 의해 업로드 시 이미 검사된 파일에 대한 추가 보호 계층을 제공합니다. SharePoint, OneDrive 및 Microsoft Teams용 안전 첨부 파일은 팀 사이트 및 문서 라이브러리에서 악성으로 식별된 기존 파일을 검색하고 차단하는 데 도움이 됩니다.

SharePoint, OneDrive 및 Microsoft Teams에 대한 안전한 첨부 파일은 기본적으로 사용하도록 설정되지 않습니다. 이 기능을 켜면 [SharePoint, OneDrive](turn-on-atp-for-spo-odb-and-teams.md)및 Microsoft Teams에 대한 안전한 첨부 파일 켜기 기능을 참조합니다.

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>SharePoint, OneDrive 및 Microsoft Teams의 안전한 첨부 파일 작동 방식

SharePoint, OneDrive 및 Microsoft Teams용 안전 첨부 파일을 사용하도록 설정하고 파일을 악성으로 식별하면 파일 저장소와 직접 통합하여 파일이 잠겨집니다. 다음 이미지는 라이브러리에서 검색된 악성 파일의 예를 보여줍니다.

![악성 파일로 탐지된 한 개의 파일을 포함한 비즈니스용 OneDrive에 있는 파일](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

차단된 파일은 문서 라이브러리 및 웹, 모바일 또는 데스크톱 응용 프로그램에 계속 나열되어도 파일을 열거나 복사하거나 이동하거나 공유할 수 없습니다. 하지만 차단된 파일을 삭제할 수 있습니다.

다음은 모바일 장치에서 차단된 파일의 모양을 예로 들 수 있습니다.

![OneDrive 모바일 앱의 비즈니스용 OneDrive에서 차단된 파일 삭제](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

기본적으로 사용자들은 차단된 파일을 다운로드할 수 있습니다. 다음은 모바일 장치에서 차단된 파일을 다운로드하는 모양입니다.

![비즈니스용 OneDrive에서 차단된 파일 다운로드](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Online 관리자는 사용자가 악성 파일을 다운로드하지 못하게 할 수 있습니다. 자세한 내용은 [SharePoint Online PowerShell을](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)사용하여 사용자가 악성 파일을 다운로드하지 못하게 합니다.

파일이 악성으로 감지된 사용자 경험에 대한 자세한 내용은 [SharePoint Online, OneDrive](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)또는 Microsoft Teams에서 악성 파일이 발견될 때 할 일에 대해 참조하세요.

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint, OneDrive 및 Microsoft Teams의 안전한 첨부 파일에서 검색된 악성 파일에 대한 정보 보기

Office 365용 Microsoft Defender에서 악성으로 식별된 파일은 [Office 365용 Microsoft Defender](view-reports-for-atp.md) 및 [탐색기(및](threat-explorer.md)실시간 검색)에 대한 보고서에 나타납니다.

2018년 5월 현재, Office 365용 Microsoft Defender에 의해 파일이 악성으로 식별된 경우 해당 파일은 또한 무단으로 사용할 수 있습니다. 자세한 내용은 보안 및 준수 센터를 & 파일을 [관리하세요.](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)

## <a name="keep-these-points-in-mind"></a>다음의 사항을 염두에 둡니다.

- Office 365용 Defender는 SharePoint Online, 비즈니스용 OneDrive 또는 Microsoft Teams의 모든 단일 파일을 검색하지 않습니다. 이것은 정상적인 현상입니다. 파일이 비동기적으로 검색됩니다. 이 프로세스에서는 공유 및 게스트 활동 이벤트를 스마트 추적 및 위협 신호와 함께 사용하여 악성 파일을 식별합니다.

- SharePoint 사이트가 최신 환경을 사용하도록 [구성되어 있는지 확인](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience) Office 365 보호용 Defender는 최신 환경 또는 클래식 보기 사용 여부에 따라 적용됩니다. 그러나 파일이 차단된 시각적 표시기는 최신 환경에서만 사용할 수 있습니다.

- SharePoint, OneDrive 및 Microsoft Teams의 안전한 첨부 파일은 EOP(Exchange Online Protection)의 스팸 방지 및 맬웨어 방지 보호와 Office 365용 Microsoft Defender의 안전한 링크 및 안전한 첨부 파일을 포함하는 조직의 전반적인 위협 방지 전략의 일부입니다. 자세한 내용은 [Office 365에서 위협으로부터](protect-against-threats.md)보호를 참조합니다.
