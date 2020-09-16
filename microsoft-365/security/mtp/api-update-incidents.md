---
title: 문제 API 업데이트
description: Microsoft Threat Protection API를 사용 하 여 인시던트를 업데이트 하는 방법에 대해 알아봅니다.
keywords: 업데이트, api, 인시던트
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: e790f4f415575323cfdd5fc15db41baa8b59c7f6
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650436"
---
# <a name="update-incidents-api"></a><span data-ttu-id="8c19e-104">문제 API 업데이트</span><span class="sxs-lookup"><span data-stu-id="8c19e-104">Update incidents API</span></span>

<span data-ttu-id="8c19e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="8c19e-105">**Applies to:**</span></span>
- <span data-ttu-id="8c19e-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="8c19e-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="8c19e-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8c19e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="8c19e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="8c19e-109">API 설명</span><span class="sxs-lookup"><span data-stu-id="8c19e-109">API description</span></span>
<span data-ttu-id="8c19e-110">기존 인시던트의 속성을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-110">Updates properties of existing incident.</span></span>
<br><span data-ttu-id="8c19e-111">업데이트할 수 있는 속성은 ```status``` ,, ```determination``` ```classification``` ```assignedTo``` 및 ```tags``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo``` and ```tags```.</span></span>


## <a name="limitations"></a><span data-ttu-id="8c19e-112">제한 사항</span><span class="sxs-lookup"><span data-stu-id="8c19e-112">Limitations</span></span>
1. <span data-ttu-id="8c19e-113">이 API의 속도 제한은 분당 50 통화이 고 시간당 1500 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="8c19e-114">```determination```분류가 TruePositive로 설정 된 경우에만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-114">You can set the ```determination``` only if the classification is set to TruePositive.</span></span>


## <a name="permissions"></a><span data-ttu-id="8c19e-115">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8c19e-115">Permissions</span></span>
<span data-ttu-id="8c19e-116">이 API를 호출 하려면 다음 사용 권한 중 하나가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8c19e-117">사용 권한을 선택 하는 방법을 비롯 하 여 자세한 내용은 [Microsoft Threat Protection Api 액세스](api-access.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8c19e-117">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md).</span></span>

<span data-ttu-id="8c19e-118">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="8c19e-118">Permission type</span></span> |   <span data-ttu-id="8c19e-119">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8c19e-119">Permission</span></span>  |   <span data-ttu-id="8c19e-120">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="8c19e-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8c19e-121">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="8c19e-121">Application</span></span> |   <span data-ttu-id="8c19e-122">인시던트의 모든</span><span class="sxs-lookup"><span data-stu-id="8c19e-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="8c19e-123">' 모든 인시던트 읽기 및 쓰기 '</span><span class="sxs-lookup"><span data-stu-id="8c19e-123">'Read and write all incidents'</span></span>
<span data-ttu-id="8c19e-124">위임 됨 (회사 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="8c19e-124">Delegated (work or school account)</span></span> | <span data-ttu-id="8c19e-125">인시던트-ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8c19e-125">Incident.ReadWrite</span></span> | <span data-ttu-id="8c19e-126">' 인시던트 읽기 및 쓰기 '</span><span class="sxs-lookup"><span data-stu-id="8c19e-126">'Read and write incidents'</span></span>

>[!NOTE]
> <span data-ttu-id="8c19e-127">사용자 자격 증명을 사용 하 여 토큰을 가져올 때:</span><span class="sxs-lookup"><span data-stu-id="8c19e-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="8c19e-128">사용자에 게 포털의 인시던트를 업데이트할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-128">The user needs to have permission to update the incident in the portal.</span></span>


## <a name="http-request"></a><span data-ttu-id="8c19e-129">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="8c19e-129">HTTP request</span></span>

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="8c19e-130">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="8c19e-130">Request headers</span></span>

<span data-ttu-id="8c19e-131">이름</span><span class="sxs-lookup"><span data-stu-id="8c19e-131">Name</span></span> | <span data-ttu-id="8c19e-132">유형</span><span class="sxs-lookup"><span data-stu-id="8c19e-132">Type</span></span> | <span data-ttu-id="8c19e-133">설명</span><span class="sxs-lookup"><span data-stu-id="8c19e-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="8c19e-134">권한 부여</span><span class="sxs-lookup"><span data-stu-id="8c19e-134">Authorization</span></span> | <span data-ttu-id="8c19e-135">문자열</span><span class="sxs-lookup"><span data-stu-id="8c19e-135">String</span></span> | <span data-ttu-id="8c19e-136">전달자 {토큰}.</span><span class="sxs-lookup"><span data-stu-id="8c19e-136">Bearer {token}.</span></span> <span data-ttu-id="8c19e-137">**필수**입니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-137">**Required**.</span></span>
<span data-ttu-id="8c19e-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="8c19e-138">Content-Type</span></span> | <span data-ttu-id="8c19e-139">문자열</span><span class="sxs-lookup"><span data-stu-id="8c19e-139">String</span></span> | <span data-ttu-id="8c19e-140">application/json</span><span class="sxs-lookup"><span data-stu-id="8c19e-140">application/json.</span></span> <span data-ttu-id="8c19e-141">**필수**입니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="8c19e-142">요청 본문</span><span class="sxs-lookup"><span data-stu-id="8c19e-142">Request body</span></span>
<span data-ttu-id="8c19e-143">요청 본문에서 업데이트 해야 하는 관련 필드의 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-143">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="8c19e-144">요청 본문에 포함 되지 않은 기존 속성은 이전 값을 유지 하거나 다른 속성 값의 변경 내용에 따라 다시 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-144">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="8c19e-145">최적의 성능을 위해 변경 되지 않은 기존 값은 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-145">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="8c19e-146">속성</span><span class="sxs-lookup"><span data-stu-id="8c19e-146">Property</span></span> | <span data-ttu-id="8c19e-147">유형</span><span class="sxs-lookup"><span data-stu-id="8c19e-147">Type</span></span> | <span data-ttu-id="8c19e-148">설명</span><span class="sxs-lookup"><span data-stu-id="8c19e-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="8c19e-149">상태별</span><span class="sxs-lookup"><span data-stu-id="8c19e-149">status</span></span> | <span data-ttu-id="8c19e-150">열거할</span><span class="sxs-lookup"><span data-stu-id="8c19e-150">Enum</span></span> | <span data-ttu-id="8c19e-151">알림의 현재 상태를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-151">Specifies the current status of the alert.</span></span> <span data-ttu-id="8c19e-152">가능한 값은 ```Active``` ```Resolved``` 및 ```Redirected``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-152">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="8c19e-153">assignedTo</span><span class="sxs-lookup"><span data-stu-id="8c19e-153">assignedTo</span></span> | <span data-ttu-id="8c19e-154">문자열</span><span class="sxs-lookup"><span data-stu-id="8c19e-154">string</span></span> | <span data-ttu-id="8c19e-155">인시던트의 소유자입니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-155">Owner of the incident.</span></span>
<span data-ttu-id="8c19e-156">유형을</span><span class="sxs-lookup"><span data-stu-id="8c19e-156">classification</span></span> | <span data-ttu-id="8c19e-157">열거할</span><span class="sxs-lookup"><span data-stu-id="8c19e-157">Enum</span></span> | <span data-ttu-id="8c19e-158">경고의 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-158">Specification of the alert.</span></span> <span data-ttu-id="8c19e-159">가능한 값은 ```Unknown``` , ```FalsePositive``` 및 ```TruePositive``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-159">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="8c19e-160">가져옴을</span><span class="sxs-lookup"><span data-stu-id="8c19e-160">determination</span></span> | <span data-ttu-id="8c19e-161">열거할</span><span class="sxs-lookup"><span data-stu-id="8c19e-161">Enum</span></span> | <span data-ttu-id="8c19e-162">경고에 대 한 결정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-162">Specifies the determination of the alert.</span></span> <span data-ttu-id="8c19e-163">가능한 값은 ```NotAvailable``` ,, ```Apt``` ```Malware``` , ```SecurityPersonnel``` , ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-163">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="8c19e-164">사이</span><span class="sxs-lookup"><span data-stu-id="8c19e-164">tags</span></span> | <span data-ttu-id="8c19e-165">문자열 목록</span><span class="sxs-lookup"><span data-stu-id="8c19e-165">string List</span></span> | <span data-ttu-id="8c19e-166">인시던트 태그의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-166">List of Incident tags.</span></span>



## <a name="response"></a><span data-ttu-id="8c19e-167">응답</span><span class="sxs-lookup"><span data-stu-id="8c19e-167">Response</span></span>
<span data-ttu-id="8c19e-168">성공한 경우이 메서드는 200 OK를 반환 하 고 업데이트 된 속성을 사용 하 여 응답 본문에 인시던트 엔티티를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-168">If successful, this method returns 200 OK, and the incident entity in the response body with the updated properties.</span></span> <span data-ttu-id="8c19e-169">지정 된 id를 가진 인시던트를 찾을 수 없는 경우-404를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-169">If incident with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="8c19e-170">예제</span><span class="sxs-lookup"><span data-stu-id="8c19e-170">Example</span></span>

<span data-ttu-id="8c19e-171">**요청이**</span><span class="sxs-lookup"><span data-stu-id="8c19e-171">**Request**</span></span>

<span data-ttu-id="8c19e-172">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8c19e-172">Here is an example of the request.</span></span>

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a><span data-ttu-id="8c19e-173">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8c19e-173">Related topic</span></span>
- [<span data-ttu-id="8c19e-174">인시던트 Api</span><span class="sxs-lookup"><span data-stu-id="8c19e-174">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="8c19e-175">인시던트 목록</span><span class="sxs-lookup"><span data-stu-id="8c19e-175">List incidents</span></span>](api-list-incidents.md)