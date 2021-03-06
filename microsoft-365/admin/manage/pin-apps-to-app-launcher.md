---
title: 사용자의 앱 시작에 앱 고정
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: 전역 관리자는 사용자의 앱 시작 관리자에 최대 3개의 앱을 고정할 수 있습니다.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310878"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>사용자의 앱 시작에 앱 고정

Azure Active Directory 포털의 컨트롤을 사용하여 조직의 모든 사용자에 대해 최대 Office.com 앱을 고정할 수 있습니다. 응용 프로그램 그룹을 구성할 수 있습니다. 나중에 추가하는 모든 앱은 사용자가 원하는 경우 이 기능을 언핑할 수 있습니다. 사용자를 위해 앱을 고정하려면 클라우드 응용 프로그램 관리자 또는 Azure Active Directory의 응용 프로그램 관리자 또는 Office 365의 전역 관리자입니다. 관리자 역할에 대한 자세한 내용은 [Azure Active Directory의](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 관리자 역할 및 [Microsoft 365의](../add-users/about-admin-roles.md)관리자 역할을 참조하세요. 

앱 시작 프로그램 및 앱 Office.com 대한 자세한 [](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) 내용은 앱 시작 office.com 및 [Office 365](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) 앱 시작 프로그램 블로그 문서를 참조하세요.

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Azure Active Directory 포털을 사용하여 앱 고정

1. Go to the Microsoft 365 admin center <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> at.
2. In the left nav, choose **All,** and under **Admin centers,** choose **Azure Active Directory**.
3. **Azure Active Directory에서** 엔터프라이즈 응용 **프로그램 사용자 설정을**  >  **선택합니다.**
4. Office **365 설정** 섹션에서 응용 프로그램 **추가를 선택합니다.**
5. 사용자의 앱 시작 프로그램에 고정하려는 응용 프로그램을 선택한 다음 추가를 **선택하십시오.**

:::image type="content" source="../../media/add-apps.png" alt-text="앱을 고정하기 위해 Microsoft 365 설정":::

### <a name="pin-a-custom-app"></a>사용자 지정 앱 고정

> [!NOTE]
> 이 기능을 사용하기 위해 추가 Azure AD 라이선스를 구입해야 하는지가 사용자 인터페이스에 표시됩니다. 자세한 내용은 [Azure Active Directory 가격을 참조하세요.](https://azure.microsoft.com/pricing/details/active-directory/)

1. **Azure Active Directory에서** 모든 응용 프로그램 페이지의 맨 위에 있는 엔터프라이즈 응용 프로그램 새 응용   >   **프로그램을** 선택합니다.
2. 응용 프로그램 **추가 페이지에서**  갤러리가 아닌 응용  프로그램을 선택하거나 Azure Active Directory의 미리 보기 버전에 있는 경우 자체 응용 프로그램을 만드십시오. 
3. 응용 프로그램의 이름을 입력한 다음 사용자 및 그룹 탭에 사용자를 **할당합니다.**
4. 속성 **탭을** 사용하여 앱의 아이콘을 업로드합니다.
5. 앱에 URL을 할당하기 위해 **Single Sign-On** 탭에서 **연결된** URL을 선택한 다음 URL을 입력합니다.
6. **저장** 을 선택합니다.

## <a name="create-application-collections"></a>응용 프로그램 컬렉션 만들기

조직의 사용자에 대한 응용 프로그램 컬렉션을 만들 수도 있습니다. 자세한 내용은 Azure Portal의 내 앱 포털에서 [컬렉션 만들기를 참조하세요.](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections)