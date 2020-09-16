---
title: 고급 구하기 Api
description: Microsoft Threat Protection API를 사용 하 여 고급 구하기 쿼리를 실행 하는 방법 알아보기
keywords: 고급 구하기, Api, api, MTP
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
ms.openlocfilehash: 9e92a0328d2e7fb9cfe7461241dd866081926876
ms.sourcegitcommit: 62a8c226422eac9c085cc886b4836b037f95ef6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47825377"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="66485-104">고급 구하기 Api</span><span class="sxs-lookup"><span data-stu-id="66485-104">Advanced hunting APIs</span></span>

<span data-ttu-id="66485-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="66485-105">**Applies to:**</span></span>
- <span data-ttu-id="66485-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="66485-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="66485-107">일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66485-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="66485-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="66485-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="66485-109">제한 사항</span><span class="sxs-lookup"><span data-stu-id="66485-109">Limitations</span></span>
1. <span data-ttu-id="66485-110">지난 30 일간의 데이터에 대해서만 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66485-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="66485-111">결과에는 최대 10만 행이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66485-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="66485-112">실행 횟수는 테 넌 트 당 초당 최대 10 개의 통화, 시간당 10 분의 실행 시간, 그리고 하루에 4 시간까지 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66485-112">The number of executions is limited per tenant: up to 10 calls per minute, 10 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="66485-113">단일 요청의 최대 실행 시간은 10 분입니다.</span><span class="sxs-lookup"><span data-stu-id="66485-113">The maximal execution time of a single request is 10 minutes.</span></span>
5. <span data-ttu-id="66485-114">429 응답은 요청 수 또는 CPU로 인해 할당량 제한에 도달 하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="66485-114">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="66485-115">또한 429 응답 본문은 할당량이 갱신 될 때 까지의 시간도 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="66485-115">The 429 response body will also indicate the time until the quota is renewed.</span></span> 


## <a name="permissions"></a><span data-ttu-id="66485-116">사용 권한</span><span class="sxs-lookup"><span data-stu-id="66485-116">Permissions</span></span>
<span data-ttu-id="66485-117">이 API를 호출 하려면 다음 사용 권한 중 하나가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="66485-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="66485-118">사용 권한을 선택 하는 방법을 비롯 하 여 자세한 내용은 [Microsoft Threat Protection Api 액세스](api-access.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66485-118">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="66485-119">사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="66485-119">Permission type</span></span> |   <span data-ttu-id="66485-120">사용 권한</span><span class="sxs-lookup"><span data-stu-id="66485-120">Permission</span></span>  |   <span data-ttu-id="66485-121">사용 권한 표시 이름</span><span class="sxs-lookup"><span data-stu-id="66485-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="66485-122">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="66485-122">Application</span></span> |   <span data-ttu-id="66485-123">AdvancedHunting 모든</span><span class="sxs-lookup"><span data-stu-id="66485-123">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="66485-124">' 고급 쿼리 실행 '</span><span class="sxs-lookup"><span data-stu-id="66485-124">'Run advanced queries'</span></span>
<span data-ttu-id="66485-125">위임 됨 (회사 또는 학교 계정)</span><span class="sxs-lookup"><span data-stu-id="66485-125">Delegated (work or school account)</span></span> | <span data-ttu-id="66485-126">AdvancedHunting 읽기</span><span class="sxs-lookup"><span data-stu-id="66485-126">AdvancedHunting.Read</span></span> | <span data-ttu-id="66485-127">' 고급 쿼리 실행 '</span><span class="sxs-lookup"><span data-stu-id="66485-127">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="66485-128">사용자 자격 증명을 사용 하 여 토큰을 가져올 때:</span><span class="sxs-lookup"><span data-stu-id="66485-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="66485-129">사용자에 게 ' View Data ' AD 역할이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66485-129">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="66485-130">장치 그룹 설정에 따라 사용자에 게 장치에 대 한 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66485-130">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="66485-131">HTTP 요청</span><span class="sxs-lookup"><span data-stu-id="66485-131">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="66485-132">요청 헤더</span><span class="sxs-lookup"><span data-stu-id="66485-132">Request headers</span></span>

<span data-ttu-id="66485-133">Header</span><span class="sxs-lookup"><span data-stu-id="66485-133">Header</span></span> | <span data-ttu-id="66485-134">값</span><span class="sxs-lookup"><span data-stu-id="66485-134">Value</span></span> 
:---|:---
<span data-ttu-id="66485-135">권한 부여</span><span class="sxs-lookup"><span data-stu-id="66485-135">Authorization</span></span> | <span data-ttu-id="66485-136">전달자 {토큰}.</span><span class="sxs-lookup"><span data-stu-id="66485-136">Bearer {token}.</span></span> <span data-ttu-id="66485-137">**필수**입니다.</span><span class="sxs-lookup"><span data-stu-id="66485-137">**Required**.</span></span>
<span data-ttu-id="66485-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="66485-138">Content-Type</span></span>    | <span data-ttu-id="66485-139">application/json</span><span class="sxs-lookup"><span data-stu-id="66485-139">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="66485-140">요청 본문</span><span class="sxs-lookup"><span data-stu-id="66485-140">Request body</span></span>
<span data-ttu-id="66485-141">요청 본문에서 다음 매개 변수를 사용 하 여 JSON 개체를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="66485-141">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="66485-142">매개 변수</span><span class="sxs-lookup"><span data-stu-id="66485-142">Parameter</span></span> | <span data-ttu-id="66485-143">유형</span><span class="sxs-lookup"><span data-stu-id="66485-143">Type</span></span>    | <span data-ttu-id="66485-144">설명</span><span class="sxs-lookup"><span data-stu-id="66485-144">Description</span></span>
:---|:---|:---
<span data-ttu-id="66485-145">Query</span><span class="sxs-lookup"><span data-stu-id="66485-145">Query</span></span> | <span data-ttu-id="66485-146">텍스트</span><span class="sxs-lookup"><span data-stu-id="66485-146">Text</span></span> |  <span data-ttu-id="66485-147">실행할 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="66485-147">The query to run.</span></span> <span data-ttu-id="66485-148">**필수**입니다.</span><span class="sxs-lookup"><span data-stu-id="66485-148">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="66485-149">응답</span><span class="sxs-lookup"><span data-stu-id="66485-149">Response</span></span>
<span data-ttu-id="66485-150">성공 하면이 메서드는 응답 본문에 200 OK 및 _Queryresponse_ 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="66485-150">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="66485-151">Response 개체는 3 개의 부분으로 나뉩니다 (속성).</span><span class="sxs-lookup"><span data-stu-id="66485-151">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="66485-152">```Stats``` -성능 통계를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="66485-152">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="66485-153">```Schema``` -응답의 스키마 이며 각 열에 대 한 이름 형식 쌍의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="66485-153">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="66485-154">```Results``` -고급 구하기 이벤트 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="66485-154">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="66485-155">예제</span><span class="sxs-lookup"><span data-stu-id="66485-155">Example</span></span>

<span data-ttu-id="66485-156">요청이</span><span class="sxs-lookup"><span data-stu-id="66485-156">Request</span></span>

<span data-ttu-id="66485-157">다음은 요청의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="66485-157">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="66485-158">응답</span><span class="sxs-lookup"><span data-stu-id="66485-158">Response</span></span>

<span data-ttu-id="66485-159">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="66485-159">Here is an example of the response.</span></span>


```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}

```

## <a name="related-topic"></a><span data-ttu-id="66485-160">관련 항목</span><span class="sxs-lookup"><span data-stu-id="66485-160">Related topic</span></span>
- [<span data-ttu-id="66485-161">Microsoft Threat Protection Api 액세스</span><span class="sxs-lookup"><span data-stu-id="66485-161">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)