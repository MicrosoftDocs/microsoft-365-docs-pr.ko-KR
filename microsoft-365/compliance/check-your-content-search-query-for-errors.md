---
title: 오류에 대한 콘텐츠 검색 쿼리 확인
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: 검색을 실행하기 전에 콘텐츠 검색에 대한 키워드 쿼리에서 오류 및 오타를 검색하는 방법을 알아보겠습니다.
ms.openlocfilehash: 250db272014d5801bfb3927d14072eea94bd635f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818097"
---
# <a name="check-your-content-search-query-for-errors"></a>오류에 대한 콘텐츠 검색 쿼리 확인

콘텐츠 검색을 만들거나 편집할 때 Microsoft 365에서 쿼리에서 지원되지 않는 문자와 소문자 부울 연산자를 확인하게 할 수 있습니다. 방법 콘텐츠 **검색의 쿼리** 페이지에서 오타 확인 쿼리를 클릭합니다. 
  
!["오타에 대한 쿼리 확인"을 클릭하여 검색 쿼리에서 미지원 문자를 확인](../media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
다음은 확인할 수 없는 문자의 목록입니다. 일반적으로 검색 오류가 발생하거나 의도하지 않은 결과를 반환하는 경우도 있습니다.
  
- **스마트 따옴표** - 은은한 따옴표와 이중 따옴표(희미한 따옴표라고도 지음)는 지원되지 않습니다. 검색 쿼리에는 직선 인용 부호만 사용할 수 있습니다. 
    
- **인쇄할** 수 없는 문자와 컨트롤 문자 - 인쇄할 수 없는 문자와 컨트롤 문자는 영문자 같은 쓴 기호를 나타내지 않습니다. 인쇄할 수 없는 문자와 컨트롤 문자의 예로는 텍스트 서식을 지정하는 문자나 별도의 텍스트 줄이 있습니다. 
    
- **왼쪽에서 오른쪽** 및 오른쪽에서 왼쪽으로 표시 - 이러한 표시는 왼쪽에서 오른쪽으로 쓰는 언어(예: 영어 및 스페인어) 및 오른쪽에서 왼쪽으로 쓰는 언어(예: 아랍어 및 Hebrew)의 텍스트 방향을 나타내는 데 사용되는 컨트롤 문자입니다.
    
- **소문자 부울** 연산자 - 검색 쿼리에서 **AND**, **OR** 및 **NOT과** 같은 부울 연산자를 사용하는 경우 대문자입니다. 쿼리에서 오타를 확인할 때 쿼리 구문은 소문자 연산자를 사용할 수 있는 경우에도 부울 연산자가 사용 중으로 표시될 수 있습니다. 예를 들면 다음과  `(WordA or WordB) and (WordC or WordD)` 같습니다.
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>쿼리에 사용할 수 없는 문자가 있는 경우 어떻게 하나요?

쿼리에서 미지원 문자가 발견되면 해당 문자를 찾지 못했다는 경고 메시지가 표시되고 대안을 제안합니다. 그런 다음 원래 쿼리를 그대로 유지하거나 제안된 수정된 쿼리로 대체할 수 있습니다. 다음은 이전 스크린샷에서 검색 쿼리에 대한 오타 확인 쿼리를 클릭한 후 표시되는 경고 메시지의 예입니다.  원래 쿼리에는 똑똑한 따옴표와 소문자 부울 연산자가 포함되어 있습니다. 
  
![쿼리에 대한 제안된 변경과 함께 경고 메시지가 표시됩니다.](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>검색 쿼리에서 지원되지 않는 문자를 방지하는 방법

지원되지 않는 문자는 일반적으로 Microsoft Word 또는 Microsoft Excel과 같은 다른 응용 프로그램에서 쿼리나 쿼리의 일부를 복사하여 콘텐츠 검색의 쿼리 페이지에 있는 키워드 상자에 붙여 넣는 경우 쿼리에 추가됩니다. 이러한 문자를 방지하는 가장 좋은 방법은 키워드 상자에 쿼리를 입력하는 것입니다. 또는 Word 또는 Excel에서 쿼리를 복사한 다음 Microsoft 메모장과 같은 일반 텍스트 편집기에서 붙여넣을 수 있습니다. 텍스트 파일을 저장하고 인코딩  드롭다운 목록에서 **ANSI를** 선택합니다. 그러면 서식 및 지원되지 않는 문자가 제거됩니다. 그런 다음 텍스트 파일에서 키워드 쿼리 상자로 쿼리를 복사하여 붙여넣을 수 있습니다. 
