---
title: 1단계. 엔터프라이즈용 Microsoft 365 테넌트
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: 다중 위치 및 이동 위치에 대한 옵션을 사용하여 단일 또는 여러 Microsoft 365 테넌트를 배포하고 관리합니다.
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908718"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="94839-104">1단계.</span><span class="sxs-lookup"><span data-stu-id="94839-104">Step 1.</span></span> <span data-ttu-id="94839-105">엔터프라이즈용 Microsoft 365 테넌트</span><span class="sxs-lookup"><span data-stu-id="94839-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="94839-106">첫 번째 테넌트 결정 중 하나는 가지는 수입니다.</span><span class="sxs-lookup"><span data-stu-id="94839-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="94839-107">각 Microsoft 365 테넌트는 다른 모든 Microsoft 365 테넌트와는 고유하며 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="94839-108">또한 해당 Azure AD 테넌트는 다른 모든 Microsoft 365 테넌트와는 고유하며 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="94839-109">단일 테넌트</span><span class="sxs-lookup"><span data-stu-id="94839-109">Single tenant</span></span>
<span data-ttu-id="94839-110">테넌트가 하나만 있는 경우 조직에서 Microsoft 365를 사용하는 다양한 측면이 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="94839-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="94839-111">단일 테넌트는 단일 계정, 그룹 및 정책 집합이 있는 단일 Azure AD 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="94839-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="94839-112">조직 전체의 사용 권한 및 리소스 공유는 이 중앙 ID 공급자를 통해 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="94839-113">단일 테넌트는 사용자에게 가장 기능이 풍부하고 간소화된 공동 작업 및 생산성 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="94839-114">다음은 Microsoft 365 테넌트의 기본 위치 및 Azure AD 테넌트에 대한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="94839-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![Azure AD 테넌트가 있는 단일 Microsoft 365 테넌트](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="94839-116">여러 테넌트</span><span class="sxs-lookup"><span data-stu-id="94839-116">Multiple tenants</span></span>

<span data-ttu-id="94839-117">조직에 여러 테넌트가 있을 수 있는 이유는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="94839-118">관리 에지</span><span class="sxs-lookup"><span data-stu-id="94839-118">Administrative isolation</span></span>
- <span data-ttu-id="94839-119">분산된 IT</span><span class="sxs-lookup"><span data-stu-id="94839-119">Decentralized IT</span></span>
- <span data-ttu-id="94839-120">기록 결정</span><span class="sxs-lookup"><span data-stu-id="94839-120">Historical decisions</span></span>
- <span data-ttu-id="94839-121">합병, 인수 또는 매입</span><span class="sxs-lookup"><span data-stu-id="94839-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="94839-122">대기업 조직에 대한 브랜딩 명확한 분리</span><span class="sxs-lookup"><span data-stu-id="94839-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="94839-123">사전 프로덕션, 테스트 또는 샌드박스 테넌트</span><span class="sxs-lookup"><span data-stu-id="94839-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="94839-124">다음은 동일한 기본 데이터 센터 지리적으로 두 테넌트(테넌트 A 및 테넌트 B)가 있는 조직의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="94839-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="94839-125">각 테넌트는 별도의 Azure AD 테넌트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="94839-125">Each tenant as a separate Azure AD tenant.</span></span>

![자체 Azure AD 테넌트가 있는 여러 Microsoft 365 테넌트](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="94839-127">테넌트가 여러 개인 경우 테넌트 관리 및 사용자에게 서비스를 제공하는 경우 제한 사항 및 추가 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="94839-128">테넌트 간 공동 작업</span><span class="sxs-lookup"><span data-stu-id="94839-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="94839-129">사용자가 안전한 방식으로 다른 Microsoft 365 테넌트에서 보다 효과적으로 공동 작업을 하게 하려는 경우 테넌트 간 공동 작업 옵션으로는 파일 및 대화에 대한 중앙 위치 사용, 일정 공유, 통신을 위한 IM 사용, 오디오/비디오 통화 사용, 리소스 및 응용 프로그램에 대한 액세스 보안이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="94839-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="94839-130">자세한 내용은 [Microsoft 365](../enterprise/microsoft-365-inter-tenant-collaboration.md)테넌트 간 공동 작업을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94839-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="94839-131">테넌트 간 사서함 마이그레이션(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="94839-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="94839-132">테넌트 간에 Exchange Online 사서함을 이동하기 전에(미리 보기) 현재 테넌트(원본 테넌트)에서 온-프레미스로 사용자 사서함을 완전히 오프보드한 다음 새 테넌트(대상 테넌트)에 온보드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="94839-133">새로운 테넌트 간 사서함 마이그레이션 기능을 사용하면 원본 테넌트와 대상 테넌트의 테넌트 관리자가 모두 해당 테넌트 간에 사서함을 이동할 수 있으며, 해당 테넌트 간의 인프라 종속성은 최소 수준으로 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="94839-134">이렇게 하여 사서함을 오프보드하고 온보드할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="94839-135">다음은 테넌트 간 사서함 마이그레이션 전에 두 가지 예로 테넌트와 해당 사서함을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![여러 Microsoft 365 테넌트 및 해당 사서함](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="94839-137">이 그림에서는 두 개의 개별 테넌트에 자체 도메인과 Exchange 사서함 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="94839-138">다음은 테넌트 간 사서함 마이그레이션 후의 대상 테넌트(테넌트 A)입니다.</span><span class="sxs-lookup"><span data-stu-id="94839-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![테넌트 간 사서함 마이그레이션 후의 대상 테넌트](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="94839-140">이 그림에서는 단일 테넌트에 도메인과 Exchange 사서함 집합이 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="94839-141">자세한 내용은 테넌트 간 사서함 [마이그레이션을 참조하십시오.](../enterprise/cross-tenant-mailbox-migration.md)</span><span class="sxs-lookup"><span data-stu-id="94839-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="94839-142">테넌트 간 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="94839-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="94839-143">합병, 인수, 매입 및 기존 Microsoft 365 테넌트의 마이그레이션을 새 테넌트로 마이그레이션할 수 있는 기타 시나리오에 대한 아키텍처 방식이 여러 가지 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="94839-144">자세한 지침은 [Microsoft 365 테넌트 대 테넌트](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)마이그레이션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94839-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="94839-145">테넌트에 대한 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="94839-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="94839-146">Microsoft 365 Multi-Geo를 사용하면 데이터 보관 요구 사항을 충족하기 위해 선택한 다른 데이터 센터 지리적 위치에 미사용 데이터를 프로비전하고 저장할 수 있으며, 동시에 최신 생산성 환경의 글로벌 롤아웃을 작업자에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="94839-147">Multi-Geo 환경에서 Microsoft 365 테넌트는 Microsoft 365 구독이 원래 만들어진 기본 위치 또는 중앙 위치와 하나 이상의 위성 위치로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="94839-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="94839-148">다중 위치 테넌트에서 지리적 위치, 그룹 및 사용자 정보에 대한 정보는 전역 Azure AD 테넌트에서 마스터됩니다.</span><span class="sxs-lookup"><span data-stu-id="94839-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="94839-149">테넌트 정보는 중앙에서 마스터된 후 각 지리적 위치로 동기화하기 때문에 회사의 모든 사용자와 관련된 공동 작업 환경이 여러 위치에서 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="94839-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="94839-150">다음은 유럽의 기본 위치와 북미의 위성 위치를 가지는 조직의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="94839-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="94839-151">두 위치는 단일 Microsoft 365 테넌트에 대해 동일한 전역 Azure AD 테넌트를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![Multi-Geo Microsoft 365 테넌트의 예](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="94839-153">자세한 내용은 [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94839-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="94839-154">핵심 데이터를 새 데이터 센터 지역으로 이동</span><span class="sxs-lookup"><span data-stu-id="94839-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="94839-155">Microsoft는 계속해서 Microsoft 365 서비스에 대한 새 데이터 센터 지역을 열고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="94839-156">이러한 새로운 데이터 센터 지역은 지속적인 고객 수요 및 사용 증가를 지원하기 위해 용량 및 계산 리소스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="94839-157">또한 새로운 데이터 센터 지역은 핵심 고객 데이터에 대한 지역 내 데이터 레지스터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="94839-158">새 데이터 센터 지역을 열면 사용자 및 기존 데이터 센터 위치에 저장된 핵심 데이터에 영향을 미치는 것은 아니며, Microsoft는 휴지 상태의 조직의 핵심 고객 데이터를 새 데이터 센터 지역으로 조기 마이그레이션할 것을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="94839-159">다음은 Microsoft 365 테넌트가 유럽 연합(EU) 데이터 센터 지역에서 영국(영국)에 있는 테넌트로 이동된 예입니다.</span><span class="sxs-lookup"><span data-stu-id="94839-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![데이터 센터 지역 간에 Microsoft 365 테넌트 이동의 예](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="94839-161">자세한 내용은 핵심 데이터를 새 Microsoft 365 데이터 센터 지역으로 [이동을 참조하세요.](../enterprise/moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="94839-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="94839-162">테넌트의 제품 및 라이선스</span><span class="sxs-lookup"><span data-stu-id="94839-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="94839-163">Microsoft 365 E3와 같은 첫 번째 제품을 구매하면 Microsoft 365 테넌트가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="94839-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="94839-164">제품과 함께 월별 또는 연간 요금을 부과하는 라이선스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="94839-165">그런 다음 관리자는 직접 또는 그룹 구성원 자격을 통해 제품 중 하나에서 사용 가능한 라이선스를 사용자 계정에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="94839-166">조직의 비즈니스 요구에 따라 각각 자체 라이선스 풀이 있는 제품 집합이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="94839-167">제품 집합 및 각 제품의 라이선스 수를 결정하려면 다음을 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="94839-168">고급 기능이 필요한 사용자 계정에 대한 라이선스가 충분한지 확인</span><span class="sxs-lookup"><span data-stu-id="94839-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="94839-169">조직의 직원 관리 변경에 따라 라이선스가 많지 않은 경우나 너무 많은 허가되지 않은 라이선스가 있는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="94839-170">1단계 결과</span><span class="sxs-lookup"><span data-stu-id="94839-170">Results of Step 1</span></span>

<span data-ttu-id="94839-171">엔터프라이즈용 Microsoft 365 테넌트의 경우 다음을 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="94839-172">필요한 테넌트 수</span><span class="sxs-lookup"><span data-stu-id="94839-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="94839-173">각 테넌트에 대해 구매해야 하는 제품 및 라이선스</span><span class="sxs-lookup"><span data-stu-id="94839-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="94839-174">테넌트가 데이터 레지던스 요구 사항을 준수하기 위해 Multi-Geo가 필요한지 여부</span><span class="sxs-lookup"><span data-stu-id="94839-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="94839-175">테넌트 간 공동 작업을 설정해야 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="94839-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="94839-176">테넌트 하나를 다른 테넌트로 마이그레이션해야 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="94839-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="94839-177">핵심 데이터를 한 데이터 센터 지역에서 새 데이터 센터 지역으로 이동해야 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="94839-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="94839-178">다음은 새 테넌트의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="94839-178">Here is an example of a new tenant.</span></span>

![새 테넌트의 예](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="94839-180">이 그림에서 테넌트에는 다음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="94839-181">Microsoft 365 데이터 센터 지리적 위치에 해당하는 기본 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="94839-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="94839-182">제품 및 라이선스 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="94839-182">A set of products and licenses.</span></span>
- <span data-ttu-id="94839-183">클라우드 생산성 앱 집합(일부는 제품과 관련이 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="94839-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="94839-184">전역 관리자 계정과 초기 DNS 도메인 이름을 포함하는 Azure AD 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="94839-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="94839-185">이 솔루션의 추가 단계를 진행할 때 이 그림을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="94839-186">테넌트에 대한 지속적인 유지 관리</span><span class="sxs-lookup"><span data-stu-id="94839-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="94839-187">지속적인 기준에 따라 다음을 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94839-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="94839-188">새 테넌트 추가</span><span class="sxs-lookup"><span data-stu-id="94839-188">Add a new tenant.</span></span>
- <span data-ttu-id="94839-189">초기 라이선스 수가 있는 테넌트에 새 제품을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="94839-190">테넌트의 제품에 대한 라이선스 집합을 변경하여 직원 요구 사항을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="94839-191">테넌트에서 새 데이터 센터 지리적 위치로 핵심 데이터를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="94839-192">데이터 저장 요구 사항에 대해 Multi-Geo를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="94839-193">테넌트 간 공동 작업을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="94839-194">다음 단계</span><span class="sxs-lookup"><span data-stu-id="94839-194">Next step</span></span>

<span data-ttu-id="94839-195">[![2단계. 액세스를 위해 네트워크에 대한 테넌트 최적화](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="94839-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="94839-196">네트워킹을 [계속하여](tenant-management-networking.md) 작업자에서 Microsoft 365 클라우드 서비스로의 최적의 네트워킹을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="94839-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>