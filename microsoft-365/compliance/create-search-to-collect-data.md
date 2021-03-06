---
title: 검색 만들기
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
description: Advanced eDiscovery 사례에서 검색할 수 있는 위치 및 상주 위치를 만들고 정의하고 선택하는 방법을 학습합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1d9051824ff3f28484d0750b982edd70334a9b88
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035770"
---
# <a name="create-a-search"></a>검색 만들기

사례의 **검색** 탭에서 새 검색을 클릭하고 마법사를  따라 새 검색을 만들 수 있습니다.

![Advanced eDiscovery 사례의 검색 마법사](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a>검색 이름을 지정하고 설명 제공

사례가 있는 각 검색에는 고유한 이름이 지정해야 합니다. 원하는 경우 검색에 대한 설명을 제공할 수 있습니다. 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a>검색할 양도인 및 양도 위치를 선택하세요.

사례에 추가한 양도인을 지정하여 검색할 수 있는 콘텐츠 위치를 선택하세요. 보호자 선택을 통해 보호자에 매핑된 모든 데이터 원본에 대해 검색을 실행합니다. 또한 각 보호자에 대해 선택한 데이터 원본으로 검색 범위를 좁힐 수도 있습니다. 관리인을 추가하고 데이터 원본을 관리하는 방법에 대한 자세한 내용은 관리인과의 [작업(Work with custodians)을 참조하세요.](managing-custodians.md)

## <a name="choose-non-custodial-locations"></a>양도하지 않은 위치 선택

경우에 따라 보호자와 연결되지 않은 데이터 원본을 검색할 수 있습니다. 이 경우 검색할 위치를 지정하거나 특정 Microsoft 서비스의 모든 콘텐츠 위치(예: 모든 Exchange 사서함 또는 모든 SharePoint 사이트 및 OneDrive 계정 검색)를 검색하도록 선택할 수 있습니다.

## <a name="define-the-search-query-and-conditions"></a>검색 쿼리 및 조건 정의

미리 작성된 조건 카드를 사용하거나 KQL(키워드 쿼리 언어)을 사용하여 키워드 쿼리 및 검색 조건을 정의할 수 있습니다. 자세한 내용은 검색 쿼리 [작성을 참조하세요.](building-search-queries.md)
