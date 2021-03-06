---
title: 단일 항목 오류 수정
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
description: 대량 오류 수정 프로세스를 따를 필요 없이 Advanced eDiscovery의 검토 집합에서 문서의 처리 오류를 수정할 수 있습니다.
ms.openlocfilehash: 8e5d8d00f507dc5792a1beda018d4c76632b82f7
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751585"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a>Advanced eDiscovery의 단일 항목 오류 수정

오류 수정을 통해 Advanced eDiscovery 사용자는 Advanced eDiscovery가 콘텐츠를 제대로 처리하지 못하게 하는 데이터 문제를 수정하는 기능을 제공합니다. 예를 들어 암호로 보호된 파일은 잠기거나 암호화되어 있기 때문에 처리될 수 없습니다. 이전에는 이 워크플로를 사용하여 대량으로 오류를 [수정해야만 합니다.](error-remediation-when-processing-data-in-advanced-ediscovery.md) 그러나 경우에 따라 조사하고 있는 사례에 응답하는 파일이 없는 경우 여러 파일의 오류를 수정하는 것이 타당하지 않습니다. 또한 파일 메타데이터(예: 파일 위치 또는 액세스 권한이 있는 사용자)를 검토하여 응답성에 대한 선행 결정을 내리는 데 도움이 되기 전에 오류를 수정하는 것이 부적연할 수 있습니다. 단일 항목  오류 수정이라는 새로운 기능을 통해 eDiscovery 관리자는 처리 오류로 파일의 메타데이터를 보고 필요한 경우 검토 집합에서 직접 오류를 수정하는 기능을 제공합니다. 이 문서에서는 검토 집합에서 오류를 처리하여 파일을 식별, 무시 및 수정하는 방법에 대해 논의합니다.

## <a name="identify-documents-with-errors"></a>오류가 있는 문서 식별

이제 검토 집합에서 오류를 처리하는 문서가 배너로 식별됩니다. 오류를 수정하거나 무시할 수 있습니다. 다음 스크린샷은 암호로 보호된 검토 집합의 Word 문서에 대한 처리 오류 배너를 보여줍니다. 또한 처리 오류와 함께 문서의 파일 메타데이터를 볼 수 있습니다.

![처리 오류와 함께 문서에 표시되는 배너](../media/SIERimage1.png)

검토 집합에서 문서를 쿼리할 때 처리 상태  조건을 사용하여 처리 오류가 있는 문서를 검색할 [수도 있습니다.](review-set-search.md)

![처리 상태 조건을 사용하여 오류 문서 검색](../media/SIERimage2.png)

### <a name="ignore-errors"></a>오류 무시

처리 오류 배너에서 **무시를** 클릭하여 처리 오류를 무시할 수 있습니다. 오류를 무시하면 문서가 대량 오류 수정 워크플로에서 [제거됩니다.](error-remediation-when-processing-data-in-advanced-ediscovery.md) 오류가 무시되면 문서 배너의 색이 변경되고 처리 오류가 무시된 것입니다. 원하는 경우 되전을 클릭하여 오류를 무시할지 결정을 **되전할 수 있습니다.**

![처리 오류를 무시하려면 무시를 클릭합니다.](../media/SIERimage3.png)

검토 집합에서 문서를 쿼리할 때 무시된 처리 오류 조건을  사용하여 처리 오류가 무시된 모든 문서를 검색할 수도 있습니다.

![무시된 처리 오류 조건을 사용하여 무시된 오류 문서 검색](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a>오류로 문서 수정

경우에 따라 암호 제거, 암호화된 파일 암호 해독 또는 손상된 문서 복구를 통해 문서의 처리 오류를 수정한 다음 수정된 문서를 검토 집합에 추가해야 할 수 있습니다. 이렇게 하면 오류 문서를 검토하고 검토 집합의 다른 문서와 함께 내보낼 수 있습니다. 

단일 문서를 수정하기 위해 다음 단계를 수행합니다.

1. 원본 **다운로드를** 클릭하여 파일 복사본을 로컬 컴퓨터에  >   다운로드합니다.

   ![처리 오류와 함께 문서 다운로드](../media/SIERimage5.png)

2. 오프라인으로 파일의 오류를 수정합니다. 암호 보호를 제거하려면 암호 해독 소프트웨어가 필요한 암호화된 파일의 경우 암호를 제공하고 파일을 저장하거나 암호 크래커를 사용하세요. 파일을 수정한 후 다음 단계로 이동하십시오.

3. 검토 집합에서 수정한 처리 오류가 있는 파일을 선택하고 **수정을 클릭합니다.**

   ![처리 오류로 문서 배너에서 수정 클릭](../media/SIERimage6.png)


4. **찾아보기를** 클릭하고 로컬 컴퓨터에서 수정된 파일의 위치로 이동한 다음 파일을 선택합니다.

   ![찾아보기를 클릭하고 로컬 컴퓨터에서 수정된 파일 선택](../media/SIERimage7.png)

    수정된 파일을 선택한 후 검토 집합에 자동으로 업로드됩니다. 파일의 처리 상태를 추적할 수 있습니다.

    ![업데이트 관리 프로세스의 상태가 표시됩니다.](../media/SIERimage8.png)

   처리가 완료되면 수정된 문서를 볼 수 있습니다.

    ![검토 집합에서 수정된 파일을 기본 형식으로 볼 수 있습니다.](../media/SIERimage9.png)

문서가 수정되는 경우 발생하는 일에 대한 자세한 내용은 파일을 수정하면 [어떻게 될지 참조하세요.](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated)

## <a name="search-for-remediated-documents"></a>수정된 문서 검색

키워드 조건을 사용하고 **IsFromErrorRemediation:true** 속성을  지정하여 수정된 검토 집합의 모든 문서를 검색할 수 있습니다. 이 속성은 검토 집합에서 문서를 내보낼 때 로드 파일 내보내기에서도 사용할 수 있습니다.
