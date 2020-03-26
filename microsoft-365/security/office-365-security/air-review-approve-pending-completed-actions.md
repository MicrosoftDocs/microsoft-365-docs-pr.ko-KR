---
title: Office 365 자동 조사 및 응답에서 보류 중인 재구성 작업 검토 및 승인
keywords: AIR, autoIR, ATP, 자동화, 조사, 대응, 재구성, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection 계획 2의 자동화 된 조사 및 응답 기능의 수정 작업에 대해 알아봅니다.
ms.openlocfilehash: d2b617e29fc36d1f39ab6c9ef6f708d5f608b206
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826460"
---
# <a name="view-pending-or-completed-remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="03f0b-104">Office 365에서 자동화 된 조사에 따라 보류 중 또는 완료 된 재구성 작업 보기</span><span class="sxs-lookup"><span data-stu-id="03f0b-104">View pending or completed remediation actions following an automated investigation in Office 365</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="03f0b-105">보류 중인 작업 승인 (또는 거부)</span><span class="sxs-lookup"><span data-stu-id="03f0b-105">Approve (or reject) pending actions</span></span>

![AIR 조사 작업 페이지](../../media/air-investigationactionspage.png)

<span data-ttu-id="03f0b-107">[조사 세부 정보](air-view-investigation-results.md)를 볼 때 보류 중인 모든 수정 작업을 승인 하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03f0b-107">While viewing the [details of an investigation](air-view-investigation-results.md), you can approve or reject any pending remediation actions.</span></span> <span data-ttu-id="03f0b-108">자동 조사가 완료 되도록 가능한 한 빨리이 작업을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="03f0b-108">We recommend doing this as soon as possible so that your automated investigations complete.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03f0b-109">재구성 작업을 승인 하거나 거부 하려면 적절 한 사용 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="03f0b-109">Appropriate permissions are required to approve or reject remediation actions.</span></span> <span data-ttu-id="03f0b-110">[AIR 기능을 사용 하려면 필수 권한을](office-365-air.md#required-permissions-to-use-air-capabilities)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03f0b-110">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

1. <span data-ttu-id="03f0b-111">[https://protection.office.com](https://protection.office.com)으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="03f0b-111">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="03f0b-112">그러면 보안 & 준수 센터로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="03f0b-112">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="03f0b-113">**위협 관리** > **조사**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="03f0b-113">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="03f0b-114">조사 목록에서 **ID** 열의 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="03f0b-114">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="03f0b-115">**작업** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="03f0b-115">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="03f0b-116">목록에서 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="03f0b-116">Select an item in the list.</span></span> <span data-ttu-id="03f0b-117">승인 및 거부 단추가 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03f0b-117">(This activates the Approve and Reject buttons.)</span></span>

6. <span data-ttu-id="03f0b-118">선택한 항목에 대해 사용 가능한 정보를 검토 하 고 작업을 승인 하거나 거부 합니다.</span><span class="sxs-lookup"><span data-stu-id="03f0b-118">Review available information for the item(s) you selected, and then either approve or reject the action(s).</span></span> 
 - <span data-ttu-id="03f0b-119">**승인** 을 사용 하 여 업데이트를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03f0b-119">**Approve** allows remediation to begin.</span></span>
 - <span data-ttu-id="03f0b-120">**거부** 는 추가 작업을 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03f0b-120">**Reject** takes no further action</span></span>

## <a name="next-steps"></a><span data-ttu-id="03f0b-121">다음 단계</span><span class="sxs-lookup"><span data-stu-id="03f0b-121">Next steps</span></span>

- [<span data-ttu-id="03f0b-122">Office 365의 자동화 된 조사에 대 한 세부 정보 및 결과</span><span class="sxs-lookup"><span data-stu-id="03f0b-122">Details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

- [<span data-ttu-id="03f0b-123">위협 탐색기 사용</span><span class="sxs-lookup"><span data-stu-id="03f0b-123">Use Threat Explorer</span></span>](threat-explorer.md)