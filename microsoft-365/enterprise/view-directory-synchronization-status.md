---
title: Microsoft 365에서 디렉터리 동기화 상태 보기
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: 이 문서에서는 Office 365에서 디렉터리 동기화 상태를 확인 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: c77898b58b58c6ae91492debd7ad66f395d80d52
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692630"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>Microsoft 365에서 디렉터리 동기화 상태 보기

온-프레미스 환경을 Microsoft 365와 동기화 하 여 온-프레미스 Active Directory를 Azure AD와 통합 한 경우에도 동기화 상태를 확인할 수 있습니다.
  
## <a name="view-directory-synchronization-status"></a>디렉터리 동기화 상태 보기

- [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 하 고 홈 페이지에서 **DirSync 상태** 를 선택 합니다.
- 또는 **사용자** \> **활성 사용자**로 이동 하 여 **활성 사용자** 페이지에서 **더 많은** \> **디렉터리 동기화**를 선택 합니다. **디렉터리 동기화** 창에서 **DirSync 관리로 이동을**선택 합니다.

## <a name="information-on-the-manage-directory-synchronization-page"></a>디렉터리 동기화 관리 페이지에 대 한 정보

다음 표에서는 페이지에 대 한 정보를 얻을 수 있는 기능을 보여 줍니다.
  
디렉터리 동기화에 문제가 있으면 오류가이 페이지에도 표시 됩니다. 발생할 수 있는 다양 한 오류에 대 한 자세한 내용은 [Microsoft 365에서 디렉터리 동기화 오류 파악](identify-directory-synchronization-errors.md)를 참조 하십시오.
  
|**항목**|**용도**|
|:-----|:-----|
|**확인 된 도메인** | 사용자가 본인을 확인 한 Microsoft 365 테 넌 트의 도메인 수입니다. |
|**도메인이 확인 되지 않음** | 추가한 도메인 (확인 되지 않음) |
|**디렉터리 동기화 사용** |True 또는 False입니다. 디렉터리 동기화를 사용 하도록 설정 했는지 여부를 지정 합니다. |
|**최신 디렉터리 동기화** | 디렉터리 동기화를 마지막으로 실행 한 시간입니다. 마지막 동기화가 3 일 전까지 경고 및 문제 해결 도구에 대 한 링크를 표시 합니다. |
|**암호 동기화 사용** | True 또는 False입니다. 온-프레미스와 Microsoft 365 테 넌 트 간에 암호 해시 동기화가 있는지 여부를 지정 합니다. |
|**마지막 암호 동기화** | 암호 해시 동기화를 마지막으로 실행 한 시간입니다. 마지막 동기화가 3 일 전까지 경고 및 문제 해결 도구에 대 한 링크를 표시 합니다. |
|**디렉터리 동기화 클라이언트 버전** | 새 버전의 Azure AD Connect가 릴리스되면 다운로드 링크를 포함 합니다. |
|**디렉터리 동기화 서비스 계정** | Microsoft 365 디렉터리 동기화 서비스 계정의 이름을 표시 합니다. |