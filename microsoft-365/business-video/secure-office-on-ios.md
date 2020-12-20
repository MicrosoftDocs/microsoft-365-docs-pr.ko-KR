---
title: iOS의 Office 앱 보안
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 Business Premium을 사용하여 iOS에서 Office 앱을 보호하는 방법을 배워야 합니다.
ms.openlocfilehash: 1703faa7cd7731f0779bacc3d2fa3ad3e4556910
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702652"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="b6712-103">iOS의 Office 앱 보안</span><span class="sxs-lookup"><span data-stu-id="b6712-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="b6712-104">모바일 사용자가 로그인하기 위해 PIN 또는 지문을 입력해야 하는 사용자 액세스 정책을 설정하고 장치에 저장된 작업 파일을 암호화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6712-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="b6712-105">사용해 보세요!</span><span class="sxs-lookup"><span data-stu-id="b6712-105">Try it!</span></span>

1. <span data-ttu-id="b6712-106">Microsoft 365 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b6712-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="b6712-107">**정책에서** 정책 **추가를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6712-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="b6712-108">정책 추가 **창에서** 정책 이름 아래에 이름을 입력하고 정책 유형에서 원하는 정책 유형을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6712-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="b6712-109">사용자가 모바일 **장치에서 Office 파일에 액세스하는** 방법 관리 기능을 켜고 다음 세 가지 설정이 켜져 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b6712-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="b6712-110">**Office 앱 액세스에 PIN 또는 지문 필요**</span><span class="sxs-lookup"><span data-stu-id="b6712-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="b6712-111">**장치를 분실하거나 도난당한 경우 작업 파일 보호**</span><span class="sxs-lookup"><span data-stu-id="b6712-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="b6712-112">**작업 파일 암호화**</span><span class="sxs-lookup"><span data-stu-id="b6712-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="b6712-113">이러한 **앱의 파일에서** 보호됩니다. 모바일 장치에서 보호할 Office 앱을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b6712-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="b6712-114">이러한 설정을 사용할 사용자 **아래에는** 모든 사용자가 기본적으로 선택되지만, 변경을 선택하여 만든 보안 그룹을 선택할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="b6712-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="b6712-115">정책 만들기를 완료하고 추가를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6712-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="b6712-116">정책 추가 **페이지에서** 닫기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6712-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="b6712-117">관리 센터 홈 페이지에서 정책을 선택하고 정책 페이지에서  정책을 검토하여 새 정책이 추가된 것을 **확인하십시오.**</span><span class="sxs-lookup"><span data-stu-id="b6712-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>