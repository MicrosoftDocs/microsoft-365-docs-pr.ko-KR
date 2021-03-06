---
title: 장치에 앱 배포
description: Microsoft Managed Desktop 디바이스에 앱을 추가하고 배포하기 위한 정보입니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 앱, LOB 앱
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eb8b984550f301af9d99e738f6db4623aa2cc86
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769109"
---
# <a name="deploy-apps-to-devices"></a>장치에 앱 배포
Microsoft Managed Desktop에 대한 온보드의 일부로 사용자의 장치에 앱을 추가하고 배포하는 것이 포함됩니다. Microsoft Managed Desktop 포털을 사용하고 나면 앱을 추가하고 배포할 수 있습니다. 

전체 프로세스는 다음과 같습니다.
1. [Microsoft Managed Desktop](#1) 포털에 앱 추가 - 기존 LOB(LOB) 앱 또는 Intune과 동기화한 비즈니스용 Microsoft Store의 앱일 수 있습니다. 
2. [앱 할당에 대한 Azure AD(Active Directory)](#2) 그룹 만들기 - 이러한 그룹을 사용하여 앱 할당을 관리합니다.
3. [사용자에게 앱 할당](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>1단계: Microsoft Managed Desktop 포털에 앱 추가
[Win32 또는 Windows MSI](#lob-apps)기반 앱 또는 [비즈니스용 Microsoft Store](#msfb-apps) 앱을 Microsoft Managed Desktop에 추가한 다음 Microsoft Managed Desktop 디바이스에 배포할 수 있습니다.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Microsoft Managed Desktop으로의 Win32 또는 Windows MSI 기반 앱

LOB(LOB) 앱을 Microsoft Managed Desktop 포털에 추가할 수 있습니다. Microsoft Managed Desktop 장치에 설치된 앱의 요구 사항에 대한 자세한 내용은 Microsoft Managed Desktop 앱 요구 [사항을 참조하세요.](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)

이 절차에서는 추가할 앱 종류를 선택한 다음 앱 원본을 구성하고 업로드합니다. 

**LOB 앱 또는 Windows 앱을 Microsoft Managed Desktop 포털에 추가**

Microsoft Managed Desktop 포털에 로그인하거나 Intune에 로그인한 다음 Microsoft Managed Desktop을 검색할 수 있습니다. Microsoft Managed Desktop 포털에 로그인하는 것이 표시됩니다. 

1.    [Microsoft Managed Desktop 관리 포털에 로그인합니다.](https://aka.ms/mmdportal) 
2.    **인벤토리에서** 앱을 **선택합니다.**
3.    앱 워크로드에서 추가를 **선택합니다.**
4.    앱 **추가에서**  업무 앱 또는 Windows **앱(Win32)을 선택합니다.**
    - 업무용 앱을 선택한 경우 MICROSOFT [Intune에 Windows](https://docs.microsoft.com/intune/lob-apps-windows) 업무 앱 추가를 참조하여 업무 앱 추가 및 구성에 대한 지침이 표시됩니다.
    - **Windows 앱(Win32)을** 선택한 경우 Windows 앱 추가 및 구성에 대한 지침은 [Win32](https://docs.microsoft.com/intune/apps-win32-app-management) 앱 관리를 참조하세요.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>비즈니스용 Microsoft Store 앱
비즈니스용 Microsoft Store에 등록하지 않은 경우 앱을 쇼핑할 때 등록할 수 있습니다. 앱을 다운로드한 후 Microsoft Managed Desktop과 동기화할 수 있습니다. 

**비즈니스용 Microsoft Store에서 앱을 구입하는 경우**

1. 비즈니스용 [Microsoft Store](https://businessstore.microsoft.com) 관리자 계정으로 비즈니스용 Microsoft Store에 로그인합니다.
2. Select **Shop for my group.**
3. 검색을 사용하여 원하는 앱을 찾고 앱을 선택합니다.
4. 제품 세부 정보에서 앱 **다운로드를 선택합니다.** Microsoft Store는 조직의 제품에 **앱을** 추가합니다.

**Intune과 비즈니스용 Microsoft Store 간에 동기화를 강제로 설정**
1. Microsoft Endpoint Manager 관리 [센터에 로그인합니다.](https://go.microsoft.com/fwlink/?linkid=2109431)
2. **테넌트 관리** 커넥터를 선택하고 비즈니스용  >    >  **Microsoft Store를 토큰합니다.**
3. **동기화를** 선택하여 Microsoft Store에서 Intune으로 구입한 앱을 다운로드합니다.

**Intune과 비즈니스용 Microsoft Store 간의 동기화가 활성 상태인지 확인**
1. 비즈니스용 [Microsoft Store](https://businessstore.microsoft.com) 관리자 계정으로 비즈니스용 Microsoft Store에 로그인합니다.
2. 관리 **선택**.
3. 설정을 **선택하고** 배포를 **선택합니다.**
4. 관리 **도구에서** Intune이 나열되어 있으며 상태가 활성 상태인지 **확인**  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>2단계: Azure AD 그룹 만들기

각 앱에 대해 3개의 Azure AD 그룹을 생성합니다. 다음 표에서는 필요한 그룹(사용 가능, 필수 및 제거)에 대해 간략하게 설명합니다. 

앱 할당 유형 |    그룹 사용    | 예제 Azure AD 이름
--- | --- | ---
사용할 수 있음 |  이 앱은 회사 포털 앱 또는 웹 사이트에서 사용할 수 있습니다. | MMD - *앱 이름* - 사용 가능
필수 |  앱은 선택한 그룹의 장치에 설치됩니다. | MMD – *앱 이름* - 필수
Uninstall |  선택한 그룹의 장치에서 앱이 제거됩니다. | MMD – *앱 이름* - 제거

앱을 사용할 수 있도록 설정하거나, 앱을 설치하거나, Microsoft Managed Desktop 장치에서 앱을 제거하려면 이러한 그룹에 사용자를 추가합니다. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>3단계: 사용자에게 앱 할당

**사용자에게 앱을 할당하기 위해**

1. [Microsoft Managed Desktop 관리 포털에 로그인합니다.](https://aka.ms/mmdportal)
2. 관리되는 데스크톱 창에서 앱을 **선택합니다.**
3. 앱 워크로드에서 사용자에게 할당할 앱을 선택하고 사용자 그룹 **할당을 선택합니다.**
4. 특정 앱에 대해 할당 유형(사용 가능, 필수, 제거)을 선택하고 적절한 그룹을 할당합니다.
5. 앱 할당 창에서 확인을 **선택합니다.**


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop을 시작하기 위한 단계

1. [관리 포털에서 관리자 연락처 추가 및 확인](add-admin-contacts.md)
2. [조건부 액세스 조정](conditional-access.md)
3. [라이선스 할당](assign-licenses.md)
4. [Intune 회사 포털 배포](company-portal.md)
5. [엔터프라이즈 상태 로밍 사용](enterprise-state-roaming.md)
6. [장치 설정](set-up-devices.md)
7. [사용자들이 장치를 사용할 수 있도록 준비시키기](get-started-devices.md)
8. 앱 배포(이 항목)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
