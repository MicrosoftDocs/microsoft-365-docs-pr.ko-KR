---
title: 핵심 eDiscovery 사례에서 콘텐츠 내보내기 및 다운로드
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 핵심 eDiscovery 사례에서 콘텐츠를 내보내고 다운로드 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: e0d4315c48a0d0878b8052265ff8663cd1987169
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551419"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>핵심 eDiscovery 사례에서 콘텐츠 내보내기

검색을 성공적으로 실행 한 후에는 검색 결과를 내보낼 수 있습니다. 검색 결과를 내보낼 때 사서함 항목은 PST 파일이 나 개별 메시지로 다운로드 됩니다. SharePoint 및 비즈니스용 OneDrive 사이트에서 콘텐츠를 내보낼 때 기본 Office 문서 및 기타 문서의 복사본이 내보내집니다. 내보낸 모든 항목에 대 한 정보 및 모든 검색 결과에 대 한 정보가 포함 된 매니페스트 파일 (XML 형식)이 포함 된 결과 .csv 파일을 내보냅니다.
  
[사례와 연결 된 단일 검색](#export-the-results-of-a-single-search) 의 결과를 내보내거나 [사례와 연결 된 여러 검색](#export-the-results-of-multiple-searches)의 결과를 내보낼 수 있습니다.
  
## <a name="export-the-results-of-a-single-search"></a>단일 검색 결과 내보내기

1. [https://compliance.microsoft.com](https://compliance.microsoft.com) 적절 한 eDiscovery 권한이 할당 된 사용자 계정에 대 한 자격 증명을 사용 하 여으로 이동 하 여 로그인 합니다.

2. Microsoft 365 준수 센터의 왼쪽 탐색 창에서 **모두 표시**를 클릭 한 다음 **eDiscovery > 코어**를 클릭 합니다.

3. **핵심 eDiscovery** 페이지에서 검색 결과를 내보내려는 사례를 선택 하 고 **열기 사례**를 클릭 합니다.

4. 사례에 대 한 **홈** 페이지에서 **검색** 탭을 클릭 합니다.

5. 사례에 대 한 검색 목록에서 검색 결과를 내보내려는 검색을 클릭 한 다음 플라이 아웃에서 **결과 내보내기를** 클릭 합니다.

    **결과 내보내기** 페이지가 표시 됩니다. 

    ![내보내기 결과 페이지](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    핵심 eDiscovery 사례와 연결 된 검색 결과를 내보내기 위한 워크플로는 **콘텐츠 검색** 페이지에서 검색에 대 한 검색 결과를 내보내는 것과 같습니다. 단계별 지침은 [Export content search results](export-search-results.md)를 참조 하십시오.

    > [!NOTE]
    > 검색 결과를 내보낼 때는 검색 된 사서함에서 같은 메시지의 인스턴스가 여러 개 발견 된 경우에도 전자 메일 메시지의 복사본 하나만 내보내도록 하는 옵션을 사용할 수 있습니다. 복제 제거 및 중복 항목이 식별 되는 방식에 대 한 자세한 내용은 [eDiscovery 검색 결과의 중복](de-duplication-in-ediscovery-search-results.md)제거를 참조 하십시오.

    내보내기를 시작한 후에는 검색 결과가 다운로드 가능 하므로 Microsoft 클라우드에서 Microsoft가 제공한 Azure 저장소 위치로 업로드 됩니다.
  
6. **내보내기** 탭을 클릭 하 여 사례에 대 한 내보내기 작업 목록을 표시 합니다.
  
    **새로 고침** 을 클릭 하 여 만든 내보내기 작업이 표시 되도록 내보내기 작업 목록을 업데이트 해야 할 수 있습니다. 내보내기 작업의 이름은 검색 이름에 **_Export** 추가 된 해당 검색과 같습니다.

7. 만든 내보내기 작업을 클릭 하 여 플라이 아웃 페이지에 상태 정보를 표시 합니다. 이 정보에는 Azure 저장소 위치로 전송 된 항목의 백분율이 포함 됩니다.

8. 모든 항목을 전송 하 고 나면 **결과 다운로드** 를 클릭 하 여 로컬 컴퓨터에 검색 결과를 다운로드 합니다. 검색 결과를 다운로드 하는 방법에 대 한 자세한 내용은 [Export content search results](export-search-results.md#step-2-download-the-search-results) in의 2 단계를 참조 하십시오.

## <a name="export-the-results-of-multiple-searches"></a>여러 검색 결과 내보내기

사례와 연결 된 단일 검색의 결과를 내보내는 대신 단일 내보내기 작업에서 여러 검색의 결과를 동일한 case에서 내보낼 수 있습니다. 결과를 한 번에 하나씩 내보내는 것 보다 여러 검색의 결과를 내보낼 때 보다 빠르고 쉽게 작업할 수 있습니다.
  
> [!NOTE]
> 이러한 검색 중 하나가 보류 중인 위치를 검색 하도록 구성 된 경우에는 여러 검색의 결과를 내보낼 수 없습니다.

1. [https://compliance.microsoft.com](https://compliance.microsoft.com) 적절 한 eDiscovery 권한이 할당 된 사용자 계정에 대 한 자격 증명을 사용 하 여으로 이동 하 여 로그인 합니다.

2. Microsoft 365 준수 센터의 왼쪽 탐색 창에서 **모두 표시**를 클릭 한 다음 **eDiscovery > 코어**를 클릭 합니다.

3. **핵심 eDiscovery** 페이지에서 검색 결과를 내보내려는 사례를 선택 하 고 **열기 사례**를 클릭 합니다.

4. 사례에 대 한 **홈** 페이지에서 **검색** 탭을 클릭 합니다.
    
5. 사례에 대 한 검색 목록에서 검색 결과를 내보내려는 두 개 이상의 검색 옆에 있는 확인란을 선택 합니다. 

   **대량 작업** 플라이 아웃 페이지가 나타납니다. 

    ![대량 작업 페이지에서 결과 내보내기 클릭](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
6. **결과 내보내기를**클릭 합니다.

   **결과 내보내기** 페이지가 표시 됩니다. 

    ![내보내기 결과 페이지](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    이 시점에서 코어 eDiscovery 사례와 연결 된 여러 검색의 결과를 내보내기 위한 워크플로는 단일 검색에 대 한 검색 결과를 내보내는 것과 같습니다. 이전 섹션의 5 단계를 참조 하세요.

### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a>여러 검색 결과 내보내기에 대 한 자세한 정보

- 여러 검색의 결과를 내보낼 때 모든 검색의 검색 쿼리를 사용 하 여 **OR** 연산자를 결합 한 다음 결합 된 검색을 시작 합니다. 결합 된 검색의 예상 결과는 선택한 내보내기 작업의 플라이 아웃 페이지에 표시 됩니다. 검색 결과가 Microsoft 클라우드의 Azure Storage 위치에 복사 됩니다. 복사 작업의 상태는 플라이 아웃 페이지에도 표시 됩니다. 앞에서 설명한 것 처럼 모든 검색 결과를 복사한 후 로컬 컴퓨터에 다운로드할 수 있습니다.

- 내보내려는 모든 검색에 대 한 쿼리의 최대 키워드 수는 500입니다. 이 제한은 단일 검색에서 동일 합니다. 내보내기 작업은 **OR** 연산자를 사용 하 여 모든 검색 쿼리를 결합 하기 때문입니다. 이 제한을 초과 하면 오류가 반환 됩니다. 이 경우 검색 결과를 줄여서 내보낼 원본 검색의 검색 쿼리를 단순화 해야 합니다.

- 내보낸 검색 결과는 항목을 찾은 콘텐츠 위치로 구성 됩니다. 즉, 내보내기 결과의 콘텐츠 위치에 여러 검색에서 반환 되는 항목이 있을 수 있습니다. 예를 들어 각 사서함에 대해 한 PST 파일에 전자 메일 메시지를 내보내도록 선택한 경우 PST 파일에 여러 검색 결과가 있을 수 있습니다.

- 내보낸 검색 중 둘 이상에서 동일한 콘텐츠 위치에 있는 동일한 전자 메일 항목 또는 문서를 반환 하는 경우에는 항목의 복사본을 하나만 내보냅니다.

- 여러 검색을 만든 후에는 해당 내보내기를 편집할 수 없습니다. 예를 들어 내보내기 작업에서 검색을 추가 하거나 제거할 수 없습니다. 내보낼 검색 결과를 변경 하려면 내보내기 작업을 만들어야 합니다. 내보내기 작업을 만든 후에는 결과를 컴퓨터로 다운로드 하거나, 내보내기를 다시 시작 하거나, 내보내기 작업을 삭제할 수 있습니다.

- 내보내기를 다시 시작 하면 내보내기 작업을 구성 하는 검색 쿼리에 대 한 모든 변경 내용이 검색 된 검색 결과에 영향을 주지 않습니다. 내보내기를 다시 시작 하면 내보내기 작업을 만들 때 실행 된 것과 동일한 결합 된 검색 쿼리 작업이 다시 실행 됩니다.

- 또한 내보내기를 다시 시작 하면 Azure 저장소 위치로 복사 되는 검색 결과가 이전 결과를 덮어씁니다. 이전에 복사한 결과를 다운로드할 수 없습니다.

- 고급 eDiscovery (클래식)에서 여러 검색의 결과를 준비 하는 것은 사용할 수 없습니다. 고급 eDiscovery (클래식)에서 분석에 대 한 단일 검색 결과만 준비할 수 있습니다.