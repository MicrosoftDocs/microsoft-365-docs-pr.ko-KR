---
title: 관리 센터에서 추가 기능 관리
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 관리 센터에서 중앙 집중식 배포를 사용 하 여 조직의 사용자 및 그룹에 추가 기능을 배포 하는 방법을 알아봅니다.
ms.openlocfilehash: caaea8404c099f56704d21684323a4b20e61f52d
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103114"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="685c9-103">관리 센터에서 추가 기능 관리</span><span class="sxs-lookup"><span data-stu-id="685c9-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="685c9-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-104">The admin center is changing.</span></span> <span data-ttu-id="685c9-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="685c9-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="685c9-106">Office 추가 기능은 문서를 개인 설정 하 고 웹에서 정보에 액세스 하는 방법을 간소화 하는 데 도움이 됩니다 ( [Office 추가 기능 사용 시작](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)참조).</span><span class="sxs-lookup"><span data-stu-id="685c9-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="685c9-107">관리자가 조직의 사용자에 대 한 추가 기능을 배포한 후에는 관리자가 추가 기능을 해제 하거나 설정, 편집, 삭제 및 관리 하 여 추가 기능에 대 한 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="685c9-108">관리 센터에서 추가 기능을 설치 하는 방법에 대 한 자세한 내용은 [관리 센터에서 추가 기능 배포](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="685c9-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="685c9-109">추가 기능 상태</span><span class="sxs-lookup"><span data-stu-id="685c9-109">Add-in states</span></span>

<span data-ttu-id="685c9-110">추가 기능의 **설정** 또는 **해제** 상태 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="685c9-111">**상태**</span><span class="sxs-lookup"><span data-stu-id="685c9-111">**State**</span></span>|<span data-ttu-id="685c9-112">**상태가 적용되는 경우**</span><span class="sxs-lookup"><span data-stu-id="685c9-112">**How the state occurs**</span></span>|<span data-ttu-id="685c9-113">**영향**</span><span class="sxs-lookup"><span data-stu-id="685c9-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="685c9-114">**활성**</span><span class="sxs-lookup"><span data-stu-id="685c9-114">**Active**</span></span>  <br/> |<span data-ttu-id="685c9-115">관리자가 추가 기능을 업로드 하 고 사용자 또는 그룹에 할당 했습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="685c9-116">추가 기능에 할당된 사용자 및 그룹은 관련 클라이언트에서 추가 기능을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="685c9-117">**해제됨**</span><span class="sxs-lookup"><span data-stu-id="685c9-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="685c9-118">관리자가 추가 기능을 해제했습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="685c9-119">추가 기능에 할당된 사용자 및 그룹이 더 이상 추가 기능에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="685c9-120">추가 기능 상태가 활성으로 변경되면 사용자 및 그룹이 추가 기능에 다시 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="685c9-121">**삭제됨**</span><span class="sxs-lookup"><span data-stu-id="685c9-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="685c9-122">관리자가 추가 기능을 삭제했습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="685c9-123">추가 기능에 할당된 사용자 및 그룹이 더 이상 추가 기능에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="685c9-124">더 이상 사용 하지 않는 추가 기능을 삭제 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="685c9-125">예를 들어 추가 기능을 해제 하는 작업은 특정 기간 동안에만 사용 되는 경우에 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="685c9-126">추가 기능 삭제</span><span class="sxs-lookup"><span data-stu-id="685c9-126">Delete an add-in</span></span>

<span data-ttu-id="685c9-127">배포 된 추가 기능을 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="685c9-128">관리 센터에서 **설정**  >  **서비스 & 추가** 기능 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="685c9-129">배포 된 추가 기능을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-129">Select the deployed add-in.</span></span>

3. <span data-ttu-id="685c9-130">**추가 기능 삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-130">Click on **Delete Add-In**.</span></span> <span data-ttu-id="685c9-131">오른쪽 아래 모서리에 있는 추가 기능 단추를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-131">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="685c9-132">선택한 항목의 유효성을 검사 하 고 **추가 기능 제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-132">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="685c9-133">추가 기능 액세스 편집</span><span class="sxs-lookup"><span data-stu-id="685c9-133">Edit add-in access</span></span>

<span data-ttu-id="685c9-134">배포 후 관리자는 추가 기능에 대 한 사용자 액세스를 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-134">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="685c9-135">관리 센터에서 **설정**  >  **서비스 & 추가** 기능 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-135">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="685c9-136">배포 된 추가 기능을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-136">Select the deployed add-in.</span></span>

3. <span data-ttu-id="685c9-137">**액세스 권한이 있는 사용자**아래에서 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-137">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="685c9-138">변경 내용을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-138">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="685c9-139">모든 클라이언트로부터 Office 스토어를 꺼서 추가 기능 다운로드 방지 (Outlook 제외)</span><span class="sxs-lookup"><span data-stu-id="685c9-139">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="685c9-140">Outlook 추가 기능 설치는 [다른 프로세스](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)를 통해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-140">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="685c9-141">조직에서는 Office 스토어에서 새 Office 추가 기능을 다운로드 하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-141">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="685c9-142">이를 중앙 집중식 배포와 함께 사용 하 여 조직 내에서 사용자에 게 승인 된 추가 기능만 배포 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-142">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="685c9-143">**추가 기능 취득 기능을 해제 하려면**</span><span class="sxs-lookup"><span data-stu-id="685c9-143">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="685c9-144">관리 센터 미리 보기에서 **설정** \> [서비스 &amp; 추가 기능](https://go.microsoft.com/fwlink/p/?linkid=2053743) 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-144">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>
    
3. <span data-ttu-id="685c9-145">**사용자가 소유한 앱 및 서비스를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-145">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="685c9-146">사용자가 Office 스토어에 액세스 하도록 허용 하는 옵션을 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-146">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="685c9-147">이렇게 하면 모든 사용자가 저장소에서 다음 추가 기능을 취득할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-147">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="685c9-148">Word, Excel 및 PowerPoint 2016의 추가 기능:</span><span class="sxs-lookup"><span data-stu-id="685c9-148">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="685c9-149">Windows</span><span class="sxs-lookup"><span data-stu-id="685c9-149">Windows</span></span>
    
  - <span data-ttu-id="685c9-150">Mac</span><span class="sxs-lookup"><span data-stu-id="685c9-150">Mac</span></span>
    
  - <span data-ttu-id="685c9-151">사무실</span><span class="sxs-lookup"><span data-stu-id="685c9-151">Office</span></span>
    
    
- <span data-ttu-id="685c9-152">**Appsource** 내에서 시작 하는 인수</span><span class="sxs-lookup"><span data-stu-id="685c9-152">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="685c9-153">Microsoft 365 내의 추가 기능</span><span class="sxs-lookup"><span data-stu-id="685c9-153">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="685c9-154">저장소에 액세스 하려고 하는 사용자에 게는 **Office 스토어 추가 기능의 개별 가져오기를 차단 하도록 Microsoft 365이 구성 되어** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-154">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="685c9-155">다음 버전에서는 Office 스토어의 기능 지원을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-155">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="685c9-156">Windows: 16.0.9001-현재 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-156">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="685c9-157">Mac: 16.10.18011401-현재 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-157">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="685c9-158">iOS: 2.9.18010804-현재 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-158">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="685c9-159">웹-현재 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-159">The web - Currently available.</span></span>
    
<span data-ttu-id="685c9-160">이는 관리자가 중앙 집중식 배포를 사용 하 여 Office 스토어에서 추가 기능을 할당 하는 것을 막지는 못합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-160">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="685c9-161">사용자가 Microsoft 계정으로 로그인 하지 못하게 하기 위해 조직 계정만 사용 하도록 로그온을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-161">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="685c9-162">자세한 내용은 [Office 2016의 id, 인증 및 권한 부여](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="685c9-162">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="685c9-163">추가 기능의 최종 사용자 환경에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="685c9-163">More about the end user experience with add-ins</span></span>

<span data-ttu-id="685c9-164">추가 기능을 배포한 후에는 최종 사용자가 Office 응용 프로그램에서 사용을 시작할 수 있습니다 ( [Office 추가 기능 사용 시작](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)참조).</span><span class="sxs-lookup"><span data-stu-id="685c9-164">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="685c9-165">추가 기능에서 지 원하는 모든 플랫폼에 추가 기능이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-165">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="685c9-166">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span><span class="sxs-lookup"><span data-stu-id="685c9-166">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span></span> <span data-ttu-id="685c9-167">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span><span class="sxs-lookup"><span data-stu-id="685c9-167">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![검색 인용이 있는 Office 리본 메뉴](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="685c9-169">배포 된 추가 기능이 추가 기능 명령을 지원 하지 않거나 배포한 모든 추가 기능을 보려는 경우 **내 추가 기능**을 통해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-169">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="685c9-170">Word 2016, Excel 2016 또는 PowerPoint 2016의 경우</span><span class="sxs-lookup"><span data-stu-id="685c9-170">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="685c9-171">\*\* \> 내 추가 기능 삽입을\*\*선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-171">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="685c9-172">Office 추가 기능 창에서 **관리자가 관리함** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-172">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="685c9-173">이전에 배포한 추가 기능을 두 번 클릭합니다(이 예에서는 **인용** ).</span><span class="sxs-lookup"><span data-stu-id="685c9-173">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="685c9-174">![Office 추가 기능 페이지의 관리 관리 탭](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="685c9-174">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="685c9-175">Outlook의 경우</span><span class="sxs-lookup"><span data-stu-id="685c9-175">In Outlook</span></span>

1. <span data-ttu-id="685c9-176">**홈** 리본에서 **추가 기능 가져오기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-176">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="685c9-177">![Outlook의 스토어 단추](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="685c9-177">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="685c9-178">왼쪽 탐색 창에서 **관리-관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-178">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="685c9-179">자세한 정보</span><span class="sxs-lookup"><span data-stu-id="685c9-179">Learn more</span></span>

[<span data-ttu-id="685c9-180">관리 센터에 추가 기능 배포</span><span class="sxs-lookup"><span data-stu-id="685c9-180">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="685c9-181">[Office 추가 기능](https://go.microsoft.com/fwlink/p/?linkid=846362)을 만들고 빌드하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="685c9-181">Learn more about creating and building [Office Add-ins](https://go.microsoft.com/fwlink/p/?linkid=846362).</span></span>
  
<span data-ttu-id="685c9-182">[중앙 집중식 배포 PowerShell cmdlet을 사용 하 여 추가 기능을 관리](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)합니다.</span><span class="sxs-lookup"><span data-stu-id="685c9-182">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="685c9-183">문제 해결: 사용자가 추가 기능을 볼 수 없음</span><span class="sxs-lookup"><span data-stu-id="685c9-183">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="685c9-184">Microsoft 스토어에서 추가 기능 미성년자가 및 가져오기</span><span class="sxs-lookup"><span data-stu-id="685c9-184">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)