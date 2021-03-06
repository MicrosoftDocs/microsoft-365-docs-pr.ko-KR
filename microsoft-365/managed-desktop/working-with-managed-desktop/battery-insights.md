---
title: 배터리 정보 활용
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f339fc98ea94c291c533045e9906f626f4b74e2a
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529842"
---
# <a name="battery-insights"></a>배터리 정보 활용
이 보기는 Microsoft Managed Desktop 디바이스에 대한 전원, 배터리 및 앱 사용 메트릭을 제공합니다. 이러한 목적을 위해 앱은 실행 중일 때 포커스가 있는 경우 "사용 중"으로 간주됩니다.

사용 현황 데이터를 확인하려면 배터리 **탭을** 선택합니다.

![배터리 창: 왼쪽 위, 상단 에너지 소비자(앱)의 장치 모델당 배터리 사용 시간 예측. 오른쪽 위에 있는 인사이트 테이블이 아래쪽에 표시됩니다. 오른쪽 위 문서 링크](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>배터리 수명 예측

예측된 배터리 **수명** 영역에 장치 모델별로 구성되는 장치의 예상 배터리 수명에 대한 예측을 제공합니다.

> [!NOTE]
> 이 데이터는 데이터를 보고하는 Microsoft Managed Desktop 배포에서 <em></em> 임의로 선택한 디바이스에서 샘플링 에너지 사용량, 사용 시간 및 배터리 용량에서 파생됩니다.

이 표에서는 예측된 배터리 사용 시간(시간), 다른 Microsoft Managed Desktop 배포의 동일한 모델에 대한 평균 배터리 사용 시간 및 사용자 환경에서 이 데이터를 보고하는 장치 수를 제공합니다. 열 제목을 선택하여 데이터를 정렬합니다.



## <a name="top-energy-consumers"></a>상위 에너지 소비자

Top **energy consumers(Top energy consumers)** 영역에는 밀리와트 시간(mWh)에서 가장 많은 에너지가 소비되는 앱을 찾을 수 있습니다. 표시된 앱은 왼쪽의 예측 배터리 사용  수명 섹션에서 선택하는 특정 장치별입니다. 예를 들어 Microsoft Surface Book 2 장치에 대한 앱당 소비를 확인하려면 배터리 수명 영역의 해당 행을 선택합니다. 모델을 선택하지 않은 경우 표시되는 앱 사용 데이터는 데이터를 전체적으로 사용하는 모든 앱에 대한 것입니다.

 각 앱에 대해 색이 있는 세그먼트는 앱의 에너지 사용 분포를 다음과 같은 범주로 보여 주게 됩니다.

- CPU
- 표시
- 네트워크
- 기타

"기타"에는 디스크 활동, 모바일 광대역 사용량, 내부 저항으로 손실된 에너지와 같은 다양한 소스의 에너지 소비가 포함됩니다. 

오른쪽 위에 있는 메뉴를 사용하여 포그라운드 앱, 백그라운드 앱 또는 둘 다를 표시하기 위해 이 보기를 필터링할 수 있습니다. 포그라운드 앱은 마우스로 무언가를 선택하는 등 지난 28일 동안 사용자 조작이 있는 앱입니다.

## <a name="insights"></a>인사이트

**인사이트 영역에는** CPU 및 네트워크 범주의 상위 3개 에너지 소비자가 표시되어 있습니다. 이러한 항목은 모든 Microsoft Managed Desktop 배포에 비해 평균 에너지보다 더 많이 소비됩니다. 디스플레이 리소스는 장치 사용 시간 및 화면 밝기 설정에 따라 크게 달라지기 때문에 표시되지 않습니다. 

자세한 내용은 세부 정보  열에서 목록을 선택합니다.

## <a name="battery-optimization"></a>배터리 최적화

Windows 10은 [](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) 전원 사용량을 개선하고 Microsoft Managed Desktop 장치의 배터리 수명을 늘리기 위해 다양한 장치 설정을 제공합니다. 이러한 설정 중 일부는 다른 Windows 기능을 떨어질 수 있으므로 조직의 디바이스 역할과 같은 다른 요인도 고려해야 합니다. Windows 지원에서는 이러한 배터리 절약 팁 [목록을 유지 관리합니다.](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)

사용자는 관리자 권한 상승 또는 지원 없이도 일부 설정을 직접 조정할 수 있습니다. 다른 설정을 사용하려면 조직의 IT 관리자로부터 지원을 요구합니다.
