---
title: Microsoft OneDrive
description: Microsoft Managed Desktop에서 등록된 장치에 대해 OneDrive를 설정하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 앱, LOB 앱
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 6cd2c993e0ca9d4c456a2914b866b65b59799afa
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233925"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft Managed Desktop은 비즈니스용 [OneDrive를](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) 모든 Microsoft Managed Desktop 장치에 대한 클라우드 저장소 서비스로 사용하여 장치가 가능한 한 상태를 저장하지 않도록 합니다. 사용자는 로그인하는 디바이스에 상관없이 파일을 찾을 수 있습니다. 예를 들어 Microsoft Managed Desktop 장치를 새 장치로 바꾸면 파일이 새 디바이스에 자동으로 동기화됩니다.

Microsoft Managed Devices에서 기본적으로 이러한 설정을 자동으로 구성합니다.

- OneDrive는 사용자 계정으로 자동으로 구성되며 사용자 조작 없이 Windows에 로그인하는 데 사용된 사용자 계정에 자동으로 로그인됩니다. 자세한 내용은 사용자 계정 자동 구성 [- OneDrive를 참조하세요.](https://docs.microsoft.com/onedrive/use-silent-account-configuration)

- 사용자가 디스크 공간을 불필요하게 사용하지 않고도 OneDrive의 클라우드 저장소에서 파일에 액세스할 수 있도록 파일 관리 기능을 사용할 수 있습니다. 자세한 내용은 [Windows 10용 OneDrive On-Demand 파일로 디스크 공간 저장을 참조하세요.](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)

- 알려진 폴더 이동 기능은 클라우드에서 사용자의 데이터를 백업할 수 있도록 자동으로 사용하도록 설정되어 모든 장치에서 파일에 액세스할 수 있습니다. 자세한 내용은 [OneDrive를](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)사용하여 문서, 사진 및 데스크톱 폴더 백업을 참조하세요.

- 사용자는 알려진 폴더 이동 기능을 사용하지 않도록 설정하거나 알려진 폴더의 위치를 변경하여 Microsoft Managed Desktop 장치에서 일관된 환경을 보장할 수 없습니다.

## <a name="user-experience"></a>사용자 환경

Microsoft Managed Desktop 사용자가 새 디바이스를 받으면 디바이스를 설정하는 동안 Azure 자격 증명을 입력하여 첫 실행 환경을 진행합니다. 이 프로세스가 완료되면 데스크톱에 액세스하고 OneDrive 환경을 사용할 수 있습니다.

1. 시스템은 OneDrive가 구성되어 있으며 OneDrive에 자동으로 로그인되어 있는지 사용자에게 알 수 있습니다.

:::image type="content" source="media/onedrive-sync.png" alt-text="이제 OneDrive를 동기화하고 있으며 OneDrive에서 파일을 편집할 수 있습니다. 파일을 보려면 여기를 클릭하십시오.":::

2. 시스템은 OneDrive 알려진 폴더 이동이 해당 폴더에 대해 구성되어 있는지 사용자에게 알 수 있습니다.

:::image type="content" source="media/onedrive-folders.png" alt-text="IT 부서를 읽은 알림이 중요한 폴더를 백업했습니다. 이제 폴더가 OneDrive에 백업된 후 다른 장치에서 사용할 수 있습니다.":::

3. 디바이스를 초기화하거나 다시 초기화할 때 바탕 화면의 중복 아이콘을 방지하기 위해 시스템은 파일 탐색기의 이 보기에 표시된 같이 OneDrive 동기화에서 Microsoft Edge 및 Microsoft Teams 아이콘을 자동으로 제거합니다.

:::image type="content" source="media/onedrive-teams.png" alt-text="선택 취소된 확인란 및 마우스로 읽은 마우스 텍스트 읽기가 동기화에서 제외된 Teams 및 Edge 목록을 표시하는 파일 탐색기입니다.":::


## <a name="onedrive-sync-restrictions"></a>OneDrive 동기화 제한

OneDrive 동기화를 제한해야 하는 경우 Azure Active Directory 조건부 액세스 정책을 사용하여 액세스를 제어하는 것이 좋습니다. 자세한 내용은 OneDrive 동기화 앱에서 조건부 액세스 지원 [사용을 참조하세요.](https://docs.microsoft.com/onedrive/enable-conditional-access)

조직에서 Azure AD 조건부 액세스 정책을 사용할 수 없는 경우 IT 관리자는 다음 단계를 따라야 합니다.

1. 아직 모르는 경우 Microsoft 365 테넌트 ID 찾기에 설명된 테넌트 [ID를 찾아 봐야 합니다.](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id)
2. OneDrive 관리 센터에 로그인한 다음  왼쪽 창에서 동기화를 선택합니다. 특정 도메인에 가입된 **PC에서만** 동기화 허용 확인란을 선택한 다음 도메인 목록에 테넌트 ID를 추가합니다. 자세한 내용은 특정 도메인에 가입된 컴퓨터에서만 동기화 [허용을 참조하세요.](https://docs.microsoft.com/onedrive/allow-syncing-only-on-specific-domains)

> [!NOTE]
> 이 지침은 Microsoft Managed Desktop의 테넌트에만 적용됩니다. 이 문서에서 설명하지 않은 다른 설정이 사용 중입니다.
