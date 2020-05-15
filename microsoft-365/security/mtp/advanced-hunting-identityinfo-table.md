---
title: 고급 구하기 스키마의 IdentityInfo 테이블
description: 고급 구하기 스키마의 IdentityInfo 테이블에서 사용자 계정 정보에 대해 자세히 알아보기
keywords: 고급 구하기, 위협 검색, 사이버 위협 검색, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, description, AccountInfo, IdentityInfo, account
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 12f8d0995d00daffe8a1ca1c2c8d9dfe25a11581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209778"
---
# <a name="identityinfo"></a><span data-ttu-id="dfb7f-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="dfb7f-104">IdentityInfo</span></span>

<span data-ttu-id="dfb7f-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="dfb7f-105">**Applies to:**</span></span>
- <span data-ttu-id="dfb7f-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="dfb7f-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="dfb7f-107">`IdentityInfo` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Azure Active Directory를 비롯 하 여 다양 한 서비스에서 가져온 사용자 계정에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfb7f-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="dfb7f-108">이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb7f-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="dfb7f-109">이 테이블의 이름은에서 변경 되었습니다 `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="dfb7f-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="dfb7f-110">이름을 변경 하는 동안에는 포털에 저장 된 모든 쿼리가 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfb7f-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="dfb7f-111">다른 위치에서 저장 한 쿼리를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb7f-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="dfb7f-112">고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dfb7f-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="dfb7f-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="dfb7f-113">Column name</span></span> | <span data-ttu-id="dfb7f-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="dfb7f-114">Data type</span></span> | <span data-ttu-id="dfb7f-115">설명</span><span class="sxs-lookup"><span data-stu-id="dfb7f-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="dfb7f-116">문자열</span><span class="sxs-lookup"><span data-stu-id="dfb7f-116">string</span></span> | <span data-ttu-id="dfb7f-117">Azure AD의 계정에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb7f-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="dfb7f-118">문자열</span><span class="sxs-lookup"><span data-stu-id="dfb7f-118">string</span></span> | <span data-ttu-id="dfb7f-119">계정의 UPN (사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="dfb7f-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="dfb7f-120">문자열</span><span class="sxs-lookup"><span data-stu-id="dfb7f-120">string</span></span> | <span data-ttu-id="dfb7f-121">계정의 온-프레미스 SID (보안 식별자)</span><span class="sxs-lookup"><span data-stu-id="dfb7f-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="dfb7f-122">문자열</span><span class="sxs-lookup"><span data-stu-id="dfb7f-122">string</span></span> | <span data-ttu-id="dfb7f-123">계정의 클라우드 보안 식별자</span><span class="sxs-lookup"><span data-stu-id="dfb7f-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="dfb7f-124">문자열</span><span class="sxs-lookup"><span data-stu-id="dfb7f-124">string</span></span> | <span data-ttu-id="dfb7f-125">계정 사용자의 이름이 나 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfb7f-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="dfb7f-126">문자열</span><span class="sxs-lookup"><span data-stu-id="dfb7f-126">string</span></span> | <span data-ttu-id="dfb7f-127">계정 사용자의 성, 패밀리 이름 또는 성</span><span class="sxs-lookup"><span data-stu-id="dfb7f-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="dfb7f-128">문자열</span><span class="sxs-lookup"><span data-stu-id="dfb7f-128">string</span></span> | <span data-ttu-id="dfb7f-129">주소록에 표시 되는 계정 사용자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb7f-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="dfb7f-130">일반적으로 주어진 이름이 나 이름, 중간 시작, 성 또는 성의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb7f-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="dfb7f-131">문자열</span><span class="sxs-lookup"><span data-stu-id="dfb7f-131">string</span></span> | <span data-ttu-id="dfb7f-132">계정 사용자가 속한 부서의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb7f-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="dfb7f-133">문자열</span><span class="sxs-lookup"><span data-stu-id="dfb7f-133">string</span></span> | <span data-ttu-id="dfb7f-134">계정 사용자의 직함</span><span class="sxs-lookup"><span data-stu-id="dfb7f-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="dfb7f-135">문자열</span><span class="sxs-lookup"><span data-stu-id="dfb7f-135">string</span></span> | <span data-ttu-id="dfb7f-136">계정의 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb7f-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="dfb7f-137">문자열</span><span class="sxs-lookup"><span data-stu-id="dfb7f-137">string</span></span> | <span data-ttu-id="dfb7f-138">계정의 도메인</span><span class="sxs-lookup"><span data-stu-id="dfb7f-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="dfb7f-139">문자열</span><span class="sxs-lookup"><span data-stu-id="dfb7f-139">string</span></span> | <span data-ttu-id="dfb7f-140">계정의 SMTP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="dfb7f-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="dfb7f-141">문자열</span><span class="sxs-lookup"><span data-stu-id="dfb7f-141">string</span></span> | <span data-ttu-id="dfb7f-142">계정의 SIP (over IP) session (세션 시작 프로토콜) 주소</span><span class="sxs-lookup"><span data-stu-id="dfb7f-142">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="dfb7f-143">문자열</span><span class="sxs-lookup"><span data-stu-id="dfb7f-143">string</span></span> | <span data-ttu-id="dfb7f-144">계정 사용자가 있는 구/군/시</span><span class="sxs-lookup"><span data-stu-id="dfb7f-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="dfb7f-145">문자열</span><span class="sxs-lookup"><span data-stu-id="dfb7f-145">string</span></span> | <span data-ttu-id="dfb7f-146">계정 사용자가 있는 국가/지역</span><span class="sxs-lookup"><span data-stu-id="dfb7f-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="dfb7f-147">부울</span><span class="sxs-lookup"><span data-stu-id="dfb7f-147">boolean</span></span> | <span data-ttu-id="dfb7f-148">계정을 사용할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dfb7f-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="dfb7f-149">관련 항목</span><span class="sxs-lookup"><span data-stu-id="dfb7f-149">Related topics</span></span>
- [<span data-ttu-id="dfb7f-150">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="dfb7f-150">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="dfb7f-151">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="dfb7f-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="dfb7f-152">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="dfb7f-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="dfb7f-153">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="dfb7f-153">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="dfb7f-154">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="dfb7f-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="dfb7f-155">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="dfb7f-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)