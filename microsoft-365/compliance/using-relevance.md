---
title: Advanced eDiscovery에서 데이터 분석에 연결 모듈 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery의 해당 워크플로 및 교육 단계에 대한 설명이 있는 증거의 데이터를 분석하는 방법을 알아보십시오.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4a05ec47a4a6b2100c062912e7668c2bf785caf7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286064"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a>Advanced eDiscovery에서 데이터 분석에 연결 모듈 사용

Advanced eDiscovery에서 관련성 모듈에는 사례와 관련된 파일의 관련성 교육 및 검토가 포함되어 있습니다. 해당 워크플로를 사용하려면 검토 집합 내에서 검토 집합 관리로 이동한 후 해당성 표시를 클릭합니다. 워크플로를 시작하기 전에 완료해야 하는 몇 가지 단계가 있습니다.

- 프로세스: 검토 집합에 추가된 각 부하 집합은 여기에 "컨테이너"로 표시될 것입니다. 관련성 모듈에 추가하려면 먼저 이러한 문서를 처리해야 합니다. 이 경우 특정 문제를 위해 이러한 태그를 시드로 표시하거나 미리 태그가 지정될 수도 있습니다.

- 관련성 추가: 관련성 로드에서 관련성에 대해 처리된 문서를 추가하여 교육에 사용할 수 있도록 할 \> 수 있습니다.

다음과 같이 워크플로가 표시 및 설명되어 있습니다.
  
![관련성 워크플로](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **평가 및 추적 주기:**
    
  - **평가:** 임의 파일 샘플을 기반으로 초기 평가를 사용할 수 있으며, 이 평가를 사용하여 결정을 적용하여 예측 코딩 프로세스의 성능을 판단합니다. 
    
  - **트랙:** 프로세스의 통계 유효성을 모니터링하는 동안 평가의 중간 결과를 계산하고 표시합니다. 
    
- **교육 및 추적 주기**
    
  - **태그**: Advanced eDiscovery는 개별 파일의 전문가의 되번기 검토 및 태그 지정에 따라 각 문제와 관련성 기준을 학습합니다.
    
  - **추적:** 프로세스의 통계 유효성을 모니터링하는 동안 관련성 교육의 중간 결과를 계산하고 표시합니다. 
    
- **일괄** 계산: 누적 및 학습된 해당 기준이 전체 파일 모음에 적용되고 각 파일에 대해 해당 점수가 생성됩니다.
    
- **결정**: 전체 사례에 적용된 분석 결과는 일괄 계산 후 표시되고 문서 검토 결정을 내리는 데 사용되는 데이터가 표시됩니다.
    
- **테스트:** 결과를 테스트하여 Advanced eDiscovery 처리의 유효성과 유효성을 확인할 수 있습니다.

- **검색**: 관련성 워크플로가 완료되면 검토 집합 내에서 쿼리를 실행할 때 문제의 문서의 읽기 백분위수와 같은 출력을 사용할 수 있습니다.
    
## <a name="guidelines-for-relevance-training-and-review"></a>관련성 교육 및 검토에 대한 지침

다음은 관련성 교육 및 검토에 대한 지침의 개요입니다.
  
- **오류 및** 불일치: 교육 중에 태그 지정 오류가 발생하면 이전 파일 샘플로 돌아가 오류를 수정합니다. 오류가 너무 많거나 사례나 문제의 새로운 관점이 있는 경우 관리자는 해당 기준을 다시 정의하고 해당 교육을 다시 시작해야 합니다.
    
- **태그 지정 및 교육**: 
    
  - 파일에는 콘텐츠에만 태그를 지정해야 합니다. 양도자, 날짜 또는 파일 경로와 같은 메타데이터는 고려하지 않습니다. 
    
  - 파일에 태그를 지정하는 경우 텍스트에 날짜 범위 표시를 고려하지 않습니다.
    
  - 파일에 태그를 지정하는 경우 포함된 그래픽 이미지를 고려하지 않습니다.
     
  - 관련성에 적용된 텍스트는 관련성의 텍스트 보기에 표시되는 파일 콘텐츠에서 제거됩니다. 무시 텍스트의 값이 이미 해당 학습을 시작한 후에 정의된 경우 무시된 새 텍스트는 정의한 지점에서 만든 예제 파일에 적용됩니다. 텍스트 무시 기능을 사용할 경우 파일 분석 성능이 낮아지기에 신중하게 사용해야 합니다.
    
  - 필요한 경우 태그 **지정 건너뛰기** 옵션을 사용하세요. Advanced eDiscovery는 건너뛴 파일을 기반으로 교육하지 않습니다. 평가에서 파일이 관련성이 있는지 여부를 밝히기 어려운 경우 가능하면 건너뛰기보다는 관련성(R) 또는 NR(관련이 없는)으로 태그를 지정하는 것이 **좋습니다.** Advanced eDiscovery에서 교육을 평가하면 이러한 유형의 파일이 얼마나 잘 처리된지 알 수 있습니다.
    
  - 추출된 텍스트가 매우 적은 파일라도 가능한 경우 "건너뛰기"가 아니라 R/NR 교육에서 태그를 지정해야 합니다. 
    
  - 파일을 읽을 수 있으며 R/NR로 태그가 지정될 수 있는 한 태그 지정은 분류자에 영향을 줄 수 있습니다.
    
  - 태그 탭에 표시된 예제 파일 목록에  있는 파일 시퀀스 번호를 사용하면 파일의 원래 표시된 순서로 돌아올 수 있습니다. 
    
  - 샘플로 돌아가 평가 및 교육 집합 파일의 태그를 변경할 수 있습니다. 다음 샘플을 만들 때 변경 내용이 적용됩니다.
    
  - PDF 형식의 검색된 Excel 파일은 파일에 태그를 지정하는 경우 네이티브 Excel 파일과 동일하게 처리해야 합니다.
    
  - 파일의 관련성 태그 지정과 관련하여 의심스러우면 전문가에게 문의합니다. 또한 과정의 후반부에 시간이 손실될 수 있으며 전체 결과의 품질에 부정적인 영향을 줄 수 있습니다.
    
  - 키워드 목록에 정의된 키워드는 사용자가 태그를 지정하는 동안 관련 파일을 식별할 수 있도록 색으로 표시됩니다.
    
- **일괄** 계산: 전문가가 R/NR로 태그가 지정한 파일은 0 또는 100점의 점수를 받게 됩니다. 이는 일괄 계산 전에 수행된 태그 지정에 적용됩니다. 전문가가 일괄 계산 후 이 문제를 유휴로 전환하고 이 문제를 계속 태그를 지정하면 새로 태그가 지정된 점수는 100/0이 아니라 원래 점수가 됩니다.
    
- **문제 및** 샘플링 모드: 문제는 일반적으로 해당 작업 완료(관련성 교육이 안정화되고 일괄 계산이 수행된 경우), 문제가 취소되거나 다른 사용자가 문제를 작업할 때 꺼집니다.
    
## <a name="steps-in-relevance-training"></a>관련성 교육의 단계

관련성 **\>** 추적 탭에서 Advanced eDiscovery는 다음 단계와 함께 처리를 진행하는 방법에 대한 권장 사항을 제공합니다. 다음과 같은 각 단계가 의미 교육 프로세스에서 권장되는 경우의 의미에 대해 설명합니다. 
  
- 태그 지정 / 계속 태그 지정: 샘플 내의 각 파일 및 문제와 전문가가 수행한 파일 검토 및 관계성 태그 지정
    
  - 의미: 기존 샘플에 태그를 지정해야 합니다.
    
- 평가/ 평가 계속: 사례 문제의 유효성을 조기 검사하고 현재 사례에 대해 가져온 파일 인구의 예비 보기를 사용할 수 있습니다.
    
  - 의미: 추가 평가가 필요하거나 권장됩니다.
    
- 교육/계속 교육: Advanced eDiscovery가 파일 샘플에 태그를 지정하는 전문가로부터 학습하고 각 사례의 컨텍스트 내에서 각 문제와 관련성 기준을 식별하는 기능을 획득하는 프로세스입니다.
    
  - 의미: 이 문제의 경우 추가 교육이 필요합니다. 다음 샘플을 만들어 태그를 지정해야 합니다. 
    
- 일괄 계산: Advanced eDiscovery가 교육 단계에서 획득한 지식을 사용하여 전체 파일 수집에 적용하는 과정입니다. 해당 파일 그룹의 모든 파일은 해당성에 대해 평가되어 해당 점수가 할당됩니다.
    
  - 의미: 문제가 안정화되고 일괄 계산을 수행할 수 있습니다.
    
- Catch-up: 전문가가 롤링 로드 시나리오 중에 추가 파일 부하에서 선택한 파일 샘플을 검토하고 태그를 지정하는 경우를 나타냅니다.
    
  - 의미: 새 부하가 추가되고 작업을 계속하려면 추가가 필요합니다.
    
- 태그 불일치: 프로세스는 Advanced eDiscovery 알고리즘을 통해 분석에 부정적인 영향을 줄 수 있는 파일 태그 지정 프로세스의 불일치가 식별됩니다.
    
  - 의미: 다음 샘플에는 이전 샘플에서 태그가 지정된 파일이 포함되고 해당 태그를 다시 지정해야 합니다.
    
- 업데이트 분류자: 사용자가 태그 지정 또는 시드 변경 내용을 적용할 수 있습니다.
    
  - 의미: 태그 지정 및 시드 변경 내용을 다른 의미 샘플을 수동으로 실행할 필요 없이 적용할 수 있습니다.
    
- 보류 중: The Relevance training process is completed.
    
  - 의미: 현재 관련성 교육이 필요하지 않습니다.
    
Advanced eDiscovery는 여러 단계에서 권장되는 다음 단계를 통해 프로세스를 안내하기는 하지만 탭과 페이지 간을 탐색하고 개별 사례, 문제 또는 문서 검토 프로세스와 관련이 있을 수 있는 상황을 해결할 수 있습니다. 
  
Advanced eDiscovery 다음 단계 처리 선택을 수락하거나 다시 사용할 수 있습니다. 권장되는 다음 단계가 다른 단계를 수행하려면 대화  상자의 확장된 문제 표시에 나열된  다음 단계를 클릭하고 다음 단계 옆에 있는 수정 단추를 클릭한 다음 다른 다음 단계 옵션을 선택합니다. 
  
> [!NOTE]
> 일부 옵션은 잠금 해제 후 프로세스의 그 시점에서 사용할 수 없는 상태로 유지될 수 있습니다. 
  
## <a name="more-information"></a>추가 정보

[이해와 무관성 평가](assessment-in-relevance-in-advanced-ediscovery.md)
  
[태그 지정 및 평가](tagging-and-assessment-in-advanced-ediscovery.md)
  
[태그 지정 및관련성 교육](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[추적과정성 분석](track-relevance-analysis-in-advanced-ediscovery.md)
  
[결과에 따라 결정](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[테스트와의관성 분석](test-relevance-analysis-in-advanced-ediscovery.md)

[검토 집합에서 데이터 쿼리](review-set-search.md)
