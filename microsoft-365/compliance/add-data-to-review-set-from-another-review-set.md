---
title: 검토 집합의 데이터를 다른 검토 집합으로 추가
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 한 검토 집합에서 문서를 선택하고 Advanced eDiscovery 사례의 다른 집합에서 개별적으로 문서와 함께 작업하는 방법을 학습합니다.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285183"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>다른 검토 집합의 검토 집합에 데이터 추가

경우에 따라 한 검토 집합에서 문서를 선택하고 다른 검토 집합에서 개별적으로 작업해야 할 수 있습니다. 이 기능은 검토 집합에서 콘텐츠를 선점하고 데이터의 하위 집합에 대해 분석을 실행하려는 경우 특히 유용합니다.

이 문서의 워크플로에 따라 한 검토 집합의 콘텐츠를 다른 검토 집합으로 추가합니다.

## <a name="create-a-review-set"></a>검토 집합 만들기

시작하기 전에 데이터를 추가할 검토 집합을 만들어야 합니다.  사례의 검토 집합 탭에  새 검토 집합을 추가할 수 있습니다. 자세한 내용은 검토 집합 [만들기를 참조하세요.](managing-review-sets.md#create-a-review-set)

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>1단계: 다른 검토 집합에 추가할 콘텐츠 식별

원본 검토 집합에서 특정 문서를 선택하거나 검토 집합 쿼리에서 반환된 모든 항목을 선택하여 검토 집합의 콘텐츠를 다른 검토 집합에 추가할 수 있습니다. 선택한 항목을 추가하는 경우 항목을 선택하고 작업을 선택한 다음 다른 검토 집합에 **추가를 선택합니다.**

![작업 메뉴에서 다른 검토 집합에 추가](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>2단계: 다른 검토 집합에 추가하기 위한 옵션 지정

다른 **검토** 집합 옵션 플라이아웃 페이지에 항목을 추가할 리뷰 집합을 선택합니다. 모든 검색 결과 또는 **선택한** 항목을 **추가할지 여부를 선택 합니다.**  **추가** 정보는 항목의 모든 메타데이터를 포함할 수 있는 옵션과 문서를 새  검토 집합에 추가할 때 원본 검토 집합의 태그(레이블 확인란 선택)를 포함할지 여부를 제공합니다.  

![다른 검토 집합에 데이터를 추가하기 위한 옵션](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

확인을 클릭하면 다른 검토 집합에 데이터를 추가하는 새 작업(다른 검토 집합에 데이터 추가)이 만들어지며 다른 검토 집합에 콘텐츠를 추가합니다.  작업 탭으로  이동하여 이 작업의 진행률을 모니터링할 수 있습니다. 자세한 내용은 작업 관리 [를 참조하십시오.](managing-jobs-ediscovery20.md)
