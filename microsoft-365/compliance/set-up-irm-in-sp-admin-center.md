---
title: SharePoint Online 관리 센터에서 IRM(정보 권한 관리)을 설정
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: Microsoft Azure RMS(Azure Active Directory Rights Management Services)를 통해 SharePoint Online IRM을 사용하여 SharePoint 목록 및 문서 라이브러리를 보호하는 방법을 설명합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 33e5a72ea1d0733656379bc4efdca7dd14f78cb1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819198"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>SharePoint Online 관리 센터에서 IRM(정보 권한 관리)을 설정

SharePoint Online에서 IRM 보호가 목록 및 라이브러리 수준의 파일에 적용됩니다. 조직에서 IRM 보호를 사용하기 전에 먼저 권한 관리를 설정해야 합니다. IRM은 Microsoft Azure Information Protection의 Microsoft Azure AD Rights Management 서비스에 의존하여 사용 제한을 암호화하고 할당합니다. 일부 Microsoft 365 요금제에는 Azure 권한 관리가 포함되어 있지만 모두 포함하지는 않습니다. 자세한 내용은 Office 응용 프로그램 및 서비스가 [Azure Rights Management를 지원하는 방법을 읽어보면 됩니다.](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support)
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>SharePoint 관리 센터를 사용하여 IRM 서비스 켜기

조직에서 SharePoint 목록 및 라이브러리를 IRM으로 보호하려면 먼저 조직의 권한 관리 서비스를 활성화해야 합니다. Azure 권한 관리 활성화를 [참조하세요.](https://docs.microsoft.com/information-protection/deploy-use/activate-service) 권한 관리 서비스를 사용하도록 설정하려면 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용해야 합니다. 그렇지 않으면 SharePoint Online에서 IRM 기능을 사용할 수 없습니다.
  
권한 관리 서비스를 활성화한 후 SharePoint 관리 센터에 로그인하여 IRM을 켜야 합니다.
  
1. 전역 관리자 또는 SharePoint 관리자로 로그인합니다.
    
2. 왼쪽 위에서 앱 시작 관리자 아이콘 ![The app launcher icon in Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png)을 선택하고 **관리자** 를 선택하여 Microsoft 365 관리 센터를 엽니다. (관리 타일이 없는 경우 조직에 관리자 권한이 없습니다.) 
    
3. 왼쪽 창에서 **관리** 센터 \> **SharePoint를 선택 합니다.**
    
4. 왼쪽 창에서 설정을 **선택한** 다음 클래식 설정 **페이지를 선택합니다.**
    
5. **IRM(정보 권한 관리)** 섹션에서 구성에 지정된 IRM 서비스 사용, **IRM** 설정 새로 **고침을 선택합니다.** IRM 설정을 새로 고치면 조직의 사용자들이 SharePoint 목록 및 문서 라이브러리에서 IRM 사용을 시작할 수 있습니다. 그러나 라이브러리 설정 및 목록 설정에 표시하는 데 최대 1시간이 걸릴 수 있습니다.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>IRM 사용 SharePoint 문서 라이브러리 및 목록
<a name="__toc220831191"> </a>

IRM 설정을 새로 고치면 사이트 소유자가 SharePoint 목록 및 문서 라이브러리를 IRM으로 보호할 수 있습니다. 자세한 내용은 목록 또는 라이브러리에 정보 권한 관리 [적용을 참조하십시오.](apply-irm-to-a-list-or-library.md)
  
사이트 소유자가 목록 또는 라이브러리에 대해 IRM을 사용하도록 설정하면 해당 목록 또는 라이브러리에서 지원되는 모든 파일 형식을 보호할 수 있습니다. 라이브러리에 IRM을 사용하도록 설정하면 권한 관리가 해당 라이브러리의 모든 파일에 적용됩니다. 목록에 대해 IRM을 사용하도록 설정하면 권한 관리가 실제 목록 항목이 아닌 목록 항목에 첨부된 파일에만 적용됩니다.
  
사용자가 IRM 사용 목록 또는 라이브러리에서 파일을 다운로드할 때 권한이 있는 사용자만 볼 수 있도록 파일이 암호화됩니다. 또한 각 권한 관리 파일에는 파일을 보는 사용자에 대한 제한을 적용하는 발행 라이선스가 포함되어 있습니다. 일반적인 제한으로는 파일을 읽기 전용으로 설정하고, 텍스트 복사를 사용할 수 없습니다. 사용자가 로컬 복사본을 저장하지 못하게 하는 것을 방지하고, 사용자가 파일을 인쇄할 수 없습니다. IRM 지원 파일 형식을 읽을 수 있는 클라이언트 프로그램은 권한 관리 파일 내의 발행 라이선스를 사용하여 이러한 제한을 적용합니다. 이는 권한 관리 파일이 다운로드된 후에도 보호를 유지하는 방식입니다. 목록 또는 라이브러리에서 IRM을 사용하도록 설정하려면 목록 또는 라이브러리에 정보 권한 관리 [적용을 참조하세요.](apply-irm-to-a-list-or-library.md)
  
브라우저에서 Office를 사용하여 IRM 사용 라이브러리에서 문서를 만들거나 편집할 수는 없습니다. 대신 한 번씩 IRM으로 암호화된 파일을 다운로드하고 편집할 수 있습니다. 체크 인 및 체크 아웃을 사용하여 여러 사용자에 대해 공동 작성  *또는*  제작을 관리합니다. 
  
IRM으로 보호된 라이브러리에서 PDF 파일을 다운로드하면 Microsoft 365에서 보호된 PDF 파일을 만듭니다. 파일의 확장명은 변경되지 않지만 파일이 보호됩니다. 이 파일을 보기 위해 Azure Information Protection 뷰어, 전체 Azure Information Protection 클라이언트 또는 보호된 PDF 파일 보기를 지원하는 다른 응용 프로그램이 필요합니다. 
  
SharePoint Online은 다음과 같은 파일 형식의 암호화를 지원합니다.
  
- PDF
    
- Word, Excel 및 PowerPoint와 같은 Microsoft Office 97-2003 파일 형식
    
- Word, Excel 및 PowerPoint와 같은 Microsoft Office Office Open XML 형식
    
- XPS(XML Paper Specification) 형식
 
> [!NOTE]
> SharePoint에서 업로드할 때 문서를 열기 위해 필요한 보호된 문서(예: 디지털 서명된 PDF 파일)에는 IRM 보호를 적용할 수 없습니다. 

## <a name="next-steps"></a>다음 단계
<a name="__toc220831191"> </a>

SharePoint Online에 대해 IRM을 사용하도록 설정한 후 목록 및 라이브러리에 권한 관리 적용을 시작할 수 있습니다. 자세한 내용은 목록 또는 라이브러리에 정보 권한 [관리 적용을 참조하십시오.](apply-irm-to-a-list-or-library.md)
  
Windows용 새 OneDrive 동기화 클라이언트는 이제 IRM으로 보호된 SharePoint 문서 라이브러리 및 OneDrive 위치 동기화를 지원합니다(라이브러리에 대한 IRM 설정이 문서 액세스 권한 만료로 설정되지 않은 경우). 자세한 내용은 Windows용 [새 OneDrive](https://docs.microsoft.com/onedrive/deploy-on-windows)동기화 클라이언트 배포를 참조하세요.
  
[Top of page](set-up-irm-in-sp-admin-center.md)
