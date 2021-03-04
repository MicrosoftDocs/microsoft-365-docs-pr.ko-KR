---
title: 보존 정책 및 보존 레이블 정책에 대한 제한 사항
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 보존 정책 및 보존 레이블 정책에 대한 정책당 최대 정책 및 항목 수 이해
ms.openlocfilehash: 547c6396fa9bfcba6dbd271f09a7ea59f9acf170
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261593"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="424bb-103">보존 정책 및 보존 레이블 정책에 대한 제한 사항</span><span class="sxs-lookup"><span data-stu-id="424bb-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="424bb-104">*[보안 및 규정 준수에 대한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="424bb-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="424bb-105">[보존 정책 및 보존 레이블 정책](retention.md#retention-policies-and-retention-labels)을 사용하여 조직의 데이터를 자동으로 보존하거나 삭제하는 경우 알아야 할 최대 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="424bb-106">테넌트당 최대 정책 수</span><span class="sxs-lookup"><span data-stu-id="424bb-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="424bb-107">단일 테넌트의 경우 최대 10,000개 정책(모든 구성)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="424bb-108">이 최대 수에는 DLP 정책과 같은 다양한 보존 정책과 기타 규정 준수 정책이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-108">This maximum number includes the different policies for retention and other policies for compliance, such as DLP policies.</span></span>

<span data-ttu-id="424bb-109">워크로드당 최대 보존 정책 수:</span><span class="sxs-lookup"><span data-stu-id="424bb-109">Maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="424bb-110">Exchange Online(모든 구성): 1,800</span><span class="sxs-lookup"><span data-stu-id="424bb-110">Exchange Online (any configuration): 1,800</span></span>
- <span data-ttu-id="424bb-111">SharePoint 또는 OneDrive: (모든 사이트가 자동으로 포함됨): 13</span><span class="sxs-lookup"><span data-stu-id="424bb-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="424bb-112">SharePoint 또는 OneDrive(특정 위치 포함 또는 제외): 2,600</span><span class="sxs-lookup"><span data-stu-id="424bb-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="424bb-113">정책당 최대 항목 수</span><span class="sxs-lookup"><span data-stu-id="424bb-113">Maximum number of items per policy</span></span>

<span data-ttu-id="424bb-114">선택적 구성을 사용하여 특정 사용자, 특정 Microsoft 365 그룹 또는 특정 사이트에 대한 보존 설정의 범위를 지정하는 경우 다음의 정책별 몇 가지 제한 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-114">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="424bb-115">보존 정책당 최대 항목 수:</span><span class="sxs-lookup"><span data-stu-id="424bb-115">Maximum numbers of items per policy for retention:</span></span>

  - <span data-ttu-id="424bb-116">1,000개의 사서함(사용자 사서함 또는 그룹 사서함)</span><span class="sxs-lookup"><span data-stu-id="424bb-116">1,000 mailboxes (user mailboxes or group mailboxes)</span></span>
  - <span data-ttu-id="424bb-117">1,000개의 Microsoft 365 그룹</span><span class="sxs-lookup"><span data-stu-id="424bb-117">1,000 Microsoft 365 groups</span></span>
  - <span data-ttu-id="424bb-118">Teams 비공개 채팅에 참여하는 1,000명의 사용자</span><span class="sxs-lookup"><span data-stu-id="424bb-118">1,000 users for Teams private chats</span></span>
  - <span data-ttu-id="424bb-119">100개의 사이트(OneDrive 또는 SharePoint)</span><span class="sxs-lookup"><span data-stu-id="424bb-119">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="424bb-120">이러한 제한 사항은 정책당로 적용되므로 특정 포함 또는 제외를 사용하여 이러한 수를 검토해야 하는 경우 동일한 보존 설정을 가진 추가 정책을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-120">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="424bb-121">이러한 이유로 여러 보존 정책을 사용하는 일부 [예제 시나리오 및 솔루션](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers)은 다음 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="424bb-121">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="424bb-122">그러나 여러 정책으로 인해 관리 오버헤드가 증가하므로 포함 및 제외가 정말 필요한지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-122">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="424bb-123">전체 위치에 적용되는 기본 구성에는 제한이 없으며, 이 구성 선택은 여러 정책을 만들고 유지하는 것보다 더 나은 솔루션이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-123">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="424bb-124">이 시나리오에 대해 여러 정책을 생성하고 유지 관리해야하는 경우 보다 효율적인 구성을 위해 [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels)을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-124">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="424bb-125">최대 수 초과를 방지하는 여러 정책을 사용하는 예</span><span class="sxs-lookup"><span data-stu-id="424bb-125">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="424bb-126">다음 예제는 보존 정책의 위치만 지정할 수 없는 경우에 대한 몇 가지 설계 솔루션을 제공하며, 이전 섹션에서 설명한 최대 항목 수를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-126">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="424bb-127">Exchange 예제:</span><span class="sxs-lookup"><span data-stu-id="424bb-127">Exchange example:</span></span>

- <span data-ttu-id="424bb-128">**요구 사항**: 사용자 사서함이 40,000개 이상인 조직에서 대부분의 사용자는 7년 동안 전자 메일을 보존해야 하지만 식별된 사용자(425명)의 하위 집합은 5년 동안만 전자 메일을 보존해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-128">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="424bb-129">**솔루션**: 보존 기간이 7년인 Exchange 전자 메일에 대해 하나의 보존 정책을 생성하고 사용자 하위 집합을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-129">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="424bb-130">그런 다음 보존 기간이 5년인 Exchange 전자 메일에 대한 두 번째 보존 정책을 생성하고 사용자 하위 집합을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-130">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="424bb-131">두 경우 모두 포함 및 제외된 수는 단일 정책에 대해 지정된 최대 사서함 수보다 적으며, 두 번째 정책보다 [보존 기간이 길기 때문에](retention.md#the-principles-of-retention-or-what-takes-precedence) 사용자 하위 집합은 첫 번째 정책에서 명시적으로 제외되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-131">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="424bb-132">사용자 하위 집합에서 더 긴 보존 정책이 필요한 경우 첫 번째 정책에서 제외할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-132">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="424bb-133">이 솔루션을 사용하면 새로 참가한 사람이 있으면 해당 우편함이 7년 동안 자동으로 첫 번째 정책에 포함되며 지원되는 최대 수에 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-133">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="424bb-134">그러나 5년 보존 기간이 필요한 새 사용자는 포함 및 제외 수에 추가되며 이 제한은 1,000에 도달하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-134">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="424bb-135">SharePoint 예제</span><span class="sxs-lookup"><span data-stu-id="424bb-135">SharePoint example:</span></span>

- <span data-ttu-id="424bb-136">**요구 사항**: 한 조직에서 SharePoint 사이트는 수천 개이지만 2,000개 사이트만 10년 보존 기간이 필요하며 8,000개 사이트에서는 4년 보존 기간이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-136">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="424bb-137">**솔루션**: 100개의 특정 사이트를 포함하는 10년의 보존 기간으로 SharePoint용 20개 보존 정책을 생성하고, 100개의 특정 사이트를 포함하는 4년의 보존 기간으로 SharePoint용 80개 보존 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-137">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="424bb-138">모든 SharePoint 사이트를 보유할 필요는 없으므로 특정 사이트를 지정하는 보존 정책을 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-138">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="424bb-139">보존 정책은 100개 이상의 지정된 사이트를 지원하지 않으므로 두 보존 기간에 대해 여러 정책을 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-139">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="424bb-140">이러한 보존 정책에는 최대 개수의 사이트가 포함되므로 보존해야 하는 다음 새 사이트에는 보존 기간에 관계없이 새 보존 정책이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="424bb-140">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>
