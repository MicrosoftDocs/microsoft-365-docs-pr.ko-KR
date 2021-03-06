---
title: SharePoint Online 클래식 게시 사이트에 대한 이미지 최적화
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/18/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c7edb02a-fdab-4f91-9a20-cba01dad28ef
description: SharePoint Online 클래식 게시 사이트에서 이미지 성능을 개선하기 위해 버전 및 스프라이트를 사용하는 방법을 학습합니다.
ms.openlocfilehash: 47d0f085c13c192417842fcef88c695fe875124c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692529"
---
# <a name="image-optimization-for-sharepoint-online-classic-publishing-sites"></a>SharePoint Online 클래식 게시 사이트에 대한 이미지 최적화

웹 페이지의 로드 속도는 이미지, HTML, JavaScript 및 CSS를 포함하여 페이지를 렌더링하는 데 필요한 모든 구성 요소의 조합된 크기에 따라 달라 습니다. 이미지는 사이트를 더욱 매력적으로 만들 수 있는 좋은 방법이지만 크기는 성능에 영향을 줄 수 있습니다. 압축 및 크기 조정으로 이미지를 최적화하고 스프라이트를 사용하여 매우 큰 이미지의 효과를 오프셋할 수 있습니다. SharePoint 이미지 Nditions를 사용하면 큰 단일 이미지를 업로드하고 이미지의 섹션을 표시하여 다시 로드하지 않고 다시 사용할 수 있습니다.

>[!NOTE]
>이 항목은 최신 포털 사이트가 아니라 SharePoint Online 클래식 게시 사이트에 적용됩니다. SharePoint Online 최신 포털 사이트의 이미지 최적화에 대한 자세한 내용은 SharePoint Online 최신 포털 페이지에서 이미지 [최적화를 참조하세요.](modern-image-optimization.md)
  
## <a name="using-sprites-to-speed-up-image-loading"></a>스프라이트를 사용하여 이미지 로드 속도 향상

|||
|:-----|:-----|
| 이미지 스프라이트에는 여러 개의 작은 이미지가 포함되어 있습니다. CSS를 사용하면 절대 위치가 있는 페이지의 특정 부분에 표시할 복합 이미지 부분을 선택합니다. 기본적으로 여러 이미지를 로드하는 대신 페이지 주위에 단일 이미지를 이동하고 스프라이트 이미지의 필수 부분이 최종 사용자에게 표시되는 작은 창을 통해 해당 이미지의 작은 부분을 볼 수 있도록 만듭니다. SharePoint Online에서는 스프라이트를 사용하여 스프라이트의 여러 아이콘을 spcommon.png.  <br/>  여기서 다루는 사항:  <br/>  이미지 압축  <br/>  이미지 최적화  <br/>  SharePoint 이미지 Nditions  <br/> |![spcommon의 스크린샷](../media/cc5cdee1-8e54-4537-9a8a-8854f4ee849f.png)|
   
이렇게 하는 경우 여러 이미지 대신 하나의 이미지만 다운로드한 다음 해당 이미지를 캐시하고 다시 사용할 수 있기 때문에 성능이 향상될 수 있습니다. 이미지가 캐시된 상태로 유지되지 않는 경우에도 여러 이미지 대신 단일 이미지를 사용하여 이 메서드를 사용하면 서버에 대한 총 HTTP 요청 수가 줄어들어 페이지 로드 시간이 줄어듭니다. 이는 실제로 이미지 번들화의 한 형태입니다. 이 방법은 위에 제공된 SharePoint 예제와 같이 이미지가 자주 변경되지 않는 경우(예: 아이콘) 매우 유용한 기술입니다. 타사 오픈 소스 커뮤니티 기반 [프로젝트인 Web Essentials를](https://vswebessentials.com/)사용하여 Microsoft 365에서 쉽게 이 기능을 Visual Studio. 자세한 내용은 SharePoint Online의 최소화 및 [번들링을 참조하세요.](https://go.microsoft.com/fwlink/?LinkId=708698)
  
## <a name="using-image-compression-and-optimization-to-speed-up-page-loading"></a>이미지 압축 및 최적화를 사용하여 페이지 로드 속도 향상

이미지 압축 및 최적화는 사이트에서 사용하는 이미지의 파일 크기를 줄이는 것입니다. 이미지 크기를 줄이는 가장 좋은 방법은 사이트에서 볼 수 있는 최대 크기로 이미지 크기를 변경하는 것입니다. 이미지를 보기보다 크게 하는 것은 의미가 없습니다. 이미지 편집기를 사용하여 이미지가 올바른 크기로 표시하는 것이 페이지 크기를 빠르고 쉽게 줄일 수 있는 방법입니다.
  
이미지 크기가 올바른 경우 다음 단계는 이러한 이미지의 압축을 최적화하는 것입니다. 사진 갤러리 및 타사 도구를 포함하여 압축 및 최적화에 사용할 수 있는 다양한 도구가 있습니다. 압축의 핵심은 최종 사용자의 품질을 잃지 않고 파일 크기를 최대한 줄이는 것입니다. 압축된 파일을 고화질 디스플레이에서 테스트하여 파일이 계속 보기 좋게 표시되도록 합니다.
  
## <a name="speed-up-page-downloads-by-using-sharepoint-image-renditions"></a>SharePoint 이미지Ndition을 사용하여 페이지 다운로드 속도 향상

이미지 버전은 미리 정의된 이미지 크기에 따라 여러 버전의 이미지를 지원할 수 있는 SharePoint Online의 기능입니다. 이는 사용자 생성 이미지 콘텐츠가 있는 경우나 사이트의 CSS에 의해 너비 및 높이와 같은 이미지 크기를 고정하는 경우 특히 중요합니다. 이미지를 CSS로 수정한 경우에도 전체 해상도 이미지가 계속 로드됩니다. 이 경우 이미지 변경을 사용하여 파일 크기를 줄일 수 있습니다.
  
> [!NOTE]
> 게시를 사용하도록 설정한 경우 SharePoint에서만Nditions를 사용할 수 있습니다. 사이트 설정 관리 사이트 기능 SharePoint Server 게시에서 게시를 사용하도록 \> \> 설정할 수 \> 있습니다. 그렇지 않으면 옵션이 나타나지 않습니다.
  
이미지 크기 조정은 정의하는 가장 작은 차원(너비 또는 높이)을 고려한 다음 가로 세로 비율에 따라 다른 차원의 크기가 자동으로 조정될 수 있도록 이미지의 크기 조정을 통해 작동합니다. 기본적으로 이미지가 가운데에서 나머지 크기로 자르기됩니다. 예를 들어 너비가 100px와 50px로 정의하고 원래 이미지의 너비가 1000px와 800px인 경우 크기는 이제 800px 차원이 50px로, 1000px 차원(현재 62.5px)이 이미지 중심에서 잘리게 됩니다.
  
단계는 비교적 간단하지만 이미지가 해당 NDITION을 사용하려면 이미지를 추가하기 전에 SharePoint 사이트에 해당 Nditions가 필요합니다. 또한 SharePoint Server 게시 인프라(사이트 모음 수준) 및 SharePoint Server 게시(사이트 수준) 기능도 켜져야 합니다.
  
### <a name="add-an-image-rendition-to-speed-up-page-loading"></a>페이지 로드 속도를 향상하기 위해 이미지 Ndition 추가
  
1. 이 절차를 수행하는 사용자 계정에 최소한 사이트 모음의 최상위 사이트에 대한 디자인 권한이 있으며 해당 사이트가 웹 페이지로 게시되고 있는지 확인해야 합니다.

2. 웹 브라우저에서 게시 사이트 모음의 최상위 사이트로 이동하십시오.

3. 설정 **아이콘을** 선택합니다.

4. 사이트 설정 **페이지의** 모양  및 느낌 섹션에 기본 제공 이미지가 표시됩니다.

    기본으로 사용할 수 있는Nditions를 사용하거나 이미지 변경을 사용하여 새 이미지를 만들 수 있습니다. 

    ![Image Rendition 스크린샷](../media/eaae0d53-657d-47ef-b687-65c5167eae4d.PNG)
  
5. 이미지 **재배포 페이지에서** 새 항목 **추가를 선택합니다.**

    ![새 항목 추가를 보여 주는 스크린샷](../media/8cede22e-52bf-4d9d-99cb-162f2f6ce92b.PNG)
  
6. 새 **이미지 변경** 페이지의 **이름** 상자에 해당 변경의 이름을 입력합니다.

7. 너비  및 **높이** 텍스트 상자에 텍스트 상자의 너비와 높이를 픽셀 단위로 입력한 다음 저장을 **선택해야 합니다.**

    ![이미지 변환 이름을 보여 주는 스크린샷](../media/5a6119ed-c163-40df-a4db-ec629d15607d.PNG)
  
## <a name="custom-cropping-with-image-renditions"></a>이미지Ndition을 사용하여 사용자 지정 자르기

기본적으로 이미지가 이미지의 가운데에서 생성됩니다. 사용하려는 이미지 부분을 자르면 개별 이미지에 대한 이미지 Ndition을 조정할 수 있습니다. 이미지를 개별적으로 자르면 됩니다. 이미지를 자르면 SharePoint의 Blob 캐시를 사용하여 각 버전에 대한 이미지 버전을 만들어 페이지 로드 속도를 향상할 수 있습니다. 이렇게 하면 이미지의 배정이 한 번만 줄어들고 최종 사용자에게 여러 번 서비스를 제공해야 하기 때문에 서버 부하가 줄어듭니다. 이미지 재배포를 자르는 방법에 대한 자세한 내용은 [이미지 자르기(자르기)를 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=525626)
  

