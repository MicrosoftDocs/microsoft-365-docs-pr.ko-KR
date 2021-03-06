---
title: 관리 센터의 Microsoft 365 보고서 - SharePoint 활동
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- SPO160
- BSA160
ms.assetid: a91c958f-1279-499d-9959-12f0de08dc8f
description: SharePoint 활동 사용 현황 보고서를 통해 모든 SharePoint 사용자의 활동, 공유되는 파일 수 및 저장소 사용률을 알 수 있습니다.
ms.openlocfilehash: b0c628300647e83889e273268bef7abd9e337ed4
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948871"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>관리 센터의 Microsoft 365 보고서 - SharePoint 활동

Microsoft 365 관리자는 **보고서** 대시보드에 조직의 다양한 제품에 대한 활동 개요가 표시됩니다. 각 제품의 고유한 활동에 대한 자세한 정보를 확인할 수 있습니다. [Microsoft 365](activity-reports.md)관리 센터에서 활동 보고서를 체크 아웃합니다.
  
예를 들어 파일과의 상호 작용을 확인하여 SharePoint를 사용하도록 라이선스가 부여된 모든 사용자의 활동을 파악할 수 있습니다. 또한 공유된 파일 수를 확인하여 진행 중인 공동 작업의 수준을 파악하는 데도 도움이 됩니다.
  
> [!NOTE]
> 일부 기능은 점차적으로 도입됩니다. 즉, 이 기능이 아직 표시되지 않거나 도움말 문서에 설명된 것과 다를 수 있습니다. 아직 보이지 않아도 걱정마세요. 곧 볼 수 있습니다. 
  
각 SharePoint 사이트와 관련하여 수행되는 활동의 양과 저장소 활용도를 파악하려면 [SharePoint 사이트 사용 보고서](sharepoint-site-usage.md)를 참조하세요.
  
> [!NOTE]
> Microsoft 365의 전역 관리자, 전역 읽기 권한자 또는 보고서 읽기 권한자 또는 Exchange, SharePoint, Teams 서비스, Teams 커뮤니케이션 또는 비즈니스용 Skype 관리자인 경우 보고서를 볼 수 있어야 합니다.  
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>SharePoint 활동 보고서에 어떻게 액세스하나요?

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요.

    
2. 보고서 **선택 드롭다운에서** **SharePoint 활동을** \> **선택합니다.**
  
## <a name="interpreting-the-sharepoint-activity-report"></a>SharePoint 활동 보고서 해석

**파일** 및 **사용자** 보기를 확인하여 SharePoint 활동을 볼 수 있습니다.<br/> ![SharePoint Activity Report](../../media/96ee85af-f213-499b-9e2b-22912bd0b8c2.png)
  
|항목|설명|
|:-----|:-----|
|1.  <br/> |**SharePoint 활동 보고서** 에서 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택하면 표(7)에 현재 날짜로부터 최대 28일간의 데이터가 표시됩니다(보고서가 생성된 날짜가 아미지 않습니다).  <br/> |
|2.  <br/> |각 보고서의 데이터는 일반적으로 최근 24시간에서 48시간까지 처리됩니다.  <br/> |
|3.  <br/> |**파일** 보기를 통해 SharePoint 사이트에 저장된 파일과 상호 작용을 수행하는 라이선스가 부여된 고유한 사용자 수를 파악할 수 있습니다.  <br/> |
|4.  <br/> |**페이지** 보기는 사용자가 방문한 고유한 페이지 수가 표시됩니다.  <br/> |
|5.  <br/> |**사용자** 보기를 사용하면 활성 사용자 수의 추세를 파악할 수 있습니다. 사용자가 지정된 기간 동안 파일 활동(저장, 동기화, 수정 또는 공유)을 실행하거나 페이지를 방문한 경우 활성으로 간주됩니다.  <br/> 참고: 단일 파일에 대해 파일 활동이 여러 번 발생할 수 있지만 하나의 활성 파일로 계산됩니다. 예를 들어 지정된 기간 동안 같은 파일을 여러 번 저장하고 동기화할 수 있지만, 데이터에서 하나의 동기화된 파일 및 하나의 활성 파일로 계산됩니다.           |
|6.  <br/> | **파일** 차트에서 Y축은 사용자가 저장, 동기화, 수정 또는 공유한 고유 파일 수입니다.  <br/>  **사용자** 차트에서 Y축은 사이트에서 파일 상호 작용(저장, 동기화, 수정 또는 공유)을 수행한 고유 사용자 수입니다.  <br/>  **페이지** 차트에서 X축은 사용자가 방문한 고유 페이지 수 입니다.  <br/>  모든 차트의 X축은 모두 이 특정 보고서에 선택된 날짜 범위입니다.  <br/> |
|7.  <br/> |범례에서 항목을 선택하여 차트에 표시하는 계열을 필터링할 수 있습니다. 예를 들어 파일  차트에서 보기 또는 **편집,** 동기화, 내부적으로 공유  또는 외부 공유를 선택하여 각 데이터와 관련된 정보만 볼 수 있습니다.  이 선택 항목을 변경해도 눈금 표에 있는 정보가 변경되지는 않습니다.  <br/> |
|8.  <br/> | 이 표에서는 사이트 수준별 활동 분석 결과를 보여줍니다.  <br/>  <br/> **사용자** 이름은 SharePoint 사이트에서 활동을 수행한 사용자의 전자 메일 주소입니다.  <br/> **마지막 활동 날짜(UTC)** 는 선택한 데이터 범위에 따라 파일 활동을 수행하거나 페이지를 방문한 최신 날짜입니다. 특정 날짜에 발생한 활동을 보려면 차트에서 직접 날짜를 선택합니다.  <br/> ![차트에서 특정 날짜 선택](../../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png) <br/> 이렇게 하면 해당 특정 일에 활동을 수행한 사용자에 대한 파일 활동 데이터만 표시하도록 테이블이 필터링됩니다.  <br/>  **보거나 편집한 파일** 은 사용자가 업로드, 다운로드, 수정 또는 본 파일의 수입니다.  <br/>  **동기화된** 파일은 사용자의 로컬 장치에서 SharePoint 사이트로 동기화된 파일 수입니다.  <br/>  **내부적으로** 공유되는 파일은 조직 내의 사용자 또는 그룹 내의 사용자(외부 사용자를 포함할 수 있는 사용자)와 공유된 파일의 수입니다.  <br/>  **외부적으로 공유된 파일** 은 조직 외부의 사용자와 공유한 파일의 수입니다.  <br/>  **방문한** 페이지는 사용자가 방문한 고유 페이지입니다.  <br/>  **삭제됨** 은 사용자의 라이선스가 제거되었음을 나타냅니다.  <br/>  **참고:** 삭제된 사용자의 활동은 선택한 기간 동안 사용이 허가된 경우 보고서에 계속 표시됩니다. 삭제된 열을 통해 사용자가 더 이상 활성이 아니지만 보고서의 데이터에 기여함을 알 수 있습니다.  <br/> **삭제된 날짜** 는 사용자의 라이선스가 제거된 날짜입니다.  <br/>  **할당된 제품은** 사용자에게 라이선스가 부여된 Microsoft 365 제품입니다.  <br/> |
|9.  <br/> |열 관리 **아이콘** 열을 선택하여 보고서에서 열을 추가하거나 ![ ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) 제거합니다.  <br/> |
|10.  <br/> |내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 파일로 내보낼 **수** 있습니다. 그러면 모든 사용자의 데이터를 내보내고 향후 분석을 위해 간단하게 정렬 및 필터링을 수행할 수 있습니다. 사용자가 2,000명 미만인 경우 보고서 자체의 표에서 정렬 및 필터링할 수 있습니다. 사용자가 2,000명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다.  <br/> |
|||
   

