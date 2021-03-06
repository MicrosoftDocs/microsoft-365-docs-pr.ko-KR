---
title: 관리 센터의 Microsoft 365 보고서 - 양식 활동
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
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
description: Microsoft 365 관리 센터에서 Microsoft 365 보고서 대시보드를 사용하여 Microsoft Forms 활동 보고서를 다운로드하는 방법을 학습합니다.
ms.openlocfilehash: 843548e77067c7598cfa78ba6fac985237f6f62c
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841116"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>관리 센터의 Microsoft 365 보고서 - 양식 활동

Microsoft 365 **보고서** 대시보드에는 조직의 제품 전체에 대한 활동 개요가 표시됩니다. 보고서 대시보드를 통해 개별 제품 수준 보고서의 하위 수준을 표시하여 각 제품 내의 활동에 대한 더 세부화된 정보를 확인할 수 있습니다. [보고서 개요 항목](activity-reports.md)을 확인하세요.
  
예를 들어 양식과의 상호 작용을 보고 Microsoft Forms 사용이 허가된 모든 사용자의 활동을 이해할 수 있습니다. 또한 작성된 양식 및 사용자가 응답한 양식의 수를 보고 진행되는 공동 작업 수준을 이해하는 데도 도움이 됩니다.
  
> [!NOTE]
> Microsoft 365의 전역 관리자, 전역 읽기 권한자 또는 보고서 읽기 권한자 또는 Exchange, SharePoint, Teams 서비스, Teams 커뮤니케이션 또는 비즈니스용 Skype 관리자인 경우 보고서를 볼 수 있어야 합니다. 

## <a name="how-to-get-to-the-forms-activity-report"></a>양식 활동 보고서에 도착하는 방법

1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요.

    
2. 보고서 **선택 드롭다운에서** 양식 **활동을** \> **선택합니다.**

## <a name="interpret-the-forms-activity-report"></a>양식 활동 보고서 해석

활동 및 사용자 차트를 확인하여 사용자의 양식 활동을 **볼** **수** 있습니다. 

![양식 활동 보고서](../../media/adminformsactivity.png)

|항목|설명|
|:-----|:-----|
|1.  <br/> |양식 **활동** 보고서에서 지난 7일, 30일, 90일 또는 180일간의 추세를 볼 수 있습니다. 그러나 보고서에서 특정 날짜를 선택하면 표(7)에 현재 날짜로부터 최대 28일간의 데이터가 표시됩니다(보고서가 생성된 날짜가 아미지 않습니다).  <br/> |
|2.  <br/> |각 보고서의 데이터는 일반적으로 최근 24시간에서 48시간까지 처리됩니다.  <br/> |
|3.  <br/> |사용자 **보기를** 사용하면 활성 양식 사용자 수의 추세를 파악하는 데 도움이 됩니다. 사용자가 양식에 대한 활동(만들기, 편집, 보기 등)을 실행하거나 특정 기간 내에 양식에 응답한 경우 활성으로 간주됩니다.  <br/> |
|4.  <br/> |활동  보기를 사용하면 활성 사용자 수의 추세를 파악하는 데 도움이 됩니다. 사용자가 지정된 기간 동안 파일 활동(저장, 동기화, 수정 또는 공유)을 실행하거나 페이지를 방문한 경우 활성으로 간주됩니다.<br/> 참고: 활동은 단일 양식에 대해 여러 번 발생할 수 있지만 하나의 활성 양식으로 계산됩니다. 예를 들어 폼을 만들고 지정된 기간 동안 같은 폼을 여러 번 편집할 수 있지만 하나의 양식으로 계산됩니다. 그러나 사용자가 동일한 양식에 대해 여러 응답을 제출한 경우 각 응답은 여전히 개별 응답이 따라서 여러 번 계산됩니다. <br/> |
|5.<br/>|사용자 **차트에서** Y축은 고유 사용자 수입니다. X축은 고유 사용자가 활성화된 날짜입니다. 범례는 다음입니다.<br/><br/>**디자이너는** 사용자가 양식을 만들거나 편집했다는 의미입니다.<br/>**응답자는** 사용자가 양식에 응답을 제출했다는 의미입니다.<br/> **총 사용자** 수란 디자이너 또는 응답자인 회사의 모든 사용자를 의미합니다.<br/><br/> 활동 **차트에서** Y축은 고유한 폼이나 응답의 수입니다. X축은 양식 또는 응답 활동이 발생한 날짜입니다. 범례는 다음입니다.<br/><br/>**만들어진 양식은** 사용자가 만든 고유한 양식의 수입니다.<br/> **조직의 사용자가** 수신한 응답에 서명된 응답의 수에 응답으로 서명됩니다.<br/> **익명 응답은** 조직의 사용자가 수신한 익명 응답 수입니다.<br/><br/>|
|6.<br/>|범례에서 항목을 선택하여 차트에 표시하는 계열을 필터링할 수 있습니다. 예를 들어 사용자 차트에서 디자이너, 응답자 또는 총 사용자를 선택하여 각 사용자와 관련된 정보만 볼 수 있습니다. 이 선택을 변경해도 아래 표의 정보는 변경되지 않습니다.|
|7.<br/>|이 표에는 사용자 수준별 활동 분석이 표시됩니다. 범례는 다음입니다.<br/><br/>**사용자** 이름은 Microsoft Forms에서 활동을 수행한 사용자의 전자 메일 주소입니다.<br/>**마지막 활동 날짜(UTC)는** 선택한 날짜 범위에 대해 사용자가 양식 활동을 마지막으로 수행한 날짜입니다. 특정 날짜에 발생한 활동을 보려면 차트에서 직접 날짜를 선택합니다.<br/><br/>이렇게 하면 해당 특정 일에 활동을 수행한 사용자에 대한 파일 활동 데이터만 표시하도록 테이블이 필터링됩니다.<br/><br/>**만들어진 양식 수는** 사용자가 만든 양식의 수입니다.<br/> **응답한 양식의** 수는 사용자가 응답을 제출한 양식의 수입니다.|
|8.<br/>|열 관리 **아이콘을** 선택하여 보고서에서 열을 추가하거나 제거합니다.|
|9.<br/>|내보내기 링크를 선택하여 보고서 데이터를 Excel .csv 파일로 내보낼 **수** 있습니다. 이렇게 하면 모든 사용자에 대한 데이터를 내보내고 추가 분석을 위해 간단한 집계, 정렬 및 필터링을 할 수 있습니다. 사용자가 100명 미만인 경우 보고서 자체의 테이블 내에서 정렬 및 필터링할 수 있습니다. 사용자가 100명 이상인 경우 필터링 및 정렬하려면 데이터를 내보내야 합니다.|