---
title: 청구 프로필을 사용하여 구독 결제
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- MET150
description: 청구 프로필을 사용하여 구독 비용을 결제하는 데 사용할 수 있는 결제 방법을 알아보세요.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- commerce
ms.openlocfilehash: 15feb1b806b46d147d427256ce2416ea75b48bbe
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50143194"
---
# <a name="how-to-pay-for-your-subscription-with-a-billing-profile"></a><span data-ttu-id="7d58a-103">청구 프로필을 사용하여 구독 비용을 결제하는 방법</span><span class="sxs-lookup"><span data-stu-id="7d58a-103">How to pay for your subscription with a billing profile</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="7d58a-104">관리 센터가 변경되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-104">The admin center is changing.</span></span> <span data-ttu-id="7d58a-105">사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d58a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="7d58a-106">구독을 구입하면 청구 프로필로 구독 비용을 지불합니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-106">When you buy a subscription, you pay for it with a billing profile.</span></span> <span data-ttu-id="7d58a-107">청구 프로필은 특정 결제 방법에 연결되어 있으며 신용 카드나 직불 카드 또는 송장일 수 있지만 은행 계좌는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-107">The billing profile is linked to a specific payment method and can be a credit or debit card, or an invoice, but not a bank account.</span></span>

<span data-ttu-id="7d58a-108">계정에 청구 프로필이 있는지 확실하지 않은 경우 청구 프로필 [이해를 참조하세요.](manage-billing-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="7d58a-108">If you’re not sure if your account has a billing profile, see [Understand billing profiles](manage-billing-profiles.md).</span></span> <span data-ttu-id="7d58a-109">청구 프로필이 없는 경우 구독 비용을 지불하는 [방법을 참조하세요.](pay-for-your-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="7d58a-109">If you don’t have a billing profile, see [How to pay for your subscription](pay-for-your-subscription.md).</span></span>

## <a name="paying-with-recurring-billing-turned-on-or-off"></a><span data-ttu-id="7d58a-110">재발급 대금 결제 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="7d58a-110">Paying with recurring billing turned on or off</span></span>

<span data-ttu-id="7d58a-111">기본적으로는 재발급 청구를 사용하는 모든 유료 구독에 대해 재발급 청구가 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-111">By default, recurring billing is automatically turned on for all paid subscriptions that use recurring billing.</span></span> <span data-ttu-id="7d58a-112">모든 청구 기간에는 해당 청구 프로필을 사용하는 구독에 대해 요금을 청구 프로필과 연결된 결제 방법에 자동으로 청구합니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-112">Every billing period, we automatically charge the payment method associated with the billing profile to pay for any subscriptions that use that billing profile.</span></span> <span data-ttu-id="7d58a-113">결제 방법이 거부된 경우 송장의  지금 결제 단추를 사용하여 구독에 대해 일회성 결제를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-113">If your payment method is declined, you can use the **Pay now** button on your invoice to make a one-time payment for your subscription.</span></span>

<span data-ttu-id="7d58a-114">청구 프로필에 대해 재발급 청구가 해제된 경우  청구 프로필에 연결된 결제 방법에 관계없이 송장의 지금 결제 단추를 사용하여 청구 기간마다 결제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-114">If recurring billing is turned off for a billing profile, you can use the **Pay now** button on your invoice to pay for it every billing period, regardless of what payment method is linked with the billing profile.</span></span> <span data-ttu-id="7d58a-115">수표 또는 EFT(전자 자금 이체)로 결제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-115">You can also pay by check or electronic funds transfer (EFT).</span></span> <span data-ttu-id="7d58a-116">이 작업을 하는 방법에 대한 지침은 송장의 PDF 복사본에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-116">Instructions for how to do that are included on the PDF copy of your invoice.</span></span>

## <a name="paying-by-invoice"></a><span data-ttu-id="7d58a-117">송장으로 결제</span><span class="sxs-lookup"><span data-stu-id="7d58a-117">Paying by invoice</span></span>

<span data-ttu-id="7d58a-118">송장으로 결제를 설정한 청구 프로필이 있는 경우 수표 또는 EFT로 구독 비용을 지불할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-118">If you have a billing profile that is set up to be paid by invoice, you can pay for your subscription with a check or EFT.</span></span> <span data-ttu-id="7d58a-119">신용 카드를 사용하여 송장의 지금 결제 단추를 사용하여 온라인 결제를 할 수도 있습니다. </span><span class="sxs-lookup"><span data-stu-id="7d58a-119">You can also use a credit card to make an online payment by using the **Pay now** button on your invoice.</span></span>

<span data-ttu-id="7d58a-120">송장으로 결제할 자격을 제공하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-120">To be eligible to pay by invoice, you must:</span></span>

- <span data-ttu-id="7d58a-121">확립된 고객 1명</span><span class="sxs-lookup"><span data-stu-id="7d58a-121">Be an established customer</span></span>
- <span data-ttu-id="7d58a-122">특정 금액을 초과하는 구독 비용이 있는 경우(이 금액은 서비스 위치에 따라 다를 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="7d58a-122">Have a subscription cost that exceeds a certain amount (this amount varies by service location)</span></span>
- <span data-ttu-id="7d58a-123">신용 검사 통과</span><span class="sxs-lookup"><span data-stu-id="7d58a-123">Pass a credit check</span></span>

<span data-ttu-id="7d58a-124">신용 확인이 필요한 경우 구독을 구입할 때 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-124">If a credit check is required, you’re notified when you buy your subscription.</span></span> <span data-ttu-id="7d58a-125">연락에 동의한 경우 신용 승인 신청에 대한 자세한 정보가 포함된 전자 메일을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-125">If you agree to be contacted, you get an email that includes more information about applying for credit approval.</span></span> <span data-ttu-id="7d58a-126">신용 검사는 보통 영업일 기준 2일 이내에 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-126">Credit checks are usually completed within two business days.</span></span>

<span data-ttu-id="7d58a-127">청구 프로필이 송장으로 지원되면 청구서를 볼 준비가 된 경우 전자 메일을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-127">If your billing profile is backed by an invoice, you get an email when your billing statement is ready to view.</span></span> <span data-ttu-id="7d58a-128">이 전자 메일은 청구서 사본을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-128">This email doesn’t contain a copy of your billing statement.</span></span> <span data-ttu-id="7d58a-129">그러나 [전자 메일로 청구서 사본을 받도록](view-your-bill-or-invoice.md#receive-a-copy-of-your-billing-statement-in-email) 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-129">However, you can choose to [receive a copy of your billing statement in email](view-your-bill-or-invoice.md#receive-a-copy-of-your-billing-statement-in-email).</span></span> <span data-ttu-id="7d58a-130">청구서에는 결제 옵션에 대한 세부 정보와 전송 위치가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-130">Your billing statement includes details about your options for making a payment, and where to send it.</span></span> <span data-ttu-id="7d58a-131">청구 프로필에 PO(구매 주문) 번호를 입력하면 해당 번호가 청구서에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-131">If you enter a purchase order (PO) number in your billing profile, the number appears on your billing statement.</span></span> <span data-ttu-id="7d58a-132">청구서를 확인하는 방법에 대한 자세한 내용은 [청구서 또는 송장 보기](view-your-bill-or-invoice.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d58a-132">For information about accessing billing statements, see [View your bill or invoice](view-your-bill-or-invoice.md).</span></span>

## <a name="where-do-i-send-my-check-or-eft-payment"></a><span data-ttu-id="7d58a-133">수표 또는 EFT 결제를 어디로 보내야 하나요?</span><span class="sxs-lookup"><span data-stu-id="7d58a-133">Where do I send my check or EFT payment?</span></span>

<span data-ttu-id="7d58a-134">[결제 지침을 송장에](view-your-bill-or-invoice.md) 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="7d58a-134">[Check your invoice](view-your-bill-or-invoice.md) for payment instructions.</span></span> <span data-ttu-id="7d58a-135">아래 드롭다운을 사용하여 국가에 대한 결제 지침을 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-135">You can also use the drop-down below to find payment instructions for your country.</span></span> <span data-ttu-id="7d58a-136">지불 금액이 확실하지 않은 경우 온라인으로 청구서 및 청구 내역을  결제 페이지의 청구서 <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">탭에서 확인할 &</a> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-136">If you're not sure how much you owe, you can check your bill and billing history online on the **Invoices** tab of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

> [!NOTE]
> <span data-ttu-id="7d58a-137">수표 결제는 일부 국가에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-137">Paying by check is only available in a few countries.</span></span>

 <span data-ttu-id="7d58a-138">**아래 드롭다운 메뉴에서 “청구지” 국가 또는 지역을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7d58a-138">**Choose your "bill-to" country or region from the drop-down menu below.**</span></span>

> [!div class="op_single_selector"]
> - **국가 또는 지역 선택**
> - [아프가니스탄](../pay/afghanistan.md)
> - [알바니아](../pay/albania.md)
> - [알제리](../pay/algeria.md)
> - [앙골라](../pay/angola.md)
> - [아르헨티나](../pay/argentina.md)
> - [아르메니아](../pay/armenia.md)
> - [오스트레일리아](../pay/australia.md)
> - [오스트리아](../pay/austria.md)
> - [아제르바이잔](../pay/azerbaijan.md)
> - [바하마](../pay/bahamas.md)
> - [바레인](../pay/bahrain.md)
> - [방글라데시](../pay/bangladesh.md)
> - [바베이도스](../pay/barbados.md)
> - [벨로루시](../pay/belarus.md)
> - [벨기에](../pay/belgium.md)
> - [벨리즈](../pay/belize.md)
> - [버뮤다](../pay/bermuda.md)
> - [볼리비아](../pay/bolivia.md)
> - [보스니아 헤르체고비나](../pay/bosnia-and-herzegovina.md)
> - [보츠와나](../pay/botswana.md)
> - [브라질](../pay/brazil.md)
> - [브루나이](../pay/brunei.md)
> - [불가리아](../pay/bulgaria.md)
> - [카메룬](../pay/cameroon.md)
> - [캐나다](../pay/canada.md)
> - [카보베르데](../pay/cape-verde.md)
> - [케이맨 제도](../pay/cayman-islands.md)
> - [칠레](../pay/chile.md)
> - [중국](../pay/china-prc.md)
> - [콜롬비아](../pay/colombia.md)
> - [코스타리카](../pay/costa-rica.md)
> - [코트디부아르](../pay/cote-divoire.md)
> - [크로아티아](../pay/croatia.md)
> - [퀴라소](../pay/curacao.md)
> - [키프로스](../pay/cyprus.md)
> - [체코](../pay/czech-republic.md)
> - [콩고 공화국](../pay/democratic-republic-of-congo.md)
> - [덴마크](../pay/denmark.md)
> - [도미니카 공화국](../pay/dominican-republic.md)
> - [에콰도르](../pay/ecuador.md)
> - [이집트](../pay/egypt.md)
> - [엘살바도르](../pay/el-salvador.md)
> - [에스토니아](../pay/estonia.md)
> - [에티오피아](../pay/ethiopia.md)
> - [페로 제도](../pay/faroe-islands.md)
> - [피지](../pay/fiji.md)
> - [핀란드](../pay/finland.md)
> - [프랑스](../pay/france.md)
> - [프랑스령 기아나](../pay/french-guiana.md)
> - [조지아](../pay/georgia.md)
> - [독일](../pay/germany.md)
> - [가나](../pay/ghana.md)
> - [그리스](../pay/greece.md)
> - [그레나다](../pay/grenada.md)
> - [과들루프](../pay/guadeloupe.md)
> - [괌](../pay/guam.md)
> - [과테말라](../pay/guatemala.md)
> - [가이아나](../pay/guyana.md)
> - [아이티](../pay/haiti.md)
> - [온두라스](../pay/honduras.md)
> - [홍콩](../pay/hong-kong.md)
> - [헝가리](../pay/hungary.md)
> - [아이슬란드](../pay/iceland.md)
> - [인도](../pay/india.md)
> - [인도네시아](../pay/indonesia.md)
> - [이라크](../pay/iraq.md)
> - [아일랜드](../pay/ireland.md)
> - [이스라엘](../pay/israel.md)
> - [이탈리아](../pay/italy.md)
> - [자메이카](../pay/jamaica.md)
> - [일본](../pay/japan.md)
> - [요르단](../pay/jordan.md)
> - [카자흐스탄](../pay/kazakhstan.md)
> - [케냐](../pay/kenya.md)
> - [대한민국](../pay/korea.md)
> - [쿠웨이트](../pay/kuwait.md)
> - [키르기스스탄](../pay/kyrgyzstan.md)
> - [라트비아](../pay/latvia.md)
> - [레바논](../pay/lebanon.md)
> - [리비아](../pay/libya.md)
> - [리히텐슈타인](../pay/liechtenstein.md)
> - [리투아니아](../pay/lithuania.md)
> - [룩셈부르크](../pay/luxembourg.md)
> - [마카오](../pay/macao.md)
> - [마케도니아](../pay/macedonia.md)
> - [말레이시아](../pay/malaysia.md)
> - [몰타](../pay/malta.md)
> - [모리셔스](../pay/mauritius.md)
> - [멕시코](../pay/mexico.md)
> - [몰도바](../pay/moldova.md)
> - [모나코](../pay/monaco.md)
> - [몽골](../pay/mongolia.md)
> - [몬테네그로](../pay/montenegro.md)
> - [모로코](../pay/morocco.md)
> - [나미비아](../pay/namibia.md)
> - [네팔](../pay/nepal.md)
> - [네덜란드](../pay/netherlands.md)
> - [뉴질랜드](../pay/new-zealand.md)
> - [니카라과](../pay/nicaragua.md)
> - [나이지리아](../pay/nigeria.md)
> - [노르웨이](../pay/norway.md)
> - [오만](../pay/oman.md)
> - [파키스탄](../pay/pakistan.md)
> - [팔레스타인](../pay/palestinian-authority.md)
> - [파나마](../pay/panama.md)
> - [파라과이](../pay/paraguay.md)
> - [페루](../pay/peru.md)
> - [필리핀](../pay/philippines.md)
> - [폴란드](../pay/poland.md)
> - [포르투갈](../pay/portugal.md)
> - [푸에르토리코](../pay/puerto-rico.md)
> - [카타르](../pay/qatar.md)
> - [루마니아](../pay/romania.md)
> - [러시아](../pay/russia.md)
> - [르완다](../pay/rwanda.md)
> - [세인트키츠 네비스](../pay/saint-kitts-and-nevis.md)
> - [세인트루시아](../pay/saint-lucia.md)
> - [세인트빈센트그레나딘](../pay/saint-vincent-and-the-grenadines.md)
> - [사우디아라비아](../pay/saudi-arabia.md)
> - [세네갈](../pay/senegal.md)
> - [세르비아](../pay/serbia.md)
> - [싱가포르](../pay/singapore.md)
> - [슬로바키아](../pay/slovakia.md)
> - [슬로베니아](../pay/slovenia.md)
> - [남아프리카 공화국](../pay/south-africa.md)
> - [스페인](../pay/spain.md)
> - [스리랑카](../pay/sri-lanka.md)
> - [수리남](../pay/suriname.md)
> - [스웨덴](../pay/sweden.md)
> - [스위스](../pay/switzerland.md)
> - [대만](../pay/taiwan.md)
> - [타지키스탄](../pay/tajikistan.md)
> - [탄자니아](../pay/tanzania.md)
> - [태국](../pay/thailand.md)
> - [트리니다드 토바고](../pay/trinidad-and-tobago.md)
> - [투르크메니스탄](../pay/turkmenistan.md)
> - [튀니지](../pay/tunisia.md)
> - [터키](../pay/turkey.md)
> - [우간다](../pay/uganda.md)
> - [우크라이나](../pay/ukraine.md)
> - [아랍에미리트](../pay/united-arab-emirates.md)
> - [영국](../pay/united-kingdom.md)
> - [미국](../pay/united-states.md)
> - [우루과이](../pay/uruguay.md)
> - [우즈베키스탄](../pay/uzbekistan.md)
> - [베네수엘라](../pay/venezuela.md)
> - [베트남](../pay/vietnam.md)
> - [미국령 버진 아일랜드](../pay/virgin-islands.md)
> - [예멘](../pay/yemen.md)
> - [잠비아](../pay/zambia.md)
> - [짐바브웨](../pay/zimbabwe.md)

## <a name="can-i-pay-my-invoice-online"></a><span data-ttu-id="7d58a-291">온라인으로 송장을 결제할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7d58a-291">Can I pay my invoice online?</span></span>

<span data-ttu-id="7d58a-292">청구 프로필에 대해 재발급 청구가 해제된 경우 신용 카드를 사용하여 온라인으로 송장을 결제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-292">If recurring billing is turned off for your billing profile, you can use a credit card to pay your invoice online.</span></span> <span data-ttu-id="7d58a-293">결제하려면 Microsoft 365 관리 센터의 송장에 지금 결제 단추를 사용하세요. </span><span class="sxs-lookup"><span data-stu-id="7d58a-293">To make a payment, use the **Pay now** button on your invoice in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7d58a-294">To find your invoice, [see View your bill or invoice.](view-your-bill-or-invoice.md)</span><span class="sxs-lookup"><span data-stu-id="7d58a-294">To find your invoice, see [View your bill or invoice](view-your-bill-or-invoice.md).</span></span>

## <a name="can-i-change-from-my-current-payment-method-to-paying-by-invoice"></a><span data-ttu-id="7d58a-295">현재 결제 방법에서 송장 결제로 변경할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7d58a-295">Can I change from my current payment method to paying by invoice?</span></span>

<span data-ttu-id="7d58a-296">청구 프로필이 신용 카드 또는 직불 카드로 백업된 경우 결제 방법을 다른 신용 카드 또는 직불 카드로만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-296">If your billing profile is backed by credit or debit card, you can only change the payment method to another credit or debit card.</span></span> <span data-ttu-id="7d58a-297">송장 결제로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-297">You can’t change to paying by invoice.</span></span>

## <a name="can-i-change-from-paying-by-invoice-to-using-a-different-payment-method"></a><span data-ttu-id="7d58a-298">송장 결제에서 다른 결제 방법으로 변경할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7d58a-298">Can I change from paying by invoice to using a different payment method?</span></span>

<span data-ttu-id="7d58a-299">청구 프로필이 송장 결제로 백업된 경우 결제 방법을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-299">If your billing profile is backed by invoice payments, you can’t change the payment method.</span></span> <span data-ttu-id="7d58a-300">송장에서  지금 결제 단추를 사용하여 신용 카드 또는 직불 카드로 결제하거나 수표 또는 EFT로 결제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d58a-300">You can use the **Pay now** button on your invoice to pay with a credit or debit card, or by check or EFT.</span></span>

## <a name="related-content"></a><span data-ttu-id="7d58a-301">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="7d58a-301">Related content</span></span>

<span data-ttu-id="7d58a-302">[결제 방법](manage-payment-methods.md) 관리(문서)</span><span class="sxs-lookup"><span data-stu-id="7d58a-302">[Manage payment methods](manage-payment-methods.md) (article)</span></span>\
<span data-ttu-id="7d58a-303">[청구서 또는 송장](view-your-bill-or-invoice.md) 보기(문서)</span><span class="sxs-lookup"><span data-stu-id="7d58a-303">[View your bill or invoice](view-your-bill-or-invoice.md) (article)</span></span>\
<span data-ttu-id="7d58a-304">[청구서 또는 송장](understand-your-invoice.md) 이해(문서)</span><span class="sxs-lookup"><span data-stu-id="7d58a-304">[Understand your bill or invoice](understand-your-invoice.md) (article)</span></span>