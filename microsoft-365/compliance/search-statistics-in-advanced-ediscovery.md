---
title: Advance eDiscovery의 검색 통계
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Advanced eDiscovery에서 컬렉션 검색을 실행한 후 생성되는 통계를 확인하여 검색 결과의 유효성을 검사합니다.
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750779"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>Advanced eDiscovery의 검색 통계

검색 결과의 유효성을 검사할 수 있는 한 가지 방법은 결과와 관련한 통계를 확인하여 기대치에 부합하는지 확인할 수 있습니다. 검색이 완료되면 검색 세부 정보 플라이아웃에 높은 수준의 통계가 표시됩니다.

- 검색에 의해 검색된 항목의 수 및 볼륨

- 검색 위치에서 발견된 부분적으로 인덱싱되거나 인덱싱되지 않은 항목의 수 및 볼륨

- 검색된 사서함 및 위치 수입니다.
자세한 통계를 보려면 검색 세부 정보 플라이아웃에서 "통계"를 클릭합니다.

## <a name="summary-view"></a>요약 보기

요약 보기에서 위치 유형(예: Exchange)별로 검색 결과를 세분화할 수 있습니다. 각 위치 유형에 대해 다음을 볼 수 있습니다.

- 검색 조건과 일치하는 항목이 있는 위치 수

- 검색 조건과 일치하는 위치의 항목 수

- 검색 조건과 일치하는 총 항목 볼륨입니다.

## <a name="top-locations-view"></a>위쪽 위치 보기

위쪽 위치 보기에서는 일치하는 위치가 가장 많은 개별 위치를 볼 수 있습니다. 각 위치에 대해 다음이 표시됩니다.

- 위치 이름(예: SharePoint URL)

- 위치 종류

- 검색 조건과 일치하는 항목 수

- 검색 조건과 일치하는 총 항목 볼륨입니다.

## <a name="queries-view"></a>쿼리 보기

쿼리에 키워드 또는 키워드 행을 사용한 경우 위치 유형별 쿼리 보기에서 쿼리 분석 결과를 볼 수 있습니다. 각 위치 유형에 대해 다음이 표시됩니다.

- 파트: 이 열에는 "Primary" 또는 "Keyword"라는 단어가 있습니다. "기본"은 행이 전체 쿼리에 통계를 제시하는 반면 " Keyword"는 쿼리 구성 요소 중 하나를 의미합니다.

- 쿼리: 행이 참조하는 실제 쿼리 구성 요소입니다. Part이 "Primary"이면 전체 쿼리가 됩니다. Part가 "Keyword"이면 여기에 쿼리 구성 요소 중 하나를 볼 수 있습니다.
  
  - 키워드를 지정하지 않은 모든 콘텐츠 콘텐츠 사서함을 검색할 때 모든 항목이 반환될 수 있도록 실제 쿼리(크기 >= 0)입니다.
  
  - SharePoint Online 및 비즈니스용 OneDrive 사이트를 검색하면 다음 두 구성 요소가 추가됩니다.
    
    - NOT IsExternalContent:1 - On-premises SharePoint 조직에서 콘텐츠를 제외합니다.
    
    - NOT isOneNotePage: 1 - 검색 쿼리와 일치하는 모든 문서의 복제본이기 때문에 모든 OneNote 파일을 제외합니다.

- 검색 조건과 일치하는 항목이 있는 위치 수입니다.

- 검색 조건과 일치하는 이러한 위치의 항목 수입니다.

- 검색 조건과 일치하는 총 항목 볼륨입니다.
