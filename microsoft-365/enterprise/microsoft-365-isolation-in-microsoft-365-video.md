---
title: Office 365 비디오에서 테넌트 격리
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 이 문서에서는 테넌트가 분리되어 각 테넌트의 저장된 비디오를 Office 365 비디오에서 별도로 유지하는 방법에 대한 설명을 찾아 보세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 626a995fc5a3ac971c48cc87bec1017134e87b88
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332247"
---
# <a name="tenant-isolation-in-office-365-video"></a>Office 365 비디오에서 테넌트 격리

> [!NOTE]
> Office 365 비디오는 Microsoft Stream으로 대체됩니다. 비디오 공동 작업에 인텔리전스를 추가하는 새로운 엔터프라이즈 비디오 서비스에 대해 자세히 알아보고 현재 Microsoft 365 비디오 고객을 위한 전환 계획에 대한 자세한 내용은 [Microsoft Stream 개요로 Office 365 비디오](https://docs.microsoft.com/stream/migrate-from-office-365)전환을 참조하세요.

## <a name="introduction"></a>소개

Azure Storage는 Office 365 비디오 및 Sway를 포함하여 여러 Office 365 서비스에 대한 데이터를 저장하는 데 사용됩니다. Azure Storage에는 구조화되지 않은 데이터를 저장하는 데 사용되는 확장성이 뛰어난 REST 기반 클라우드 개체 저장소인 Blob Storage가 포함되어 있습니다. Azure Storage는 간단한 액세스 제어 모델을 사용하며, 각 Azure 구독은 하나 이상의 저장소 계정을 만들 수 있습니다. 각 저장소 계정에는 해당 저장소 계정의 모든 데이터에 대한 액세스를 제어하는 데 사용되는 단일 비밀 키가 있습니다. 이는 저장소가 응용 프로그램과 연결되어 있으며 해당 응용 프로그램이 연결된 데이터에 대한 모든 제어를 가지는 일반적인 시나리오를 지원합니다. 예를 들어 Azure Storage에 콘텐츠를 저장하는 Sway입니다. Sway의 모든 고객 콘텐츠는 공유 Azure 저장소 계정에 저장됩니다. 각 사용자의 콘텐츠는 Azure 저장소에 있는 Blob의 별도 디렉터리 트리에 있습니다.

고객 환경(예: Azure Portal, SMAPI 등)에 대한 액세스를 관리하는 시스템은 Microsoft에서 운영하는 Azure 응용 프로그램 내에서 격리됩니다. 이렇게 하여 고객 액세스 인프라를 고객 응용 프로그램 및 저장소 계층과 논리적으로 분리합니다.

## <a name="tenant-isolation-in-office-365-video"></a>Office 365 비디오에서 테넌트 격리

[Office 365 비디오는](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) 조직에 비디오 콘텐츠를 게시, 공유 및 검색할 수 있는 매우 안전한 조직 전체의 대상을 제공하는 엔터프라이즈 포털입니다. Office 365 비디오에서는 각 테넌트의 비디오가 모든 위치에서 격리 및 암호화된 상태로 유지되며, 조직의 비디오에 대한 액세스 및 사용 권한이 있는 인증된 사용자에게만 제공됩니다. Office 365 비디오에서는 기술을 조합하여 사용하여 이 작업을 수행할 수 있습니다.

- SharePoint Online은 비디오 파일 및 메타데이터(비디오 제목, 설명 등)를 저장하는 데 사용됩니다. 또한 보안 및 준수 계층(인증 포함) 및 검색 기능을 제공합니다.
- Azure Media Services는 변환, 적응 스트리밍, 보안 전달(AES 암호화 사용) 및 미리 보기 기능을 제공합니다.

[Azure Media Services는](https://azure.microsoft.com/services/media-services/) 클라우드에서 종단식 미디어 워크플로를 사용하도록 설정하기 위한 플랫폼 as-a-service 제품입니다. 플랫폼은 전 세계의 Azure 데이터 센터를 통해 미디어를 업로드, 인코딩, 암호화(PlayReady 사용) 및 전달하기 위한 REST API를 제공합니다.

Office 365 비디오에 대한 모든 업로드는 HTTPS를 통해 발생합니다. 비디오 파일이 업로드될 때 SharePoint Online에 저장되고 파일의 복사본이 암호화된 채널을 통해 Azure Media Services로 전송됩니다. Azure Media Services는 보기 환경을 위해 최적화된 여러 형식(예: 모바일, 낮은 대역폭, 높은 대역폭 등)으로 비디오를 코드 변환합니다. 이러한 파일은 업로드하는 동안 획득한 원본 파일과 함께 Azure Blob Storage에 저장됩니다. 파일은 재생을 위해 MPEG 일반 암호화 패키징 알고리즘(또는 이전 PlayReady 버전)에 따라 AES 128을 사용하여 암호화되고 Azure Blob Storage에 저장되기 전에 AES 256 저장소 암호화를 사용하여 암호화됩니다. (Azure Media Services 클라이언트 SDK를 사용하여 고객은 사용되는 암호화를 제어할 수 있습니다. 예를 들어 고객은 Azure Blob Storage를 업로드하기 전에 고가치 미디어 자산에 Azure Media Services 저장소 암호화(AES 256)를 적용할 수 있습니다.

Azure Media Services는 또한 비디오에 대한 미리 보기를 생성하여 암호화된 채널을 통해 미리 보기 메타데이터와 함께 SharePoint Online으로 전송합니다.
