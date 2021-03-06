---
title: Microsoft 365 Defender에서 인시던트 조사
description: 장치, 사용자 및 사서함과 관련된 인시던트를 분석합니다.
keywords: 인시던트, 컴퓨터, 장치, 사용자, ID, 메일, 전자 메일, 사서함, 조사, 그래프, 증거
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6a3bd6be81b4ea4ef11a366267d7a36d45e622b9
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926897"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender에서 인시던트 조사

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**

- Microsoft 365 Defender

Microsoft 365 Defender는 장치, 사용자 및 사서함에서 모든 관련 경고, 자산, 조사 및 증거를 집계하여 공격의 전체 너비를 포괄적으로 살펴 봐야 합니다.

네트워크에 영향을 미치는 알림을 조사하고, 해당 내용이 무엇인지 이해하고, 인시던트와 관련된 증거를 수집하여 효과적인 수정 계획을 세울 수 있습니다.

## <a name="investigate-an-incident"></a>인시던트 조사

1. 인시던트 대기열에서 인시던트를 선택합니다. <BR> 사이드 패널이 열리며 상태, 심각도, 범주 및 영향을 주는 엔터티와 같은 중요한 정보를 미리 볼 수 있습니다.

    ![인시던트 사이드 패널의 이미지](../../media/incident-side-panel.png)

2. **인시던트 페이지 열기** 를 선택합니다. <BR> 그러면 인시던트 세부 정보, 설명 및 작업, 탭(개요, 경고, 장치, 사용자, 조사, 증거)을 찾을 수 있는 인시던트 페이지가 열립니다.

3. 인시던트에 관련된 알림, 장치, 사용자, 기타 엔터티를 검토합니다.

## <a name="incident-overview"></a>인시던트 개요

개요 페이지에서는 인시던트에 대한 주요 정보를 볼 수 있는 스냅숏을 보여 줍니다.

![인시던트 개요 페이지의 이미지](../../media/incidents-overview.png)

공격 범주는 킬 체인에 대해 공격이 진행된 상황을 시각적 및 숫자로 확인할 수 있습니다. 다른 Microsoft 보안 제품과 함께 Microsoft 365 Defender는 [MITRE ATT 및 &trade; CK](https://attack.mitre.org/)&정렬됩니다.

범위 섹션에서는 이 인시던트의 일부인 영향을 받는 상위 자산 목록을 제공합니다. 위험 수준, 조사 우선 순위 및 자산에 대한 태그 지정과 같은 해당 자산에 관한 특정 정보가 있는 경우 이 섹션에도 표시됩니다.

알림 시간 표시 막대는 알림이 발생한 시간 순서와 해당 인시던트에 대해 이러한 알림이 발생한 이유에 대한 미리 보기를 제공합니다.

그리고 마지막인 증거 섹션에는 인시던트에 얼마나 많은 아티팩트가 포함되었는지와 치료 상태에 대한 요약 정보가 제공되므로 사용자 측에서 어떤 조치가 필요한지 즉시 확인할 수 있습니다.

이 개요는 사용자가 알아야 할 인시던트의 주요 특징에 대한 통찰력을 제공함으로써 인시던트의 초기 분류를 도울 수 있습니다.

## <a name="alerts"></a>알림

심각도, 경고에 관련된 엔터티, 경고 원본(ID용 Microsoft Defender, 끝점용 Microsoft Defender, Office 365용 Microsoft Defender) 및 함께 연결된 이유 등 인시던트와 관련된 모든 경고 및 기타 정보를 볼 수 있습니다.

![인시던트 알림 페이지 이미지](../../media/incident-alerts.png)

기본적으로 알림은 시간을 기준으로 순서대로 정렬되며, 이를 통해 시간에 따라 처음부터 공격이 진행된 방식을 확인할 수 있습니다. 각 경고를 클릭하면 해당 경고에 대한 심층 조사를 실시할 수 있는 관련 경고 페이지로 이동됩니다.

## <a name="devices"></a>장치

장치 탭에는 인시던트와 관련된 알림이 표시되는 모든 장치가 표시됩니다.

공격이 수행된 컴퓨터의 이름을 클릭하면 컴퓨터 페이지로 이동하여 해당 컴퓨터에서 트리거된 알림 및 관련 이벤트를 쉽게 조사할 수 있습니다.

![인시던트의 컴퓨터 탭 이미지](../../media/incident-machines.png)

시간 표시 막대 탭을 선택하면 컴퓨터 시간 표시 막대를 스크롤하여 컴퓨터에서 관찰된 경고와 함께 시간 순서 대로 관찰된 모든 이벤트와 동작을 볼 수 있습니다.

## <a name="users"></a>사용자

주어진 인시던트의 일부로 식별되거나 이와 관련된 사용자를 참조하세요.

사용자 이름을 클릭하면 추가 조사를 수행할 수 있는 사용자의 클라우드 앱 보안 페이지로 이동합니다.

![인시던트의 사용자 탭 이미지](../../media/incident-users.png)

## <a name="mailboxes"></a>사서함

인시던트의 일부로 식별되거나 이와 관련된 사서함을 조사하세요. 추가 조사 작업을 수행하려면 메일 관련 알림을 선택하면 수정 작업을 수행할 수 있는 Office 365용 Microsoft Defender가 열립니다.

![인시던트의 사서함 탭 이미지](../../media/incident-mailboxes.png)

## <a name="investigations"></a>조사

조사를 **선택하여** 이 인시던트의 경고에 의해 트리거된 모든 자동화된 조사를 볼 수 있습니다. 조사는 끝점용 Microsoft Defender 및 Office 365용 Defender에서 자동화된 조사를 실행하도록 구성한 방법에 따라 수정 작업을 수행하거나 분석가의 작업 승인을 기다릴 것입니다.

![인시던트의 조사 탭 이미지](../../media/incident-investigations.png)

조사를 선택하여 조사 세부 사항 페이지로 이동하고 조사 및 수정 상태에 대한 전체 정보를 확인하세요. 조사의 일부로 승인 대기 중인 작업이 있는 경우 보류 중인 작업 탭에 표시됩니다. 인시던트 수정의 일부로 조치를 취합니다.

## <a name="evidence"></a>증거

Microsoft 365 Defender는 알림에서 모든 인시던트 지원 이벤트 및 의심스러운 엔터티를 자동으로 조사하여 중요한 파일, 프로세스, 서비스, 전자 메일에 대한 자동 대응 및 정보를 제공합니다. 이를 통해 인시던트의 잠재적 위협을 신속하게 탐지하고 차단할 수 있습니다.

![인시던트의 증거 탭 이미지](../../media/incident-evidence.png)

분석된 각 엔터티에는 수정 상태뿐만 아니라 결과 (악성적임, 의심스러움, 깨끗함)가 표시됩니다. 이를 통해 전체 인시던트의 수정 상태를 파악하고 추가적인 치료를 위한 다음 단계를 확인하는 데 도움이 됩니다.

## <a name="related-topics"></a>관련 항목

- [인시던트 개요](incidents-overview.md)
- [인시던트 우선 순위 지정](incident-queue.md)
- [인시던트 관리](manage-incidents.md)

