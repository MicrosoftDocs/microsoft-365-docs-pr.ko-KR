---
title: 두 계정 간에 수동으로 데이터 전송
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 7dc5d983-84b2-4802-bef0-602ae1780a42
description: 요금제 또는 회사 이름을 변경하거나 여러 구독을 하나의 계정으로 결합한 경우 두 Microsoft 365 계정 간에 데이터를 수동으로 전송하는 방법을 찾아야 합니다.
ms.openlocfilehash: b7b0bb9c9b95b31d98040ae90632ef87a7fb0e3b
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645146"
---
# <a name="transfer-data-manually-between-two-accounts"></a>두 계정 간에 수동으로 데이터 전송

일정에서 여유를 옮기고 시간 청크를 차단할 준비를 합니다. 두 Microsoft 365 계정 간에 데이터를 전송하는 것은 수동, 복잡하고 시간이 많이 걸리는 프로세스입니다. 이 프로세스는 자동화되거나 지원되는 프로세스가 아니며, 시작을 하게 될 것입니다.
  
> [!CAUTION]
> 전자 메일, 비즈니스용 Skype 및 Microsoft 365에 호스트된 공개 웹 사이트가 작동하지 않는 프로세스가 진행되는 동안에는 작동이 되지 않습니다. 사용자는 새 사용자 이름과 암호를 얻을 수 있으며 Outlook을 다시 설정해야 합니다.

**다음 중 하나를 적용하는 경우 이 항목의 지침을 사용하여 수동으로 데이터를 전송합니다.**
  
- 다른 서비스 패밀리의 계획으로 변경해야 합니다.

- 회사 이름이 변경된 후 다른 초기 도메인 이름을 사용하려는 경우 새 구독을 만들고 데이터를 마이그레이션하기로 결정했습니다.

- 여러 구독을 하나의 새 구독으로 결합해야 합니다.

> [!IMPORTANT]
> 구독 계획을 [](../../commerce/subscriptions/switch-to-a-different-plan.md) 변경해야 하는 경우 및 요금제 전환 마법사를 사용할 수 있는 경우 또는 요금제 전환 마법사가 작동하지 않는 경우에도 동일한 구독 패밀리의 새 구독 요금제로 이전해야 하는 경우 데이터를 수동으로 전송할 필요가 없습니다. 작동이 쉽지 않습니다.

|**Tasks**|**Steps**|
|:-----|:-----|
|이동하려는 계획을 구매합니다.  <br/> |등록할 때 초기 도메인 이름에 사용할 회사 이름(예: *yourcompany* .onmicrosoft.com, *yourcompany* -public.sharepoint.com 및company .sharepoint.com.  기존 구독과  *다른company*  이름을 사용해야 합니다.  <br/> > [!NOTE]> 시스템에서 해당 구성을 사용하는 초기 도메인 이름을 해제하기 위해 구독을 취소한 후 일반적으로 최소 몇 개월이 걸릴 수 있습니다.  이전 Microsoft 365 구독의 모든 데이터를 저장하고 해당 구독을 취소하는 경우에도  *이전company*  값을 새 구독에서 즉시 사용할 수 없습니다.           |
|이전 Microsoft 365 구독에서 사용자 지정 도메인을 제거합니다.  <br/> | 도메인을 [](remove-a-domain.md) 제거하기 전에 필요한 단계에 따라 사용자 전자 메일 주소에서 도메인 이름을 제거하고 사용자 지정 도메인의 전자 메일 및 Lync에 대한 DNS 레코드를 제거합니다. Microsoft 365에서 공개 웹 사이트를 호스팅하는 경우 해당 웹 사이트를 지점으로 하는 CNAME 레코드도 제거해야 합니다.  <br/> > [!IMPORTANT]> 이 사용자 지정 도메인으로 전자 메일을 라우팅하는 MX 레코드를 제거하면 새 계정에 도메인을 추가하고 새 MX 레코드를 설정하고 사용자를 설정할 때까지 전자 메일의 작동이 중지됩니다. Lync에 대한 DNS 레코드를 제거하면 Lync의 작동이 중지됩니다. 또한 공개 웹 사이트를 포인트로 하는 CNAME 레코드를 제거하면 사용할 수 없습니다.           [도메인을 제거합니다.](remove-a-domain.md)  <br/> |
|새 구독에 대한 사용자 지정 도메인을 설정하고 사용자를 설정합니다.  <br/> | 사용자 지정 도메인에 필요한 DNS 레코드 만들기를 포함하여 새 구독을 설정합니다.  <br/>  사용자 지정 도메인의 전자 메일 주소를 사용하여 사용자를 만들 수 있습니다.  <br/> |
|이전 구독에서 새 구독으로 데이터를 전송합니다.  <br/> | 별도의 브라우저 창에서 두 계정 모두에 로그인합니다.  <br/>  브라우저 아이콘을 마우스 오른쪽 단추로 클릭하고 두 개의 개인 브라우저 창을 여는 방법을 제공합니다. 두 창에서 서로 다른 자격 증명을 사용하여 두 계정 모두에 로그인할 수 있습니다.  <br/> [구독 간에 관리 설정 전송](#email) <br/> [팀 사이트 구조 및 데이터 전송](#transfer-team-site-structure-and-data) <br/> [구독 간에 공개 웹 사이트 전송](#transfer-a-public-website-between-subscriptions) <br/> [구독 간에 관리 설정 전송](#email) <br/> |
|Microsoft 365에 대한 Microsoft 지원에 문의하여 완료한 요금제의 구독을 취소합니다.  <br/> | 새 구독이 작동 중이고 모든 데이터가 전송된지 확인  <br/>  [고객 지원에 문의하여](../contact-support-for-business-products.md) 이전 구독을 취소합니다.  <br/> |

## <a name="transfer-administrative-settings-between-subscriptions"></a>구독 간에 관리 설정 전송

각 계정의 다음 페이지로 이동하여 이전 계정의 설정에 따라 새 계정을 설치합니다.
  
Microsoft 365에서 Microsoft 365 Midsize Business 또는 Microsoft 365 Enterprise로 데이터를 전송하는 경우 관리 페이지는 다르게 구성됩니다. 비디오 [시청: Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365/admin/)소개 및 다음 위치로 이동하여 관리자 설정을 확인합니다.
  
Microsoft 365 Enterprise 및 Microsoft 365 Midsize Business의 경우:
  
|**위치**|**용도**|
|:-----|:-----|
|**관리자** \> **Microsoft 365** \> **서비스 설정** <br/> |메일, 사이트, Lync, 사용자 소프트웨어, 암호, 커뮤니티, 권한 관리 및 모바일에 대한 설정에 대해 각 탭을 선택합니다.  <br/> |
|**관리자** \> **Exchange** <br/> | Exchange Online 설정  <br/> |
|**관리자** \> **SharePoint** <br/> | SharePoint Online 설정  <br/> |
|**관리자** \> **비즈니스용 Skype** <br/> |추가 비즈니스용 Skype 설정  <br/> |

For Microsoft 365 Small Business
  
|**위치**|**용도**|
|:-----|:-----|
|**관리자** \> **조직 전체 설정 관리** <br/> |관리 설정  <br/> |

## <a name="transfer-a-public-website-between-subscriptions"></a>구독 간에 공개 웹 사이트 전송

Microsoft 365에서 호스팅하는 공개 웹 사이트가 있는 경우 해당 웹 사이트를 저장하고 새 구독에서 다시 만들어야 합니다.
  
> [!NOTE]
> 공개 웹 사이트가 DNS 호스팅 공급자에서 호스팅되는 경우 변경이 필요하지 않습니다. 전환의 영향을 받지 않습니다.
  
SharePoint Online 환경에서 파일 공유 또는 로컬 컴퓨터로 문서 라이브러리 또는 목록 콘텐츠를 저장하려면 SharePoint Online 콘텐츠의 수동 [마이그레이션을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=402910)
  
> [!NOTE]
> 공용 사이트 마이그레이션 앱은 데이터를 다른 구독으로 전송할 수 없습니다.
  
## <a name="transfer-team-site-structure-and-data"></a>팀 사이트 구조 및 데이터 전송

팀 사이트 데이터를 저장하거나 전송하는 방법에는 여러 가지가 있습니다.
  
- 이전 사이트를 서식 파일로 저장하고 서식 파일을 새 사이트로 가져올 수 있습니다.

- 문서를 전송하려면 먼저 새 사이트에서 계층 구조를 수동으로 다시 작성합니다. 그런 다음 두 SharePoint 팀 사이트를 동시에 열고, Windows 탐색기를 사용하여 두 문서 라이브러리를 열고, 문서를 복사하여 붙여넣을 수 있습니다. 비디오 [참조: 탐색기에서 열기를](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790)사용하여 라이브러리 파일 복사 또는 이동

- 목록 데이터를 전송하기 위해 목록 서식 파일을 저장하고 [저장된](https://support.microsoft.com/office/c3884ad1-bc49-44b8-b3d6-3bc6a01eb393)서식 파일을 사용하여 새 사이트에서 목록을 다시 만듭니다.

- SharePoint Online 환경(비즈니스용 OneDrive 또는 팀 사이트)에서 파일 공유 또는 로컬 컴퓨터에 문서 라이브러리 또는 목록 콘텐츠를 저장하려면 [SharePoint Online](https://support.microsoft.com/kb/2783484)콘텐츠의 수동 마이그레이션에 대한 정보를 참조하세요.

## <a name="transfer-users-data-between-subscriptions"></a>구독 간에 사용자 데이터 전송

### <a name="email"></a>메일 주소:

새 구독을 설정한 후 사용자에게 전자 [메일, 연락처,](https://support.microsoft.com/office/0996ece3-57c6-49bc-977b-0d1892e2aacc) 작업 및 일정 정보를 이동하게 요청합니다. 사용자는 이전 전자 메일과 같은 초기 사용자 이름을 사용하여 이전 전자 메일로 sue@contoso.onmicrosoft.com.
  
### <a name="onedrive-for-business-data"></a>비즈니스용 OneDrive 데이터:

사용자에게 비즈니스용 [OneDrive](https://support.microsoft.com/office/59b1de2b-519e-4d3a-8f45-51647cf291cd)콘텐츠를 복사/동기화할 수 있도록 요청한 다음 새 구독에 다시 추가합니다.

### <a name="onenote"></a>OneNote 

사용자에게 [OneNote를](https://support.microsoft.com/office/back-up-notes-f58b34b0-611d-435e-87fa-7942a1767af4?ui=en-us&rs=en-us&ad=us) 백업하고 [](https://support.microsoft.com/en-us/office/restore-notes-from-a-backup-5daf9cb0-6769-4998-a5de-f044fdd0d831?ui=en-us&rs=en-us&ad=us) 백업에서 새 구독으로 메모를 복원하도록 요청합니다.
