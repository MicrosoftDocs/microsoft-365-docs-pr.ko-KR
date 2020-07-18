---
title: 콘텐츠를 보존하거나 삭제하는 보존 레이블을 만들고 앱에 적용하기
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
description: 보존 레이블을 만들어서 게시한 후에 필요한 항목은 보존하고 필요하지 않은 항목은 삭제하도록 앱에 적용하기 위한 지침
ms.openlocfilehash: ba83243caf2873b2983837b8ab8d4861e1187e2f
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127597"
---
# <a name="create-retention-labels-and-apply-them-in-apps"></a>보존 레이블을 만들고 앱에 적용하기

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*

다음 정보를 사용하여 [보존 레이블](retention.md)을 만들어서 게시한 다음 문서 및 전자 메일에 적용하는 데 도움을 받습니다.

보존 레이블은 항목 수준(문서 또는 전자 메일)에서 필요한 항목은 보존하고 필요하지 않은 항목은 삭제할 수 있게 해줍니다. 또한 Microsoft 365 데이터에 대한 [레코드 관리](records-management.md) 솔루션의 일부로 항목을 레코드로 선언하는 데에도 사용됩니다.

콘텐츠를 분류할 수 있도록 조직의 사용자에게 보존 레이블을 제공하는 작업은 2단계 프로세스입니다. 

1. 보존 레이블 만들기

2. 보존 레이블 정책을 사용하여 보존 레이블 게시하기
  
![레이블의 역할 및 작업 다이어그램](../media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)

두 가지 관리 단계를 수행하려면 다음 지침을 사용합니다.

## <a name="before-you-begin"></a>시작하기 전에

조직의 전역 관리자는 보존 레이블과 해당 정책을 만들고 편집할 수 있는 모든 권한을 가지고 있습니다. 전역 관리자로 로그인하지 않은 경우 [보존 정책 및 보존 레이블을 만들고 관리하는 데 필요한 권한](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels)을 참조하세요.

## <a name="how-to-create-and-publish-retention-labels"></a>보존 레이블을 만들고 게시하는 방법

먼저 보존 레이블을 만듭니다. 그런 다음 레이블을 앱에 적용할 수 있게 되는 레이블 정책을 만듭니다.

보존 레이블을 만들고 구성하는 위치는 레코드 관리를 사용 중인지 여부에 따라 달라집니다. 두 시나리오 모두에 대한 지침이 제공 됩니다.

### <a name="step-1-create-retention-labels"></a>1단계: 보존 레이블 만들기

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 다음의 위치 중 한 곳으로 이동합니다.
    
    - 레코드 관리를 사용하는 경우:
        - **솔루션** > **레코드 관리** > **파일 계획** 탭 > **+ 레이블 만들기** > **보존 레이블**
        
    - 레코드 관리를 사용하지 않는 경우:
       - **솔루션** > **정보 관리** > **레이블** tab > + **레이블 만들기**
    
    바로 옵션이 표시되지 않나요? 먼저 **모두 표시**를 선택합니다. 

2. 마법사의 지시를 따릅니다. 레코드 관리를 사용하는 경우:
    
    - 파일 계획 설명자에 대한 자세한 내용은 [파일 계획을 사용하여 보존 레이블 관리의 개요](file-plan-manager.md)를 참조하세요
    
    - 보존 레이블을 사용하여 콘텐츠를 레코드로 선언하려면 **레이블을 사용하여 콘텐츠를 “기록”으로 분류** 확인란을 체크합니다.

3. 이 단계를 반복하여 레이블을 더 만듭니다.

기존 레이블을 편집하려면 레이블을 선택하고 **레이블 편집**을 선택하여 레이블 설명과 [적격 설정](#updating-retention-labels-and-their-policies)을 변경하는 데 사용하는 동일한 마법사를 2단계에서 시작합니다. 또는 사용 가능한 **편집** 옵션 중 하나를 선택하여 해당 페이지로 바로 이동하고 업데이트를 수행합니다.

### <a name="step-2-publish-retention-labels"></a>2단계: 보존 레이블 만들기 및 게시

관리자 및 사용자가 적용할 수 있도록 보존 레이블을 게시합니다.

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com/)에서 다음의 위치 중 한 곳으로 이동합니다.
    
    - 레코드 관리를 사용하는 경우:
        - **솔루션** > **레코드 관리** > > **레이블 정책** 탭 > **레이블 게시**
    
    - 레코드 관리를 사용하지 않는 경우:
        - **솔루션** > **정보 관리** > **레이블 정책** 탭 > **레이블 게시**
    
    바로 옵션이 표시되지 않나요? 먼저 **모두 표시**를 선택합니다. 

2. 마법사의 지시를 따릅니다.
    
    보존 레이블이 지원하는 위치에 대한 자세한 내용은 [보존 레이블과 위치](retention.md#retention-label-policies-and-locations) 섹션을 참조하세요. 

기존 보존 레이블 정책을 편집하려면 레이블을 선택하고 **정책 편집**을 선택하여 정책 설명과 [적격 설정](#updating-retention-labels-and-their-policies)을 변경하는 데 사용하는 동일한 마법사를 2단계에서 시작합니다. 또는 사용 가능한 **편집** 옵션 중 하나를 선택하여 해당 페이지로 바로 이동하고 업데이트를 수행합니다.


## <a name="when-retention-labels-become-available-to-apply"></a>보존 레이블을 적용할 수 있게 되면

SharePoint 또는 OneDrive에 보존 레이블을 게시하면 일반적으로 1일 이내에 최종 사용자가 선택하도록 레이블이 표시됩니다. 그러나 최대 7일까지 걸릴 수 있습니다. 

보존 레이블을 Exchange에 게시하는 경우 해당 보존 레이블이 최종 사용자에게 표시되기까지 최대 7일이 걸릴 수 있으며 사서함에 10MB 이상의 데이터를 저장할 수 있어야 합니다.

예제:
  
![수동 레이블이 적용되는 경우를 나타내는 다이어그램](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  

### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a>Exchange에 게시된 보존 레이블의 상태를 확인하는 방법

Exchange Online에서 보존 레이블은 7일마다 실행되는 프로세스를 통해 최종 사용자에게 제공됩니다. PowerShell을 사용하여 이 프로세스가 마지막으로 실행된 시간을 확인할 수 있고 따라서 이 프로세스가 다시 실행될 시간을 확인할 수 있습니다.
  
1. [Exchange Online PowerShell에 연결합니다](https://go.microsoft.com/fwlink/?linkid=799773).
    
2. 다음 명령을 실행합니다.
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}   ```

In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox. If it has not happened since the time you created the policy, the labels are not going to appear. To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.
    
If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).
    

## How to apply published retention labels

Use the following sections to learn how published retention labels can be applied in apps:

- [Manually apply retention labels](#manually-apply-retention-labels)

- [Applying a default retention label to all content in a SharePoint library, folder, or document set](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)

- [Automatically applying a retention label to email by using rules](#automatically-applying-a-retention-label-to-email-by-using-rules)

### Manually apply retention labels 

End users, as well as administrators, can manually apply retention labels from the following locations:  

- Outlook and Outlook on the web
    
- OneDrive
    
- SharePoint
    
- Microsoft 365 groups (both the group site and group mailbox in Outlook on the web)
    
Use the following sections to understand how to apply retention labels. 

#### Applying retention labels in Outlook

To label an item in the Outlook desktop client, select the item. On the **Home** tab on the ribbon, click **Assign Policy**, and then choose the retention label. 
  
![Assign Policy button](../media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
You can also right-click an item, click **Assign Policy** in the context menu, and then choose the retention label. 

After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email has a retention label applied that has an associated retention period, you can see at a glance when the email expires.
  
You can also apply retention labels to folders, in which case:
  
- All items in the folder automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them. Explicitly labeled items keep their existing retention label. For more information, see [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) section on this page. 
    
- If you change or remove the default retention label for a folder, the retention label's also changed or removed for all items in the folder, **except** items with explicitly assigned retention labels. 
    
- If you move an item with a default retention label from one folder to another folder with a different default retention label, the item gets the new default retention label.
    
- If you move an item with a default retention label from one folder to another folder with no default retention label, the old default retention label is removed.

#### Applying retention labels in Outlook on the web

To label an item in Outlook on the web, right-click the item \> **Assign policy** \> choose the retention label. 
  
![Assign policy menu in Outlook on the web](../media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.
  
![Label assigned to email in Outlook on the web](../media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
As with Outlook on the web, you can also apply retention labels to folders. 

#### Applying retention labels in OneDrive and SharePoint

To label a document (including OneNote files) in OneDrive or SharePoint, select the item \> in the upper-right corner, choose **Open the details pane**![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Apply retention label** \> choose the retention label. 
  
You can also apply a retention label to a folder or document set, and you can set a [default retention label for a document library](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
  
![Apply label list for an item in SharePoint](../media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
After a retention label is applied to an item, you can view it in the details pane when that item's selected.
  
![Applied label shown in Details pane](../media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
For SharePoint, but not OneDrive, you can create a view of the library that contains the **Labels** column or **Item is a Record** column. This view lets you see at a glance the retention labels assigned to all items and which items are records. Note, however, that you can't filter the view by the **Item is a Record** column. For instructions how to add columns, see [Show or hide columns in a list or library](https://support.microsoft.com/en-us/office/show-or-hide-columns-in-a-list-or-library-b820db0d-9e3e-4ff9-8b8b-0b2dbefa87e2).


#### Applying retention labels in Microsoft 365 groups

When you publish retention labels to Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), the retention labels appear in both the group site and group mailbox in Outlook on the web. The experience of applying a retention label to content is identical to that for email and documents.

To retain content for a Microsoft 365 group, use the **Office 365 groups** location. Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire Exchange location won't include content in Microsoft 365 group mailboxes.

In addition, it's not possible to use the Exchange location to include or exclude a specific group mailbox. Although the Exchange location initially allows a group mailbox to be selected, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.
  
First, create and configure the sensitivity labels that you want to make available for apps and other services. For example, the labels you want users to see and apply from Office apps. 

Then, create one or more label policies that contain the labels and policy settings that you configure. It's the label policy that publishes the labels and settings for your chosen users and locations.

### Applying a default retention label to all content in a SharePoint library, folder, or document set

This method requires retention labels to be published to a retention label policy.

In addition to enabling people to apply a retention label to individual documents, you can also apply a default retention label to a SharePoint library, folder, or document set, so that all documents in that location get the default retention label.
  
For a document library, this is done on the **Library settings** page for a document library. When you choose the default retention label, you can also choose to apply it to existing items in the library. 
  
For example, if you have a tag for marketing materials, and you know a specific document library contains only that type of content, you can make the Marketing Materials tag the default for all documents in that library.
  
![Apply label option on library Settings page](../media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
If you apply a default retention label to existing items in the library, folder, or document set:
  
- All items in the library, folder, or document set automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them (such as records). Explicitly labeled items keep their existing label. For more information, see the below section on [The principles of retention, or what takes precedence](retention.md#the-principles-of-retention-or-what-takes-precedence).
    
- If you change or remove the default retention label for a library, folder, or document set, the retention label is also changed or removed for all items in the library, folder, or document set, **except** items with explicit retention labels (such as records).
    
- If you move an item with a default retention label from one site collection, library, folder, or document set to another site collection, library, folder, or document set that has a different label, the item keeps its existing default retention label, even if the new location has a different default retention label. If the item does not have a label before moving, it will take on the default retention label of the new location.

**Records:** If you apply a default record label to a library, folder, or document set, then a record label is applied to all the individual items within those locations. When you move a new item into a location with a record label, that item is labeled a record. However, if you change the default retention label to a label that doesn't declare content as a record, that action does not remove the record label from the individual items; those items retain their record label. Only a site collection admin can explicitly remove or change the retention label of record items.

For more information about retention labels that declare content as a record, see [Learn about records](records.md).

### Automatically applying a retention label to email by using rules

In Outlook, you can create rules to apply a retention label.
  
For example, you can create a rule that applies a specific retention label to all messages sent to or from a specific distribution group.
  
To create a rule, right-click an item \> **Rules** \> **Create Rule** \> **Advanced Options** \> **Rules Wizard** \> **apply retention policy**.
  
![Rules wizard with option to apply retention policies](../media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)
  

## Updating retention labels and their policies

When you edit a retention label or retention label policy, and the retention label or policy is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.

Some settings can't be changed after the label or policy is created and saved, which include:
- The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.
- The option to classify as a record.

## Next steps

Event-based retention is another supported scenario for retention labels. For more information, see the following articles:

- [Start retention when an event occurs](event-driven-retention.md)
- [Automate event-based retention](automate-event-driven-retention.md)
- [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md)